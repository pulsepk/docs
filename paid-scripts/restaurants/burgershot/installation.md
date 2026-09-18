# Installation

{% hint style="info" %}
Upgrading from v2? Read [What's New in v3](whats-new-v3.md) first — several
settings were renamed or moved into pl\_lib.
{% endhint %}

***

## Dependency matrix

| Resource | Required? | Why |
|---|---|---|
| [`ox_lib`](https://github.com/overextended/ox_lib) | **Required** | Callbacks, menus, points, zones, skill checks |
| [`oxmysql`](https://github.com/overextended/oxmysql) | **Required** | Database access |
| [`pl_lib`](https://github.com/pulsepk/pl_lib) | **Required** | Framework (ESX/QBCore/Qbox), target, notify, textUI, clothing, society/banking bridge — see [pl\_lib docs](../../../pl_lib/pl_lib/README.md) |
| `pl_restaurant_props` | **Required** | Custom food/kiosk props — not declared in `fxmanifest.lua`, see below |
| [`ox_target`](https://github.com/overextended/ox_target) or [`qb-target`](https://github.com/qbcore-fivem/qb-target) | Required if `Config.Interaction = 'target'` | Configured through pl\_lib |
| `ox_inventory`, `qb-inventory`, or ESX items | **Required** (pick one) | Item registration |
| [`xsound`](https://github.com/Xogy/xsound) | Optional | Grill/fryer sizzle + drink machine pour sound. Script works fine without it, just silently no sound. |
| [`rpemotes`](https://github.com/alberttheprince/rpemotes-reborn) (or your emote resource) | Recommended | Carry/cooking animation dictionaries — see below |
| [`ctn-text3d`](https://github.com/icetinturkey/ctn-text3d) | Optional | Only needed if `Config.Interaction = 'text3d'` for any zone |
| [`pl_restaurant_tools`](https://github.com/pulsepk/pl_restaurant_tools) | Optional | Gates in-world builder/editing tools, if you use it |
| `pl_restaurantapp` | Optional | Delivery/ordering companion app for lb-phone/gksphone |

***

## Step 1 — Download & place

Drop the `pl_burgershot` folder into your server's `resources` directory.

***

## Step 2 — Install pl\_lib first

pl\_lib **must** be installed, configured, and started before `pl_burgershot`.
Follow the [pl\_lib installation guide](../../../pl_lib/pl_lib/installation.md),
then come back here. If pl\_lib isn't running when pl\_burgershot starts,
framework/target/notify detection fails and the whole script silently breaks.

***

## Step 3 — Required manual steps not enforced by fxmanifest

These aren't in `pl_burgershot`'s `dependencies {}` block, so it's easy to
install the script and think it's "done" while these are still missing.

### 1. pl\_restaurant\_props (required)

A separate map/prop resource that streams the custom models the config
references by name — `pl_rawpatty`, `pl_cookedpatty`, `pl_burnedpatty`,
`pl_cookedfries`, `pl_fries`, `pl_burnedfries`, `pl_fry_basket`,
`pl_burgerbun`, `pl_kiosk`. Drop the `pl_restaurant_props` folder into
`resources` and `ensure` it in `server.cfg` **before** `pl_burgershot`.
Without it, cooked food and the kiosk prop simply won't render.

### 2. xsound sound files (optional, but silent otherwise)

If you run [`xsound`](https://github.com/Xogy/xsound), copy the 3 files from
`pl_burgershot/Installfolder/sounds/` into your `xsound` resource's own sounds folder:

| File | Used by |
|---|---|
| `drinkmachine.mp3` | `Config.DrinkMachine.PourSound` |
| `fryer.mp3` | `Config.Fryer.SizzleSound` |
| `grillstation.mp3` | `Config.Grill.SizzleSound` |

The `Url` values in `shared/config.lua` are relative to xsound's own html
folder — keep the filenames the same, or update the `Url` fields to match
wherever you place them.

### 3. Animation dictionaries in your emote resource (required for animations to work)

The custom `.ycd` files in `pl_burgershot/Installfolder/animations/`
(`cup_holding`, `fries_eating`, `frybasket`, `kitchen_spatula`,
`pl_fry_basket`) need to be added/registered in your emote resource (e.g.
[`rpemotes`](https://github.com/alberttheprince/rpemotes-reborn)) so the game
can find them. Without this step, carry and cooking animations that reference
these dictionaries won't play. Follow your emote resource's own instructions
for adding a custom animation dictionary.

***

## Step 4 — server.cfg

```cfg
ensure ox_lib
ensure oxmysql
ensure pl_lib

ensure pl_restaurant_props

# your map pack, e.g.
ensure gabz_burgershot

ensure pl_burgershot
```

***

## Step 5 — Configure

Open `shared/config.lua` and set, at minimum:

- `Config.location` — the map pack you're using (`gabz`, `molo`, `gn`, `smalo`,
  `uniqx`, `king`, `tstudio`, `giant`), or `'auto'` to detect it from whichever
  resource is running (fill in `Config.LocationResources` first if you use `auto`).
- `Config.Jobname` / `Config.JobLabel` — must match the job you create in Step 7.
- `Config.Interaction` — `'target'`, `'textui'`, or `'text3d'`.
- `Config.RequireDuty` / `Config.RequireHandWash` — turn these on if you want
  employees to clock in / wash hands before working.

Everything else has sensible defaults — see [Preview Config](preview-config.md)
for the full annotated file, and [Feature Guide](feature-guide.md) for what
each system does.

***

## Step 6 — Database

Leave `Config.AutoInstallSQL = true` (the default). On first boot the script
creates all 4 tables it needs — `pl_burgershot`, `pl_burgershot_fridge`,
`pl_burgershot_orders`, `pl_burgershot_shifts` — and seeds the fridge with the
items from `Config.Shop.Storage`. If you upgrade later, it also auto-migrates
older table formats without touching your existing data.

{% hint style="warning" %}
Your database user needs `CREATE TABLE`, `ALTER TABLE`, and `INSERT`
privileges for auto-install/auto-migration to work. If it only has
`SELECT/INSERT/UPDATE/DELETE`, turn `Config.AutoInstallSQL` off and run the SQL
below by hand instead.
{% endhint %}

<details>

<summary>Manual SQL (only if AutoInstallSQL is off or fails)</summary>

```sql
-- Main table (also holds shop open/closed state + item stock/price for the kiosk)
CREATE TABLE IF NOT EXISTS `pl_burgershot` (
  `stock` LONGTEXT DEFAULT NULL,
  `state` VARCHAR(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- Fridge/ingredient stock (single-row JSON)
CREATE TABLE IF NOT EXISTS `pl_burgershot_fridge` (
  `stock` LONGTEXT DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- Completed order history
CREATE TABLE IF NOT EXISTS `pl_burgershot_orders` (
  `id`                       INT AUTO_INCREMENT PRIMARY KEY,
  `order_id`                 VARCHAR(36)   NOT NULL,
  `placed_at`                INT UNSIGNED  NOT NULL,
  `player_name`              VARCHAR(64)   NOT NULL,
  `player_identifier`        VARCHAR(64)   NOT NULL,
  `items`                    LONGTEXT      NOT NULL,
  `total`                    DECIMAL(10,2) NOT NULL,
  `payment_method`           VARCHAR(10)   NOT NULL,
  `paid_account`             VARCHAR(10)   DEFAULT NULL,
  `approved_by_name`         VARCHAR(64)   NOT NULL,
  `approved_by_identifier`   VARCHAR(64)   NOT NULL,
  `completed_by_name`        VARCHAR(64)   NOT NULL,
  `completed_by_identifier`  VARCHAR(64)   NOT NULL,
  `completed_at`             TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  UNIQUE KEY `unique_order` (`order_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- Employee clock in/out shifts
CREATE TABLE IF NOT EXISTS `pl_burgershot_shifts` (
  `id`             INT AUTO_INCREMENT PRIMARY KEY,
  `identifier`     VARCHAR(64)  NOT NULL,
  `player_name`    VARCHAR(64)  NOT NULL,
  `clock_in_at`    INT UNSIGNED NOT NULL,
  `clock_out_at`   INT UNSIGNED DEFAULT NULL,
  `status`         VARCHAR(12)  NOT NULL DEFAULT 'open',
  `items_cooked`   INT UNSIGNED DEFAULT NULL,
  INDEX `idx_identifier_status` (`identifier`, `status`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

**ESX only** — also create the society account/job:

```sql
INSERT INTO `addon_account` (name, label, shared) VALUES
    ('society_burgershot', 'BurgerShot', 1);

INSERT INTO `datastore` (name, label, shared) VALUES
    ('society_burgershot', 'BurgerShot', 1);

INSERT INTO `jobs` (name, label, whitelisted) VALUES
    ('burgershot', 'BurgerShot', 1);

INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
    ('burgershot', 0, 'cashier', 'Cashier', 20, '{}', '{}'),
    ('burgershot', 1, 'cook',    'Cook',    40, '{}', '{}'),
    ('burgershot', 2, 'staff',   'Staff',   60, '{}', '{}'),
    ('burgershot', 3, 'manager', 'Manager', 85, '{}', '{}'),
    ('burgershot', 4, 'boss',    'Owner',   100,'{}', '{}');
```

</details>

***

## Step 7 — Job

<details>

<summary>QBCore — paste into qb-core/shared/jobs.lua</summary>

```lua
['burgershot'] = {
    label = 'BurgerShot',
    defaultDuty = true,
    grades = {
        ['0'] = { name = 'Cashier',       payment = 50  },
        ['1'] = { name = 'Cook',          payment = 75  },
        ['2'] = { name = 'Shift Manager', payment = 100 },
        ['3'] = { name = 'Manager',       payment = 125 },
        ['4'] = { name = 'Owner',         payment = 125, isboss = true },
    },
},
```

</details>

<details>

<summary>Qbox — same job, grade keys without quotes</summary>

```lua
['burgershot'] = {
    label = 'BurgerShot',
    defaultDuty = true,
    grades = {
        [0] = { name = 'Cashier',       payment = 50  },
        [1] = { name = 'Cook',          payment = 75  },
        [2] = { name = 'Shift Manager', payment = 100 },
        [3] = { name = 'Manager',       payment = 125 },
        [4] = { name = 'Owner',         payment = 125, isboss = true },
    },
},
```

</details>

ESX users: the job + grades are created automatically by the manual SQL in
Step 6 (or by AutoInstallSQL).

`Config.BossGrade` (default `4`) is the minimum grade that can use boss/
management actions — match it to whichever grade number you make "Owner"/"Manager".

***

## Step 8 — Register items

{% hint style="info" %}
The v3 item catalog below is intentionally smaller than v2's — it's exactly
the items `shared/recipe.lua` uses, plus a few standalone ingredients/utility
items. The script now ships its own custom props (`pl_restaurant_props`), so
v3 no longer depends on the external DJ Collections prop pack — register just
the items below.
{% endhint %}

<details>

<summary>ox_inventory — copy into ox_inventory/data/items.lua</summary>

```lua
-- CONSUMABLES
["bs_classic_burger"] = {
    label = "Classic Burger", weight = 1,
    client = { status = { hunger = 200000 }, anim = 'eating', prop = 'burger', usetime = 2500, notification = 'You ate a delicious Classic Burger' },
},
["bs_cheese_burger"] = {
    label = "Cheese Burger", weight = 1,
    client = { status = { hunger = 200000 }, anim = 'eating', prop = 'burger', usetime = 2500, notification = 'You ate a delicious Cheese Burger' },
},
["bs_classic_fries"] = {
    label = "Classic Fries", weight = 1,
    client = { status = { hunger = 100000 }, anim = 'eating', prop = 'burger', usetime = 2500, notification = 'You ate some Classic Fries' },
},
["bs_cola"] = {
    label = "BurgerShot Cola", weight = 1,
    client = { status = { thirst = 200000 }, anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' }, prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) }, usetime = 2500, notification = 'You drank a refreshing BurgerShot Cola' },
},

-- INGREDIENTS (not eaten directly — stack/close only)
["bs_bun"]           = { label = "Burger Bun",   weight = 1, stack = true, close = true },
["bs_beef_patty"]    = { label = "Beef Patty",   weight = 1, stack = true, close = true },
["bs_cheese_slice"]  = { label = "Cheese Slice", weight = 1, stack = true, close = true },
["bs_emptycup"]      = { label = "BurgerShot Empty Cup", weight = 1, stack = true, close = true },
["bs_icecubes"]      = { label = "Ice Cubes",    weight = 1, stack = true, close = true },
["bs_waterbottle"]   = { label = "Water Bottle", weight = 1, stack = true, close = true },
["bs_grilled_patty"] = { label = "Grilled Patty",weight = 1, stack = true, close = true },
["bs_frozen_fries"]  = { label = "Frozen Fries", weight = 1, stack = true, close = true },
["bs_cooked_fries"]  = { label = "Cooked Fries", weight = 1, stack = true, close = true },

-- Purchase receipt (each copy is its own order, so it does not stack)
["bs_receipt"] = { label = "Receipt", weight = 1, stack = false, close = true },
```

Full file: `Installfolder/items-ox_inventory.lua`.

</details>

<details>

<summary>qb-inventory — copy into qb-core/shared/items.lua</summary>

```lua
['bs_classic_burger'] = {['name']='bs_classic_burger', ['label']='Classic Burger', ['weight']=10, ['type']='item', ['image']='bs_classic_burger.png', ['unique']=false, ['useable']=true, ['shouldClose']=true, ['combinable']=nil, ['description']=''},
['bs_cheese_burger']  = {['name']='bs_cheese_burger',  ['label']='Cheese Burger',  ['weight']=10, ['type']='item', ['image']='bs_cheese_burger.png',  ['unique']=false, ['useable']=true, ['shouldClose']=true, ['combinable']=nil, ['description']=''},
['bs_classic_fries']  = {['name']='bs_classic_fries',  ['label']='Classic Fries',  ['weight']=10, ['type']='item', ['image']='bs_classic_fries.png',  ['unique']=false, ['useable']=true, ['shouldClose']=true, ['combinable']=nil, ['description']=''},
['bs_cola']           = {['name']='bs_cola',           ['label']='BurgerShot Cola',['weight']=10, ['type']='item', ['image']='bs_cola.png',           ['unique']=false, ['useable']=true, ['shouldClose']=true, ['combinable']=nil, ['description']=''},

['bs_bun']           = {['name']='bs_bun',           ['label']='Burger Bun',   ['weight']=10, ['type']='item', ['image']='bs_bun.png',           ['unique']=false, ['useable']=false, ['shouldClose']=true, ['combinable']=nil, ['description']=''},
['bs_beef_patty']    = {['name']='bs_beef_patty',    ['label']='Beef Patty',   ['weight']=10, ['type']='item', ['image']='bs_beef_patty.png',    ['unique']=false, ['useable']=false, ['shouldClose']=true, ['combinable']=nil, ['description']=''},
['bs_cheese_slice']  = {['name']='bs_cheese_slice',  ['label']='Cheese Slice', ['weight']=10, ['type']='item', ['image']='bs_cheese_slice.png',  ['unique']=false, ['useable']=false, ['shouldClose']=true, ['combinable']=nil, ['description']=''},
['bs_emptycup']      = {['name']='bs_emptycup',      ['label']='Empty Cup',    ['weight']=10, ['type']='item', ['image']='bs_emptycup.png',      ['unique']=false, ['useable']=false, ['shouldClose']=true, ['combinable']=nil, ['description']=''},
['bs_icecubes']      = {['name']='bs_icecubes',      ['label']='Ice Cubes',    ['weight']=10, ['type']='item', ['image']='bs_icecubes.png',      ['unique']=false, ['useable']=false, ['shouldClose']=true, ['combinable']=nil, ['description']=''},
['bs_waterbottle']   = {['name']='bs_waterbottle',   ['label']='Water Bottle', ['weight']=10, ['type']='item', ['image']='bs_waterbottle.png',   ['unique']=false, ['useable']=false, ['shouldClose']=true, ['combinable']=nil, ['description']=''},
['bs_grilled_patty'] = {['name']='bs_grilled_patty', ['label']='Grilled Patty',['weight']=10, ['type']='item', ['image']='bs_grilled_patty.png', ['unique']=false, ['useable']=false, ['shouldClose']=true, ['combinable']=nil, ['description']=''},
['bs_frozen_fries']  = {['name']='bs_frozen_fries',  ['label']='Frozen Fries', ['weight']=10, ['type']='item', ['image']='bs_frozen_fries.png',  ['unique']=false, ['useable']=false, ['shouldClose']=true, ['combinable']=nil, ['description']=''},
['bs_cooked_fries']  = {['name']='bs_cooked_fries',  ['label']='Cooked Fries', ['weight']=10, ['type']='item', ['image']='bs_cooked_fries.png',  ['unique']=false, ['useable']=false, ['shouldClose']=true, ['combinable']=nil, ['description']=''},

-- Given to customers after checking out at the kiosk
['bs_receipt'] = {['name']='bs_receipt', ['label']='Receipt', ['weight']=10, ['type']='item', ['image']='bs_receipt.png', ['unique']=true, ['useable']=true, ['shouldClose']=true, ['combinable']=nil, ['description']=''},
```

Full file: `Installfolder/items-qb-inventory.lua`.

</details>

<details>

<summary>ESX — SQL insert</summary>

```sql
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
    ('bs_classic_burger', 'Classic Burger', 1),
    ('bs_cheese_burger',  'Cheese Burger',  1),
    ('bs_classic_fries',  'Classic Fries',  1),
    ('bs_cola',           'BurgerShot Cola',1),
    ('bs_frozen_fries',   'Frozen Fries',   1),
    ('bs_cooked_fries',   'Cooked Fries',   1),
    ('bs_bun',            'Burger Bun',     1),
    ('bs_beef_patty',     'Beef Patty',     1),
    ('bs_cheese_slice',   'Cheese Slice',   1),
    ('bs_emptycup',       'Empty Cup',      1),
    ('bs_icecubes',       'Ice Cubes',      1),
    ('bs_waterbottle',    'Water Bottle',   1),
    ('bs_grilled_patty',  'Grilled Patty',  1),
    ('bs_receipt',        'Receipt',        1);
```

</details>

### Item images

The kiosk/fridge/display NUI reads its icons straight from
`web/assets/items/` via `Config.ImagesPath` — nothing to do there. Your
**inventory's own UI** (the item icon shown in a player's inventory slots,
hotbar, etc.) is separate and reads from its own image folder, so you still
need to copy the icons from `pl_burgershot/Installfolder/images/` into it:

| Inventory | Copy the images into |
|---|---|
| `ox_inventory` | `ox_inventory/web/images/` |
| `qb-inventory` | `qb-inventory/html/images/` |

`Installfolder/images/` contains one `.png` per core item (matching the item
names above, including `bs_receipt.png` for the receipt) — drop all of them
in, don't rename anything.

***

## Step 9 — Optional: delivery app

If you want customers to order (and staff to deliver) BurgerShot food from a
phone, install the companion **`pl_restaurantapp`** resource (lb-phone or
gksphone builds — see its own documentation) and add an entry for
`"burgershot"` to its `Config.Restaurants`, with `dbTable = "pl_burgershot"`
matching `Config.DBTable` here exactly.

***

## Common pitfalls

<details>
<summary>Food/kiosk props are invisible or wrong-looking</summary>

`pl_restaurant_props` isn't installed or isn't started before `pl_burgershot`.
See Step 3.
</details>

<details>
<summary>No sizzle/pour sound</summary>

Either you don't have `xsound` installed (expected — it's optional and fails
silently), or you have it but haven't copied the 3 files from
`Installfolder/sounds/` into it. See Step 3.
</details>

<details>
<summary>Carry/cooking animations don't play, or the player just stands still</summary>

The custom `.ycd` animation dictionaries from `Installfolder/animations/`
haven't been registered in your emote resource. See Step 3.
</details>

<details>
<summary>Items show up in the inventory UI with no icon/a broken image</summary>

The `.png` files from `Installfolder/images/` haven't been copied into your
inventory's own image folder yet — this is separate from the NUI icons the
kiosk/fridge already load automatically. See [Step 8 → Item images](installation.md#item-images).
</details>

<details>
<summary>Everything silently doesn't work — no target prompts, no notifications</summary>

`pl_lib` isn't installed, isn't started, or is started **after**
`pl_burgershot` in `server.cfg`. Start order matters.
</details>

<details>
<summary>Blip/props/grill appear in the wrong spot, or "Config.location" errors</summary>

`Config.location` doesn't match the map pack you actually have running, or (if
using `'auto'`) the resource name in `Config.LocationResources` doesn't match
your map pack's real resource folder name.
</details>
