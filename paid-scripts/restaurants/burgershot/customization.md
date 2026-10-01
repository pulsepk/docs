# 🛠️ Customization Guide

How to extend BurgerShot without breaking the core station logic.

***

## Adding or changing a menu item

Everything about what can be made lives in **`shared/recipe.lua`**
(`ItemDefinitions.categories`). Copy an existing entry in the right category
and change its details:

```lua
bs_double_cheese_burger = {
    label    = "Double Cheese Burger",
    price    = 65,
    reward   = 1, -- how many finished items this produces per craft
    required = {
        { item = 'bs_grilled_patty', label = "Grilled Patty", quantity = 2 },
        { item = 'bs_bun',           label = "Burger Bun",    quantity = 1 },
        { item = 'bs_cheese_slice',  label = "Cheese Slice",  quantity = 2 },
    },
},
```

For a drink/multi-station item, add a `duration` and a `steps` list — each
step names a `station` (must match a key handled in
`client/modules/interactivecooking.lua`'s `GetStationCoords`, currently just
`'DrinkMachine'`), how long it takes, and whether it needs a skill check:

```lua
steps = {
    { label = 'Fill drink', station = 'DrinkMachine', duration = 13000, skill = false },
},
```

After adding an item, remember to:
1. Register the new item name in your inventory (see [Installation → Step 8](installation.md#step-8-register-items)).
2. Add it to `Config.Shop.Storage` if it (or its ingredients) should be
   orderable from the fridge.
3. Restart the resource — `AutoInstallSQL` will re-seed any brand-new
   ingredient into the fridge stock automatically the next time the fridge
   table is touched, but existing rows aren't rewritten, so double-check the
   fridge menu shows the new item.

***

## Adding a new map / location

1. Add your map pack to `Config.LocationResources` (only needed if you use
   `Config.location = 'auto'`) and to the `locationBlips` table in
   `shared/config.lua` with the blip coordinates for your map.
2. `shared/location.lua` holds a full `Location.*` table **per map pack**
   (`Location.Grill`, `Location.Fryer`, `Location.Assembly`, `Location.DrinkMachine`,
   `Location.Management`, `Location.Delivery`, `Location.DisplayBoard`,
   `Location.KitchenDirtyProps`, `Location.Tables`, `Location.ChairGroups`,
   `Location.CupPickup`, `Location.BuyMenu`, `Location.FryerAssembly`) — copy an
   existing map's block and adjust every coordinate to your new interior.
   `Config.Debug.PolyZone`/`DrawSprite` are extremely useful here: turn them
   on to see red interaction boxes and white markers while you place coordinates.
3. Set `Config.location` to your new key.

***

## Carry animations & props

`Config.Carry[itemName]` controls what a player looks like while physically
carrying an item (cooked fries, a grilled patty, an empty cup, etc). Three shapes:

- `{ Emote = 'key' }` — plays an emote by name from **rpemotes**.
- `{ Model=, Bone=, Offset=, Dict=, Clip= }` — a single held prop.
- `{ PropOne=, PropTwo=, Bone=, PropOneOffset=, PropTwoOffset=, Dict=, Clip= }`
  — two props together (e.g. fries sitting in a basket). Add `Duration` (ms)
  to make it a one-shot animation instead of something held the whole time.

Use the in-game `/rtattach` command to preview and fine-tune the
Offset/PropOneOffset/PropTwoOffset numbers live, then copy the values it gives
you back into the config. Any custom animation dictionary referenced here must
be registered in your emote resource first — see
[Installation → Step 3](installation.md#3-animation-dictionaries-in-your-emote-resource-required-for-animations-to-work).

***

## Permissions

BurgerShot's own permission model is entirely job-grade based, via pl\_lib:

- **Employee-gated actions** (cooking, kiosk approval, fridge access, duty
  toggle, etc.) check `GetJob(src) == Config.Jobname`.
- **Boss/management actions** (society withdraw/deposit, hire/fire, clear
  history, open/close shop) additionally check
  `GetJobGrade(src) >= Config.BossGrade`.

There's no separate ACE permission layer in the script itself — if you need
finer-grained permissions than job grade, gate it at the framework/job level
(e.g. custom grade names/numbers), not inside BurgerShot's Lua.

The one **optional** external permission hook is
`exports['pl_restaurant_tools']:hasBuilderAccess(source)`, used only by the
carry/builder-tools integration if you install
[`pl_restaurant_tools`](https://github.com/pulsepk/pl_restaurant_tools).

***

## What's safe to edit (escrow build)

If you bought the escrowed version, `fxmanifest.lua`'s `escrow_ignore` list is
exactly what ships unencrypted and editable:

```
readme.md, Installfolder/*, client/unlocked.lua, client/IceMachine.lua,
client/interaction.lua, client/lib.lua, client/modules/*, client/props.lua,
server/modules/*, server/modules/grill.lua, server/lib.lua, server/IceMachine.lua,
server/unlocked.lua, server/Log.lua, shared/*, targets/targets.lua, locales/**.json
```

In practice: **config, locations, recipes, locales, all client modules, all
server modules, and targets** are open — which covers everything in this
customization guide. Core files not in that list (e.g. `server/main.lua`,
`client/main.lua`) stay locked in the escrow build; buy the OpenSource
edition if you need to modify those directly.
