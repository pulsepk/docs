# Utilities

***

## Entity Utilities — Client

### EnsureModel

Load a model by name or hash before spawning/using it. Returns `false` if the model is not in the asset cache.

```lua
local ok = exports.pl_lib:EnsureModel(model)
-- model: string name or number hash
```

**Example:**

```lua
if exports.pl_lib:EnsureModel('prop_atm_01') then
    -- safe to use the model
end
```

***

### NetToEnt

Convert a network ID to a local entity handle. Returns `0` on failure.

```lua
local entity = exports.pl_lib:NetToEnt(netId)
```

**Example:**

```lua
local atmEntity = exports.pl_lib:NetToEnt(atmNetId)
if atmEntity ~= 0 then
    -- entity is valid
end
```

***

### TryRequestControl

Request network control of an entity with a timeout. Required before modifying a networked entity's physics or state.

```lua
local ok = exports.pl_lib:TryRequestControl(entity, timeoutMs)
-- timeoutMs: default 1000
```

**Example:**

```lua
if exports.pl_lib:TryRequestControl(atmEntity, 1000) then
    SetEntityDynamic(atmEntity, true)
end
```

***

## Animation — Client

### LoadAnimDict

Load an animation dictionary and wait until it is ready.

```lua
exports.pl_lib:LoadAnimDict(dict)
```

### PlayAnim

Play an animation on an entity.

```lua
exports.pl_lib:PlayAnim(entity, dict, anim, blendIn, blendOut, duration, flags)
```

| Parameter  | Type   | Default | Description                  |
| ---------- | ------ | ------- | ---------------------------- |
| `entity`   | number | —       | Entity handle                |
| `dict`     | string | —       | Animation dictionary         |
| `anim`     | string | —       | Animation clip name          |
| `blendIn`  | number | `8.0`   | Blend in speed               |
| `blendOut` | number | `-8.0`  | Blend out speed              |
| `duration` | number | `-1`    | Duration in ms (`-1` = loop) |
| `flags`    | number | `49`    | Animation flags              |

**Example:**

```lua
exports.pl_lib:PlayAnim(PlayerPedId(), 'amb@world_human_hang_out_street@female_variant_01@base', 'base', 8.0, -8.0, -1, 49)
```

### LookAt

Rotate the player ped to face a set of coordinates.

```lua
exports.pl_lib:LookAt(coords)
-- coords: vector3
```

***

## Fuel — Client

Set a vehicle's fuel level, routed through your configured fuel resource.

```lua
exports.pl_lib:SetVehicleFuel(vehicle, level)
-- level: 0.0 – 100.0
```

**Example:**

```lua
exports.pl_lib:SetVehicleFuel(GetVehiclePedIsIn(PlayerPedId(), false), 100.0)
```

**Supported systems:** LegacyFuel, cdn-fuel, okokGasStation, rcore\_fuel, ox\_fuel

***

## Vehicle Keys — Client

Give the player keys to a vehicle (triggers their vehicle key resource).

```lua
exports.pl_lib:GiveVehicleKeys(vehicle)
```

**Example:**

```lua
local veh = GetVehiclePedIsIn(PlayerPedId(), false)
exports.pl_lib:GiveVehicleKeys(veh)
```

**Supported systems:** qb-vehiclekeys, wasabi\_carlock, qs-vehiclekeys, vehicles\_keys

***

## Appearance — Client

### SetPlayerUniform

Force a clothing outfit onto a player ped. Commonly used for job uniforms.

```lua
exports.pl_lib:SetPlayerUniform(playerPed, uniformData)
```

`uniformData` is a table with component/prop pairs matching your framework's clothing format:

```lua
exports.pl_lib:SetPlayerUniform(PlayerPedId(), {
    tshirt_1 = 15, tshirt_2 = 0,
    torso_1  = 55, torso_2  = 0,
    pants_1  = 24, pants_2  = 0,
    shoes_1  = 25, shoes_2  = 0,
})
```

### RevertPlayerClothing

Restore the player's saved outfit (undoes `SetPlayerUniform`).

```lua
exports.pl_lib:RevertPlayerClothing()
```

**Supported clothing systems:** esx\_skin, illenium-appearance, fivem-appearance, qb-clothing, tgiann-clothing, rcore\_clothing
