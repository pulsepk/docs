# Target System

All target exports work transparently with both **ox\_target** and **qb-target**. Set the active system via `PLLib.Target` in `config.lua`, or leave it as `'autodetect'`.

All exports are **client-side**.

***

## AddEntityTarget

Add interaction options to a specific entity (vehicle, ped, prop).

```lua
exports.pl_lib:AddEntityTarget(entity, opt)
```

| Parameter | Type | Description |
|---|---|---|
| `entity` | number | Entity handle |
| `opt` | table | See option fields below |

**Option fields:**

| Field | Type | Description |
|---|---|---|
| `name` | string | Unique option ID |
| `label` | string | Label shown in the target menu |
| `icon` | string | FontAwesome icon class (e.g. `'fas fa-hand'`) |
| `distance` | number | Interaction range in metres (default: 2.5) |
| `event` | string | Client event to trigger on select |
| `serverEvent` | string | Server event to trigger on select |
| `args` | table | Arguments passed with the event |
| `jobRequired` | string | Job name required to see this option |
| `grade` | number | Minimum job grade required |

**Example:**
```lua
exports.pl_lib:AddEntityTarget(atmEntity, {
    name     = 'rob_atm',
    label    = 'Rob ATM',
    icon     = 'fas fa-dollar-sign',
    distance = 2.0,
    event    = 'pl_atmrobbery:startRob',
})
```

***

## RemoveEntityTarget

Remove all pl\_lib target options from an entity.

```lua
exports.pl_lib:RemoveEntityTarget(entity)
```

***

## AddBoxTarget

Create a box zone with interaction options.

```lua
local zoneId = exports.pl_lib:AddBoxTarget(zone, opt)
```

**Zone fields:**

| Field | Type | Description |
|---|---|---|
| `TargetCoords` | vector3 | Centre of the box |
| `w` | number | Width |
| `h` | number | Length/depth |
| `height` | number | Box height |
| `heading` | number | Rotation in degrees |
| `minZ` | number | Minimum Z (optional) |
| `maxZ` | number | Maximum Z (optional) |
| `debug` | bool | Show debug outline (optional) |

**Example:**
```lua
local zone = exports.pl_lib:AddBoxTarget(
    { TargetCoords = vec3(100.0, 200.0, 30.0), w = 1.5, h = 1.5, height = 1.0, heading = 0.0 },
    { name = 'shop_zone', label = 'Open Shop', icon = 'fas fa-store', event = 'shop:open' }
)
```

***

## RemoveBoxTarget

```lua
exports.pl_lib:RemoveBoxTarget(zoneId)
```

***

## AddModelTarget

Add interaction options to every entity matching a model hash. Useful for world props (ATMs, gas pumps, etc.).

```lua
exports.pl_lib:AddModelTarget(model, opts)
```

| Parameter | Type | Description |
|---|---|---|
| `model` | string \| number | Model name or hash |
| `opts` | table | Array of option tables (same fields as AddEntityTarget) |

**Example:**
```lua
exports.pl_lib:AddModelTarget('prop_atm_01', {
    {
        name     = 'use_atm',
        label    = 'Use ATM',
        icon     = 'fas fa-credit-card',
        distance = 1.5,
        event    = 'atm:open',
    }
})
```

***

## RemoveModelTarget

```lua
exports.pl_lib:RemoveModelTarget(model)
```

***

## AddChairTarget

Create a sit/stand interaction on a chair or seat prop.

```lua
local zoneId = exports.pl_lib:AddChairTarget(zoneName, chair, debug)
```

**Chair fields:**

| Field | Type | Description |
|---|---|---|
| `coords` | vec4 | Position and heading of the chair |
| `w` | number | Zone width |
| `h` | number | Zone length |
| `height` | number | Zone height |
| `label` | string | Interaction label |
| `minZ` | number | Optional min Z |
| `maxZ` | number | Optional max Z |
| `stand` | vector4 | Where the player stands when they get up |

**Selection event:**
```lua
AddEventHandler('pl_lib:targetSelected', function(data)
    -- data.loc  = the chair coords
    -- data.stand = the stand position
end)
```

**Example:**
```lua
exports.pl_lib:AddChairTarget('barstool_1', {
    coords = vec4(100.0, 200.0, 30.0, 180.0),
    w = 0.5, h = 0.5, height = 0.7,
    label  = 'Sit Down',
    stand  = vec4(101.0, 200.0, 30.0, 180.0),
})
```
