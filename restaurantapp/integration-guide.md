# 🔌 Integration Guide

How RestaurantApp talks to restaurant scripts, and how to hook up your own.

{% hint style="warning" %}
Every event/callback name below is written out as a literal string in the
source (e.g. `'pl_restaurantapp-lb:isEmployee'`), **not** generated from
`GetCurrentResourceName()` the way `pl_burgershot`'s events are. If you're
running the `-gks` build, double-check the actual prefix used in that
resource's own `client.lua`/`server.lua` before wiring up an external
integration — it may still read `pl_restaurantapp-lb:...` if that string
wasn't renamed when the gks build was created from the lb one.
{% endhint %}

***

## The adapter contract

RestaurantApp never talks to a restaurant script directly — every call goes
through an **adapter**, a small table of three functions that describes how
to work with that kind of restaurant. Today there's one: `"kiosk"`.

```lua
-- client.lua
Adapters["kiosk"] = {
    getMenu = function(restaurant, cb)
        lib.callback(restaurant.resource .. ':getKioskData', false, cb)
    end,
    placeOrder = function(restaurant, items, cb)
        lib.callback(restaurant.resource .. ':placeKioskOrder', false, function(orderId, err)
            cb(orderId, err)
        end, items, 'bank')
    end,
    notifyEvent = function(restaurant)
        return restaurant.resource .. ':client:notify'
    end,
}
```

A restaurant that registers with `adapter = "kiosk"` in `Config.Restaurants`
just needs to expose these three things, using its **own** resource name as
the prefix:

| The app expects... | As... | Example (BurgerShot) |
|---|---|---|
| A menu-fetching callback | `lib.callback.register('<resource>:getKioskData', ...)` returning a categorized menu table | `pl_burgershot:getKioskData` |
| An order-placing callback | `lib.callback.register('<resource>:placeKioskOrder', ...)` taking `(items, paymentMethod)`, returning `orderId` or `nil, err` | `pl_burgershot:placeKioskOrder` |
| A customer-notify event | `TriggerClientEvent('<resource>:client:notify', ...)` with `(message, ntype)` | `pl_burgershot:client:notify` |

This is exactly the contract `pl_burgershot` implements — see its own
[Kiosk integration contract](../paid-scripts/restaurants/burgershot/exports-and-events.md#kiosk-integration-contract)
for the full payload shapes. Any script that implements the same 3 things
works with the `"kiosk"` adapter without RestaurantApp needing to know
anything else about it.

### Writing a new adapter

If a restaurant script uses a completely different pattern (not ox\_lib
callbacks, or a different payload shape), add a new entry to the `Adapters`
table in `client.lua` with the same 3 keys (`getMenu`, `placeOrder`,
`notifyEvent`), then set `adapter = "your-new-key"` on that restaurant's
`Config.Restaurants` entry. Nothing else in the app needs to change — every
NUI callback that touches a restaurant goes through `Adapters[restaurant.adapter]`.

***

## NUI callback reference

Called from the app's own frontend (`ui/src`) via `RegisterNUICallback` — for
reference if you're customizing the UI or building a compatible frontend.

| Callback | Payload in | Payload out |
|---|---|---|
| `getRestaurants` | — | `[{ id, name, description, icon, color }]` |
| `getMenu` | `{ restaurantId }` | The adapter's `getMenu` result, or `nil` |
| `placeOrder` | `{ restaurantId, items }` | `{ success, orderId }` or `{ success: false, error }` |
| `isEmployee` | — | `boolean` |
| `getMyCoords` | — | `{ x, y, z, street }` |
| `placeDeliveryOrder` | restaurant/order data | `{ success, orderId }` or `{ success: false, error }` |
| `getDeliveries` | — | list of open deliveries for the caller's job |
| `acceptDelivery` | `{ deliveryId }` | `{ success, error? }` |
| `markDelivered` | `{ deliveryId }` | `{ success, error? }` |
| `cancelDelivery` | `{ deliveryId }` | `{ success }` |
| `setGpsWaypoint` | `{ x, y }` | `{ success }` |
| `callCustomer` | `{ deliveryId }` | `{ success }` |

## Server callbacks & events

| Name | Kind | Notes |
|---|---|---|
| `isEmployee` | `lib.callback.register` | Whether the caller has a job matching any registered restaurant |
| `placeDeliveryOrder` | `lib.callback.register` | Creates an in-memory delivery, broadcasts it to that restaurant's on-duty staff |
| `getDeliveries` | `lib.callback.register` | Open deliveries for the caller's job |
| `acceptDelivery` | `lib.callback.register` | Claims a delivery; rejects if already claimed or wrong job |
| `markDelivered` | `lib.callback.register` | Completes the delivery, writes it to `<dbTable>_orders`, clears it after 60s |
| `deliveryUpdate` | `TriggerClientEvent` | Pushed to the customer as their delivery status changes |
| `newDelivery` | `TriggerClientEvent` | Pushed to every on-duty employee of that restaurant when a delivery is placed |
| `callCustomer` | `TriggerServerEvent` | Fired from the NUI when a driver taps "Call" |

***

## Data model notes

- **No database of its own.** Open deliveries live in a plain Lua table on the
  server (`local deliveries = {}`) and are gone on resource restart. Only a
  **completed** delivery gets written anywhere — into the target restaurant's
  own `<dbTable>_orders` table, using that table's existing columns.
- **Society payments.** `Config.EnableSocietyMoney` controls whether a
  delivery's payment goes to the restaurant's society account instead of the
  driver directly — the actual payout logic lives in `server.lua`, not in the
  adapter.
