# Config File



```lua
Config = {}

Config.CheckVersion = true

-- Framework Configuration
-- Options: 'esx', 'qbcore', 'qbox'
Config.Framework = 'esx'

-- Target Configuration
-- Options: 'qb-target', 'ox_target', false
Config.Target = 'ox_target'

-- Only Works when Target is set to false
Config.Commands = {
    placewheel = "placeWheelClamp",
    removewheel = "removeWheelClamp"
}

-- Item name that will be used for the wheel clamper
Config.ClampItem = 'wheel_clamper'
Config.ClampCutterItem = 'wheel_clamp_cutter'

-- Police job names
Config.PoliceJobs = {
    ['police'] = true,
    ['sheriff'] = true,
    -- Add more police job names as needed
}

Config.offsets = {
    default = {
        all = vector4(-0.005, 0.30, 0.0, -90.0)
    },
    baseRotation = vector3(109.168, -270.995, -89.715),
}

--qbcore for qbcore default
--ps-dispatch for ps-dispatch
--aty_disptach for aty_disptach
--custom for your own

Config.Dispatch= {
    enable = false,
    script = 'ps-dispatch'
}

-- Animation settings
Config.Animation = {
    dict = 'anim@amb@clubhouse@tutorial@bkr_tut_ig3@',
    name = 'machinic_loop_mechandplayer',
    flag = 1,
    duration = 5000, -- milliseconds
}

-- Wheel clamp object model
Config.ClampModel = 'pl_wheelclamper'

Config.DisallowedClampVehicles = {
    "police",      -- Police cars
    "ambulance",   -- Ambulance
    "firetruk",    -- Firetruck
    "rhino",       -- Tank
    "bmx",         -- Bicycle
    "buzzard",     -- Helicopter
}

-- Text for notifications
Config.Text = {
    noVehicleNearby = 'No vehicle nearby',
    notPolice = 'You are not authorized to use this item',
    placingClamp = 'Placing wheel clamp...',
    clampPlaced = 'Wheel clamp placed successfully',
    removingClamp = 'Removing wheel clamp...',
    attachingClamp = 'Attaching wheel clamp...',
    clampRemoved = 'Wheel clamp removed successfully',
    alreadyClamped = 'Vehicle is already clamped',
    cannotClamp = 'Cannot clamp this vehicle',
    insideVehicle = 'You cannot use this while inside a vehicle',
    notallowedtoclamp = 'This vehicle is not allowed to be clamped.',
    gotolefttyre = 'Go to the left front tire to place the clamp.',
    noclampnearby = 'No clamp nearby to remove.',
    notclosetotyre = 'Not Close to the tyre',
    vehicleclampcutting = 'Someone is cutting the wheel clamp...',
    pleasewait = 'You cant place the clamp right now. Please wait.'
}

Config.Debug = false

function Config.DebugPrint(message)
    if Config.Debug then
        print('[pl_wheelclamper] ' .. message)
    end
end
```
