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
--greenbergs: https://greencome-mapping.tebex.io/package/6266966

Config.location = "greenbergs" --'greenbergs'  -- Location of the shop

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
    greenbergs = vector3(-1230.703, -1039.518, 8.283)
}

local blipcoords = locationBlips[Config.location]

Config.Blip = {
    BlipName = "Bubble Cafe", -- Blip Name
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
Config.Jobname = 'bubblegum' -- Job Name

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
    ice_itemname = 'bg_icecubes',
    water_itemname = 'bg_waterbottle',
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
            Pizzas = {
                { name = "bg_dough", label="Pizza Dough", price = 50, amount = 50},
                { name = "bg_basil_leaves", label="Basil Leaves", price = 50, amount = 50},
                { name = "bg_marinara_sauce", label="Marinara Sauce", price = 50, amount = 50},
                { name = "bg_bbq_sauce", label="Smoky BBQ Sauce", price = 50, amount = 50},
                { name = "bg_black_olives", label="Black Olives", price = 50, amount = 50},
                { name = "bg_pineapple_chunks", label="Pineapple Chunks ", price = 50, amount = 50},
            },
            Salads = {
                { name = "bg_vinegar", label="Vinegar", price = 50, amount = 50},
                { name = "bg_parmesan", label="Parmesan Shavings", price = 50, amount = 50},
                { name = "bg_kalamata_olives", label="Kalamata Olives", price = 50, amount = 50},
                { name = "bg_balsamic_glaze", label="Balsamic Glaze", price = 50, amount = 50},
                { name = "bg_garlic_croutons", label="Garlic Croutons", price = 50, amount = 50},
                { name = "bg_avocado_slice", label="Avocado Slices", price = 50, amount = 50},
            },
            Deserts = {
                { name = "bg_butter", label="Butter", price = 50, amount = 50},
                { name = "bg_chocolate_cream", label="Chocolate Cream filling", price = 50, amount = 50},
                { name = "bg_apple_filling", label="Apple filling", price = 50, amount = 50},
                { name = "bg_cinnamon_sugar", label="Cinnamon Sugar", price = 50, amount = 50},
                { name = "bg_pastry_cream", label="Pastry Cream", price = 50, amount = 50},
            },
            Drinks = {
                { name = "bg_emptycup", label="Empty Cup", price = 50, amount = 50},
                { name = "bg_waterbottle", label="Water Bottle", price = 50, amount = 50},
                { name = "bg_butter", label="Butter", price = 50, amount = 50},
                { name = "bg_caramel_syrup", label="Caramel syrup", price = 50, amount = 50},
                { name = "bg_chocolate_syrup", label="Chocolate Syrup", price = 50, amount = 50},
                { name = "bg_coffee_beans", label="Coffee Beans", price = 50, amount = 50},
                { name = "bg_matcha_powder", label="Matcha Powder", price = 50, amount = 50},
                { name = "bg_vanilla_syrup", label="Vanilla Syrup", price = 50, amount = 50},
            }            
        },
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
            { name = "bg_margherita", label = "Classic Margherita", quantity = 1 },
            { name = "bg_iced_caramel_latte", label = "Iced Caramel Latte", quantity = 1 }, 
        },
        total = 200
    },
    {
        items = {
            { name = "bg_pepperoni", label = "Pepperoni Feast", quantity = 1 },
            { name = "bg_mocha_frappe", label = "Mocha Frappe", quantity = 1 },
        },
        total = 150
    },
    {
        items = {
            { name = "bg_bbq_chicken", label = "BBQ Chicken", quantity = 1 },
            { name = "bg_cold_brew_coffee", label = "Cold Brew Coffee", quantity = 1 },
        },
        total = 135
    } 
}

```

</details>
