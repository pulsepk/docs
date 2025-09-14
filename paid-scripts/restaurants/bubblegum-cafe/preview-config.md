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
    BlipName = "BubbleGum Cafe", --Blip Name
    Enable = true,
    Coords = vector3(-1230.703, -1039.518, 8.283),
    Options = {
        Sprite = 106,
        Color = 12,
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
Config.Jobname = 'bubblegum' -- Job Name
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
			tshirt_1 = 15,  tshirt_2 = 0,
			torso_1 = 382,   torso_2 = 0,
			decals_1 = 0,   decals_2 = 0,
			arms = 0,
			pants_1 = 0,   pants_2 = 0,
			shoes_1 = 0,   shoes_2 = 0,
			helmet_1 = 156,  helmet_2 = 0,
			chain_1 = 0,    chain_2 = 0,
			ears_1 = 0,     ears_2 = 0
		},
		female = {
			tshirt_1 = 15,  tshirt_2 = 0,
			torso_1 = 382,   torso_2 = 0,
			decals_1 = 0,   decals_2 = 0,
			arms = 0,
			pants_1 = 0,   pants_2 = 0,
			shoes_1 = 0,   shoes_2 = 0,
			helmet_1 = 156,  helmet_2 = 0,
			chain_1 = 0,    chain_2 = 0,
			ears_1 = 0,     ears_2 = 0
		}
	},
}
Config.CheckCanCarryItem = false -- Only for ESX
Config.Shop = {
    Clothing = {
        Coords = vector3(-1219.734, -1045.373, 8.283),
    },
    management = vector3(-1229.173, -1037.906, 8.283), --Where you can manage your shop
    fridge = vector3(-1224.058, -1039.88, 8.283), -- From where you will buy ingrediants
    process = vector3(-1222.466, -1043.375, 8.283), --From where you will start making items
    shop = { --Shop buy menu
    vector3(-1230.542, -1039.503, 8.283),
    },
    storagestash = vector3(-1225.082, -1035.9, 8.283),
    bossmenu = vector3(-1235.346, -1049.801, 12.93),
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
                { name = "bg_ice", label="Ice", price = 50, amount = 50},
                { name = "bg_butter", label="Butter", price = 50, amount = 50},
                { name = "bg_chocolate_cream", label="Chocolate Cream filling", price = 50, amount = 50},
                { name = "bg_apple_filling", label="Apple filling", price = 50, amount = 50},
                { name = "bg_cinnamon_sugar", label="Cinnamon Sugar", price = 50, amount = 50},
                { name = "bg_pastry_cream", label="Pastry Cream", price = 50, amount = 50},
            },
            Drinks = {
                { name = "bg_butter", label="Butter", price = 50, amount = 50},
                { name = "bg_caramel_syrup", label="Caramel syrup", price = 50, amount = 50},
                { name = "bg_chocolate_syrup", label="Chocolate Syrup", price = 50, amount = 50},
                { name = "bg_coffee_beans", label="Coffee Beans", price = 50, amount = 50},
                { name = "bg_matcha_powder", label="Matcha Powder", price = 50, amount = 50},
                { name = "bg_vanilla_syrup", label="Vanilla Syrup", price = 50, amount = 50},
            }            
        },
	},
    ItemOrder = {
        "Pizzas",
        "Salads",
        "Deserts",
        "Drinks",
    },
    categories = {
        Pizzas = { 
            label = "Pizzas", --Donot Change
            icon = "fas fa-cookie-bite",
            workingcoords = vector3(-1220.235, -1042.492, 8.283),
            items = {
                bg_margherita = {
                    label="Classic Margherita",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_dough', label="Dough", quantity = 1},
                    {item = 'bg_basil_leaves', label="Basil Leaves", quantity = 1},
                    },
                },
                bg_pepperoni = {
                    label="Pepperoni Feast",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_dough', label="Dough", quantity = 1},
                    {item = 'bg_marinara_sauce', label="Marinara Sauce", quantity = 1},
                    },
                },
                bg_bbq_chicken = {
                    label="BBQ Chicken",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_dough', label="Dough", quantity = 1},
                    {item = 'bg_bbq_sauce', label="Smoky BBQ Sauce", quantity = 1},
                    },
                },
                bg_Supreme = {
                    label="Veggie Supreme",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_dough', label="Dough", quantity = 1},
                    {item = 'bg_black_olives', label="Black Olives", quantity = 1},
                    },
                },
                bg_hawaiian = {
                    label="Hawaiian Paradise",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_dough', label="Dough", quantity = 1},
                    {item = 'bg_pineapple_chunks', label="Pineapple Chunks", quantity = 1},
                    },
                },
            }, 
        },
        Salads= { 
            label = "Salads", --Donot Change
            icon = "fas fa-glass-martini-alt",
            workingcoords = vector3(-1221.263, -1039.413, 8.283),
            items = {
                bg_Caesar = {
                    label="Classic Caesar Salad",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_vinegar',label="Vinegar", quantity = 1},
                    {item = 'bg_parmesan',label="Parmesan Shavings", quantity = 1},
                    },
                },
                bg_greek_feta = {
                    label="Greek Feta Salad",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_vinegar',label="Vinegar", quantity = 1},
                    {item = 'bg_kalamata_olives',label="Kalamata Olives", quantity = 1},
                    },
                },
                bg_caprese = {
                    label="Caprese Salad",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_vinegar',label="Vinegar", quantity = 1},
                    {item = 'bg_balsamic_glaze',label="Balsamic Glaze", quantity = 1},
                    },
                },
                bg_chicken_caesar = {
                    label="Chicken Caesar Salad",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_vinegar',label="Vinegar", quantity = 1},
                    {item = 'bg_garlic_croutons',label="Garlic Croutons", quantity = 1},
                    },
                },
                bg_fresh_garden = {
                    label="Garden Fresh Salad",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_vinegar',label="Vinegar", quantity = 1},
                    {item = 'bg_avocado_slice',label="Avocado Slices", quantity = 1},
                    },
                },          
            }
        },
        Deserts = { 
            label = "Deserts", --Donot Change
            icon = "fas fa-bread-slice",
            workingcoords = vector3(-1227.596, -1038.694, 8.283),
            items = {
                bg_croissant = {
                    label="Croissant",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_butter',label="Butter", quantity = 1},
                    {item = 'bg_chocolate_cream',label="Chocolate Cream filling", quantity = 1},
                    },
                },
                bg_apple_turnover = {
                    label="Apple Turnovers",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_butter',label="Butter", quantity = 1},
                    {item = 'bg_apple_filling',label="Apple filling", quantity = 1},
                    },
                },
                bg_cinnamon_roll = {
                    label="Cinnamon Rolls",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_butter',label="Butter", quantity = 1},
                    {item = 'bg_cinnamon_sugar',label="Cinnamon Sugar", quantity = 1},
                    },
                },
                bg_eclairs = {
                    label="Eclairs",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_butter',label="Butter", quantity = 1},
                    {item = 'bg_pastry_cream',label="Pastry cream", quantity = 1},
                    },
                },
                bg_danish_pastry = {
                    label="Danish Pastry",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_butter',label="Butter", quantity = 1},
                    {item = 'bg_cream_cheese',label="Cream cheese", quantity = 1},
                    },
                },
            }         
        },      
        Drinks = {
            label = "Drinks", -- Do not change
            icon = "fas fa-box",
            workingcoords = vector3(-1227.261, -1039.605, 8.283),
            items = {
                bg_iced_caramel_latte = {
                    label="Iced Caramel Latte",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_ice',label="Ice", quantity = 1},
                    {item = 'bg_caramel_syrup', label="Caramel syrup", quantity = 1},
                    },
                },
                bg_mocha_frappe = {
                    label="Mocha Frappe",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_ice',label="Ice", quantity = 1},
                    {item = 'bg_chocolate_syrup', label="Chocolate Syrup", quantity = 1},
                    },
                },
                bg_cold_brew_coffee = {
                    label="Cold Brew Coffee",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_ice',label="Ice", quantity = 1},
                    {item = 'bg_coffee_beans', label="Coffee Beans", quantity = 1},
                    },
                },
                bg_iced_matcha_latte = {
                    label="Iced Matcha Latte",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_ice',label="Ice", quantity = 1},
                    {item = 'bg_matcha_powder', label="Matcha powder", quantity = 1},
                    },
                },
                bg_vanilla_iced_coffee = {
                    label="Vanilla Iced Coffee",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'bg_ice',label="Ice", quantity = 1},
                    {item = 'bg_vanilla_syrup', label="Vanilla Syrup", quantity = 1},
                    },
                },
            }
        },
    },
}
Config.Chairs = {
    --RoundTableSeating
	{ coords = vector4(122.391, -1046.867, 29.630, 139.665), stand = vector3(121.628, -1046.55, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
	{ coords = vector4(121.752, -1048.591, 29.630, 350.704), stand = vector3(120.97, -1047.994, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
	{ coords = vector4(117.92, -1047.669, 29.630, 58.348), stand = vector3(118.159, -1046.881, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
	{ coords = vector4(116.246, -1047.045, 29.630, 248.141), stand = vector3(116.672, -1046.521, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(123.494, -1028.738, 29.630, 183.503), stand = vector3(122.812, -1028.967, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(125.098, -1029.066, 29.630, 162.554), stand = vector3(125.469, -1030.07, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
--squaretableseating and rectangle table
	{ coords = vector4(-1235.704, -1039.221, 8.34, 199.715), stand = vector3(-1237.997, -1040.333, 8.283-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
	{ coords = vector4(-1236.806, -1039.623, 8.34, 199.715), stand = vector3(-1237.997, -1040.333, 8.283-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
	{ coords = vector4(-1236.095, -1041.691, 8.34, 26.803), stand = vector3(-1237.541, -1041.688, 8.283-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
	{ coords = vector4(-1234.866, -1041.092, 8.34, 41.031), stand = vector3(-1237.541, -1041.688, 8.283-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1239.647, -1040.727, 8.34, 207.318), stand = vector3(-1238.35, -1040.472, 8.283-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1238.833, -1042.585, 8.34, 30.235), stand = vector3(-1237.67, -1042.16, 8.283-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1238.202, -1044.405, 8.34, 201.045), stand = vector3(-1237.048, -1044.014, 8.283-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1237.517, -1046.092, 8.34, 27.777), stand = vector3(-1236.377, -1045.753, 8.283-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1232.969, -1049.683, 8.57, 304.221), stand = vector3(-1233.6, -1047.52, 8.508-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1233.33, -1048.701, 8.57, 286.295), stand = vector3(-1233.6, -1047.52, 8.508-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1231.247, -1049.063, 8.57, 111.536), stand = vector3(-1232.204, -1046.871, 8.508-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1231.594, -1047.89, 8.57, 106.266), stand = vector3(-1232.204, -1046.871, 8.508-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1229.977, -1048.593, 8.57, 290.39), stand = vector3(-1230.69, -1046.28, 8.506) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1230.338, -1047.606, 8.57, 289.935), stand = vector3(-1230.69, -1046.28, 8.506-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1228.281, -1047.866, 8.57, 107.259), stand = vector3(-1229.045, -1046.032, 8.508-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1228.595, -1046.956, 8.57, 94.436), stand = vector3(-1229.045, -1046.032, 8.508-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
--upstairs
    { coords = vector4(-1238.526, -1042.205, 12.95, 283.951), stand = vector3(-1238.318, -1043.097, 12.93-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1236.945, -1042.856, 12.95, 20.233), stand = vector3(-1238.062, -1043.331, 12.93-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1235.91, -1042.46, 12.95, 21.234), stand = vector3(-1234.785, -1042.037, 12.93-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1234.99, -1040.797, 12.95, 104.261), stand = vector3(-1235.21, -1040.112, 12.93-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1236.777, -1040.193, 12.95, 188.722), stand = vector3(-1235.762, -1039.727, 12.93-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1237.676, -1040.588, 12.95, 196.464), stand = vector3(-1238.861, -1040.994, 12.93-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1232.428, -1040.867, 12.95, 268.766), stand = vector3(-1231.841, -1041.654, 12.93-0.5), minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1232.837, -1039.593, 12.95, 283.389), stand = vector3(-1233.245, -1038.724, 12.93-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1230.537, -1039.905, 12.95, 90.862), stand = vector3(-1230.132, -1041.021, 12.93-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1230.945, -1038.951, 12.95, 100.806), stand = vector3(-1231.234, -1037.934, 12.93-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1228.216, -1036.665, 12.95, 202.412), stand = vector3(-1229.101, -1037.128, 12.93-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1227.649, -1038.676, 12.95, 22.493), stand = vector3(-1228.482, -1038.724, 12.93-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1227.098, -1040.119, 12.95, 203.093), stand = vector3(-1228.186, -1040.312, 12.93-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1226.325, -1041.938, 12.95, 38.601), stand = vector3(-1227.16, -1042.328, 12.93-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
--office upstairs
    { coords = vector4(-1230.522, -1047.952, 12.95, 115.852), stand = vector3(-1231.417, -1047.331, 12.936-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1232.204, -1049.68, 12.95, 17.753), stand = vector3(-1233.215, -1049.571, 12.936-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(-1231.23, -1049.32, 12.95, 20.098), stand = vector3(-1233.215, -1049.571, 12.936-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
-- single chair
    { coords = vector4(119.913, -1044.945, 29.61, 338.011), stand = vector3(120.637, -1044.905, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(118.787, -1044.046, 29.61, 298.612), stand = vector3(118.739, -1043.435, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(118.796, -1042.821, 29.61, 262.925), stand = vector3(118.784, -1042.161, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(119.117, -1041.76, 29.61, 250.687), stand = vector3(119.635, -1041.208, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},  
    { coords = vector4(121.838, -1034.455, 29.61, 246.69), stand = vector3(121.632, -1035.157, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(122.222, -1033.43, 29.61, 247.653), stand = vector3(122.744, -1032.893, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(123.017, -1032.385, 29.61, 193.797), stand = vector3(123.627, -1032.573, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords = vector4(124.368, -1032.503, 29.61, 162.677), stand = vector3(125.637, -1033.042, 29.278-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
}
Config.Tables = {
    --squaretable
        { name = "Bubble Gum Table 01", coords = vec3(-1239.15, -1041.65, 8.0), heading = 24, minZ = 8.1, maxZ = 8.3, w = 1.2, h = 1.2, },
        { name = "Bubble Gum Table 02", coords = vec3(-1237.832, -1045.229, 8.0), heading = 110, minZ = 8.1, maxZ = 8.3, w = 1.2, h = 1.2, },
        { name = "Bubble Gum Table 03", coords = vec3(-1226.65, -1041.0, 13.0), heading = 110, minZ = 12.80, maxZ = 13.05, w = 1.2, h = 1.2, },
        { name = "Bubble Gum Table 04", coords = vec3(-1227.95, -1037.7, 13.0), heading = 110, minZ = 12.80, maxZ = 13.05, w = 1.2, h = 1.2, },
    --rectangletable
        { name = "Bubble Gum Table 05", coords =vec3(-1235.95, -1040.35, 7.9), heading = 20, minZ = 7.8, maxZ = 8.30, w = 2.15, h =1.2, },
        { name = "Bubble Gum Table 06", coords =vec3(-1232.25, -1048.75, 8.05), heading = 200, minZ = 8.0, maxZ = 8.6, w = 1.2, h =2.15, },
        { name = "Bubble Gum Table 07", coords =vec3(-1229.315, -1047.616, 8.1), heading = 200, minZ = 8.0, maxZ = 8.6, w = 1.2, h =2.15, },
        { name = "Bubble Gum Table 08", coords =vec3(-1236.795, -1041.532, 13.037), heading = 110, minZ = 12.80, maxZ = 13.05, w = 1.2, h =2.45, },
        { name = "Bubble Gum Table 09", coords =vec3(-1231.7, -1039.8, 13.0), heading = 200, minZ = 12.80, maxZ = 13.05, w = 1.2, h =2.45, },
    
}
Config.Billing = {
    { name = "Bubble Gum Billing Counter 1", coords =vector3(-1228.592, -1040.023, 8.387), heading = 113.19, minZ = 8.1, maxZ = 8.5, w = 0.5, h = 0.4, },
}
Config.Counter = {
    { name = "Bubble Gum Counter 01", coords = vector3(-1228.762, -1041.531, 8.292), heading =113.19, minZ = 8.1, maxZ = 8.35, w = 0.5, h = 0.7, },
}
--This is Used When Config.RemoveMarkers = true
Config.TargetCoords = {
    Fridge = {
    { name = ""..Config.Jobname.." Fridge", coords =vector3(-1224.329, -1040.00, 8.183),heading=24.0, minZ = 7.9, maxZ = 8.3, w = 1.0, h = 0.8, }
    },
    Management = {
        { name = ""..Config.Jobname.." Management", coords =vec3(-1229.119, -1037.723, 8.283),heading=94.85, minZ = 8.1, maxZ = 8.4, w = 0.5, h = 0.5, }
    },
    Process = {
        { name = ""..Config.Jobname.." Process", coords =vec3(-1223.579, -1043.018,8.25),heading=107.2, minZ = 8.1, maxZ = 8.4, w = 0.5, h = 0.6, }
    },
    Stash = {
        { name = ""..Config.Jobname.." Stash", coords =vec3(-1225.771, -1035.777, 8.283),heading=94.85, minZ = 8.1, maxZ = 8.4, w = 0.5, h = 1, }
    },
    BossMenu = {
        { name = ""..Config.Jobname.." BossMenu", coords =vec3(-1234.587, -1050.266, 12.801),heading=297.45, minZ = 12.7, maxZ = 12.9, w = 0.5, h = 0.6, }
    },
    Clothing = {
        { name = ""..Config.Jobname.." Clothing", coords =vector3(-1219.734, -1045.373, 8.283),heading=273.37, minZ = 8.1, maxZ = 8.4, w = 1.0, h = 0.8, }
    }
}
```

