# 🔌 Exports & Events

BurgerShot doesn't define classic `exports(...)` functions of its own — its
cross-resource surface is a set of **ox\_lib callbacks** and **events**,
namespaced with the resource name (`pl_burgershot:...`). This page documents
every one that's actually meant to be called from outside the script, with
real payload shapes taken straight from the source.

{% hint style="warning" %}
Every event/callback name below is generated with `ResourceEvent('name')`,
which returns `GetCurrentResourceName() .. ':' .. name` — i.e.
`pl_burgershot:getKioskData`. If you rename the resource folder, these change too.
{% endhint %}

***

## Kiosk integration contract

This is the contract the companion **`pl_restaurantapp`** (delivery/ordering
app for lb-phone and gksphone — documentation forthcoming) uses to sell
BurgerShot food through its "kiosk" adapter. Any resource can use the same 3
calls to integrate.

### `pl_burgershot:getKioskData` — callback

No arguments. Returns the categorized menu, or `nil` if the shop is closed.

```lua
local menu = lib.callback.await('pl_burgershot:getKioskData', false)
-- menu = {
--   Burgers = { label = "Burgers", items = {
--     { item_name = "bs_classic_burger", name = "Classic Burger", price = 40, stock = 12, image = "nui://pl_burgershot/web/assets/items/bs_classic_burger.png" },
--     ...
--   }},
--   Fries = { ... }, Drinks = { ... },
-- }
-- returns nil if the shop is currently closed
```

### `pl_burgershot:placeKioskOrder` — callback

**Args:** `items` (array of `{ item, name?, quantity }`), `paymentMethod`
(`'bank'` or `'counter'`).
**Returns:** `orderId` (string) on success, or `nil, err` on failure.

```lua
local orderId, err = lib.callback.await('pl_burgershot:placeKioskOrder', false, {
    { item = 'bs_classic_burger', quantity = 2 },
    { item = 'bs_cola',           quantity = 1 },
}, 'bank')

if not orderId then
    -- err is one of: 'empty' | 'invalid' | 'error' | 'invalid_item' | 'invalid_qty' | 'insufficient'
end
```

`'bank'` charges the caller's bank account immediately and puts the order
straight into the **Pending** queue for staff to approve. `'counter'` places
it unpaid — staff must send a bill afterwards (see
[Custom Billing](feature-guide.md#custom-billing)).

### `pl_burgershot:client:notify` — event (server → specific client)

Fired **to the customer** at various points in the order lifecycle (order
ready, order rejected/refunded, tip received, etc). Payload: `(message: string,
ntype: 'success'|'error'|'inform')`.

```lua
RegisterNetEvent('pl_burgershot:client:notify')
AddEventHandler('pl_burgershot:client:notify', function(message, ntype)
    -- forward this to your own UI/notification system
end)
```

***

## Other server callbacks

These aren't part of the kiosk contract but are still registered with
`lib.callback.register` and safe to call from another server-side resource in
the same process (they all check the caller's job/grade internally):

| Callback | Args | Returns |
|---|---|---|
| `pl_burgershot:getOrders` | — | `pending, cooking, ready` order-queue tables (staff only) |
| `pl_burgershot:getSocietyBalance` | — | business bank balance (boss only) |
| `pl_burgershot:getOrderHistory` | — | last 500 completed orders (boss only) |
| `pl_burgershot:duty:getStatus` | — | `true`/`false`, whether the caller is currently clocked in |
| `pl_burgershot:duty:getShiftHistory` | — | last 500 shift records (boss only) |
| `pl_burgershot:getPendingOrders` | — | ingredient restock orders still in transit (staff only) |
| `pl_burgershot:grill:getState` / `fryer:getState` / `assembly:getState` | — | live station state + server game timer |

***

## Script-scope helper functions (not cross-resource exports)

`server/modules/duty.lua` defines two **global Lua functions**, not `exports`,
so other modules inside `pl_burgershot` can read/update duty status directly:

```lua
IsPlayerOnDuty(src)             -- boolean
IncrementShiftItemsCooked(src)  -- no-op if the player isn't clocked in
```

These are **not** callable via `exports['pl_burgershot']:...` from another
resource — they only exist in this script's own Lua environment. If you need
duty status from another resource, use the `duty:getStatus` callback above instead.

***

## What BurgerShot calls on other resources

For completeness — these are the external calls BurgerShot itself makes, in
case you're building a compatible replacement for one of them:

| Call | Resource | Purpose |
|---|---|---|
| `exports['pl_lib']:...` (many) | `pl_lib` | Framework, target, notify, textUI, clothing, society/banking, logging |
| `exports['pl_restaurant_tools']:hasBuilderAccess(source)` | [`pl_restaurant_tools`](https://github.com/pulsepk/pl_restaurant_tools) (optional) | Gates in-world builder/editing tools |
| `exports['rpemotes']:EmoteCancel/EmoteCommandStart` | `rpemotes` (optional carry style) | Carry emotes configured via `Config.Carry[item].Emote` |
| `exports['qb-inventory']:OpenInventory(...)` | `qb-inventory` (if detected) | Opens the stash/fridge as a linked inventory |
