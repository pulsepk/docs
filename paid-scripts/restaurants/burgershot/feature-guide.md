# 🔍 Feature Guide

A deep dive into every system in BurgerShot v3. For the config keys that
control each one, see [Preview Config](preview-config.md); for how to tweak
recipes/locations/permissions, see [Customization](customization.md).

***

## 🧑‍🍳 Duty / Clocking

Staff toggle a clock-in/out event (`duty:toggle`). Clocking in writes an
"open" shift row to `pl_burgershot_shifts` (identifier, name, clock-in time)
immediately — so a shift survives a crash, disconnect, or server restart.
Clocking out stamps the same row with a clock-out time and duration. Every
item a clocked-in employee cooks at the grill/fryer/assembly increments that
shift's `items_cooked` counter.

- If a player disconnects while still clocked in, the server force-closes
  their shift on `playerDropped`.
- On resource start, any shift still marked `open` from a previous session
  (e.g. the server crashed) is marked `interrupted` so it doesn't linger forever.
- Bosses can view full shift history and clear it from the boss menu.
- Set `Config.RequireDuty = true` to make cooking/register actions require
  being clocked in.

***

## 🧼 Kitchen Cleanliness

If `Config.Kitchen.Enable` is on, the kitchen tracks how many items have been
cooked since it was last cleaned. Once that hits `Config.Kitchen.DirtyAfterCooks`,
mess props spawn at each position listed in `Location.KitchenDirtyProps`.
Staff must clean each prop individually (taking `Config.Kitchen.CleanDuration`
ms) before the kitchen counts as clean again and cooking can continue.

## 🧽 Hand-wash Requirement

An optional, simpler prerequisite (`Config.RequireHandWash`) — if enabled,
employees must wash their hands before the script lets them cook.

***

## 🔥 Grill

A shared, multi-slot cooking station (`Location.Grill.Slots` defines how many
slots exist for your map). Any employee can place a raw `bs_beef_patty` on an
open slot; the server tracks `cooking → cooked → burnt` server-side on a
5-second tick using `Config.Grill.CookTime`/`BurnTime`, and broadcasts state to
every client so multiple staff see the same grill in real time. Taking a
finished patty gives you a **carried** item (`bs_grilled_patty` or
`bs_burnt_patty`, per `Config.CarryItems`) rather than putting it straight in
your inventory — you physically carry it to the assembly station. The sizzle
sound (via `xsound`, if installed) starts when anything is placed and stops
once every slot is empty.

## 🍟 Fryer

Works the same way as the grill (shared slots, server-tracked cook/burn timers,
real-time sync, sizzle sound) but for `Config.Fryer.Items` — by default frozen
fries → cooked/burnt fries. There's also a shared **fries counter stock**
(`Location.FryerAssembly.Slots` defines its capacity) that any employee can add
cooked fries to or draw from when assembling fries-based menu items.

## 🥪 Assembly Station

Where burgers get built. Any employee can claim an open assembly slot for a
specific recipe item; the server validates each ingredient is deposited in the
order `shared/recipe.lua`'s `required` list defines. On-screen hints
(`Config.Assembly.ItemHints`) tell staff where to get a missing ingredient
(e.g. "Go to the stove and cook a patty"). Once every required ingredient is
deposited, the finished item prop appears and the order can be marked done.

## 🥤 Drink Machine

Drinks use the **interactive multi-step crafting** system instead of a single
station: `shared/recipe.lua` can attach a `steps` list to any item (e.g. "Fill
drink" at the `DrinkMachine` station, 13 seconds, no skill check). The client
walks the player through each step in order — showing a marker/TextUI prompt
at the right station coordinates, playing the matching category emote, and
optionally running a skill check — before the item is crafted server-side.
Before a drink can be started, the server checks the player is actually
carrying an empty cup (`drinkMachine:hasEmptyCup`).

## 🧊 Ice Machine

Turns a water bottle into ice cubes. Add water (`Config.IceMachine.water_itemname`)
at the machine to start production; after `Config.IceMachine.WaitTime` seconds
it yields `Config.IceMachine.IceGiven` ice cubes (`ice_itemname`). Only one
batch can be in progress at a time, and existing ice must be collected before
starting another.

***

## 🧾 Kiosk Ordering

The kiosk is the customer-facing counter. Its full lifecycle:

1. Customer opens the kiosk NUI → `getKioskData` callback returns the
   categorized menu (from `shared/recipe.lua`) with live price/stock pulled
   from the `pl_burgershot` table.
2. Customer places an order (`placeKioskOrder`) paying by **bank** (charged
   immediately) or **counter** (staff bills them later). The order enters the
   **Pending** queue.
3. A staff member approves it (`approveOrder`) → moves to **Cooking**.
4. Staff marks it done (`markOrderDone`) → moves to **Ready**; the customer
   gets a notification if they're online.
5. Staff finishes it (`finishOrder`) → the order is written to
   `pl_burgershot_orders` (full history: who approved, who completed, what was
   paid, how) and a printed receipt is granted if `Config.Receipt.Enable`.
6. Staff can also reject a pending order (`rejectOrder`), which refunds a
   bank-paid customer automatically if they're still online.

Every stage broadcasts to every on-duty staff member's screen and to the
[order display board](#order-display-board) at once, so the whole crew (and
the TV) always show the same live queues.

### 🧾 Custom Billing

For a **counter-paid** order, staff send the customer a bill
(`sendOrderInvoice`) — the server checks they're within 5m of each other, then
pushes a payment request to the customer's screen. The customer chooses
bank/cash and, if `Config.Tip.Enable`, a tip percentage via a slider — the
actual tip amount is always calculated **server-side** from that percentage so
a modified client can't fake a different value. `Config.Commission` and
`Config.MaxBillAmount` bound what a bill can charge.

### 💵 Tipping

`Config.Tip.Distribution` controls where a tip goes: straight to the serving
employee (`'employee'`), into the business account (`'society'`), or split
between both by `Config.Tip.SocietyPercent` (`'split'`). Both the percentage
and the total dollar amount are capped (`MaxPercentage`, `MaxTipAmount`).

### 🧻 Printed Receipts

If enabled, finishing an order grants the customer a `bs_receipt` item.
Using/opening it shows an itemized receipt on their screen — and briefly on
the screens of anyone within `Config.Receipt.NearbyRadius` too, the same way
showing someone an ID card would work — for `Config.Receipt.DisplaySeconds`,
or until manually closed.

### 📺 Order Display Board

A `prop_tv_flat_01` prop is spawned at `Location.DisplayBoard` and rendered
with a DUI web page (`web/display.html` + `web/order-queue.js`) mapped onto a
runtime texture — a live Pending / Cooking / Ready board, just like a real
fast-food restaurant's order screen. It updates automatically every time the
kiosk queue changes; no interaction needed to view it.

***

## 🍔 Inbuilt Consumables

Every food/drink item defined in `shared/recipe.lua` automatically becomes a
usable item — the script registers the handler itself
(`client/consumables.lua` + `server/consumables.lua`), spawns the matching
prop, plays the eating/drinking animation, and restores hunger/thirst by the
amount configured in `Config.Consumables.Categories` for that item's category
(a fixed number, or a random range). This is entirely self-contained: you do
**not** need to configure hunger/thirst "useable" effects for these items in
your inventory's own item definitions — `Config.Consumables.Enable = false`
turns the whole system off if you'd rather handle it yourself.

***

## 🏛️ Boss Menu

Available to anyone at `Config.BossGrade` or above:

- **Open/close the shop** — closing stops `getKioskData` from returning a menu
  at all, so customers can't order.
- **Society funds** — check the business bank balance, withdraw to personal
  cash, or deposit personal cash into the business.
- **Employees** — hire, promote, demote, fire (via pl\_lib's framework bridge).
- **Order history** — view the last 500 completed orders, or clear all history.
- **Shift history** — view or clear all clock-in/out records.
- **Ingredient ordering** — the same bulk restock flow available to staff (see
  below), accessible from the boss menu too.
- **Wardrobe / stash** shortcuts.

***

## 📦 Fridge / Ingredient Ordering

Staff can bulk-order raw ingredients from the fridge menu. The server
validates every line item and price against `Config.Shop.Storage`, charges the
total up front (cash, bank, or society funds), and delivers the whole order
`Config.IngredientOrder.DeliveryTime` seconds later, updating the fridge's
JSON stock and notifying all on-duty staff when it arrives. Staff can also
manually put/take stock items directly, as long as they're standing near the
fridge.

***

## 🧱 Custom Props & 🎞️ Custom Animations

BurgerShot ships with its own dedicated prop and animation set rather than
reusing only vanilla GTA assets:

- **Props** (via the separate `pl_restaurant_props` resource): custom patty,
  fries, fry-basket, burger-bun, and kiosk models used throughout the grill,
  fryer, assembly, and kiosk stations.
- **Animations** (`.ycd` files, shipped in `Installfolder/animations/` and
  the resource's own `stream/` folder): bespoke carry/cooking dictionaries
  (`cup_holding`, `fries_eating`, `frybasket`, `kitchen_spatula`,
  `pl_fry_basket`) used by the carry system (`Config.Carry`) and the
  interactive cooking steps.

Both need to be installed correctly for the shop to look and animate as
intended — see [Installation → Required manual steps](installation.md#required-manual-steps-not-enforced-by-fxmanifest).

***

## 🚚 Delivery Van

A simple ped near the shop (`Location.Delivery.Ped`) lets any on-duty employee
spawn or return a delivery vehicle (`Location.Delivery.VehicleModel` at
`Location.Delivery.VehicleSpawn`) — for driving BurgerShot delivery gig orders
placed through the companion **`pl_restaurantapp`** (delivery/ordering app for
lb-phone and gksphone — documentation forthcoming).
Unlike v2, BurgerShot itself no longer generates or tracks delivery orders —
that entire flow (accepting, GPS routing, marking delivered) now lives in
`pl_restaurantapp`; this ped is purely the "get a van" convenience for drivers.

***

## 🎮 Interactive Cooking & Skill Checks

Recipe items with a `steps` list (see `shared/recipe.lua`) are crafted through
a guided, multi-step flow: for each step, the client shows a marker and an
`[E]` prompt at the right station, plays that category's carry/cooking emote,
optionally runs a skill-check mini-game (`step.skill = true`), then runs a
progress bar for `step.duration`. Failing a skill check produces the
configured "burnt"/failed item (`Config.FailItems`) instead of the real one.
Turn skill checks off entirely with `Config.SkillCheck.Enable = false`.
