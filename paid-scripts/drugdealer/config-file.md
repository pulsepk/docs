# Config File



```lua
Config = {}

Config.Framework = "esx" -- "esx" ,"qb", "qbox"

Config.FrameworkResources = {
    esx = {
        resource = 'es_extended',
        export = 'getSharedObject'
    },
    qb = {
        resource = 'qb-core',
        export = 'GetCoreObject'
    }
}

Config.CheckVersion = true

Config.Locale = 'en' -- 'en', 'fr', 'de', 'es', 'it' -- Language

Config.Notify = 'ox' --esx, qb, ox, okok, wasabi_notify, custom

Config.EnableSuccessSales = true --If enabled it will set the Drug Sale rate

Config.SalesRate = 90 --The percentage drug will be successfully sale

Config.Radius = 20.0 --This is the radius the peds will be spawned around you

Config.Reward = {
    BlackMoneyEnable = true, --Use BlackMoney for ESX, QBCore: https://github.com/MH-Scripts/mh-cashasitem, QBox
    MarkedBillsEnable = false, --Use only For QBCore and make sure to set BlackMoneyEnable to false
}

Config.SkillCheck = {
    -- uses ox_lib skillgame, add your own in DoSkillCheck in clientopen.lua function
    Enable = true, -- Enable or disable skill check
    Difficulty = { 'easy'}, -- Difficulty steps
    Keys = { 'w', 'a', 's', 'd' } -- Keys to use in skill check
}

Config.LevelSystem = {
    Enabled = true,
    MaxLevel = 100,
}


Config.Police={

    Job = {'police'},

    Required = true, --This will check if the police are online 

    MinimumPolice = 0, --This is the amount of police required to start drug sales

    PoliceNotify = true, --If enabled police will be notified

    PoliceCallChance = 90 --90% chance police will be alerted
}

--default qb
--ps for ps-dispatch
--aty for aty_disptach
--qs for qausar dispatch
--rcore for rcore dispatch
--custom for your own

Config.Dispatch = 'default'

Config.Props = {
    cashprop = 'hei_prop_heist_cash_pile',
    drugprop = 'prop_weed_bottle'
}

Config.Control = {
    Key = 38, --E key
}

Config.Animation = {
    Enable = true,
    Dict = 'mp_common',
    Anim = 'givetake1_a'
}

Config.StartCommand = 'start-selling'
Config.StopCommand = 'stop-selling'
Config.CheckLevelCommand = 'checklevel'


Config.Logging = {

    LogEnable = true, -- It will send logs.

    --'discord' for discord webhook. Edit the Log.lua file to add the webook
    --'fivemanage'
    --'fivemerr'
    
    LogType = 'discord'

}
Config.maxSpawnedPeds = 7 --Maximum Spawn Peds at a Time

Config.LevelPriceMultiplier = {
    { min = 0, max = 10, multiplier = 1.0 },
    { min = 11, max = 20, multiplier = 1.2 },
    { min = 21, max = 40, multiplier = 1.5 },
    { min = 41, max = 60, multiplier = 2.0 },
    { min = 61, max = 80, multiplier = 2.5 },
    { min = 81, max = 100, multiplier = 3.0 },
}

Config.Drugslist = {
    ["meth"] = {
        quantity = {min = 1, max = 3},
        price = {min = 600, max = 1200},
        levelIncrease = 0.5,
    },
    ["weed_skunk"] = {
        quantity = {min = 1, max = 3},
        price = {min = 600, max = 1200},
        levelIncrease = 0.5,
    },
}


Config.SellingZonesEnable = false
Config.SellingZones = {
    
    Grove = {
        levelrequired = 0,
        location = vector3(102.35, -1941.25, 20.8),
        areaRadius = 50,
        BlipInfo = {
            label = "Grove Street Zone",
            Sprite = 310,
            Color = 47,
            Scale = 0.7,
            Display = 4
        }
    },
}

Config.Ped = {
    "g_m_y_ballaeast_01",
    "g_m_y_famca_01",
    "g_m_y_mexgoon_02",
    "g_f_y_ballas_01",
}
```
