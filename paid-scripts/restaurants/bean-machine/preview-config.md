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
--slth: https://www.gta5-mods.com/maps/mlo-bean-machine-fivem-sp
--unlcejust: https://unclejust.tebex.io/package/4795902
--fm: https://fmshop.tebex.io/category/restaurant

Config.location = "gabz" --'gabz', 'slth', 'unlcejust', 'fm'   -- Location of the shop

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
    BlipName = "Bean Machine", -- Blip Name
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
Config.Jobname = 'beanmachine' -- Job Name

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
    ice_itemname = 'bm_icecubes',
    water_itemname = 'bm_waterbottle',
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

Config.UseDJItems = true -- This is will use Custom DJ items will Props | https://djscollections.com/package/5977681

Config.CheckCanCarryItem = false

Config.Shop = {
    Storage = {
		label = "Fridge",
		items = {
            Donuts = {
                { name = "bm_dough", label="Dough", price = 50, amount = 50},
                { name = "bm_cinnamon_sugar", label="Cinnamon Sugar", price = 50, amount = 50},
                { name = "bm_crushed_cookies", label="Crushed Cookies & Cream", price = 50, amount = 50},
                { name = "bm_egg_dough", label="Egg Dough", price = 50, amount = 50},
                { name = "bm_chocolate_syrup", label="Chocolate Syrup", price = 50, amount = 50},
                { name = "bm_strawberry_glaze", label="Strawberry Glaze", price = 50, amount = 50},   
            },
            Coffee = {
                { name = "bm_coffee_beans", label="Coffee Beans", price = 50, amount = 50},
                { name = "bm_hot_water", label="Hot Water", price = 50, amount = 50},
                { name = "bm_milk", label="Milk", price = 50, amount = 50},
                { name = "bm_ice_cubes", label="Ice Cubes", price = 50, amount = 50},
                { name = "bm_caramel_drizzle", label="Caramel Drizzle", price = 50, amount = 50},
                { name = "bm_chocolate_syrup", label="Chocolate Syrup", price = 50, amount = 50},
                { name = "bm_waterbottle", label = "WaterBottle", price = 50, amount = 50},
            },
            Cookies = {
                { name = "bm_cookie_dough", label="Cookie Dough", price = 50, amount = 50},
                { name = "bm_cocoa_powder", label="Cocoa Powder", price = 50, amount = 50},
                { name = "bm_raisins", label="Raisins", price = 50, amount = 50},
                { name = "bm_peanut_butter", label="Peanut Butter", price = 50, amount = 50},
                { name = "bm_white_chocolate", label="White Chocolate", price = 50, amount = 50},
                { name = "bm_chocolate_chip", label="Chocolate Chip", price = 50, amount = 50},
            },
            
            Sandwiches = {
                { name = "bm_bread", label="Bread", price = 50, amount = 50},
                { name = "bm_tuna_salad", label="Tuna Salad", price = 50, amount = 50},
                { name = "bm_pesto_sauce", label="Pesto Sauce", price = 50, amount = 50},
                { name = "bm_ham", label="Ham", price = 50, amount = 50},
                { name = "bm_cheese", label="Cheese", price = 50, amount = 50},
                { name = "bm_crispy_bacon", label="Crispy Bacon", price = 50, amount = 50},
            },
        }
	},
}

Config.Emotes = {
    Sandwiches = {
        prop = `prop_food_bs_juice01`,
        dict = 'mp_ped_interaction',
        anim = 'handshake_guy_a',
        bone = 28422,
        offset = vec3(0.02, 0.0, -0.10),
        rotation = vec3(0.0, 0.0, -0.50)
    },

    Coffee= {
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
            { name = "bm_strawberry_iced_donut", label = "Strawberry Iced Donut", quantity = 1 },
            { name = "bm_americano", label = "Americano", quantity = 1 },
            { name = "bm_double_chocolate_cookie", label = "Double Chocolate Cookie", quantity = 1 }, 
        },
        total = 200
    },
    {
        items = {
            { name = "bm_chocolate_frosted_donut", label = "Chocolate Frosted Donut", quantity = 1 },
            { name = "bm_cappuccino", label = "Cappuccino", quantity = 1 },
            { name = "bm_oatmeal_raisin_cookie", label = "Oatmeal Raisin Cookie", quantity = 1 },
        },
        total = 150
    },
    {
        items = {
            { name = "bm_cruller_donut", label = "Cruller Donut", quantity = 1 },
            { name = "bm_iced_coffee", label = "Iced Coffee", quantity = 1 },
            { name = "bm_peanut_butter_cookie", label = "Peanut Butter Cookie", quantity = 1 },
        },
        total = 135
    } 
}
```

</details>
