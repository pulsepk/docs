# Preview Config

```etlua
lib.locale()
Config = {}
Config.Debug = {
    PolyZone = false, --Shows Red Boxes for Target
    DrawSprite = true --Show White Circles above the target locations
}
Config.LogEnable = true --edit the webhook in Server/Log.lua
Config.CheckVersion = true
Config.Blip = {
    BlipName = "Taco Shop", --Blip Name
    Enable = true,
    Coords = vector3(7.51, -1606.1, 29.37),
    Options = {
        Sprite = 79,
        Color = 5,
        Scale = 0.8,
        Display = 4
    }
}
-- If you want to change the red marker that appears on item processing edit this
Config.MarkerSettings = {
    type = 2, -- Marker type
    width = 0.2, -- Marker width
    height = 0.3, -- Marker height
    color = { r = 255, g = 0, b = 0, a = 100 } -- Marker color
}
Config.TextUI = 'ox_lib' --'ox_lib', 'qb-core', 'jg-textui', 'esx_textui', 'cd_drawtextui'
Config.Society = {
    enable  = true,
    society_script = "qb-banking", --esx_society, qb-management,qb-banking
}
Config.Target = "qb-target" --ox-target, qb-target
Config.Notify = 'ox' --ox, esx, okok,qb,wasabi,custom
Config.ShopMode = 'automatic' -- 'self' , 'automatic'
--for ox inventory ox_inventory/web/images/
--for qausar inventory qs-inventory/html/images/
--for qb-inventory qb-inventory/html/images/
--for ps-inventory ps-inventory/html/images/
--for codem inventory codem-inventory/html/images/
--for ak47 inventory ak47_inventory/web/build/images/
Config.Invimages = 'qb-inventory/html/images/' -- Image path for your inventory
Config.Jobname = 'taco' -- Job Name
Config.Progressbar = 'ox_lib' -- qb, ox_lib, ox_lib_circle
--This is remove the green zone markers and enable target
Config.RemoveMarkers = true

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
}

Config.BillingMenu = 'qb-phone' -- 'esx_billing','qb-phone','s1n_billing','okokBilling'
Config.MaxBillAmount = 1000
Config.Clothing = 'qb-clothing' --esx_skin,illenium-appearance,fivem-appearance,qb-clothing
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
Config.CheckCanCarryItem = false -- Only for ESX
Config.Shop = {
    Clothing = {
        Coords = vector3(20.08, -1601.67, 29.38),
    },
    management = vec3(8.15, -1606.25, 29.37), --Where you can manage your shop
    fridge = vec3(17.04, -1599.6, 29.38), -- From where you will buy ingrediants
    process = vec3(14.75, -1601.1, 29.38), --From where you will start making items
    shop = { --Shop buy menu
        vector3(11.15, -1605.64, 29.39),
    },
    storagestash = vec3(12.64, -1600.39, 29.38),
    bossmenu = vec3(8.22, -1602.65, 29.371),
    Storage = {
		label = "Fridge",
		items = {
            Taco = {
                { name = "taco_grilled_skirt", label="Grilled Skirt", price = 50, amount = 50},
                { name = "taco_tortillas", label="taco_tortillas", price = 50, amount = 50},
                { name = "taco_marinated_pork", label="Marinated Pork", price = 50, amount = 50},
                { name = "taco_tilapia", label="taco_tilapia", price = 50, amount = 50},
                { name = "taco_pork_shoulder", label="Pork Shoulder", price = 50, amount = 50},
                { name = "taco_cooked_beef", label="Cooked Beef", price = 50, amount = 50},
                { name = "taco_shredded_chicken", label="Chicken Cooked", price = 50, amount = 50},
                { name = "taco_mexican_sausage", label="Chorizo Sausage", price = 50, amount = 50},
                { name = "taco_sauteed_vegetables", label="Sauteed Vegetables", price = 50, amount = 50},
                { name = "taco_sauteed_shrimp", label="Sauteed Shrimp", price = 50, amount = 50},
                { name = "taco_stewed_beef", label="Stewed Beef", price = 50, amount = 50},
                },
            Burrito = {
                { name = "taco_ground_beef", label="GroundBeef", price = 50, amount = 50},
                { name = "taco_cooked_quinoa", label="Cooked Quinoa", price = 50, amount = 50},
                { name = "taco_breakfast_sausage", label="Breakfast Sausage", price = 50, amount = 50},
                { name = "taco_grilled_steak", label="Grilled Steak", price = 50, amount = 50},
                { name = "taco_refried_beans", label="Refired Beans", price = 50, amount = 50},
                { name = "taco_bbq_chicken", label="Shredded BBQ Chicken", price = 50, amount = 50},
                },
            Nachos = {
                { name = "taco_jalapenos", label="Jalapenos", price = 50, amount = 50},
                { name = "taco_grilled_chicken", label="Grilled Chicken", price = 50, amount = 50},
                { name = "taco_pulled_pork", label="Pulled Pork", price = 50, amount = 50},
                { name = "taco_tortilla_chips", label="Tortilla Chips", price = 50, amount = 50},
                { name = "taco_black_beans", label="Black Beans", price = 50, amount = 50},
                { name = "taco_shrimp", label="Taco Shrimp", price = 50, amount = 50},
                },
            Drinks = {
                {name = "taco_emptycup",label="Empty Cup", price = 50, amount = 50},
            },
            }
        },
        ItemOrder = {
            "Taco",
            "Burrito",
            "Nachos",
            "Drinks",
        },
        categories = {
            
            Taco = { 
                label = "Taco", --Donot Change
                icon = "fa-solid fa-utensils",
                workingcoords = vector3(11.47, -1599.12, 29.38),
                
                items = {
                    taco_carne = {
                        label="Carne Asada Tacos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_grilled_skirt', label="Grilled Skirt", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_al_pastor = {
                        label="Al Pastor Tacos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_marinated_pork', label="Marinated Pork", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_fish = {
                        label="Fish Tacos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_tilapia', label="taco_tilapia", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_carnitas = {
                        label="Carnitas Tacos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_pork_shoulder', label="Pork Shoulder",quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_barbacoa = {
                        label="Barbacoa Tacos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_cooked_beef',label="Cooked Beef", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_chicken = {
                        label="Chicken Tacos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_shredded_chicken',label="Chicken Cooked", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_chorizo = {
                        label="Chorizo Tacos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_mexican_sausage',label="Spicy Mexican Chorizo Sausage", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_vegetarian = {
                        label="Vegetarian Tacos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_sauteed_vegetables',label="Sauteed Vegetables", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_shrimp = {
                        label="Shrimp Tacos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_sauteed_shrimp',label="Shrimp Tacos", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_birria = {
                        label="Birria Tacos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_stewed_beef',label="Stewed Beef", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                }
            },
            Burrito = { 
                label = "Burrito", --Donot Change
                icon = "fa-solid fa-cheese",
                workingcoords = vector3(11.47, -1599.12, 29.38),
                items = {
                    taco_beef_burrito = {
                        label="Classic Beef Burrito",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_ground_beef',label="Ground Beef", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_chicken_burrito = {
                        label="Chicken Burrito",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_shredded_chicken',label="Chicken Cooked", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_vegetarian_burrito = {
                        label="Vegetarian Burrito",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_cooked_quinoa',label="Vegetarian Burrito", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_breakfast_burrito = {
                        label="Breakfast Burrito",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_breakfast_sausage',label="Breakfast Burrito", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_carnitas_burrito = {
                        label="Carnitas Burrito",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_pork_shoulder', label="Pork Shoulder",quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_fish_burrito = {
                        label="Fish Burrito",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_tilapia', label="taco_tilapia", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_steak_burrito = {
                        label="Steak Burrito",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_grilled_steak',label="Steak Burrito", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_shrimp_burrito = {
                        label="Shrimp Burrito",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_sauteed_shrimp',label="Shrimp Burrito", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_cheese_burrito = {
                        label="Bean and Cheese Burrito",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_refried_beans',label="Bean and Cheese Burrito", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                    taco_bbqchicken_burrito = {
                        label="Bbq Chicken Burrito",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_bbq_chicken',label="Bbq Chicken Burrito", quantity = 1},
                        {item = 'taco_tortillas', label="taco_tortillas", quantity = 1},
                        },
                    },
                }
            },
    
            Nachos = { 
                label = "Nachos", --Donot Change
                icon = "fa-solid fa-cookie",
                workingcoords = vector3(11.47, -1599.12, 29.38),
                items = {
                    taco_classic_nachos = {
                        label="Classic Nachos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_jalapenos',label="Jalapenos", quantity = 1},
                        {item = 'taco_tortilla_chips',label="Tortilla Chips", quantity = 1},
                        },
                    },
                    taco_beef_nachos = {
                        label="Loaded Beef Nachos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_ground_beef',label="Ground Beef", quantity = 1},
                        {item = 'taco_tortilla_chips',label="Tortilla Chips", quantity = 1},
                        },
                    },
                    taco_chicken_nachos = {
                        label="Chicken Nachos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_grilled_chicken',label="Grilled Chicken", quantity = 1},
                        {item = 'taco_tortilla_chips',label="Tortilla Chips", quantity = 1},
                        },
                    },
                    taco_pork_nachos = {
                        label="Pulled Pork Nachos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_pulled_pork',label="Pulled Pork", quantity = 1},
                        {item = 'taco_tortilla_chips',label="Tortilla Chips", quantity = 1},
                        },
                    },
                    taco_vegetarian_nachos = {
                        label="Vegetarian Nachos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_black_beans',label="Black Beans", quantity = 1},
                        {item = 'taco_tortilla_chips',label="Tortilla Chips", quantity = 1},
                        },
                    },
                    taco_seafood_nachos = {
                        label="Seafood Nachos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_shrimp',label="Shrimp", quantity = 1},
                        {item = 'taco_tortilla_chips',label="Tortilla Chips", quantity = 1},
                        },
                    },
                    taco_breakfast_nachos = {
                        label="Breakfast Nachos",
                        price = 50, --For Starting Price
                        reward = 1, --item reward on completing
                        duration = 10000,
                        required = {  -- required items for crafting
                        {item = 'taco_scrambled_eggs',label="Scrambled Eggs", quantity = 1},
                        {item = 'taco_tortilla_chips',label="Tortilla Chips", quantity = 1},
                        },
                    },
                }
            },
            Drinks = {
                label = "Drinks", -- Do not change
                icon = "fa-solid fa-mug-saucer",
                workingcoords = vector3(13.794, -1596.336, 29.378),
                items = {
                    taco_jurritos = {
                        label = "Taco Jurritos", 
                        price = 50, -- For starting price
                        reward = 1, -- Item reward on completing
                        duration = 10000,
                        required = { -- Required items for crafting
                        { item = 'taco_emptycup',label="BurgerShot Empty Cup", quantity = 1 },
                        },
                    },
                    taco_chillwave_cola = {
                        label = "Taco Chillwave Cola",  
                        price = 50, -- For starting price
                        reward = 1, -- Item reward on completing
                        duration = 10000,
                        required = { -- Required items for crafting
                        { item = 'taco_emptycup',label="BurgerShot Empty Cup", quantity = 1 },
                        },
                    },
                    taco_fizzberry_splash = {
                        label = "Taco Fizzberry Splash",  
                        price = 50, -- For starting price
                        reward = 1, -- Item reward on completing
                        duration = 10000,
                        required = { -- Required items for crafting
                        { item = 'taco_emptycup',label="BurgerShot Empty Cup", quantity = 1 },
                        },
                    },
                    taco_lemonlush_soda = {
                        label = "Taco Lemonlush Soda", 
                        price = 50, -- For starting price
                        reward = 1, -- Item reward on completing
                        duration = 10000,
                        required = { -- Required items for crafting
                        { item = 'taco_emptycup',label="BurgerShot Empty Cup", quantity = 1 },
                        },
                    },
                    taco_zesty_zing = {
                        label = "Taco Zesty Zing", 
                        price = 50, -- For starting price
                        reward = 1, -- Item reward on completing
                        duration = 10000,
                        required = { -- Required items for crafting
                        { item = 'taco_emptycup',label="BurgerShot Empty Cup", quantity = 1 },
                        },
                    },
                },
            },
        },
    }
Config.Chairs = {
    --TableSeating
	--Table 1
    { coords = vector4(13.25, -1607.3, 29.4,144.44), stand = vector3(12.51, -1606.55, 29.4), w = 0.20, h = 0.80,},
	{ coords = vector4(12.51, -1608.01, 29.4, 320.55), stand = vector3(11.9, -1607.52, 29.4), w = 0.20, h = 0.80,},
    
	--Table 2
	{ coords = vector4(11.77, -1608.82, 29.4,144.44), stand = vector3(11.22, -1608.35, 29.4), w = 0.20, h = 0.80,},
	{ coords = vector4(11.22, -1609.73, 29.4, 320.55), stand = vector3(10.48, -1609.11, 29.4), w = 0.20, h = 0.80,},
   
	--Table 3
	{ coords = vector4(14.91, -1608.69, 29.4,144.44), stand = vector3(14.24, -1608.16, 29.41), w = 0.20, h = 0.80,},
	{ coords = vector4(14.21, -1609.45, 29.4, 320.55), stand = vector3(13.58, -1608.96, 29.41), w = 0.20, h = 0.80,},
   
	--Table 4
	{ coords = vector4(13.47, -1610.25, 29.4,144.44), stand = vector3(12.88, -1609.79, 29.41), w = 0.20, h = 0.80,},
	{ coords = vector4(12.87, -1611.04, 29.4, 320.55), stand = vector3(12.22, -1610.57, 29.41), w = 0.20, h = 0.80,},  
}
Config.Tables = {
    { name = "Taco's Table 01", coords = vector3(13.1, -1607.8, 29.0), heading = 140, minZ = 28.0, maxZ = 29.2, w = 1.7, h = 0.6, },
    { name = "Taco's Table 02", coords = vector3(11.69, -1609.43, 29.0), heading = 140, minZ = 28.0, maxZ = 29.2, w = 1.7, h = 0.6, },
    { name = "Taco's Table 03", coords = vector3(14.57, -1609.18, 29.0), heading = 140, minZ = 28.0, maxZ = 29.2, w = 1.7, h = 0.6, },
    { name = "Taco's Table 04", coords = vector3(13.25, -1610.75, 29.0), heading = 140, minZ = 28.0, maxZ = 29.2, w = 1.7, h = 0.6, },
}
Config.Billing = {
    { name = "Taco's Billing Counter 1", coords = vector3(9.6, -1605.46, 29.6), heading = 226.53, minZ = 29.0, maxZ = 30.15, w = 0.5, h = 0.4, },
}
Config.Counter = {
    { name = "Taco's Counter 01", coords = vector3(10.38, -1604.83, 29.6), heading = 226.53, minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.7, },
}
--This is Used When Config.RemoveMarkers = true
Config.TargetCoords = {
    Fridge = {
    { name = ""..Config.Jobname.." Fridge", coords =vector3(17.25, -1599.25, 29.6),heading=320.0, minZ = 28.4, maxZ = 29.8, w = 0.75, h = 0.6, }
    },
    Management = {
        { name = ""..Config.Jobname.." Management", coords =vec3(8.2, -1607.3, 29.6),heading=4.0, minZ = 29.5, maxZ = 29.8, w = 0.4, h = 0.4, }
    },
    Process = {
        { name = ""..Config.Jobname.." Process", coords =vec3(-1223.579, -1043.018,8.25),heading=107.2, minZ = 8.1, maxZ = 8.4, w = 0.5, h = 0.6, }
    },
    Stash = {
        { name = ""..Config.Jobname.." Stash", coords =vec3(-1225.771, -1035.777, 8.283),heading=94.85, minZ = 8.1, maxZ = 8.4, w = 0.5, h = 1, }
    },
    BossMenu = {
        { name = ""..Config.Jobname.." BossMenu", coords =vec3(8.0, -1602.25, 29.6),heading=320, minZ = 29.5, maxZ = 29.8, w = 0.5, h = 0.5, }
    },
    Clothing = {
        { name = ""..Config.Jobname.." Clothing", coords =vector3(20.25, -1601.5, 29.6),heading=320, minZ = 28.4, maxZ = 29.8, w = 1.0, h = 0.6, }
    }
}


```

