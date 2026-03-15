# Config File

<details>

<summary>Config File</summary>

```lua
--==============================================--
-- 💬  JOIN OUR DISCORD COMMUNITY
--
-- 🔧  Script Support
-- 🛠️   Devlogs & Sneak Peeks
-- 🔔  Updates & Announcements
--
-- 🔗  https://discord.gg/c6gXmtEf3H
--==============================================--

Config = {}

--------------------------------------------
-- General
--------------------------------------------

Config.CheckVersion    = true
Config.AutoInstallSQL  = true   -- Enable auto SQL install on resource start
Config.Logging         = true

Config.Debug = {
    Prints      = false,
    TargetZones = false,
}

--------------------------------------------
-- Framework & UI Bridges
--------------------------------------------

Config.Framework   = 'autodetect'  -- 'autodetect' | 'esx' | 'qb' | 'qbox'

Config.ContextMenu = 'ox_lib'      -- 'ox_lib' | 'lation_ui'
Config.InputDialog = 'ox_lib'      -- 'ox_lib' | 'lation_ui'
Config.AlertDialog = 'ox_lib'      -- 'ox_lib' | 'lation_ui'
Config.Progressbar = 'ox_lib'      -- 'ox_lib' | 'ox_lib_circle' | 'qb' | 'lation_ui'
Config.Notify      = 'ox_lib'      -- 'ox_lib' | 'esx_notify' | 'okokNotify' | 'lation_ui' | 'wasabi_notify' | 'brutal_notify' | 'mythic_notify'

--------------------------------------------
-- Target & Commands
--------------------------------------------

Config.Target        = 'autodetect' -- 'autodetect' | 'ox_target' | 'qb-target'
Config.DisableTarget = false        -- Set true to use commands instead of target

-- Only used when DisableTarget = true
Config.Commands = {
    placewheel  = 'placeWheelClamp',
    removewheel = 'removeWheelClamp',
    payfine     = 'payfineclamp',
}

--------------------------------------------
-- Database
--------------------------------------------
-- Defaults per framework (nil = use the framework default below).
-- Only set these if your schema differs from the defaults.
--
-- ESX    : vehicleTable = 'owned_vehicles'   ownerColumn = 'owner'
-- QBCore : vehicleTable = 'player_vehicles'  ownerColumn = 'citizenid'
-- QBox   : vehicleTable = 'player_vehicles'  ownerColumn = 'citizenid'

Config.Database = {
    vehicleTable = nil,  -- nil = framework default | override: 'owned_vehicles', 'player_vehicles', etc.
    ownerColumn  = nil,  -- nil = framework default | override: 'owner', 'citizenid', etc.
}

--------------------------------------------
-- Items
--------------------------------------------

Config.ClampItem       = 'wheel_clamper'
Config.ClampCutterItem = 'wheel_clamp_cutter'

--------------------------------------------
-- Jobs
--------------------------------------------

Config.PoliceJobs = {
    ['police']  = true,
    ['sheriff'] = true,
    -- Add more police job names as needed
}

--------------------------------------------
-- Society / Treasury
--------------------------------------------

Config.Society = {
    enable       = false,
    societyname  = 'police',        -- Must match the society name in your framework
    resourcename = 'addon_account', -- 'addon_account' | 'qb-management' | 'qb-banking'
}

--------------------------------------------
-- Dispatch
--------------------------------------------
-- 'qb'         QBCore default dispatch  (Free, built-in)
-- 'ps'         ps-dispatch              (Free:  https://github.com/Project-Sloth/ps-dispatch)
-- 'aty'        aty_dispatch             (Free:  https://github.com/atiysuu/aty_dispatch)
-- 'rcore'      rcore dispatch           (Paid:  https://store.rcore.cz/)
-- 'cd_dispatch' cd_dispatch             (Paid:  https://codesign.pro/product/4206357)
-- 'op'         op-dispatch              (Free:  https://github.com/ErrorMauw/op-dispatch)
-- 'custom'     your own implementation

Config.Dispatch = {
    enable = false,
    script = 'ps', -- see options above
}

--------------------------------------------
-- Animation
--------------------------------------------

Config.Animation = {
    dict     = 'anim@amb@clubhouse@tutorial@bkr_tut_ig3@',
    name     = 'machinic_loop_mechandplayer',
    flag     = 1,
    duration = 5000, -- milliseconds
}

--------------------------------------------
-- Prop & Attachment
--------------------------------------------

Config.ClampModel = 'pl_wheelclamper_prop01'

-- Vehicles that cannot be clamped
Config.DisallowedClampVehicles = {
    'police',    -- Police cars
    'ambulance', -- Ambulance
    'firetruck', -- Firetruck
}

-- Attachment offsets and rotation for the clamp prop.
-- Priority order: model → class → default
--
-- offset   = { x,    y,    z   }  x=right/left  y=forward/back  z=up/down
-- rotation = { rotX, rotY, rotZ } rotX=pitch  rotY=roll  rotZ=yaw
--
-- GTA V vehicle class IDs:
--   0=Compacts  1=Sedans    2=SUVs      3=Coupes    4=Muscle    5=Sports Classics
--   6=Sports    7=Super     8=Motorcycles  9=Off-Road  10=Industrial
--  11=Utility  12=Vans     17=Service  18=Emergency  20=Commercial

Config.ClampAttachOffsets = {

    default = {
        offset   = { -0.0500, 0.0000, 0.0500 },
        rotation = { -2.0000, 0.0000, 89.0000 },
    },

    -- Per bone overrides (applied on top of model/class match).
    -- Bone names: 'wheel_lf' | 'wheel_rf' | 'wheel_lm1' | 'wheel_rm1' | 'wheel_lr' | 'wheel_rr'
    bones = {
        -- ['wheel_lf'] = { offset = { 0.0, 0.0, 0.0 }, rotation = { 0.0, 0.0, 0.0 } },
    },

    -- Per model overrides (lowercase model name, takes priority over class).
    models = {
        -- ['adder']  = { offset = { 0.0, 0.0, 0.05 }, rotation = { 0.0, 0.0, 90.0 } },
        -- ['sultan'] = { offset = { 0.0, 0.0, 0.0  }, rotation = { 0.0, 0.0,  0.0 } },
    },

    -- Per class overrides (GTA V class ID).
    classes = {
        -- [18] = { offset = { 0.0, 0.0, 0.0 }, rotation = { 0.0, 0.0, 90.0 } }, -- Emergency
        -- [12] = { offset = { 0.0, 0.0, 0.1 }, rotation = { 0.0, 0.0,  0.0 } }, -- Vans
    },
}

--------------------------------------------
-- Helpers
--------------------------------------------

function Config.DebugPrint(message)
    if Config.Debug.Prints then
        print('[pl_wheelclamper] ' .. message)
    end
end

```

</details>

