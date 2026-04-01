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
    gabz = vector3(1242.684, -360.787, 69.082)
}

local blipcoords = locationBlips[Config.location]

Config.Blip = {
    BlipName = "Horny Burgers", -- Blip Name
    Enable = true,
    Coords = blipcoords,
    Options = {
        Sprite = 80,
        Color = 2,
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
Config.Jobname = 'hornyburgers' -- Job Name

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
    ice_itemname = 'hb_icecubes',
    water_itemname = 'hb_waterbottle',
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
                { name = "hb_bun", label = "Burger Bun", price = 50, amount = 50},
                { name = "hb_sauce", label = "Horny Sauce", price = 50, amount = 50},
                { name = "hb_jalapeno_relish", label = "Jalapeno Relish", price = 50, amount = 50},
                { name = "hb_melted_cheddar", label = "Melted Cheddar", price = 50, amount = 50},
                { name = "hb_crispy_bacon", label = "Crispy Bacon", price = 50, amount = 50},
                { name = "hb_bbq_sauce", label = "Special BBQ Sauce", price = 50, amount = 50},
            },
            
            Drinks = {
                { name = "hb_chocolate_syrup", label = "Chocolate Syrup", price = 50, amount = 50},
                { name = "hb_caramel_drizzle", label = "Caramel Drizzle", price = 50, amount = 50},
                { name = "hb_honey", label = "Honey", price = 50, amount = 50},
                { name = "hb_citrus_blend", label = "Citrus Blend", price = 50, amount = 50},
                { name = "hb_milk", label = "Milk", price = 50, amount = 50},
                { name = "hb_coffee", label = "Coffee", price = 50, amount = 50},
                { name = "hb_mixed_berries", label = "Mixed Berries", price = 50, amount = 50},
                { name = "hb_caffeine_base", label = "Caffeine Base", price = 50, amount = 50},
                { name = "hb_emptycup", label = "Emtpy Cup", price = 50, amount = 50},
                { name = "hb_waterbottle", label = "Water Bottle", price = 50, amount = 50},
            },
            
            Fries = {
                { name = "hb_potato_fries", label = "Potato Fries", price = 50, amount = 50},
                { name = "hb_sea_salt", label = "Sea Salt", price = 50, amount = 50},
                { name = "hb_melted_cheese", label = "Melted Cheese", price = 50, amount = 50},
                { name = "hb_sriracha", label = "Sriracha", price = 50, amount = 50},
                { name = "hb_crispy_bacon", label = "Crispy Bacon", price = 50, amount = 50},
                { name = "hb_sour_cream_chives", label = "Sour Cream & Chives", price = 50, amount = 50},
            },
            
            Sodas = {
                { name = "hb_carbonated_water", label = "Carbonated Water", price = 50, amount = 50},
                { name = "hb_cola_flavor", label = "Cola Flavoring", price = 50, amount = 50},
                { name = "hb_root_beer_extract", label = "Root Beer Extract", price = 50, amount = 50},
                { name = "hb_orange_syrup", label = "Orange Syrup", price = 50, amount = 50},
                { name = "hb_grape_syrup", label = "Grape Syrup", price = 50, amount = 50},
                { name = "hb_fresh_lemon", label = "Fresh Lemon", price = 50, amount = 50},
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
            { name = "hb_classic_burger", label = "Classic Burger", quantity = 1 },
            { name = "hb_classic_fries", label = "Classic Fries", quantity = 1 }, 
            { name = "hb_lemonlime", label = "Lemon Lime", quantity = 1 },
        },
        total = 200
    },
    {
        items = {
            { name = "hb_spicy_burger", label = "Spicy Burger", quantity = 1 },
            { name = "hb_cheesy_fries", label = "Cheesy Fries", quantity = 1 },
            { name = "hb_orange_soda", label = "Orange Soda", quantity = 1 },
        },
        total = 150
    },
    {
        items = {
            { name = "hb_cheesy_burger", label = "Cheesy Burger", quantity = 1 },
            { name = "hb_spicy_fries", label = "Spicy Fries", quantity = 1 },
            { name = "hb_cola", label = "Cola", quantity = 1 },
        },
        total = 135
    } 
}

```

</details>

