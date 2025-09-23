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
--slb2k11: https://yuri-customs.tebex.io/package/4826484

Config.location = "gabz" --'gabz', 'slb2k11'  -- Location of the shop

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
    gabz = vector3(-1835.59, -1190.72, 14.31),
    slb2k11 = vector3(-1835.59, -1190.72, 14.31)
}

local blipcoords = locationBlips[Config.location]

Config.Blip = {
    BlipName = "Pearls", -- Blip Name
    Enable = true,
    Coords = blipcoords,
    Options = {
        Sprite = 267,
        Color = 3,
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
Config.Jobname = 'pearls' -- Job Name

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
    ice_itemname = 'pearl_icecubes',
    water_itemname = 'pearl_waterbottle',
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
-- Package link: https://djscollections.com/package/6011288

Config.UseDJItems = true -- Set to true to enable DJ's custom items/props

Config.CheckCanCarryItem = false

Config.Shop = {
    Storage = {
		label = "Fridge",
		items = {
            Fish = {
                { name = "pearl_fillet", label="Fillet", price = 50, amount = 50},
                { name = "pearl_garlic_butter", label="Garlic Butter Special Sauce", price = 50, amount = 50},
                { name = "pearl_herb", label="Herb sauce", price = 50, amount = 50},
                { name = "pearl_parmesan_cheese", label="Parmesan cheese", price = 50, amount = 50},
                { name = "pearl_blackening_seaon", label="Blackening seasoning", price = 50, amount = 50},
                { name = "pearl_beer_batter", label="Beer batter ", price = 50, amount = 50},
                { name = "pearl_mango_salsa", label="Mango Salsa", price = 50, amount = 50},
                { name = "pearl_ginger", label="Ginger", price = 50, amount = 50},
                { name = "pearl_lime_slaw", label="Lime Slaw ", price = 50, amount = 50},
                { name = "pearl_lemon_sauce", label="Lemon Sauce", price = 50, amount = 50},
                { name = "pearl_pesto", label="Pesto", price = 50, amount = 50},   
            },
            Appetizers = {
                { name = "pearl_lemon", label="Lemon", price = 50, amount = 50},
                { name = "pearl_crostini", label="Crostini", price = 50, amount = 50},
                { name = "pearl_soy_sauce", label="Soy Sauce", price = 50, amount = 50},
                { name = "pearl_aioli", label="Aioli", price = 50, amount = 50},
                { name = "pearl_cocktail_sauce", label="Cocktail Sauce", price = 50, amount = 50},
                { name = "pearl_garlic", label="Garlic", price = 50, amount = 50},
                { name = "pearl_chilli_sauce", label="Chili Sauce", price = 50, amount = 50},
                { name = "pearl_tumeric", label="Tumeric", price = 50, amount = 50},
                { name = "pearl_wedges", label="Wedges", price = 50, amount = 50},
                { name = "pearl_poke_sauce", label="Poke sauce", price = 50, amount = 50},
            },
            Beverages = {
                { name = "pearl_lemon", label="Lemon", price = 50, amount = 50},
                { name = "pearl_ice", label="Ice", price = 50, amount = 50},
                { name = "pearl_honey", label="Honey", price = 50, amount = 50},
                { name = "pearl_citrus", label="Citrus Slices", price = 50, amount = 50},
                { name = "pearl_coconut", label="Coconut", price = 50, amount = 50},
                { name = "pearl_sugar", label="Sugar", price = 50, amount = 50},
                { name = "pearl_mint", label="Mint", price = 50, amount = 50},
                { name = "pearl_ginger", label="Ginger", price = 50, amount = 50},
                { name = "pearl_pineapple", label="Pineapple", price = 50, amount = 50},
                { name = "pearl_emptycup", label="Empty Cup", price = 50, amount = 50},
                { name = "pearl_waterbottle", label="Water Bottle", price = 50, amount = 50},
            },
            Coffee = {
                { name = "pearl_lemon", label="Lemon", price = 50, amount = 50},
                { name = "pearl_coffee_beans", label="Coffee Beans", price = 50, amount = 50},
                { name = "pearl_almond", label="Almond Milk", price = 50, amount = 50},
                { name = "pearl_dark_chocolate", label="Dark Chocolate", price = 50, amount = 50},
                { name = "pearl_vanilla_syrup", label="Vanilla Syrup", price = 50, amount = 50},
                { name = "pearl_chocolate_syrup", label="Chocolate Syrup", price = 50, amount = 50},
                { name = "pearl_whipped_cream", label="Whipped Cream", price = 50, amount = 50,},
                { name = "pearl_cinnamon_stick", label="Cinnamon Stick", price = 50, amount = 50},
                { name = "pearl_caramel_syrup", label="Caramel Syrup", price = 50, amount = 50},               
                { name = "pearl_hazelnut_syrup", label="Hazelnut Syrup", price = 50, amount = 50},
                { name = "pearl_vanilla_icecream", label="Vanilla Ice Cream", price = 50, amount = 50},
            },
        }
	},
}

Config.Emotes = {
    Fish = {
        prop = `prop_fish_slice_01`,
        dict = 'amb@prop_human_bbq@male@idle_a',
        anim = 'idle_b',
        bone = 28422,
        offset = vec3(0.0, 0.0, 0.0),
        rotation = vec3(0.0, 0.0, 0.0)
    },
    Beverages= {
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
            { name = "pearl_grill_salmon", label = "Grilled Salmon", quantity = 1 },
            { name = "pearl_lemonade", label = "Freshly Lemonade", quantity = 1 }, 
        },
        total = 200
    },
    {
        items = {
            { name = "pearl_seared_cod", label = "Seared Cod", quantity = 1 },
            { name = "pearl_iced_tea", label = "Iced Green Tea", quantity = 1 },
        },
        total = 150
    },
    {
        items = {
            { name = "pearl_tilapia", label = "Tilapia", quantity = 1 },
            { name = "pearl_lemon_mint", label = "Lemon and Mint", quantity = 1 },
        },
        total = 135
    } 
}

```

</details>

