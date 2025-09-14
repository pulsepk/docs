# Preview Config

<details>

<summary>Click to Check Config File</summary>

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
--mxcvinewood: https://www.markz3d.com/products?product=6487522
--mxclegion: https://www.markz3d.com/products?product=6487522
--mxcdelperrobeach: https://www.markz3d.com/products?product=6487522

Config.location = "gabz" --'gabz', 'mxcvinewood', 'mxclegion', 'mxcdelperrobeach'  -- Location of the shop

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
    gabz = vec3(808.22, -750.5, 26.78),
    mxcvinewood = vec3(544.2, 106.16, 96.55),
    mxclegion = vec3(294.0386, -967.8315, 29.4352),
    mxcdelperrobeach = vec3(-1524.93, -907.56, 10.18)
}

local blipcoords = locationBlips[Config.location]

Config.Blip = {
    BlipName = "Pizza This", -- Blip Name
    Enable = true,
    Coords = blipcoords,
    Options = {
        Sprite = 267,
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
Config.Jobname = 'pizzathis' -- Job Name

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
    ice_itemname = 'pt_icecubes',
    water_itemname = 'pt_waterbottle',
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

Config.UseDJItems = false -- This is will use Custom DJ items will Props | https://djscollections.com/package/5669923

Config.CheckCanCarryItem = false

Config.Shop = {
    Storage = {
		label = "Fridge",
		items = {
            Pizzas = {
                { name="pt_dough", label= "Pizza Base", price =50, amount = 50},
                { name = "pt_basil_leaves", label="Basil Leaves", price = 50, amount = 50},
                { name = "pt_marinara_sauce", label="Spicy Marinara Sauce", price = 50, amount = 50},
                { name = "pt_bbq_sauce", label="Smoky BBQ Sauce", price = 50, amount = 50},
                { name = "pt_black_olives", label="Black Olives", price = 50, amount = 50},
                { name = "pt_pineapple_chunks", label="Pineapple Chunks ", price = 50, amount = 50},
                { name = "pt_bacon_crumbles", label="Bacon Crumbles", price = 50, amount = 50},
                { name = "pt_gorgonzola_cheese", label="Gorgonzola Cheese", price = 50, amount = 50},
                { name = "pt_italian_suasage", label="Italian Sausage", price = 50, amount = 50},
                { name = "pt_ranch_sauce", label="Ranch Sauce", price = 50, amount = 50},
                { name = "pt_garlic_alfredo_sauce", label="Garlic Alfredo Sauce", price = 50, amount = 50},   
            },
            Appetizers = {
                {name = "pt_olive_oil",label="Olive Oil", price = 50, amount = 50},
                { name = "pt_garlic_butter", label="Garlic Butter", price = 50, amount = 50},
                { name = "pt_crispy_bread", label="Crispy Bread", price = 50, amount = 50},
                { name = "pt_mozzarella", label="Melted Mozzarella", price = 50, amount = 50},
                { name = "pt_buffalo_sauce", label="Buffalo Sauce", price = 50, amount = 50},
                { name = "pt_basil", label="Fresh Basil", price = 50, amount = 50},
                { name = "pt_cream_cheese", label="Cream Cheese", price = 50, amount = 50},
                { name = "pt_lemon_aioli", label="Lemon Aioli", price = 50, amount = 50},
                { name = "pt_artichokes", label="Artichokes", price = 50, amount = 50},
            },
            Salads = {
                {name = "pt_vinegar",label="Vinegar", price = 50, amount = 50},
                { name = "pt_parmesan", label="Parmesan Shavings", price = 50, amount = 50},
                { name = "pt_kalamata_olives", label="Kalamata Olives", price = 50, amount = 50},
                { name = "pt_balsamic_glaze", label="Balsamic Glaze", price = 50, amount = 50},
                { name = "pt_garlic_croutons", label="Garlic Croutons", price = 50, amount = 50},
                { name = "pt_avocado_slice", label="Avocado Slices", price = 50, amount = 50},
                { name = "pt_crispy_bacon", label="Crispy Bacon", price = 50, amount = 50},
                { name = "pt_quinoa", label="Quinoa", price = 50, amount = 50},
                { name = "pt_marinated_artichokes", label="Marinated Artichokes", price = 50, amount = 50},
            },
            Pastas = {
                { name = 'pt_garlic',label="Garlic", price = 50, amount = 50},
                { name = "pt_parmesan_cream_sauce", label="Parmesan Cheese", price = 50, amount = 50},
                { name = "pt_beef", label="Beef", price = 50, amount = 50},
                { name = "pt_penne_pasta", label="Penne Pasta", price = 50, amount = 50},
                { name = "pt_basil_pesto_sauce", label="Basil Pesto Sauce", price = 50, amount = 50},
                { name = "pt_mozzarella_cream_sauce", label="Mozzarella-Infused Cream ", price = 50, amount = 50},
                { name = "pt_bechamel_sauce", label="Bechamel Sauce", price = 50, amount = 50},
                { name = "pt_garlic_butter", label="Garlic-Butter ", price = 50, amount = 50},
                { name = "pt_lemon_zest", label="Lemon Zest", price = 50, amount = 50},
            },
            Beverages = {
                {name = 'pt_carbonated_water',label="Carbonated Water", price = 5, amount = 50},
                {name = 'pt_waterbottle',label="Water Bottle", price = 5, amount = 50},
                {name = 'pt_emptycup',label="Empty Cup", price = 5, amount = 50},
            },
        }
	},
}

Config.Emotes = {
    Beverages = {
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
            { name = "pt_margherita", label = "Classic Margherita Pizza", quantity = 1 },
            { name = "pt_garlic_knots", label = "Garlic Knots", quantity = 1 },
            { name = "pt_citraspark", label = "Citra Spark", quantity = 1 }, 
        },
        total = 100
    },
    {
        items = {
            { name = "pt_chicken", label = "Meat Lovers' Special", quantity = 1 },
            { name = "pt_spaghetti", label = "Spaghetti Bolognese", quantity = 1 },
            { name = "pt_berrywhirl", label = "Berry Whirl", quantity = 1 },
        },
        total = 90
    },
    {
        items = {
            { name = "pt_hawaiian", label = "Hawaiian Paradise", quantity = 1 },
            { name = "pt_chicken_pesto", label = "Chicken Pesto Pasta", quantity = 1 },
            { name = "pt_crimson_ridge", label = "Crimson Ridge", quantity = 1 },
        },
        total = 110
    } 
}
```

</details>
