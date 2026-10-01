# ❗ Common Issues

<details>

<summary>I am getting the "Shop is closed" message.</summary>

Either a boss genuinely closed the shop from the boss menu (toggle it back
open), or — if you're upgrading from v2 — you're still on the old single-table
schema. Drop the `pl_burgershot` table and restart the script to let
`AutoInstallSQL` regenerate it, or run the manual SQL from
[Installation → Step 6](installation.md#step-6-database).

</details>

<details>

<summary>Nothing works at all — no target prompts, no notifications, console full of nil errors.</summary>

`pl_lib` isn't installed, isn't started, or started **after** `pl_burgershot`
in `server.cfg`. v3 delegates framework/target/notify detection entirely to
pl\_lib — see [Installation → Step 2](installation.md#step-2-install-pllib-first).

</details>

<details>

<summary>Food/kiosk models are invisible, or look like default GTA props.</summary>

`pl_restaurant_props` isn't installed or isn't started. It's a separate
resource, not bundled inside `pl_burgershot`, and isn't listed in its
`dependencies {}` block — see [Installation → Step 3](installation.md#1-pl_restaurant_props-required).

</details>

<details>

<summary>No sizzling/pouring sound at the grill, fryer, or drink machine.</summary>

`xsound` is optional and fails silently if it isn't installed — that's
expected. If you **do** have `xsound` installed and still hear nothing, you
likely haven't copied the 3 files from `Installfolder/sounds/` into xsound's
own sounds folder yet — see [Installation → Step 3](installation.md#2-xsound-sound-files-optional-but-silent-otherwise).

</details>

<details>

<summary>Carry/cooking animations don't play — the player just stands still holding the item.</summary>

The custom `.ycd` animation dictionaries (`cup_holding`, `frybasket`,
`kitchen_spatula`, etc.) haven't been registered in your emote resource (e.g.
`rpemotes`) — see [Installation → Step 3](installation.md#3-animation-dictionaries-in-your-emote-resource-required-for-animations-to-work).

</details>

<details>

<summary>Fridge stock, blip, or grill/fryer slots are in the wrong place, or the console warns about Config.location.</summary>

`Config.location` doesn't match the map pack resource you actually have
running. If you're using `Config.location = 'auto'`, check that the resource
name in `Config.LocationResources` for your map pack matches the real folder
name of the map resource on your server — map creators occasionally rename
their resource between versions.

</details>

<details>

<summary>AutoInstallSQL doesn't create/upgrade the tables.</summary>

Your database user is missing `CREATE TABLE` / `ALTER TABLE` privileges. Grant
them, or turn `Config.AutoInstallSQL` off and run the manual SQL from
[Installation → Step 6](installation.md#step-6-database) yourself.

</details>

<details>

<summary>Delivery orders placed through pl_restaurantapp never show up in BurgerShot's order history.</summary>

`pl_restaurantapp`'s `Config.Restaurants` entry for BurgerShot has a `dbTable`
that doesn't exactly match `Config.DBTable` here (`pl_burgershot` by default),
or `pl_burgershot`'s own `pl_burgershot_orders` table doesn't exist yet
(the delivery app inserts into your restaurant's own orders table — it
doesn't create one). Start `pl_burgershot` at least once first so
`AutoInstallSQL` creates the table, then double-check the `dbTable` value.

</details>

<details>

<summary>Employees can't cook / use the register even though they're clocked in.</summary>

Check `Config.RequireHandWash` — if it's enabled, employees also need to wash
their hands before cooking, separately from being clocked in.

</details>
