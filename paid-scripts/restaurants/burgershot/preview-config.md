# ⚙️ Preview Config

The full, real `shared/config.lua` as of v3.0.0, with the in-file comments
preserved. If you're looking for what a specific setting *does* rather than
just its syntax, see the [Feature Guide](feature-guide.md).

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
-- 🔗  Recommended: https://discord.gg/c6gXmtEf3H
--==============================================--

-- Core framework and UI settings (like notification style) live in pl_lib's own config file.
-- This file only holds settings specific to the Burger Shot script itself.

Location = {}
Config = {}

Config.EventPrefix    = GetCurrentResourceName()
Config.CommandPrefix  = 'bs'   -- Short prefix used for this script's own test commands (e.g. /bstestcarry). Only change this if you're running more than one copy of this script and need the commands to have different names.

function ResourceEvent(name)
    return Config.EventPrefix .. ':' .. name
end

function ResourceId(name)
    return Config.EventPrefix .. '_' .. name
end

-- When true, the script automatically creates the database tables it needs the
-- first time it starts, so you don't have to run any SQL files by hand.
Config.AutoInstallSQL = true

Config.Locale = 'en' -- The language used for in-game text. Choose one of: 'en' (English), 'fr' (French), 'de' (German), 'es' (Spanish), 'it' (Italian), 'pt' (Portuguese), 'tr' (Turkish).
Config.Debug = {
    PolyZone = true, -- Shows red boxes around interaction areas, useful while setting up a location. Turn off once you're done configuring.
    DrawSprite = true, -- Shows white circle markers above interaction points, useful while setting up a location. Turn off once you're done configuring.
    Prints = true, -- Prints extra debug messages to the server console, useful for troubleshooting. Turn off for a live server.
}

-- This script works with several different Burger Shot interior/map packages (MLOs).
-- Below is the list of supported map packs and where to get each one, if you don't already own one:
--   gabz: https://fivem.gabzv.com/
--   molo: https://www.molo-modding.com/package/5375088
--   gn: https://gn.studio/products/burgershot
--   smalo: https://www.gta5-mods.com/maps/gtaiv-burgershot-interior-sp-and-fivem
--   uniqx: https://www.gta5-mods.com/maps/mlo-burgershot-2023-add-on-sp-fivem
--   king: https://kingmaps.net/products/6167902
--   tstudio: https://turbosaif.tebex.io/package/5956096
--   giant: https://forum.cfx.re/t/mlo-free-burger-shot/5401933

-- These are the actual resource folder names for each map pack listed above.
-- This is only used if Config.location is set to 'auto' below.
-- IMPORTANT: Check that the name here matches the actual folder/resource name
-- of the map pack you installed on your server (map creators sometimes rename
-- their resources between versions). Update any entry that doesn't match —
-- the ones you're not using can be left alone.
Config.LocationResources = {
    gabz    = 'gabz_burgershot',
    molo    = 'molo_bshot',
    gn      = 'gn_burgershot',
    smalo   = 'burgershot',
    uniqx   = 'uniqx_burgershot',
    king    = 'kingmaps_burgershot',
    tstudio = 'tstudio_burgershot',
    giant   = 'Giant_Burger',
}

-- Which map pack you're using. Set this to whichever map pack you installed:
-- 'gabz', 'molo', 'gn', 'smalo', 'uniqx', 'king', 'tstudio', or 'giant'.
-- You can also set this to 'auto' to have the script automatically detect
-- which map pack resource is currently running on your server and use that
-- one — useful if you're not sure, but setting it directly is more reliable.
Config.location = 'molo'

if Config.location == 'auto' then
    local LOCATION_PRIORITY = { 'gabz', 'molo', 'gn', 'smalo', 'uniqx', 'king', 'tstudio', 'giant' }
    local detected = nil
    for _, key in ipairs(LOCATION_PRIORITY) do
        local resourceName = Config.LocationResources[key]
        if resourceName and GetResourceState(resourceName) == 'started' then
            detected = key
            break
        end
    end
    if not detected then
        print('[pl_burgershot] WARNING: Config.location = "auto" but none of Config.LocationResources are running — falling back to "tstudio". Fill in the real resource name(s) or set Config.location directly.')
        detected = 'gabz'
    end
    Config.location = detected
end

Config.Jobname      = 'burgershot' -- The job name used in your database/framework. Must match the job you create in your job system (see Installfolder/jobs.lua).
Config.JobLabel     = 'BurgerShot' -- The display name shown to players for this job, e.g. in the job list.
Config.BossGrade    = 4    -- The minimum job grade (rank) needed to use boss/management actions - withdrawing or depositing money, hiring/firing staff, opening or closing the shop, etc.
Config.Interaction  = 'target'  -- How players interact with stations by default: 'target' (aim/use a targeting resource like ox_target), 'textui' (press a key when a prompt appears on screen), or 'text3d' (a floating 3D label in the world - see note below).
                                -- This can be overridden for individual spots in the main locations file if you want a different interaction style for a specific counter, machine, etc.

-- The 'text3d' interaction style needs the separate, optional ctn-text3d resource
-- to display the floating 3D labels. If you don't install/start it, any zones set
-- to 'text3d' simply won't show their floating label — everything else keeps working.
-- Get it here if you want to use this style: https://github.com/icetinturkey/ctn-text3d

Config.SocietyEnabled = true -- Whether this job has its own shared company/society bank account (used for boss withdraw/deposit and business profits). Keep this true for a normal restaurant job.

Config.RequireHandWash = false -- If true, employees must wash their hands before they're allowed to cook. Set to false to skip this requirement.
Config.RequireDuty     = false -- If true, employees must be clocked in (on duty) to use job actions like cooking or the register. Set to false to skip this requirement.

-- Items listed here are physically carried in the player's hand (with a matching
-- prop/animation, see Config.Carry below) instead of going straight into their
-- inventory. They're "used up" automatically when dropped off at their destination
-- (e.g. a cooked patty being carried to the assembly counter), rather than the
-- player needing to use an inventory item. You normally won't need to change this list.
Config.CarryItems = {
    bs_cooked_fries  = true,
    bs_burnt_fries   = true,
    bs_grilled_patty = true,
    bs_burnt_patty   = true,
    bs_emptycup      = true,
}

-- This section controls what a player looks like while physically carrying one
-- of the items above. See the Customization Guide for the 3 supported shapes,
-- and use /rtattach in-game to tune the offsets.
Config.Carry = {
    bs_cooked_fries = {
        PropOne = 'pl_fry_basket',
        PropTwo = 'pl_fries',
        Bone    = 28422,
        PropOneOffset = { x = 0.20, y = -1.30, z = -0.10, rx = 75.00, ry = -118.00, rz = -177.00 },
        PropTwoOffset = { x = -0.27, y = -0.75, z = 1.05, rx = -0.46, ry = 0.31, rz = 0.06 },
        Dict = 'kitchen_spatula',
        Clip = 'kitchen_spatula',
    },
    bs_burnt_fries = {
        PropOne = 'pl_fry_basket',
        PropTwo = 'pl_burnedfries',
        Bone    = 28422,
        PropOneOffset = { x = 0.20, y = -1.30, z = -0.10, rx = 75.00, ry = -118.00, rz = -177.00 },
        PropTwoOffset = { x = -0.27, y = -0.75, z = 1.05, rx = -0.46, ry = 0.31, rz = 0.06 },
        Dict = 'kitchen_spatula',
        Clip = 'kitchen_spatula',
    },
    bs_emptycup = {
        Model = 'prop_plastic_cup_02',
        Bone  = 28422,
        Offset = { x = 0.11, y = 0.05, z = -0.03, rx = -84.70, ry = 7.93, rz = 0.05 },
        Dict = 'cup_holding',
        Clip = 'cup_holding',
    },
    bs_grilled_patty = {
        PropOne = 'prop_fish_slice_01',
        PropTwo = 'pl_cookedpatty',
        Bone    = 28422,
        PropOneOffset = { x = 0.15, y = 0.00, z = -0.03, rx = -91.079, ry = 95.026, rz = -9.305 },
        PropTwoOffset = { x = 0.00, y = -0.26, z = 0.03, rx = 22.00, ry = -3.00, rz = -182.96 },
        Dict = 'kitchen_spatula',
        Clip = 'kitchen_spatula',
    },
    bs_burnt_patty = {
        PropOne = 'prop_fish_slice_01',
        PropTwo = 'pl_burnedpatty',
        Bone    = 28422,
        PropOneOffset = { x = 0.15, y = 0.00, z = -0.03, rx = -91.079, ry = 95.026, rz = -9.305 },
        PropTwoOffset = { x = 0.00, y = -0.26, z = 0.03, rx = 22.00, ry = -3.00, rz = -182.96 },
        Dict = 'kitchen_spatula',
        Clip = 'kitchen_spatula',
    },
}

Config.Logging = {
    LogEnable = true, -- Turns on logging of important actions (orders, boss actions, etc). Set to false to disable all logging.
    -- Where logs are sent. Options:
    --   'discord'    - sends logs to a Discord channel via webhook (open server/Log.lua and paste your webhook URL in there)
    --   'fivemanage' - sends logs to the Fivemanage logging service
    --   'fivemerr'   - sends logs to the Fivemerr logging service
    LogType = 'discord'
}

Config.CheckVersion = true -- If true, the script checks whether you're running the latest version and prints a notice in the console if an update is available. Safe to leave on.

-- Map coordinates for the Burger Shot blip, one for each map pack. The correct
-- one is picked automatically based on Config.location above.
local locationBlips = {
    gabz = vector3(-1188.62, -897.36, 13.8),
    molo = vector3(-821.06, -795.25, 21.16),
    gn = vector3(-1193.09, -894.76, 13.97),
    smalo = vector3(-1193.09, -894.76, 13.97),
    uniqx = vector3(-1188.62, -897.36, 13.8),
    king = vector3(-1193.74, -896.05, 13.91),
    tstudio = vector3(-1193.74, -896.05, 13.91),
}

local blipcoords = locationBlips[Config.location]

Config.Blip = {
    BlipName = Config.JobLabel,
    Enable = true,
    Coords = blipcoords,
    Options = {
        Sprite = 106,
        Color = 1,
        Scale = 0.9,
        Display = 4
    }
}

Config.MarkerSettings = {
    type = 21,
    width = 0.3,
    height = 0.3,
    color = { r = 255, g = 255, b = 255, a = 120 },
    distance = 10,
    Interact = 1,
}

Config.EnableSocietyPayment = true -- If true, money from sales goes into the job's shared company account instead of directly to the player.

Config.StashInventory = {
    StashSlot = 60,
    StashWeight = 80000,
    TableSlot = 10,
    TableWeight = 20000,
    CounterSlot = 10,
    CounterWeight = 20000,
}

Config.MaxStock = 100

Config.IngredientOrder = {
    DeliveryTime = 5, -- Seconds until an ordered ingredient delivery arrives in the fridge.
}

Config.Kitchen = {
    Enable          = true,
    DirtyAfterCooks = 10,
    CleanDuration   = 5000,
}

Config.IceMachine = {
    ice_itemname    = 'bs_icecubes',
    water_itemname  = 'bs_waterbottle',
    WaitTime        = 600,
    IceGiven        = 10
}

Config.CupPickup = {
    Item = 'bs_emptycup',
}

Config.DrinkMachine = {
    PourSound = {
        Url    = 'sounds/drinkmachine.mp3', -- Requires the optional xsound resource; no-op if not installed.
        Volume = 0.5,
    },
}

Config.Fryer = {
    CookTime   = 2,
    BurnTime   = 10,
    PropModels = {
        fries = { cooking = 'pl_fries', cooked = 'pl_fries', burnt = 'pl_burnedfries' },
    },
    Items = {
        fries = { label = 'Frozen Fries', raw = 'bs_frozen_fries', cooked = 'bs_cooked_fries', burnt = 'bs_burnt_fries' },
    },
    CraftAnim = {
        prop = 'prop_food_bs_juice01',
        dict = 'mp_ped_interaction',
        anim = 'handshake_guy_a',
    },
    SizzleSound = {
        Url    = 'sounds/fryer.mp3',
        Volume = 0.4,
    },
}

Config.DBTable    = GetCurrentResourceName()
Config.ImagesPath = GetCurrentResourceName() .. '/web/assets/items/'

Config.Tip = {
    Enable = true,
    MaxPercentage = 50,
    MaxTipAmount = 500,
    Distribution = 'employee', -- 'employee' | 'society' | 'split'
    SocietyPercent = 30,
}

Config.Receipt = {
    Enable         = true,
    Item           = 'bs_receipt',
    NearbyRadius   = 3.0,
    DisplaySeconds = 8,
    Business = {
        name    = 'BURGERSHOT',
        address = 'Los Santos, San Andreas',
        phone   = '(555) 123-4567',
    },
}

Config.Uniforms = {
    clothes = {
        male = {
            tshirt_1 = 0,  tshirt_2 = 0,
            torso_1 = 0,   torso_2 = 0,
            decals_1 = 0,   decals_2 = 0,
            arms = 0,
            pants_1 = 0,   pants_2 = 0,
            shoes_1 = 0,   shoes_2 = 0,
            helmet_1 = 0,  helmet_2 = 0,
            chain_1 = 0,    chain_2 = 0,
            ears_1 = 0,     ears_2 = 0
        },
        female = {
            tshirt_1 = 0,  tshirt_2 = 0,
            torso_1 = 0,   torso_2 = 0,
            decals_1 = 0,   decals_2 = 0,
            arms = 0,
            pants_1 = 0,   pants_2 = 0,
            shoes_1 = 0,   shoes_2 = 0,
            helmet_1 = 0,  helmet_2 = 0,
            chain_1 = 0,    chain_2 = 0,
            ears_1 = 0,     ears_2 = 0
        }
    },
}

Config.SkillCheck = {
    Enable     = true,
    Difficulty = { 'easy' },
    Keys       = { 'w', 'a', 's', 'd' },
    Lation     = {
        Title        = 'Crafting',
        Difficulties = { 'easy', 'easy', 'easy', 'easy' },
        Keys         = { 'W', 'A', 'S', 'D' }
    }
}

Config.FailItems    = { 'bs_burnt_patty', 'bs_burnt_fries' }
Config.FailItemLabels = {
    bs_burnt_patty = 'Burnt Patty',
    bs_burnt_fries = 'Burnt Fries',
}

Config.Grill = {
    CookTime  = 2,
    BurnTime  = 10,
    -- How many patties can cook at once is set per map pack in shared/location.lua, not here.
    PropModels = {
        cooking = 'pl_rawpatty',
        cooked  = 'pl_cookedpatty',
        burnt   = 'pl_burnedpatty',
    },
    SizzleSound = {
        Url    = 'sounds/grillstation.mp3',
        Volume = 0.4,
    },
}

Config.Assembly = {
    ItemProps = {
        bs_grilled_patty = { prop = 'pl_cookedpatty', coordKey = 'patty' },
        bs_bun           = { prop = 'pl_burgerbun',   coordKey = 'bun'   },
    },
    FinishedProp = 'prop_cs_burger_01',
    AssembleAnim = { dict = 'amb@prop_human_bbq@male@idle_a', clip = 'idle_b', duration = 2000 },
    ItemHints = {
        bs_grilled_patty = 'Go to the stove and cook a patty',
        bs_bun           = 'Grab a bun from the fridge',
        bs_cheese_slice  = 'Grab a cheese slice from the fridge',
    },
}

-- The staff-only supply shop (usually inside the fridge). Add a new ingredient
-- to buy by adding another line: name, label, price per unit, amount bought at once.
Config.Shop = {
    Storage = {
        label = "Fridge",
        items = {
            Burgers = {
                { name = "bs_bun",          label = "Burger Bun",   price = 50, amount = 50 },
                { name = "bs_beef_patty",   label = "Beef Patty",   price = 50, amount = 50 },
                { name = "bs_cheese_slice", label = "Cheese Slice", price = 50, amount = 50 },
            },
            Fries = {
                { name = "bs_frozen_fries", label = "Frozen Fries", price = 50, amount = 50 },
            },
            Drinks = {
                { name = "bs_emptycup",    label = "Empty Cup",    price = 50, amount = 50 },
                { name = "bs_waterbottle", label = "Water Bottle", price = 50, amount = 50 },
            },
        }
    },
}

local burgerEmote = {
    prop     = `prop_fish_slice_01`,
    dict     = 'amb@prop_human_bbq@male@idle_a',
    anim     = 'idle_b',
    bone     = 28422,
    offset   = vec3(0.0, 0.0, 0.0),
    rotation = vec3(0.0, 0.0, 0.0)
}

local drinkEmote = {
    prop     = `prop_food_bs_juice01`,
    dict     = 'mp_ped_interaction',
    anim     = 'handshake_guy_a',
    bone     = 28422,
    offset   = vec3(0.02, 0.0, -0.10),
    rotation = vec3(0.0, 0.0, -0.50)
}

Config.Emotes = {
    Burgers    = burgerEmote,
    Fries      = burgerEmote,
    Drinks     = drinkEmote,
    Milkshakes = drinkEmote,
}

Config.MaxBillAmount = 1000 -- Highest total (cash) a custom bill/invoice can charge.
Config.Commission    = 5 -- Percentage commission on custom bills, paid to the business.

Config.Consumables = {
    Enable = true,
    Groups = {
        Burgers = {
            Model  = 'prop_cs_burger_01',
            Bone   = 60309,
            Offset = { x = 0.0, y = 0.0, z = -0.02, rx = 30.0, ry = 0.0, rz = 0.0 },
            Dict   = 'mp_player_inteat@burger',
            Clip   = 'mp_player_int_eat_burger',
        },
        Fries = {
            Model  = 'prop_cs_burger_01',
            Bone   = 60309,
            Offset = { x = 0.0, y = 0.0, z = -0.02, rx = 30.0, ry = 0.0, rz = 0.0 },
            Dict   = 'mp_player_inteat@burger',
            Clip   = 'mp_player_int_eat_burger',
        },
        Drinks = {
            Model  = 'prop_food_bs_juice01',
            Bone   = 28422,
            Offset = { x = 0.02, y = 0.0, z = -0.10, rx = 0.0, ry = 0.0, rz = -0.50 },
            Dict   = 'amb@world_human_drinking@coffee@male@idle_a',
            Clip   = 'idle_c',
        },
    },
    -- A range like { 20, 35 } restores a random amount in that range; a single number restores exactly that much.
    Categories = {
        Burgers = { hunger = { 20, 35 }, thirst = 5 },
        Fries   = { hunger = { 15, 25 }, thirst = 0 },
        Drinks  = { hunger = 0,          thirst = { 15, 25 } },
    },
}
```

</details>
