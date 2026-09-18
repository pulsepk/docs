# 🆕 What's New in v3

BurgerShot **v3.0.0** is a full rebuild of the script. The kitchen is no longer a
handful of menus bolted onto counters — it's a real, multi-station fast-food
simulation with its own NUI, a relational database, and a companion delivery
app. This page explains what changed, what you need to do to upgrade, and what
each new system actually does.

{% hint style="danger" %}
**This is a breaking upgrade.** v3 depends on **pl\_lib** for framework, target,
notification, and UI detection — the old `Config.Framework / TextUI / Notify /
Target / Clothing / BillingMenu = 'autodetect'` settings from v2's config no
longer exist in pl\_burgershot's own config, because that logic now lives in
pl\_lib. Read the [Installation](installation.md) page fully before updating a
live server.
{% endhint %}

***

## Migrating from v2

1. Install and start **pl\_lib** (see [pl\_lib installation](../../../pl_lib/pl_lib/installation.md)) — it must be running before `pl_burgershot` starts.
2. Pull the new v3 files over your old install.
3. Leave `Config.AutoInstallSQL = true`. On first boot, the script automatically:
   - Creates the two new tables it needs (`pl_burgershot_orders`, `pl_burgershot_shifts`) if they don't exist.
   - Upgrades your existing `pl_burgershot_fridge` table from the old multi-row schema to the new single-row JSON schema, **carrying your existing stock numbers over** — nothing is lost.
   - Widens `order_id` to `VARCHAR(36)` and adds a `paid_account` column to `pl_burgershot_orders` if you're upgrading from an earlier v3 build.
4. Re-register your items — the v3 item catalog is smaller and renamed, and no longer needs the DJ Collections prop pack (see below). Copy the new snippets from `Installfolder/items-*` into your inventory, don't just keep your old v2 item list — and copy the icons from `Installfolder/images/` into your inventory's own image folder (e.g. `ox_inventory/web/images/`), which is separate from the NUI's own icons.
5. Install the extra resources v3 needs that **aren't** enforced by `fxmanifest.lua`: `pl_restaurant_props`, plus copying sounds into `xsound` and animations into your emote resource. See [Installation → Required manual steps](installation.md#required-manual-steps-not-enforced-by-fxmanifest) — these are easy to miss and the shop will look/sound broken without them.
6. Read through `shared/config.lua` top to bottom — most v2 settings were renamed, removed, or moved into pl\_lib. Don't copy your old config file over the new one.

***

## Breaking changes

| v2 | v3 |
|---|---|
| Standalone `'autodetect'` framework/UI/target/notify glue built into the script's own config | Delegated to **pl\_lib** (new hard dependency) — see [pl\_lib docs](../../../pl_lib/pl_lib/README.md) |
| One flat `pl_burgershot` table (`stock` + `state`) | Four tables: main, `_fridge` (JSON stock), `_orders` (full history), `_shifts` (clock in/out) — all self-installing/self-migrating |
| Item defs hard-coded per station | Declarative `shared/recipe.lua` (`ItemDefinitions`) — one place to add/edit menu items |
| ~50-item sprawling menu (many burger/wing variants), relying on the external DJ Collections prop pack | Streamlined ~25-item core menu, intentionally simplified for v3, built entirely on the script's own `pl_restaurant_props` — no external prop pack needed |
| No NUI app | Full NUI (`web/`) for the kiosk, boss menu, fridge, order queue, receipts, drink fill, supplier ordering, and the order display board |
| No companion phone app | `pl_restaurantapp` — order/delivery app for lb-phone and gksphone |

***

## New features

- **🧑‍🍳 Duty / Clocking system** — employees clock in/out, shift time and
  items-cooked are tracked in the database, survives disconnects/crashes. Gated
  by `Config.RequireDuty`.
- **🧼 Kitchen cleanliness** — the kitchen gets dirty after `Config.Kitchen.DirtyAfterCooks`
  items cooked and must be cleaned (`CleanDuration`) before staff can keep cooking.
- **🧽 Hand-wash requirement** — optional pre-cooking hygiene step (`Config.RequireHandWash`).
- **🎮 Interactive cooking with skill checks** — a proper mini-game-driven cook
  loop (`Config.SkillCheck`) with burn timers on the grill and fryer.
- **🧾 Custom billing** — staff can send a customer an ad-hoc bill from the
  kiosk, paid via a bank/cash dialog with an optional tip slider.
- **💵 Tipping** — percentage-based customer tips, split between employee and
  business (`Config.Tip`).
- **🧻 Printed receipts** — customers get a receipt item after checkout that
  shows an itemized order, visible to them and anyone standing nearby.
- **📺 Order display board** — a TV prop near the kitchen shows live
  Pending / Cooking / Ready queues, like a real fast-food order screen.
- **🍔 Inbuilt consumables** — eating/drinking animations and hunger/thirst are
  handled by the script itself (`Config.Consumables`), no inventory-side status
  config needed for BurgerShot items.
- **🗺️ Location auto-detect** — `Config.location = 'auto'` picks whichever
  supported MLO you actually have running; adds support for the free
  [**Giant** Burger Shot map](https://forum.cfx.re/t/mlo-free-burger-shot/5401933).
- **🧱 Custom props & animations** — dedicated food/kiosk models
  (`pl_restaurant_props`) and bespoke carry/cooking animation dictionaries.
- **📱 Delivery app integration** — BurgerShot exposes a kiosk callback contract
  (`getKioskData` / `placeKioskOrder` / `client:notify`) that `pl_restaurantapp`
  uses to sell BurgerShot food through lb-phone/gksphone, including a full
  delivery-driver gig job.

See the [Feature Guide](feature-guide.md) for a deep dive into each of these,
and [Exports & Events](exports-and-events.md) if you're integrating another
resource with BurgerShot's kiosk.
