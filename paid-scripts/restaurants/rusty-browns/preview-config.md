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
--e_49: https://forum.cfx.re/t/free-mlo-rusty-browns-donuts-cafe/4912809
--map4all_legion: https://fivem.map4all-shop.com/package/5139828
--map4all_vinewood: https://fivem.map4all-shop.com/package/5139828
--map4all_mirrorpark: https://fivem.map4all-shop.com/package/5139828

Config.location = "map4all_legion" --'e_49', 'map4all_legion', 'map4all_vinewood', 'map4all_mirrorpark'  -- Location of the shop

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
    e_49 = vector3(358.63, -1012.4, 29.34),
    map4all_legion = vector3(358.63, -1012.4, 29.34),
    map4all_vinewood = vec3(154.92, 251.0, 106.05),
    map4all_mirrorpark = vec3(1215.81, -451.24, 65.88)
}

local blipcoords = locationBlips[Config.location]

Config.Blip = {
    BlipName = "Rusty Browns", -- Blip Name
    Enable = true,
    Coords = blipcoords,
    Options = {
        Sprite = 739,
        Color = 1,
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
Config.Jobname = 'rustybrowns' -- Job Name

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
    ice_itemname = 'rs_icecubes',
    water_itemname = 'rs_waterbottle',
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

-- 💡 Use creator code 'PULSE' at checkout to get a 10% discount!
-- Enable DJ's custom food props/items from DJS Collection
-- Package link: https://djscollections.com/package/5681293

Config.UseDJItems = false -- Set to true to enable DJ's custom items/props

Config.CheckCanCarryItem = false

Config.Shop = {
    Storage = {
		label = "Fridge",
		items = {
            Donuts = {
                { name = "rs_flour", label="Rusty's Donut Base", price = 50, amount = 50},
                { name = "rs_berries", label="Rusty's Berries", price = 50, amount = 50},
                { name = "rs_chocolate_cream", label="Rusty's Chocolate cream filling", price = 50, amount = 50},
                { name = "rs_chocolate_glaze", label="Rusty's Chocolate glaze", price = 50, amount = 50},
                { name = "rs_sprinkling_chocolate", label="Rusty's Sprinkling Chocolate", price = 50, amount = 50},
                { name = "rs_cinnamon_sugar", label="Rusty's Cinnamon and Sugar Coating", price = 50, amount = 50},
                { name = "rs_choco_cookies", label="Rusty's Chocolate Cookies", price = 50, amount = 50},
                { name = "rs_sugar_glaze", label="Rusty's Sugar glaze", price = 50, amount = 50},
                { name = "rs_lemon", label="Rusty's Lemon", price = 50, amount = 50},
                { name = "rs_maple_glaze", label="Rusty's Maple glaze", price = 50, amount = 50},
                { name = "rs_strawberry", label="Rusty's Strawberry", price = 50, amount = 50},
            },
            IcedDrinks = {
                { name = "rs_ice", label="Rusty's Ice", price = 50, amount = 50},
                { name = "rs_caramel_syrup", label="Rusty's Caramel syrup", price = 50, amount = 50},
                { name = "rs_chocolate_syrup", label="Rusty's Chocolate Syrup", price = 50, amount = 50},
                { name = "rs_coffee_beans", label="Rusty's Coffee Beans", price = 50, amount = 50},
                { name = "rs_matcha_powder", label="Rusty's Matcha Powder", price = 50, amount = 50},
                { name = "rs_vanilla_syrup", label="Rusty's Vanilla Syrup", price = 50, amount = 50},
                { name = "rs_strawberry", label="Rusty's Strawberry", price = 50, amount = 50},
                { name = "rs_chai_tea", label="Rusty's Tea Concentrate", price = 50, amount = 50},
                { name = "rs_espresso", label="Rusty's Espresso", price = 50, amount = 50},
                { name = "rs_coconut_milk", label="Rusty's Coconut Milk", price = 50, amount = 50},
                { name = "rs_mint_icecream", label="Rusty's Mint Icecream", price = 50, amount = 50},
                { name = "rs_emptycup", label="Rusty's Empty Cup", price = 50, amount = 50},
                
            },
            Pastries = {
                { name = "rs_butter", label="Rusty's Butter", price = 50, amount = 50},
                { name = "rs_chocolate_cream", label="Rusty's Chocolate Cream filling", price = 50, amount = 50},
                { name = "rs_apple_filling", label="Rusty's Apple filling", price = 50, amount = 50},
                { name = "rs_cinnamon_sugar", label="Rusty's Cinnamon Sugar", price = 50, amount = 50},
                { name = "rs_pastry_cream", label="Rusty's Pastry Cream", price = 50, amount = 50},
                { name = "rs_cream_cheese", label="Rusty's Cream Cheese", price = 50, amount = 50},
                { name = "rs_chocolate_sticks", label="Rusty's Chocolate Sticks", price = 50, amount = 50},
                { name = "rs_whipped_cream", label="Rusty's Whipped Cream", price = 50, amount = 50},
                { name = "rs_brownbutter_cinnamon", label="Rusty's BrownButter Cinnamon", price = 50, amount = 50},
                { name = "rs_sugar_glaze", label="Rusty's Sugar Glaze", price = 50, amount = 50},
            },
        }
	},
}

Config.Emotes = {
    IcedDrinks= {
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
            { name = "berry_glazed_donut", label = "Berry Glazed Donut", quantity = 1 },
            { name = "iced_caramel_latte", label = "Iced Caramel Latte", quantity = 1 }, 
        },
        total = 200
    },
    {
        items = {
            { name = "chococream_donut", label = "Choco Cream Filled Donut", quantity = 1 },
            { name = "mocha_frappe", label = "Mocha Frappe", quantity = 1 },
        },
        total = 150
    },
    {
        items = {
            { name = "chocfrosted_donut", label = "Chocolate Frosted Donut", quantity = 1 },
            { name = "cold_brew_coffee", label = "Cold Brew Coffee", quantity = 1 },
        },
        total = 135
    } 
}

```

</details>

