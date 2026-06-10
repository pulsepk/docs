# Config File

All configuration is in `shared/config.lua`.

***

```lua
Config = {}

-- Check for script updates on resource start
Config.CheckVersion = true

-- Minimap
-- false = minimap only visible while in a vehicle
-- true  = minimap always visible on foot and in vehicles
Config.AlwaysShowMinimap = false

-- Minimap shape: 'square' or 'circle'
Config.Maptype = 'square'

-- Seatbelt mechanic
-- SeatbeltEnabled      = false disables the mechanic entirely
-- SeatbeltNotification = false silences the toggle notification
Config.SeatbeltEnabled      = true
Config.SeatbeltNotification = true

-- Key to cycle vehicle lights: OFF → LOW → HIGH
-- 74 = H key  (FiveM control index)
Config.LightToggleKey = 74

-- Key to toggle seatbelt
-- 29 = B key  (FiveM control index)
Config.SeatbeltToggleKey = 29

-- Speed unit shown on the speedometer: 'mph' or 'kmh'
Config.SpeedUnit = 'mph'

-- Fuel reading function
-- Override this if you use a custom fuel resource.
-- Default uses the native GTA fuel level.
GetVehFuel = function(veh)
    return GetVehicleFuelLevel(veh)
end
```

***

## Custom Fuel Override

If your server uses a fuel script, replace `GetVehFuel` with the correct export:

| Resource | Override |
|---|---|
| LegacyFuel | `exports['LegacyFuel']:GetFuel(veh)` |
| ox\_fuel | `exports['ox_fuel']:GetFuel(veh)` |
| ps-fuel | `exports['ps-fuel']:GetFuel(veh)` |
| cdn-fuel | `exports['cdn-fuel']:GetFuel(veh)` |

Example:
```lua
GetVehFuel = function(veh)
    return exports['LegacyFuel']:GetFuel(veh)
end
```

***

## Key Code Reference

Key values are **FiveM control indices**, not keyboard scan codes. Common ones:

| Key | Control Index |
|---|---|
| B | 29 |
| H | 74 |
| G | 47 |
| Z | 20 |
| X | 73 |

Full list: [docs.fivem.net/docs/game-references/controls](https://docs.fivem.net/docs/game-references/controls/)
