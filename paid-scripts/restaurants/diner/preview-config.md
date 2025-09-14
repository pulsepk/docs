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
--map4allrexdiner: https://fivem.map4all-shop.com/package/5995968
--mxcgreasyjoe: https://www.markz3d.com/products?product=6471456
--kiiyadiner: https://kiiya.tebex.io/package/6629013
--asrexdiner: https://as-mlo.tebex.io/package/5885870

Config.location = "asrexdiner" --'gabz', 'map4allrexdiner', 'mxcgreasyjoe', 'kiiyadiner', 'asrexdiner'   -- Location of the shop

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
    gabz = vec3(1588.713, 6455.298, 26.014),
    map4allrexdiner = vec3(2542.25, 2592.2, 38.56),
    mxcgreasyjoe = vec3(-310.57, -1470.93, 30.61),
    kiiyadiner = vec3(1041.97, 2661.41, 39.91),
    asrexdiner = vec3(2539.94, 2589.34, 38.5),
}

local blipcoords = locationBlips[Config.location]

Config.Blip = {
    BlipName = "Diner", -- Blip Name
    Enable = true,
    Coords = blipcoords,
    Options = {
        Sprite = 355,
        Color = 44,
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
Config.Jobname = 'diner' -- Job Name

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
    ice_itemname = 'diner_icecubes',
    water_itemname = 'diner_waterbottle',
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
        model='pizzaboy'
    },
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

Config.UseDJItems = false -- This is will use Custom DJ items will Props | https://djscollections.com/package/5764355

Config.CheckCanCarryItem = false

Config.Shop = {
    Storage = {
		label = "Fridge",
		items = {
            Burger = {
                { name = "diner_bun", label = "Burger Bun", price = 50, amount = 50},
                { name = "diner_beef_patty", label = "Beef Patty", price = 50, amount = 50},
                { name = "diner_sauce", label = "Diner Sauce", price = 50, amount = 50},
                { name = "diner_melted_cheddar", label = "Melted Cheddar", price = 50, amount = 50},
                { name = "diner_crispy_bacon", label = "Crispy Bacon", price = 50, amount = 50},
                { name = "diner_hot_pepper_relish", label = "Hot Pepper Relish", price = 50, amount = 50},
                { name = "diner_double_special_sauce", label = "Double Special Sauce", price = 50, amount = 50},
            },
            Sandwich = {
                { name = "diner_sandwich_bread", label = "Sandwich Bread", price = 50, amount = 50},
                { name = "diner_grilled_chicken", label = "Grilled Chicken", price = 50, amount = 50},
                { name = "diner_crispy_bacon", label = "Crispy Bacon", price = 50, amount = 50},
                { name = "diner_avocado_spread", label = "Avocado Spread", price = 50, amount = 50},
                { name = "diner_roast_beef", label = "Roast Beef", price = 50, amount = 50},
                { name = "diner_veggie_patty", label = "Veggie Patty", price = 50, amount = 50},
            },
            Fries = {
                { name = "diner_fries", label = "Fries", price = 50, amount = 50},
                { name = "diner_sea_salt", label = "Sea Salt", price = 50, amount = 50},
                { name = "diner_cheddar_sauce", label = "Cheddar Sauce", price = 50, amount = 50},
                { name = "diner_chili_cheese", label = "Chili & Cheese", price = 50, amount = 50},
                { name = "diner_seasoning", label = "Diner Seasoning", price = 50, amount = 50},
                { name = "diner_loaded_toppings", label = "Loaded Toppings", price = 50, amount = 50},
            },
            Milkshake = {
                { name = "diner_milk", label = "Milk", price = 50, amount = 50},
                { name = "diner_vanilla_extract", label = "Vanilla Extract", price = 50, amount = 50},
                { name = "diner_chocolate_syrup", label = "Chocolate Syrup", price = 50, amount = 50},
                { name = "diner_strawberry_puree", label = "Strawberry Puree", price = 50, amount = 50},
                { name = "diner_caramel_sauce", label = "Caramel Sauce", price = 50, amount = 50},
                { name = "diner_crushed_oreos", label = "Crushed Oreos", price = 50, amount = 50},
                { name = "diner_emptycup", label = "Diner Empty Cup", price = 50, amount = 50},
                { name = "diner_waterbottle", label = "Diner WaterBottle", price = 50, amount = 50},
            },
        }
	},
}

Config.Emotes = {
    Fries = {
        prop = `prop_fish_slice_01`,
        dict = 'amb@prop_human_bbq@male@idle_a',
        anim = 'idle_b',
        bone = 28422,
        offset = vec3(0.0, 0.0, 0.0),
        rotation = vec3(0.0, 0.0, 0.0)
    },
    Sandwich = {
        prop = `prop_food_bs_juice01`,
        dict = 'mp_ped_interaction',
        anim = 'handshake_guy_a',
        bone = 28422,
        offset = vec3(0.02, 0.0, -0.10),
        rotation = vec3(0.0, 0.0, -0.50)
    },
    Burger = {
        prop = `prop_fish_slice_01`,
        dict = 'amb@prop_human_bbq@male@idle_a',
        anim = 'idle_b',
        bone = 28422,
        offset = vec3(0.0, 0.0, 0.0),
        rotation = vec3(0.0, 0.0, 0.0)
    },
    Milkshake = {
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
            { name = "diner_classic_burger", label = "Classic Burger", quantity = 1 },
            { name = "diner_classic_fries", label = "Classic Fries", quantity = 1 },
            { name = "diner_vanilla_milkshake", label = "Vanilla Milkshake", quantity = 1 }, 
        },
        total = 100
    },
    {
        items = {
            { name = "diner_bacon_burger", label = "Bacon Burger", quantity = 1 },
            { name = "diner_cheesy_fries", label = "Cheesy Fries", quantity = 1 },
            { name = "diner_chocolate_milkshake", label = "Chocolate Milkshake", quantity = 1 },
        },
        total = 90
    },
    {
        items = {
            { name = "diner_spicy_burger", label = "Spicy Burger", quantity = 1 },
            { name = "diner_chili_fries", label = "Chili & Cheese", quantity = 1 },
            { name = "diner_strawberry_milkshake", label = "Strawberry Milkshake", quantity = 1 },
        },
        total = 110
    } 
}
```

</details>

