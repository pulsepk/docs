# Config File

{% hint style="info" %}
Framework, notifications, target system, progressbar, dispatch, and society banking are all handled by [pl\_lib](../../pl_lib/README.md). Configure those in `pl_lib/config/config.lua` — not here.
{% endhint %}

```lua
Config = {}

--------------------------------------------
-- General
--------------------------------------------

Config.CheckVersion   = true   -- Check for script updates on start
Config.AutoInstallSQL = true   -- Auto-create the database table on start
Config.Logging        = true   -- Enable Discord webhook logging (set webhook in server/webhook.lua)

Config.Debug = {
    Prints      = false,  -- Print debug info to server console
    TargetZones = false,  -- Draw target zone outlines (client)
}

--------------------------------------------
-- Target & Commands
--------------------------------------------

-- Set true to disable target entirely and use commands instead
Config.DisableTarget = false

-- Only used when DisableTarget = true
Config.Commands = {
    placewheel  = 'placeWheelClamp',
    removewheel = 'removeWheelClamp',
    payfine     = 'payfineclamp',
}

--------------------------------------------
-- Database
--------------------------------------------
-- Leave both as nil to use the framework default.
-- Only set these if your database schema differs from the defaults below:
--
--   ESX    → vehicleTable = 'owned_vehicles',  ownerColumn = 'owner'
--   QBCore → vehicleTable = 'player_vehicles', ownerColumn = 'citizenid'
--   QBox   → vehicleTable = 'player_vehicles', ownerColumn = 'citizenid'

Config.Database = {
    vehicleTable = nil,
    ownerColumn  = nil,
}

--------------------------------------------
-- Items
--------------------------------------------

Config.ClampItem       = 'wheel_clamper'       -- Item required to place a clamp (police)
Config.ClampCutterItem = 'wheel_clamp_cutter'  -- Item required to cut a clamp (vehicle owner)

--------------------------------------------
-- Jobs
--------------------------------------------

-- Jobs that are allowed to place and remove clamps.
-- Add any additional police job names your server uses.
Config.PoliceJobs = {
    ['police']  = true,
    ['sheriff'] = true,
}

--------------------------------------------
-- Society / Treasury
--------------------------------------------

Config.Society = {
    enable      = false,     -- Route collected fines into a society account
    societyname = 'police',  -- Society account name (must match your banking resource)
    -- Society resource is auto-detected by pl_lib
    -- Configure via PLLib.Society in pl_lib/config/config.lua
}

--------------------------------------------
-- Dispatch
--------------------------------------------

Config.Dispatch = {
    enable = false,  -- Send a dispatch alert when a clamp is cut
    -- Dispatch resource is auto-detected by pl_lib
    -- Configure via PLLib.Dispatch in pl_lib/config/config.lua
}

--------------------------------------------
-- Animation
--------------------------------------------

Config.Animation = {
    dict     = 'anim@amb@clubhouse@tutorial@bkr_tut_ig3@',
    name     = 'machinic_loop_mechandplayer',
    flag     = 1,
    duration = 5000,  -- Progress bar duration in milliseconds
}

--------------------------------------------
-- Prop & Attachment
--------------------------------------------

Config.ClampModel = 'pl_wheelclamper_prop01'

-- Vehicle models that cannot be clamped
Config.DisallowedClampVehicles = {
    'police',
    'ambulance',
    'firetruck',
}

-- Clamp prop attachment offsets and rotation.
-- Priority order: model → class → default
--
-- offset   = { x, y, z }       x=left/right  y=forward/back  z=up/down
-- rotation = { rotX, rotY, rotZ }
--
-- GTA V vehicle class IDs:
--   0=Compacts  1=Sedans  2=SUVs  3=Coupes  4=Muscle  5=Sports Classics
--   6=Sports    7=Super   8=Motorcycles  9=Off-Road  10=Industrial
--  11=Utility  12=Vans   17=Service  18=Emergency  20=Commercial

Config.ClampAttachOffsets = {

    default = {
        offset   = { -0.0500, 0.0000, 0.0500 },
        rotation = { -2.0000, 0.0000, 89.0000 },
    },

    -- Per bone overrides — applied on top of model/class match.
    -- Bone names: 'wheel_lf' | 'wheel_rf' | 'wheel_lm1' | 'wheel_rm1' | 'wheel_lr' | 'wheel_rr'
    bones = {
        -- ['wheel_lf'] = { offset = { 0.0, 0.0, 0.0 }, rotation = { 0.0, 0.0, 0.0 } },
    },

    -- Per model overrides — takes priority over class match. Use lowercase model name.
    models = {
        -- ['adder']  = { offset = { 0.0, 0.0, 0.05 }, rotation = { 0.0, 0.0, 90.0 } },
        -- ['sultan'] = { offset = { 0.0, 0.0, 0.0  }, rotation = { 0.0, 0.0,  0.0 } },
    },

    -- Per class overrides — fallback when no model match found.
    classes = {
        -- [18] = { offset = { 0.0, 0.0, 0.0 }, rotation = { 0.0, 0.0, 90.0 } }, -- Emergency
        -- [12] = { offset = { 0.0, 0.0, 0.1 }, rotation = { 0.0, 0.0,  0.0 } }, -- Vans
    },
}
```
