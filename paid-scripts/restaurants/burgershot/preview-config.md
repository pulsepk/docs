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

Config.Locale = 'en' -- 'en', 'fr', 'de', 'es', 'it', 'pt', 'tr' -- Language
Config.Debug = {
    PolyZone = true, --Shows Red Boxes for Target
    DrawSprite = true, --Show White Circles above the target locations
    Prints = true, --Prints debug messages in console
}
--gabz: https://fivem.gabzv.com/
--molo: https://www.molo-modding.com/package/5375088
--gn: https://gn.studio/products/burgershot
--smalo: https://www.gta5-mods.com/maps/gtaiv-burgershot-interior-sp-and-fivem
--uniqx: https://www.gta5-mods.com/maps/mlo-burgershot-2023-add-on-sp-fivem
--king: https://kingmaps.net/products/6167902
--tstudio: https://turbosaif.tebex.io/package/5956096

Config.location = "tstudio" --'gabz', 'molo', 'gn', 'smalo', 'uniqx', 'king', 'tstudio' -- Location of the shop

Config.TextUI = 'autodetect' --'autodetect' or 'ox_lib', 'qb-core', 'jg-textui', 'esx_textui', 'cd_drawtextui', 'brutal_textui'
Config.BossMenu = 'autodetect' --'autodetect' or 'esx_society', 'qb-management', 'qbx_management', 'vms_bossmenu'
Config.Target = 'autodetect' --'autodetect' or 'ox_target', 'qb-target'
Config.Notify = 'autodetect' --'autodetect' or 'ox_lib', 'esx_notify', 'okokNotify', 'wasabi_notify', 'brutal_notify', 'mythic_notify'
Config.Progressbar = 'ox_lib' -- 'qb', 'ox_lib', 'ox_lib_circle'
Config.BillingMenu = 'autodetect' --'autodetect' or 'esx_billing','s1n_billing','okokBilling', 'codem-billing','qb-phone'
Config.Clothing = 'autodetect' --'autodetect' or 'esx_skin', 'illenium-appearance', 'fivem-appearance', 'qb-clothing', 'tgiann-clothing'
Config.Society = {
    enable  = true,
    resourcename = 'autodetect', --'autodetect' or 'addon_account', 'qb-management', 'qb-banking', 'okokBanking', 'Renewed-Banking'
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
    BlipName = "BurgerShot", -- Blip Name
    Enable = true,
    Coords = blipcoords,
    Options = {
        Sprite = 106,
        Color = 1,
        Scale = 0.9,
        Display = 4
    }
}
-- If you want to change the white marker that appears on item processing edit this
Config.MarkerSettings = {
    type = 21, -- Marker type
    width = 0.3, -- Marker width
    height = 0.3, -- Marker height
    color = { r = 255, g = 255, b = 255, a = 120 } -- Marker color
}

Config.EnableSocietyPayment = false -- If enable you can pay from society for the fridge items
Config.Jobname = 'burgershot' -- Job Name

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
    ice_itemname = 'bs_icecubes',
    water_itemname = 'bs_waterbottle',
    WaitTime = 560,
    MaxIce = 10
}

Config.MaxBillAmount = 1000
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
        model='nspeedo'
    },
    OrderDelay = 60, -- Time in seconds between orders
    MaxOrders = 2, -- Maximum number of active orders
}

Config.SkillCheck = {
    -- uses ox_lib skillgame, add your own in DoSkillCheck in clientopen.lua function
    Enable = true, -- Enable or disable skill check
    Difficulty = { 'easy'}, -- Difficulty steps
    Keys = { 'w', 'a', 's', 'd' } -- Keys to use in skill check
}

Config.UseDJItems = false -- This is will use Custom DJ items will Props | https://djscollections.com/package/6098332

Config.CheckCanCarryItem = false

Config.Shop = {
    Storage = {
		label = "Fridge",
		items = {
            Burgers = {
                { name= "bs_piece", label= "Piece", price =50, amount = 50},
                { name = "bs_bun", label="Burger Bun", price = 50, amount = 50},
                { name = "bs_jalapeno", label="Jalapeno", price = 50, amount = 50},
                { name = "bs_pepperoni", label="Pepperoni", price = 50, amount = 50},
                { name = "bs_cheese_slice", label="Cheese Slice", price = 50, amount = 50},
                { name = "bs_beef_patty", label="Beef patty", price = 50, amount = 50},
                { name = "bs_mushroom", label="Mushroom", price = 50, amount = 50},
                { name = "bs_fish_fillet", label="Fish Fillet", price = 50, amount = 50},
                { name = "bs_bbq_sauce", label="BBQ Sauce", price = 50, amount = 50},
                { name = "bs_onion", label="Onion", price = 50, amount = 50}, 
            },
            Fries = {
                {name = "bs_potato",label="Potato", price = 50, amount = 50},
                { name = "bs_parmesan_cheese", label="Parmesan Cheese", price = 50, amount = 50},
                { name = "bs_cajun_seasoning", label="Cajun Seasoning", price = 50, amount = 50},
                { name = "bs_truffle_oil", label="Truffle Oil", price = 50, amount = 50},
                { name = "bs_tortilla", label="Tortilla", price = 50, amount = 50},
                { name = "bs_tomato", label="Tomato", price = 50, amount = 50},
                { name = "bs_piece", label="Piece", price = 50, amount = 50},
                { name = "bs_chicken", label="Chicken", price = 50, amount = 50},
                { name = "bs_honey", label="Honey", price = 50, amount = 50},
                { name = "bs_buffalo_sauce", label="Buffalo Sauce", price = 50, amount = 50},
                { name = "bs_rice", label="Rice", price = 50, amount = 50},          
            },
            Drinks = {
                {name = "bs_emptycup",label="Empty Cup", price = 50, amount = 50},
                {name = "bs_waterbottle",label="Water Bottle", price = 50, amount = 50},
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
    Drinks = {
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
            { name = "bs_fries", label = "Fries", quantity = 1 },
            { name = "bs_zinger_burger", label = "Zinger Burger", quantity = 1 },
            { name = "bs_chillwave_cola", label = "Chillwave Cola", quantity = 1 }, 
        },
        total = 100
    },
    {
        items = {
            { name = "bs_kentucky_burger", label = "Kentucky Burger", quantity = 1 },
            { name = "bs_classic_salted_fries", label = "Classic Salted Fries", quantity = 1 },
            { name = "bs_fizzberry_splash", label = "Fizzberry Splash", quantity = 1 },
        },
        total = 90
    },
    {
        items = {
            { name = "bs_zinger_stacker", label = "Zinger Stacker", quantity = 1 },
            { name = "bs_spicy_cajun_fries", label = "Spicy Cajun Fries", quantity = 1 },
            { name = "bs_lemonlush_soda", label = "Lemonlush Soda", quantity = 1 },
        },
        total = 110
    } 
}

```

</details>

