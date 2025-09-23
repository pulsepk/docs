# Preview Config

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

Location = {}
Config = {}

Config.Framework = 'autodetect' -- 'autodetect' or "esx" ,"qb", "qbox"

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
-- Enable auto SQL install on resource start
Config.AutoInstallSQL = true

Config.Locale = 'en' -- 'en', 'fr', 'de', 'es', 'it', 'pt', 'tr' -- Language
Config.Debug = {
    PolyZone = false, --Shows Red Boxes for Target
    DrawSprite = true, --Show White Circles above the target locations
    Prints = true, --Prints debug messages in console
}
--pablito: https://www.gta5-mods.com/maps/taco-restaurant-mlo-add-on-fivem-pablitomamutopaputo
--crux: https://crux.tebex.io/package/6239572
--rfc: https://store.rfcmapping.com/package/6268899

Config.location = "pablito" --'pablito', 'crux', 'rfc'   -- Location of the shop

Config.TextUI = 'autodetect' --'autodetect' or 'ox_lib', 'qb-core', 'jg-textui', 'lation_ui', 'esx_textui', 'cd_drawtextui', 'brutal_textui'
Config.BossMenu = 'autodetect' --'autodetect' or 'esx_society', 'qb-management', 'qbx_management', 'vms_bossmenu'
Config.Target = 'autodetect' --'autodetect' or 'ox_target', 'qb-target'
Config.Notify = 'autodetect' --'autodetect' or 'ox_lib', 'esx_notify', 'okokNotify','lation_ui', 'wasabi_notify', 'brutal_notify', 'mythic_notify'
Config.Progressbar = 'ox_lib' -- 'qb', 'ox_lib', 'ox_lib_circle', 'lation_ui'
Config.InputDialog = 'ox_lib' -- 'ox_lib', 'lation_ui'
Config.BillingMenu = 'builtin' --'builtin' or 'autodetect' or 'esx_billing','s1n_billing','okokBilling', 'codem-billing','qb-phone'
Config.ContextMenu = 'ox_lib' -- 'ox_lib', 'lation_ui'
Config.Clothing = 'autodetect' --'autodetect' or 'esx_skin', 'illenium-appearance', 'fivem-appearance', 'qb-clothing', 'tgiann-clothing'
Config.Society = {
    enable  = true,
    resourcename = 'autodetect', --'autodetect' or 'esx_addonaccount', 'qb-management', 'qb-banking', 'okokBanking', 'Renewed-Banking'
}

Config.Logging = {
    LogEnable = true, -- It will send logs.
    --'discord' for discord webhook. Edit the Log.lua file to add the webook
    --'fivemanage'
    --'fivemerr'
    LogType = 'discord'
}

Config.CheckVersion = true

local locationBlips = {
    pablito = vector3(7.51, -1606.1, 29.37),
    crux = vector3(7.51, -1606.1, 29.37),
    rfc = vector3(7.51, -1606.1, 29.37)
}

local blipcoords = locationBlips[Config.location]

Config.Blip = {
    BlipName = "Taco Shop", -- Blip Name
    Enable = true,
    Coords = blipcoords,
    Options = {
        Sprite = 79,
        Color = 5,
        Scale = 0.8,
        Display = 4
    }
}
-- If you want to change the white marker that appears on item processing edit this
Config.MarkerSettings = {
    type = 21, -- Marker type
    width = 0.3, -- Marker width
    height = 0.3, -- Marker height
    color = { r = 255, g = 255, b = 255, a = 120 }, -- Marker color
    distance = 10, -- Distance to show the marker
    Interact = 1, -- Distance to interact with the marker

}

Config.EnableSocietyPayment = false -- If enable you can pay from society for the fridge items
Config.Jobname = 'taco' -- Job Name

Config.StashInventory = {
    --Stash
    StashSlot = 60,
    StashWeight = 80000,
    --Table
    TableSlot = 10,
    TableWeight = 20000,
    --Counter
    CounterSlot = 10,
    CounterWeight = 20000,
    --TrashCan
    TrashCanSlot = 10,
    TrashCanWeight = 20000,
}

Config.MaxStock = 100

Config.IceMachine = {
    ice_itemname = 'taco_icecubes',
    water_itemname = 'taco_waterbottle',
    WaitTime = 560,
    MaxIce = 10
}

Config.MaxBillAmount = 1000
Config.Commission = 5 -- Commission percentage for bill payments
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

Config.Delivery = {
    Enable = true,
    FuelEnable = true, -- Enable or disable fuel consumption
    Ped = {
        model='s_m_m_trucker_01'
    },
    VehicleSpawn = {
        model='burrito'
    },
    Payout = 'money', --'money' for cash |'bank' for bank | 'society' for society
    OrderDelay = 60, -- Time in seconds between orders
    MaxOrders = 2, -- Maximum number of active orders
}

Config.SkillCheck = {
    Use = 'ox_lib', -- 'ox_lib' or 'lation_ui'
    Enable = true,
    Difficulty = { 'easy' }, -- For ox_lib: single difficulty or array
    Keys = { 'w', 'a', 's', 'd' }, -- For ox_lib
    Lation = { -- For lation_ui
        Title = 'Crafting',
        Difficulties = { 'easy', 'easy', 'easy', 'easy' },
        Keys = { 'W', 'A', 'S', 'D' }
    }
}

Config.CheckCanCarryItem = false

Config.Shop = {
    Storage = {
		label = "Fridge",
		items = {
            Taco = {
                { name = "taco_grilled_skirt", label="Grilled Skirt", price = 50, amount = 50},
                { name = "taco_tortillas", label="taco_tortillas", price = 50, amount = 50},
                { name = "taco_marinated_pork", label="Marinated Pork", price = 50, amount = 50},
                { name = "taco_tilapia", label="taco_tilapia", price = 50, amount = 50},
                { name = "taco_pork_shoulder", label="Pork Shoulder", price = 50, amount = 50},
                { name = "taco_cooked_beef", label="Cooked Beef", price = 50, amount = 50},
                { name = "taco_shredded_chicken", label="Chicken Cooked", price = 50, amount = 50},
                { name = "taco_mexican_sausage", label="Chorizo Sausage", price = 50, amount = 50},
                { name = "taco_sauteed_vegetables", label="Sauteed Vegetables", price = 50, amount = 50},
                { name = "taco_sauteed_shrimp", label="Sauteed Shrimp", price = 50, amount = 50},
                { name = "taco_stewed_beef", label="Stewed Beef", price = 50, amount = 50},
                },
            Burrito = {
                { name = "taco_ground_beef", label="GroundBeef", price = 50, amount = 50},
                { name = "taco_cooked_quinoa", label="Cooked Quinoa", price = 50, amount = 50},
                { name = "taco_breakfast_sausage", label="Breakfast Sausage", price = 50, amount = 50},
                { name = "taco_grilled_steak", label="Grilled Steak", price = 50, amount = 50},
                { name = "taco_refried_beans", label="Refired Beans", price = 50, amount = 50},
                { name = "taco_bbq_chicken", label="Shredded BBQ Chicken", price = 50, amount = 50},
                },
            Nachos = {
                { name = "taco_jalapenos", label="Jalapenos", price = 50, amount = 50},
                { name = "taco_grilled_chicken", label="Grilled Chicken", price = 50, amount = 50},
                { name = "taco_pulled_pork", label="Pulled Pork", price = 50, amount = 50},
                { name = "taco_tortilla_chips", label="Tortilla Chips", price = 50, amount = 50},
                { name = "taco_black_beans", label="Black Beans", price = 50, amount = 50},
                { name = "taco_shrimp", label="Taco Shrimp", price = 50, amount = 50},
                },
            Drinks = {
                {name = "taco_waterbottle",label="Water Bottle", price = 50, amount = 50},
                {name = "taco_emptycup",label="Empty Cup", price = 50, amount = 50},
            },
        }
	},
}

Config.Emotes = {
    Drinks= {
        prop = `prop_food_bs_juice01`,
        dict = 'mp_ped_interaction',
        anim = 'handshake_guy_a',
        bone = 28422,
        offset = vec3(0.02, 0.0, -0.10),
        rotation = vec3(0.0, 0.0, -0.50)
    }
}

Config.DeliveryFood = {
    {
        items = {
            { name = "taco_carne", label = "Carne Asada Tacos", quantity = 1 },
            { name = "taco_lemonlush_soda", label = "Taco Jurritos", quantity = 1 }, 
        },
        total = 200
    },
    {
        items = {
            { name = "taco_al_pastor", label = "Al Pastor Tacos", quantity = 1 },
            { name = "taco_chillwave_cola", label = "Taco Chillwave Cola", quantity = 1 },
        },
        total = 150
    },
    {
        items = {
            { name = "taco_fish", label = "Fish Tacos", quantity = 1 },
            { name = "taco_fizzberry_splash", label = "Taco Fizzberry Splash", quantity = 1 },
        },
        total = 135
    } 
}

```

</details>

