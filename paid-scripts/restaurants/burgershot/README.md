# 🍔 BurgerShot

{% embed url="https://youtu.be/ePB-4ZlnF1k" %}

### Purchase Escrow: [\[Click Here\]](https://pulsescripts.com/product/burgershot)

### Purchase OpenSource: [\[Click here\]](https://pulsescripts.com/category/opensource)

### Preview: [\[Click Here\]](https://youtu.be/ePB-4ZlnF1k)

{% hint style="info" %}
**v3.0.0** — a full rebuild with a real NUI, self-migrating database, and a
delivery app. Upgrading from v2? Read [What's New in v3](whats-new-v3.md) first.
{% endhint %}

### Map Supported by This Script

**Gabz :** [\[Click Here\]](https://fivem.gabzv.com/)

**Molo Modding :** [\[Click Here\]](https://www.molo-modding.com/package/5375088)

**G\&N Studio :** [\[Click Here\]](https://fivem.gn.studio/)

**Smallo** **\[FREE]** : [\[Click Here\]](https://www.gta5-mods.com/maps/gtaiv-burgershot-interior-sp-and-fivem)

**Uniqx** **\[FREE]** : [\[Click Here\]](https://www.gta5-mods.com/maps/mlo-burgershot-2023-add-on-sp-fivem)

**King Maps:** [\[Click Here\]](https://kingmaps.net/products/6167902)

**TStudio :** [\[Click Here\]](https://turbosaif.tebex.io/package/5956096)

**Giant \[FREE]:** [\[Click Here\]](https://forum.cfx.re/t/mlo-free-burger-shot/5401933)

Set `Config.location = 'auto'` and the script will pick whichever of these is
actually running on your server — see [Installation](installation.md).

### Prop Supported

**pl\_restaurant\_props** — a dedicated custom prop pack shipped alongside the
script (patties, fries, fry basket, burger bun, kiosk). v3 ships its own
props, so the old v2 dependency on the external DJ Collections prop pack is
gone. **Required**, see
[Installation](installation.md#1-pl_restaurant_props-required).

***

## Features

### 🧾 Ordering & Front of House

- **Kiosk counter ordering** — customers browse a categorized menu (via a full
  NUI, not a plain list) and pay by bank or at the counter.
- **Order queue** — Pending → Cooking → Ready → Completed, tracked live for
  every staff member on shift.
- **📺 Order display board** — a TV prop shows the live order queue, just like
  a real fast-food restaurant.
- **🧾 Custom billing** — send a customer an ad-hoc bill for anything, with an
  optional tip.
- **💵 Tipping** — percentage tips, split between the employee and the business.
- **🧻 Printed receipts** — customers get an itemized receipt after checkout.
- **📱 Delivery app** — sell through the companion `pl_restaurantapp` on
  lb-phone/gksphone, including a full delivery-driver job.

### 🧑‍🍳 Kitchen & Cooking

- **🔥 Grill** — multi-slot shared grill, real-time synced cook/burn timers.
- **🍟 Fryer** — cook frozen fries (and other fryer items), with its own
  cook/burn timers and a shared fries counter stock.
- **🥪 Assembly station** — build burgers step by step in the exact order the
  recipe requires, with on-screen hints for missing ingredients.
- **🥤 Drink machine** — multi-step drink crafting (fill → optional skill check).
- **🧊 Ice machine** — turn water bottles into ice cubes over a configurable wait time.
- **🎮 Interactive cooking & skill checks** — a real mini-game, not a progress bar.
- **🧼 Kitchen cleanliness** — the kitchen gets dirty after a set number of
  cooks and needs cleaning before work continues.
- **🧽 Optional hand-wash requirement** before cooking.
- **🍔 Inbuilt consumables** — eating/drinking animations and hunger/thirst are
  handled by the script itself, item by item.

### 🏛️ Management

- **Item stock management** — add/remove stock, update prices, live from the NUI.
- **👨‍💼 Boss menu** — open/close the shop, manage society funds (withdraw/
  deposit), hire/promote/demote/fire staff, view and clear order & shift history.
- **🧑‍🍳 Duty / clocking system** — employees clock in/out; shift duration and
  items cooked are tracked and visible to management.
- **📦 Fridge / stash storage** — order ingredients in bulk with a delivery ETA,
  store and retrieve stock.
- **👕 Wardrobe** — switch to the job uniform on duty.
- **🍽️ Tables, seats & counter trays** for a real dine-in experience.
- **🗑️ Trash can** for burnt/ruined items.

### 🛠️ Under the Hood

- Self-installing, self-migrating database schema (zero manual SQL on upgrade).
- Works with ESX, QBCore, and Qbox via **pl\_lib**.
- Works with **ox\_inventory**, **qb-inventory**, and ESX items.
- Declarative recipe system — add a new menu item by editing one file.
- Location auto-detection across 8 supported map packs.

See the [Feature Guide](feature-guide.md) for a full walkthrough of every
system, [Installation](installation.md) to get set up, and
[Exports & Events](exports-and-events.md) if you're building an integration.
