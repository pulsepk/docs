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
    BlipName = "Up n Atom", --Blip Name
    Enable = true,
    Coords = vector3(82.58, 278.78, 110.21),
    Options = {
        Sprite = 838,
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
    society_script = "qb-management", --esx_society, qb-management,qb-banking
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
Config.Jobname = 'upnatom' -- Job Name
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
        Coords = vector3(86.18, 293.75, 110.21),
    },
    management = vector3(90.94, 288.91, 110.21), --Where you can manage your shop
    fridge = vector3(93.88, 288.74, 110.21), -- From where you will buy ingrediants
    process = vector3(93.29, 290.03, 110.21), --From where you will start making items
    shop = { --Shop buy menu
        vector3(88.94, 287.29, 110.21), 
    },
    storagestash = vector3(89.11, 293.74, 110.21),
    bossmenu = vector3(81.72, 296.31, 110.25),
    Storage = {
		label = "Fridge",
		items = {
            Burgers = {
                { name = "ua_bun", label = "Burger Bun", price = 50, amount = 50 },
                { name = "ua_bbq_sauce", label = "BBQ Sauce", price = 50, amount = 50 },
                { name = "ua_mustard_sauce", label = "Mustard Sauce", price = 50, amount = 50 },
                { name = "ua_glaze", label = "Glaze Sauce", price = 50, amount = 50 },
                { name = "ua_chili", label = "Chili Sauce", price = 50, amount = 50 },
                { name = "ua_smoked", label = "Smoked Sauce", price = 50, amount = 50 }
            },
            Fries = {
                { name = "ua_potato", label = "Potato", price = 50, amount = 50 },
                { name = "ua_butter", label = "Butter", price = 50, amount = 50 },
                { name = "ua_chili", label = "Chili Glaze", price = 50, amount = 50 },
                { name = "ua_parmesan", label = "Parmesan Drizzle", price = 50, amount = 50 },
                { name = "ua_cajun", label = "Cajun Sauce", price = 50, amount = 50 },
                { name = "ua_garlic", label = "Garlic Sauce", price = 50, amount = 50 }
            },
            Drinks = {
                { name = "ua_ice", label = "Ice", price = 50, amount = 50 },
                { name = "ua_mint", label = "Mint Syrup", price = 50, amount = 50 },
                { name = "ua_ginger", label = "Ginger Syrup", price = 50, amount = 50 },
                { name = "ua_berry", label = "Berry Syrup", price = 50, amount = 50 },
                { name = "ua_tropical", label = "Tropical", price = 50, amount = 50 },
            },
            Sodas = {
                { name = "ua_lemon", label = "Lemon", price = 50, amount = 50 },
                { name = "ua_lemon_syrup", label = "Lemon Syrup", price = 50, amount = 50 },
                { name = "ua_ginger", label = "Ginger", price = 50, amount = 50 },
                { name = "ua_mint", label = "Mint", price = 50, amount = 50 },
                { name = "ua_berry", label = "Berry", price = 50, amount = 50 },
                { name = "ua_pineapple", label = "Pineapple", price = 50, amount = 50 }
            },
        }
	},
    ItemOrder = { --This Should Matches the Category Name
        "Burgers",
        "Fries",
        "Drinks",
        "Sodas",
    },
    categories = {
        Burgers = {
            label = "Burgers", -- Do not change
            icon = "fas fa-hamburger",
            workingcoords = vector3(94.86, 292.29, 110.21),
            items = {
                ua_bbq_chicken = {
                    label = "BBQ Chicken Burger",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_bun', label = "Burger Bun", quantity = 1 },
                        { item = 'ua_bbq_sauce', label = "BBQ Sauce", quantity = 1 },
                    },
                },
                ua_mustard_beef = {
                    label = "Mustard Beef Burger",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_bun', label = "Burger Bun", quantity = 1 },
                        { item = 'ua_mustard_sauce', label = "Mustard Sauce", quantity = 1 },
                    },
                },
                ua_glazed_turkey = {
                    label = "Glazed Turkey Burger",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_bun', label = "Burger Bun", quantity = 1 },
                        { item = 'ua_glaze', label = "Glaze Sauce", quantity = 1 },
                    },
                },
                ua_spicy_lamb = {
                    label = "Spicy Lamb Burger",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_bun', label = "Burger Bun", quantity = 1 },
                        { item = 'ua_chili', label = "Chili Sauce", quantity = 1 },
                    },
                },
                ua_sweet_smoky_vegan  = {
                    label = "Sweet & Smoky Vegan Burger",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_bun', label = "Burger Bun", quantity = 1 },
                        { item = 'ua_smoked', label = "Smoked Sauce", quantity = 1 },
                    },
                },
            }
        },
        Fries = {
            label = "Fries", -- Do not change
            icon = "fa-utensils",
            workingcoords = vector3(92.25, 292.22, 110.21),
            items = {
                ua_butter_fries = {
                    label = "Butter Fries",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_potato', label = "Potato", quantity = 1 },
                        { item = 'ua_butter', label = "Butter", quantity = 1 },
                    },
                },
                ua_spicy_glazed = {
                    label = "Spicy Glazed Fries",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_potato', label = "Potato", quantity = 1 },
                        { item = 'ua_chili', label = "Chili Glaze", quantity = 1 },
                    },
                },
                ua_parmesan_fries = {
                    label = "Parmesan Fries",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_potato', label = "Potato", quantity = 1 },
                        { item = 'ua_parmesan', label = "Parmesan Drizzle", quantity = 1 },
                    },
                },
                ua_sweet_cajun = {
                    label = "Sweet Cajun Fries",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_potato', label = "Potato", quantity = 1 },
                        { item = 'ua_cajun', label = "Cajun Sauce", quantity = 1 },
                    },
                },
                ua_garlic_fries = {
                    label = "Garlic Fries",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_potato', label = "Potato", quantity = 1 },
                        { item = 'ua_garlic', label = "Garlic Sauce", quantity = 1 },
                    },
                },
            }
        },
        Drinks = {
            label = "Drinks", -- Do not change
            icon = "fas fa-glass-martini-alt",
            workingcoords = vector3(93.38, 286.68, 110.21),
            items = {
                ua_green_tea = {
                    label = "Iced Green Tea",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_ice', label = "Ice", quantity = 1 },
                    },
                },
                ua_mint_cooler = {
                    label = "Mint Cooler",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_ice', label = "Ice", quantity = 1 },
                        { item = 'ua_mint', label = "Mint Syrup", quantity = 1 },
                    },
                },
                ua_ginger_punch = {
                    label = "Ginger Punch",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_ice', label = "Ice", quantity = 1 },
                        { item = 'ua_ginger', label = "Ginger Syrup", quantity = 1 },
                    },
                },
                ua_berry_refresher = {
                    label = "Berry Refresher",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_ice', label = "Ice", quantity = 1 },
                        { item = 'ua_berry', label = "Berry Syrup", quantity = 1 },
                    },
                },
                ua_tropical_splash = {
                    label = "Tropical Splash",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_ice', label = "Ice", quantity = 1 },
                        { item = 'ua_tropical', label = "Tropical", quantity = 1 },
                    },
                },
            }
        },
        
        Sodas = {
            label = "Sodas", -- Do not change
            icon = "fas fa-glass-whiskey",
            workingcoords = vector3(92.15, 287.21, 110.21),
            items = {
                ua_lemon_fizz = {
                    label = "Lemon Fizz",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_lemon', label = "Lemon", quantity = 1 },
                        { item = 'ua_lemon_syrup', label = "Lemon Syrup", quantity = 1 },
                    },
                },
                ua_ginger_soda = {
                    label = "Ginger Soda",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_lemon', label = "Lemon", quantity = 1 },
                        { item = 'ua_ginger', label = "Ginger", quantity = 1 },
                    },
                },
                ua_mint_sparkler = {
                    label = "Mint Sparkler",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_lemon', label = "Lemon", quantity = 1 },
                        { item = 'ua_mint', label = "Mint", quantity = 1 },
                    },
                },
                ua_berry_soda = {
                    label = "Berry Soda",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_lemon', label = "Lemon", quantity = 1 },
                        { item = 'ua_berry', label = "Berry", quantity = 1 },
                    },
                },
                ua_pineapple_pop = {
                    label = "Pineapple Pop",
                    price = 50, -- For Starting Price
                    reward = 1, -- item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                        { item = 'ua_lemon', label = "Lemon", quantity = 1 },
                        { item = 'ua_pineapple', label = "Pineapple", quantity = 1 },
                    },
                },
            }
        },
    },
}
Config.Chairs = {
   --TableSeating
	--Table1
    { coords = vector4(86.81, 290.29, 110.20, 72.61),stand = vector3(86.55, 289.62, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(87.06, 290.96, 110.20, 72.61),stand = vector3(86.55, 289.62, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(85.79, 291.36, 110.20, 253.99),stand = vector3(85.33, 290.08, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(85.55, 290.69, 110.20, 253.99),stand = vector3(85.33, 290.08, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    --Table2
    { coords = vector4(84.87, 290.96, 110.20, 72.61),stand = vector3(84.64, 290.18, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(85.14, 291.7, 110.20, 72.61),stand = vector3(84.64, 290.18, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(83.83, 292.14, 110.20, 253.99),stand = vector3(83.36, 290.65, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(83.49, 291.32, 110.20, 253.99),stand = vector3(83.36, 290.65, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    --Table3
    { coords = vector4(82.93, 291.74, 110.20, 72.61),stand = vector3(82.72, 291.03, 110.2), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(83.29, 292.51, 110.20, 72.61),stand = vector3(82.72, 291.03, 110.2), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(81.61, 292.04, 110.20, 253.99),stand = vector3(81.42, 291.54, 110.2), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(81.9, 292.84, 110.20, 253.99),stand = vector3(81.42, 291.54, 110.2), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    --Table4
    { coords = vector4(83.77, 285.76, 110.20, 207.96),stand = vector3(82.26, 284.99, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(83.02, 285.39, 110.20, 207.96),stand = vector3(82.26, 284.99, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(84.42, 284.5, 110.20, 26.09),stand = vector3(82.94, 283.96, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(83.71, 284.18, 110.20, 26.09),stand = vector3(82.94, 283.96, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    --Table5
    { coords = vector4(84.67, 283.82, 110.20, 207.96),stand = vector3(83.33, 283.18, 110.2), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(83.99, 283.57, 110.20, 207.96),stand = vector3(83.33, 283.18, 110.2), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(85.31, 282.51, 110.20, 26.09),stand = vector3(83.82, 281.83, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(84.7, 282.23, 110.20, 26.09),stand = vector3(83.82, 281.83, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    --Table6
    { coords = vector4(86.68, 278.69, 110.20, 207.96),stand = vector3(86.12, 278.41, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(87.28, 278.97, 110.20, 207.96),stand = vector3(88.01, 279.5, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(88.0, 277.71, 110.20, 26.09),stand = vector3(88.64, 277.96, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(87.4, 277.42, 110.20, 26.09),stand = vector3(86.68, 276.87, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
     --Table7
    { coords = vector4(85.06, 275.63, 110.20, 250.72),stand = vector3(85.19, 276.41, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(84.75, 274.87, 110.20, 250.72),stand = vector3(85.19, 276.41, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(86.09, 274.52, 110.20, 69.73),stand = vector3(86.55, 275.86, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(86.36, 275.3, 110.20, 69.73),stand = vector3(86.55, 275.86, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    --Table8
    { coords = vector4(87.01, 274.95, 110.20, 250.72),stand = vector3(87.49, 275.68, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(86.76, 274.2, 110.20, 250.72),stand = vector3(87.49, 275.68, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(88.05, 273.79, 110.20, 69.73),stand = vector3(88.57, 275.21, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(88.28, 274.54, 110.20, 69.73),stand = vector3(88.57, 275.21, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    --Table9
    { coords = vector4(89.54, 274.99, 110.20, 342.38),stand = vector3(88.86, 275.24, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(90.22, 274.76, 110.20, 342.38),stand = vector3(88.86, 275.24, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(90.62, 276.06, 110.20, 164.04),stand = vector3(89.2, 276.62, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(89.84, 276.35, 110.20, 164.04),stand = vector3(89.2, 276.62, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    --Table10
    { coords = vector4(90.95, 276.75, 110.20, 342.81),stand = vector3(89.39, 277.04, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(90.29, 276.98, 110.20, 342.81),stand = vector3(89.39, 277.04, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(91.33, 278.04, 110.20, 168.28),stand = vector3(89.76, 278.34, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(90.58, 278.3, 110.20, 168.28),stand = vector3(89.76, 278.34, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    --Small Tables
    { coords = vector4(86.31, 284.03, 110.20, 300.94),stand = vector3(87.76, 283.78, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
    { coords = vector4(85.67, 285.55, 110.20, 292.71),stand = vector3(86.24, 287.0, 110.21), minZ = 109.50, maxZ = 110.70, w = 0.3, h = 0.3},
}
Config.Tables = {
    { name = "UpnAtom Table 01", coords = vector3(86.3, 290.8, 110.0), heading = 340.0, minZ = 109.50, maxZ = 110.20, w = 0.85, h = 1.5, },
    { name = "UpnAtom Table 02", coords = vector3(84.35, 291.45, 110.0), heading = 340.0, minZ = 109.50, maxZ = 110.20, w = 0.85, h = 1.5, },
    { name = "UpnAtom Table 03", coords = vector3(82.35, 292.15, 110.0), heading = 340.0, minZ = 109.50, maxZ = 110.20, w = 0.85, h = 1.5, },
    { name = "UpnAtom Table 04", coords = vector3(83.6, 284.9, 110.0), heading = 295.0, minZ = 109.50, maxZ = 110.20, w = 0.85, h = 1.5, },
    { name = "UpnAtom Table 05", coords = vector3(84.55, 282.95, 110.0), heading = 295.0, minZ = 109.50, maxZ = 110.20, w = 0.85, h = 1.5, },
    { name = "UpnAtom Table 06", coords = vector3(87.3, 278.2, 110.0), heading = 295.0, minZ = 109.50, maxZ = 110.20, w = 0.85, h = 1.5, },
    { name = "UpnAtom Table 07", coords = vector3(85.55, 275.1, 110.0), heading = 340.0, minZ = 109.50, maxZ = 110.20, w = 0.85, h = 1.5, },
    { name = "UpnAtom Table 08", coords = vector3(87.5, 274.35, 110.0), heading = 340.0, minZ = 109.50, maxZ = 110.20, w = 0.85, h = 1.5, },
    { name = "UpnAtom Table 09", coords = vector3(90.0, 275.55, 110.0), heading = 250.0, minZ = 109.50, maxZ = 110.20, w = 0.85, h = 1.5, },
    { name = "UpnAtom Table 10", coords = vector3(90.7, 277.5, 110.0), heading = 250.0, minZ = 109.50, maxZ = 110.20, w = 0.85, h = 1.5, },
    --small
    { name = "UpnAtom Table 11", coords = vector3(86.45, 286.0, 109.75), heading = 25.0, minZ = 109.40, maxZ = 110.00, w = 0.65, h = 0.75, },
    { name = "UpnAtom Table 12", coords = vector3(87.2, 284.45, 109.7), heading = 25.0, minZ = 109.40, maxZ = 110.00, w = 0.65, h = 0.75, },

}
Config.Billing = {
    { name = "UpnAtom Billing 1", coords = vec3(89.1, 288.8, 110.5), heading = 295.0, minZ = 109.70, maxZ = 110.70, w = 0.4, h = 0.4, },
    { name = "UpnAtom Billing 2", coords = vec3(89.7, 287.7, 110.5), heading = 295.0, minZ = 109.70, maxZ = 110.70, w = 0.4, h = 0.4, },
    { name = "UpnAtom Billing 3", coords = vec3(90.25, 286.45, 110.5), heading = 295.0, minZ = 109.70, maxZ = 110.70, w = 0.4, h = 0.4, },
    { name = "UpnAtom Billing 4", coords = vec3(94.45, 284.6, 110.5), heading = 328.75, minZ = 109.70, maxZ = 110.70, w = 0.4, h = 0.4, },
}
Config.Counter = {
    { name = "UpnAtom Counter 01", coords = vector3(89.2, 288.15, 110.2), heading = 25.0, minZ = 109.50, maxZ = 110.30, w = 0.3, h = 0.5, },
    { name = "UpnAtom Counter 02", coords = vector3(89.75, 286.95, 110.2), heading = 29.75, minZ = 109.50, maxZ = 110.30, w = 0.3, h = 0.5, },
    { name = "UpnAtom Counter 03", coords = vector3(90.3, 285.8, 110.2), heading = 19.75, minZ = 109.50, maxZ = 110.30, w = 0.3, h = 0.5, },
    { name = "UpnAtom DriveBy", coords = vector3(94.7, 285.3, 110.4), heading = 340.0, minZ = 109.90, maxZ = 110.60, w = 0.3, h = 0.5, },
}

--This is Used When Config.RemoveMarkers = true
Config.TargetCoords = {
    Fridge = {
    { name = ""..Config.Jobname.." Fridge", coords =vector3(93.65, 288.15, 110.5),heading=340.0, minZ = 109.5, maxZ = 110.9, w = 1.15, h = 0.65, }
    },
    Management = {
        { name = ""..Config.Jobname.." Management", coords =vec3(91.3, 288.8, 110.4),heading=295.0, minZ = 109.10, maxZ = 110.9, w = 0.5, h = 0.5, }
    },
    Process = {
        { name = ""..Config.Jobname.." Process", coords =vec3(93.15, 290.65, 110.20),heading=340.0, minZ = 110.00, maxZ = 110.30, w = 0.4, h = 0.4, }
    },
    Stash = {
        { name = ""..Config.Jobname.." Stash", coords =vec3(89.95, 293.9, 110.1),heading=340.0, minZ = 109.30, maxZ = 110.8, w = 0.5, h = 0.5, }
    },
    BossMenu = {
        { name = ""..Config.Jobname.." BossMenu", coords =vec3(80.85, 297.2, 109.95),heading=351.5, minZ = 109.80, maxZ = 110.30, w = 0.5, h = 0.2, }
    },
    Clothing = {
        { name = ""..Config.Jobname.." Clothing", coords =vector3(85.85, 293.45, 110.30),heading=340.0, minZ = 109.20, maxZ = 110.90, w = 0.7, h = 0.45, }
    }
}
```

