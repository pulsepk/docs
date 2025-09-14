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
    gabz = vector3(-1035.28, -1483.06, 4.58)
}

local blipcoords = locationBlips[Config.location]

Config.Blip = {
    BlipName = "Koi", -- Blip Name
    Enable = true,
    Coords = blipcoords,
    Options = {
        Sprite = 197,
        Color = 73,
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
Config.Jobname = 'koi' -- Job Name

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
    ice_itemname = 'koi_icecubes',
    water_itemname = 'koi_waterbottle',
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
        model='rumpo'
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

Config.UseDJItems = true -- This is will use Custom DJ items will Props | https://djscollections.com/package/5764357

Config.CheckCanCarryItem = false

Config.Shop = {
    Storage = {
		label = "Fridge",
		items = {
            Seafoods = {
                { name="koi_grilled_salmon", label= "Dill Butter", price =50, amount = 50},
                { name = "koi_lobster_tail", label="Clarified Butter", price = 50, amount = 50},
                { name = "koi_shrimp_scampi", label="White Wine", price = 50, amount = 50},
                { name = "koi_seared_scallops", label="Truffle Oil", price = 50, amount = 50},
                { name = "koi_crab_cakes", label="Old Bay Seasoning", price = 50, amount = 50},
            },
            Drinks = {
                { name = "koi_mojito",label="Fresh Mint Leaves", price = 50, amount = 50},
                { name = "koi_pina_colada", label="Coconut Cream", price = 50, amount = 50},
                { name = "koi_margarita", label="Triple Sec", price = 50, amount = 50},
                { name = "koi_espresso_martini", label="Coffee Liquor", price = 50, amount = 50},
                { name = "koi_arnold_palmer", label="Fresh Lamonade", price = 50, amount = 50},
                { name = "koi_emptycup", label="Koi Empty Cup", price = 50, amount = 50},
            },
            Steaks = {
                { name = 'koi_ribeye_steak',label="Herb Butter", price = 50, amount = 50},
                { name = "koi_filet_mignon", label=" Béarnaise Sauce", price = 50, amount = 50},
                { name = "koi_t_bone_steak", label="Steakhouse Dry Rub", price = 50, amount = 50},
                { name = "koi_tomahawk_steak", label="Smoked Sea Salt", price = 50, amount = 50},
                { name = "koi_new_york_strip", label="Red Wine Reduction", price = 50, amount = 50},

            },
            Desserts = {
                { name = "koi_tiramisu", label = "Mascarpone Cheese", price = 50, amount = 50 },
                { name = "koi_cheesecake", label = "Graham Cracker Crust", price = 50, amount = 50 },
                { name = "koi_chocolate_lava_cake", label = "Molten Ganache Filling", price = 50, amount = 50 },
                { name = "koi_creme_brulee", label = "Caramelized Sugar Topping", price = 50, amount = 50 },
                { name = "koi_key_lime_pie", label = "Key Lime Juice", price = 50, amount = 50 }
            },
        }
	},
}

Config.Emotes = {
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
            { name = "koi_grilled_salmon", label = "Koi Grilled Salmon", quantity = 1 },
            { name = "koi_mojito", label = "Koi Mojito", quantity = 1 },
            { name = "koi_tomahawk_steak", label = "Koi Tomahawk Steak", quantity = 1 }, 
        },
        total = 100
    },
    {
        items = {
            { name = "koi_shrimp_scampi", label = "Koi Shrimp Scampi", quantity = 1 },
            { name = "koi_pina_colada", label = "Koi Pina Colada", quantity = 1 },
            { name = "koi_ribeye_steak", label = "Koi Ribeye Steak", quantity = 1 },
        },
        total = 90
    },
    {
        items = {
            { name = "koi_seared_scallops", label = "Koi Seared Scallops", quantity = 1 },
            { name = "koi_margarita", label = "Koi Margarita", quantity = 1 },
            { name = "koi_filet_mignon", label = "Koi Filet Mignon", quantity = 1 },
        },
        total = 110
    } 
}
```

</details>
