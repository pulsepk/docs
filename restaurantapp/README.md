# 📱 RestaurantApp

**pl\_restaurantapp** is a phone app that turns any of your restaurant scripts
into a real food-delivery platform. Customers browse every registered
restaurant, order for pickup or delivery straight from their phone, and
drivers pick up a proper gig job — accept an order, get a GPS waypoint, call
the customer, mark it delivered — all without leaving the phone UI.

{% hint style="info" %}
**One resource, two builds.** `pl_restaurantapp-lb` and `pl_restaurantapp-gks`
are the same app — identical logic, exports, and behavior — built for two
different phone frameworks. Install whichever one matches your server:
**lb-phone → `pl_restaurantapp-lb`**, **GKSPhone → `pl_restaurantapp-gks`**.
Everything on this page applies to both; see [Installation](installation.md)
for the one or two steps that differ between them.
{% endhint %}

***

## What's Inside

### Ordering

Customers open the app, pick a restaurant from a live list, and browse its
menu — pulled directly from that restaurant's own script, so it's always in
sync with real stock and prices. They can order for pickup, paid straight
from their bank account, or place a delivery order that goes out to any
on-duty driver.

### The delivery job

Any employee of a listed restaurant can open the app's driver view, see every
open delivery in real time, and accept one. Once accepted, the app hands them
a GPS waypoint to the customer, a way to call them directly, and a button to
mark the order delivered or cancel it. Every restaurant's staff only see
their own restaurant's deliveries.

### Live notifications

New deliveries, accepted orders, and delivery updates all push straight to
the phone — a lock-screen notification plus a live update inside the app if
it's already open — so drivers never have to sit and refresh a list.

### Built to extend

Under the hood, every restaurant is wired in through a small adapter — a
handful of functions that describe how to fetch that restaurant's menu, place
an order, and receive its notifications. The app ships with a **kiosk**
adapter that already works with any script using the same order-callback
pattern as `pl_burgershot`; adding support for a different kind of restaurant
script later is a matter of writing one more adapter, not rebuilding the app.
See [Integration Guide](integration-guide.md).

***

## Relationship to pl\_burgershot

RestaurantApp doesn't run its own restaurant logic or keep its own menu/stock
database — it's a storefront in front of whatever restaurant scripts you
register in `Config.Restaurants`. For `pl_burgershot`, that means the app
calls BurgerShot's own kiosk callbacks (`getKioskData` / `placeKioskOrder`)
to fetch the menu and place orders, and BurgerShot's own `pl_burgershot_orders`
table is what a completed delivery gets logged into — RestaurantApp has no
database of its own for that. See BurgerShot's
[Exports & Events](../paid-scripts/restaurants/burgershot/exports-and-events.md#kiosk-integration-contract)
page for the exact contract, and this app's own
[Integration Guide](integration-guide.md) for how that contract is used from
this side.

***

See [Installation](installation.md) to get set up, [Integration Guide](integration-guide.md)
for the adapter contract and full callback/event reference, and
[UI Customization](ui-customization.md) to reskin the app.
