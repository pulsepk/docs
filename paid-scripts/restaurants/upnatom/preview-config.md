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
    PolyZone = true, --Shows Red Boxes for Target
    DrawSprite = true, --Show White Circles above the target locations
    Prints = true, --Prints debug messages in console
}
--gabz: https://fivem.gabzv.com/

Config.location = "gabz" --'gabz'  -- Location of the shop

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
    gabz = vec3(119.69, -1036.463, 29.278),
    slth = vec3(281.29, -971.83, 29.42),
    unlcejust = vec3(-627.23, 234.89, 86.33),
    fm = vec3(119.69, -1036.463, 29.278)
}

local blipcoords = locationBlips[Config.location]

Config.Blip = {
    BlipName = "UpNAtom", -- Blip Name
    Enable = true,
    Coords = blipcoords,
    Options = {
        Sprite = 106,
        Color = 12,
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
Config.Jobname = 'upnatom' -- Job Name

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
    ice_itemname = 'ua_icecubes',
    water_itemname = 'ua_waterbottle',
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
            Burgers = {
                { name = "ua_bun", label = "Burger Bun", price = 50, amount = 50 },
                { name = "ua_bbq_sauce", label = "BBQ Sauce", price = 50, amount = 50 },
                { name = "ua_mustard_sauce", label = "Mustard Sauce", price = 50, amount = 50 },
                { name = "ua_glaze", label = "Glaze Sauce", price = 50, amount = 50 },
                { name = "ua_chili", label = "Chili Sauce", price = 50, amount = 50 },
                { name = "ua_smoked", label = "Smoked Sauce", price = 50, amount = 50 }
            },
            Fries = {
                { name = "ua_potato", label = "Potato", price = 50, amount = 50 },
                { name = "ua_butter", label = "Butter", price = 50, amount = 50 },
                { name = "ua_chili", label = "Chili Glaze", price = 50, amount = 50 },
                { name = "ua_parmesan", label = "Parmesan Drizzle", price = 50, amount = 50 },
                { name = "ua_cajun", label = "Cajun Sauce", price = 50, amount = 50 },
                { name = "ua_garlic", label = "Garlic Sauce", price = 50, amount = 50 }
            },
            Drinks = {
                { name = "ua_mint", label = "Mint Syrup", price = 50, amount = 50 },
                { name = "ua_ginger", label = "Ginger Syrup", price = 50, amount = 50 },
                { name = "ua_berry", label = "Berry Syrup", price = 50, amount = 50 },
                { name = "ua_tropical", label = "Tropical", price = 50, amount = 50 },
                { name = "ua_emptycup", label = "Empty Cup", price = 50, amount = 50 },
                { name = "ua_waterbottle", label = "Water Bottle", price = 50, amount = 50 },
            },
            Sodas = {
                { name = "ua_lemon", label = "Lemon", price = 50, amount = 50 },
                { name = "ua_lemon_syrup", label = "Lemon Syrup", price = 50, amount = 50 },
                { name = "ua_ginger", label = "Ginger", price = 50, amount = 50 },
                { name = "ua_mint", label = "Mint", price = 50, amount = 50 },
                { name = "ua_berry", label = "Berry", price = 50, amount = 50 },
                { name = "ua_pineapple", label = "Pineapple", price = 50, amount = 50 }
            },
        }
	},
}

Config.Emotes = {
    Burgers = {
        prop = `prop_fish_slice_01`,
        dict = 'amb@prop_human_bbq@male@idle_a',
        anim = 'idle_b',
        bone = 28422,
        offset = vec3(0.0, 0.0, 0.0),
        rotation = vec3(0.0, 0.0, 0.0)
    },
    Fries = {
        prop = `prop_fish_slice_01`,
        dict = 'amb@prop_human_bbq@male@idle_a',
        anim = 'idle_b',
        bone = 28422,
        offset = vec3(0.0, 0.0, 0.0),
        rotation = vec3(0.0, 0.0, 0.0)
    },
    Drinks= {
        prop = `prop_food_bs_juice01`,
        dict = 'mp_ped_interaction',
        anim = 'handshake_guy_a',
        bone = 28422,
        offset = vec3(0.02, 0.0, -0.10),
        rotation = vec3(0.0, 0.0, -0.50)
    },
    Sodas= {
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
            { name = "ua_bbq_chicken", label = "BBQ Chicken Burger", quantity = 1 },
            { name = "ua_butter_fries", label = "Butter Fries", quantity = 1 },
            { name = "ua_lemon_fizz", label = "Lemon Fizz", quantity = 1 }, 
        },
        total = 200
    },
    {
        items = {
            { name = "ua_mustard_beef", label = "Mustard Beef Burger", quantity = 1 },
            { name = "ua_spicy_glazed", label = "Spicy Glazed Fries", quantity = 1 },
            { name = "ua_ginger_soda", label = "Ginger Soda", quantity = 1 },
        },
        total = 150
    },
    {
        items = {
            { name = "ua_glazed_turkey", label = "Glazed Turkey Burger", quantity = 1 },
            { name = "ua_parmesan_fries", label = "Parmesan Fries", quantity = 1 },
            { name = "ua_mint_sparkler", label = "Mint Sparkler", quantity = 1 },
        },
        total = 135
    } 
}

```

</details>

