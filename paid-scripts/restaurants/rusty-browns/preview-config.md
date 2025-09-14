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
    BlipName = "Rusty Browns", --Blip Name
    Enable = true,
    Coords = vector3(358.63, -1012.4, 29.34),
    Options = {
        Sprite = 739,
        Color = 1,
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
Config.Jobname = 'rustybrowns' -- Job Name
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
        Coords = vector3(356.08, -1008.19, 29.34),
    },
    management = vector3(356.42, -1016.81, 29.34), --Where you can manage your shop
    fridge = vector3(355.03, -1010.89, 29.34), -- From where you will buy ingrediants
    process = vector3(356.22, -1014.17, 29.34), --From where you will start making items
    shop = { --Shop buy menu
    vector3(355.87, -1019.63, 29.34), 
    },
    storagestash = vector3(353.16, -1007.88, 29.34),
    bossmenu = vec3(358.28, -1007.68, 29.34),
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
                
            },
            Pastries = {
                { name = "rs_butter", label="Rusty's Butter", price = 50, amount = 50},
                { name = "rs_chocolate_cream", label="Rusty's Chocolate Cream filling", price = 50, amount = 50},
                { name = "rs_apple_filling", label="Rusty's Apple filling", price = 50, amount = 50},
                { name = "cinnamon_sugar", label="Rusty's Cinnamon Sugar", price = 50, amount = 50},
                { name = "rs_pastry_cream", label="Rusty's Pastry Cream", price = 50, amount = 50},
                { name = "rs_cream_cheese", label="Rusty's Cream Cheese", price = 50, amount = 50},
                { name = "rs_chocolate_sticks", label="Rusty's Chocolate Sticks", price = 50, amount = 50},
                { name = "rs_whipped_cream", label="Rusty's Whipped Cream", price = 50, amount = 50},
                { name = "rs_brownbutter_cinnamon", label="Rusty's BrownButter Cinnamon", price = 50, amount = 50},
                { name = "rs_sugar_glaze", label="Rusty's Sugar Glaze", price = 50, amount = 50},
            },
        }
	},
    ItemOrder = { --This Should Matches the Category Name
        "Donuts",
        "IcedDrinks",
        "Pastries",
        "BoxofDonuts",
    },
    categories = {
        Donuts = {
            label = "Donuts", --Donot Change
            icon = "fas fa-cookie-bite",
            workingcoords = vector3(357.79, -1010.76, 29.34),
            items = {
                berry_glazed_donut = {
                    label="Berry Glazed Donut",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_flour', label="Rusty's Donut Base", quantity = 1},
                    {item = 'rs_berries', label="Rusty's Berries", quantity = 1},
				    },
                },
                chococream_donut = {
                    label="Choco Cream Filled Donut",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_flour', label="Rusty's Donut Base", quantity = 1},
                    {item = 'rs_chocolate_cream', label="Rusty's Chocolate cream filling", quantity = 1},
				    },
                },
                chocfrosted_donut = {
                    label="Chocolate Frosted Donut",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_flour', label="Rusty's Donut Base", quantity = 1},
                    {item = 'rs_chocolate_glaze', label="Rusty's Chocolate glaze", quantity = 1},
				    },
                },
                sprinkled_donut = {
                    label="Chocolate Sprinkled Donut",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_flour', label="Rusty's Donut Base", quantity = 1},
                    {item = 'rs_sprinkling_chocolate', label="Rusty's Sprinkling Chocolate", quantity = 1},
				    },
                },
                cinnamon_sugar_donut = {
                    label="Cinnamon Sugar Donut",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_flour', label="Rusty's Donut Base", quantity = 1},
                    {item = 'rs_cinnamon_sugar', label="Rusty's Cinnamon and Sugar Coating", quantity = 1},
				    },
                },
                cookiecream_donut = {
                    label="Cookies and Cream Donut",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_flour', label="Rusty's Donut Base", quantity = 1},
                    {item = 'rs_choco_cookies', label="Rusty's Chocolate Cookies", quantity = 1},
				    },
                },
                cruller_donut = {
                    label="Cruller Donut",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_flour', label="Rusty's Donut Base", quantity = 1},
                    {item = 'rs_sugar_glaze', label="Rusty's Sugar glaze", quantity = 1},
				    },
                },
                lemon_iced_donut = {
                    label="Lemon Iced Donut",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_flour', label="Rusty's Donut Base", quantity = 1},
                    {item = 'rs_lemon', label="Rusty's Lemon", quantity = 1},
				    },
                },
                mapple_bar_donut = {
                    label="Mapple Bar Donut",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_flour', label="Rusty's Donut Base", quantity = 1},
                    {item = 'rs_maple_glaze', label="Rusty's Maple glaze", quantity = 1},
				    },
                },
                strawberry_iced_donut = {
                    label="Rusty's Strawberry Iced Donuts",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_flour', label="Rusty's Donut Base", quantity = 1},
                    {item = 'rs_strawberry', label="Rusty's Strawberry", quantity = 1},
				    },
                },
            }
        },
        IcedDrinks= {
            label = "Iced Drinks", --Donot Change
            icon = "fas fa-glass-martini-alt",
            workingcoords = vector3(357.79, -1010.76, 29.34),
            items = {
                iced_caramel_latte = {
                    label="Iced Caramel Latte",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_ice',label="Rusty's Ice", quantity = 1},
                    {item = 'rs_caramel_syrup', label="Rusty's Caramel syrup", quantity = 1},
				    },
                },
                mocha_frappe = {
                    label="Mocha Frappe",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_ice',label="Rusty's Ice", quantity = 1},
                    {item = 'rs_chocolate_syrup', label="Rusty's Chocolate Syrup", quantity = 1},
				    },
                },
                cold_brew_coffee = {
                    label="Cold Brew Coffee",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_ice',label="Rusty's Ice", quantity = 1},
                    {item = 'rs_coffee_beans', label="Rusty's Coffee Beans", quantity = 1},
				    },
                },
                iced_matcha_latte = {
                    label="Iced Matcha Latte",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_ice',label="Rusty's Ice", quantity = 1},
                    {item = 'rs_matcha_powder', label="Rusty's Matcha powder", quantity = 1},
				    },
                },
                vanilla_iced_coffee = {
                    label="Vanilla Iced Coffee",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_ice',label="Rusty's Ice", quantity = 1},
                    {item = 'rs_vanilla_syrup', label="Rusty's Vanilla Syrup", quantity = 1},
				    },
                },
                strawberry_lemonade_slush = {
                    label="Rusty's Strawberry Lemonade Slush",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_ice',label="Rusty's Ice", quantity = 1},
                    {item = 'rs_strawberry', label="Rusty's Strawberry", quantity = 1},
				    },
                },
                iced_chai_tea_latte = {
                    label="Iced Chai Tea Latte",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_ice',label="Rusty's Ice", quantity = 1},
                    {item = 'rs_chai_tea', label="Rusty's Tea Concentrate", quantity = 1},
				    },
                },
                iced_mocha = {
                    label="Iced Mocha",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_ice',label="Rusty's Ice", quantity = 1},
                    {item = 'rs_espresso ', label="Rusty's Espresso ", quantity = 1},
				    },
                },
                iced_coconut_coffee = {
                    label="Iced Coconut Coffee",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_ice',label="Rusty's Ice", quantity = 1},
                    {item = 'rs_coconut_milk', label="Rusty's Coconut milk", quantity = 1},
				    },
                },
                mint_chocolate_chip_milkshake = {
                    label="Mint Chocolate Chip Milkshake",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_ice',label="Rusty's Ice", quantity = 1},
                    {item = 'rs_mint_icecream', label="Rusty's Mint Icecream", quantity = 1},
				    },
                },
            }
        },

        Pastries = { 
            label = "Pastries", --Donot Change
            icon = "fas fa-bread-slice",
            workingcoords = vector3(357.79, -1010.76, 29.34),
            items = {
                croissant = {
                    label="Croissant",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_butter',label="Rusty's Butter", quantity = 1},
                    {item = 'rs_chocolate_cream',label="Rusty's Chocolate cream filling", quantity = 1},
				    },
                },
                apple_turnover = {
                    label="Apple Turnovers",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'rs_butter',label="Rusty's Butter", quantity = 1},
                    {item = 'rs_apple_filling',label="Rusty's Apple filling", quantity = 1},
				    },
                },
                cinnamon_roll = {
                    label="Cinnamon Rolls",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'rs_butter',label="Rusty's Butter", quantity = 1},
                    {item = 'cinnamon_sugar',label="Rusty's Cinnamon Sugar", quantity = 1},
				    },
                },
                eclairs = {
                    label="eclairs",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'rs_butter',label="Rusty's Butter", quantity = 1},
                    {item = 'rs_pastry_cream',label="Rusty's Pastry cream", quantity = 1},
				    },
                },
                danish_pastry = {
                    label="Danish Pastry",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'rs_butter',label="Rusty's Butter", quantity = 1},
                    {item = 'rs_cream_cheese',label="Rusty's Cream cheese", quantity = 1},
				    },
                },
                puff_pastry_tarts = {
                    label="Puff Pastry Tart",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'rs_butter',label="Rusty's Butter", quantity = 1},
                    {item = 'rs_apple_filling',label="Rusty's Apple Filling", quantity = 1},
				    },
                },
                chocolate_pastry = {
                    label="Chocolate Pastry",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_butter',label="Rusty's Butter", quantity = 1},
                    {item = 'rs_chocolate_sticks',label="Rusty's Chocolate sticks", quantity = 1},
				    },
                },
                cream_puff = {
                    label="Cream Puff",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_butter',label="Rusty's Butter", quantity = 1},
                    {item = 'rs_whipped_cream',label="Rusty's Whipped cream", quantity = 1},
				    },
                },
                sticky_bun = {
                    label="Sticky Bun",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_butter',label="Rusty's Butter", quantity = 1},
                    {item = 'rs_brownbutter_cinnamon',label="Rusty's Brown Sugar", quantity = 1},
				    },
                },
                fruit_strudel = {
                    label="Fruit Strudel",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'rs_butter',label="Rusty's Butter", quantity = 1},
                    {item = 'rs_sugar_glaze',label="Rusty's Sugar Glaze", quantity = 1},
				    },
                },
            }
        
        },
        BoxofDonuts = {
            label = "Box of Donuts", -- Do not change
            icon = "fas fa-box",
            workingcoords = vector3(357.79, -1010.76, 29.34),
            items = {
                box_donut_a = {
                    label = "Sprinkled Donut Box", 
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'sprinkled_donut',label="Chocolate Sprinkled Donut", quantity = 5},
                    },
                },
                box_donut_b = {
                    label = "ChocoCream Donut Box",  
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'choccream_donut',label='Cream Filled Donut', quantity = 5},
                    },
                },
                box_donut_c = {
                    label = "Cinnamon Sugar Donut Box",  
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'cinnamon_sugar_donut',label='Cinnamon Sugar Donut', quantity = 5},
                    },
                },
                box_donut_d = {
                    label = "Lemon Iced Donut Box", 
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'lemon_iced_donut',label='Lemon Iced Donut', quantity = 5},
                    },
                },
                box_donut_e = {
                    label = "Strawberry Iced Donut Box", 
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'strawberry_iced_donut',label='Strawberry Iced Donut', quantity = 5},
                    },
                },
            },
        },
    },
}
Config.Chairs = {
   --TableSeating
	--Row1
    { coords = vector4(356.75, -1021.49, 29.65,177.56),stand = vector3(356.17, -1021.33, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    { coords = vector4(355.89, -1022.34, 29.65,271.61), stand = vector3(356.17, -1021.33, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    { coords = vector4(357.59, -1022.26, 29.65,97.02), stand = vector3(356.17, -1021.33, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},

    { coords = vector4(359.2, -1021.49, 29.65,177.56), stand = vector3(359.29, -1020.9, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    { coords = vector4(360.01, -1022.24, 29.65, 103.7), stand = vector3(360.1, -1022.92, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    { coords = vector4(358.42, -1022.33, 29.65, 271.91), stand = vector3(358.4, -1022.92, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    
    --Row2
    { coords = vector4(355.84, -1024.71, 29.65, 272.96), stand = vector3(355.31, -1024.69, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    { coords = vector4(356.71, -1023.88, 29.65, 178.63), stand = vector3(356.06, -1023.92, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    { coords = vector4(357.59, -1024.61, 29.65, 102.21), stand = vector3(357.68, -1025.3, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},

    { coords = vector4(358.7, -1024.72, 29.65, 273.09), stand = vector3(356.17, -1021.33, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    { coords = vector4(359.28, -1023.82, 29.65, 175.28), stand = vector3(358.64, -1023.9, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    { coords = vector4(359.91, -1024.58, 29.65, 98.93), stand = vector3(360.09, -1025.34, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    --Row3

    { coords = vector4(359.45, -1026.94, 29.65, 93.65), stand = vector3(359.45, -1026.21, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    { coords = vector4(357.82, -1026.98, 29.65, 278.12), stand = vector3(357.82, -1026.35, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},

    { coords = vector4(356.92, -1026.87, 29.65, 84.79), stand = vector3(356.89, -1026.31, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    { coords = vector4(355.32, -1027.0, 29.65, 269.12), stand = vector3(355.26, -1026.25, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},

    --Row4
    { coords = vector4(351.92, -1026.0, 29.65, 5.65), stand = vector3(352.57, -1026.1, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    { coords = vector4(351.83, -1024.24, 29.65, 180.44), stand = vector3(352.58, -1024.33, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},

    { coords = vector4(351.94, -1023.45, 29.65, 0.41), stand = vector3(352.52, -1023.54, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
    { coords = vector4(351.82, -1021.77, 29.65, 190.63), stand = vector3(352.55, -1021.88, 29.34), minZ = 28.0, maxZ = 30.15, w = 0.5, h = 0.5},
}
Config.Tables = {
    { name = "Rusty Table 01", coords = vector3(356.7, -1022.3, 29.0), heading = 236.53, minZ = 28.0, maxZ = 30.15, w = 0.7, h = 0.65, },
    { name = "Rusty Table 02", coords = vector3(359.26, -1022.3, 29.0), heading = 236.53, minZ = 28.0, maxZ = 30.15, w = 0.7, h = 0.65, },
    { name = "Rusty Table 03", coords = vector3(356.75, -1024.75, 29.0), heading = 236.53, minZ = 28.0, maxZ = 30.15, w = 0.7, h = 0.65, },
    { name = "Rusty Table 04", coords = vector3(359.23, -1024.75, 29.0), heading = 236.53, minZ = 28.0, maxZ = 30.15, w = 0.7, h = 0.65, },
    { name = "Rusty Table 05", coords = vector3(356.05, -1027.0, 29.0), heading = 236.53, minZ = 28.0, maxZ = 30.15, w = 0.7, h = 0.65, },
    { name = "Rusty Table 06", coords = vector3(358.59, -1027.0, 29.0), heading = 236.53, minZ = 28.0, maxZ = 30.15, w = 0.7, h = 0.65, },
    { name = "Rusty Table 07", coords = vector3(351.95, -1025.05, 29.0), heading = 92.05, minZ = 28.0, maxZ = 30.15, w = 0.7, h = 0.65, },
    { name = "Rusty Table 08", coords = vector3(351.95, -1022.63, 29.0), heading = 92.05, minZ = 28.0, maxZ = 30.15, w = 0.7, h = 0.65, },
    
}
Config.Billing = {
    { name = "Rusty's Billing Counter 1", coords = vec3(357.25, -1018.75, 29.7), heading = 0.0, minZ = 29.5, maxZ = 29.8, w = 0.5, h = 0.5, },
}
Config.Counter = {
    { name = "Rusty's Counter 01", coords = vector3(356.0, -1019.0, 29.5), heading = 0.0, minZ = 29.3, maxZ = 29.55, w = 0.5, h = 0.7, },
}
--This is Used When Config.RemoveMarkers = true
Config.TargetCoords = {
    Fridge = {
    { name = ""..Config.Jobname.." Fridge", coords =vector3(355.15, -1010.5, 29.4),heading=0.0, minZ = 28.9, maxZ = 29.5, w = 0.8, h = 0.65, }
    },
    Management = {
        { name = ""..Config.Jobname.." Management", coords =vec3(357.0, -1013.25, 29.25),heading=0.0, minZ = 29.10, maxZ = 29.30, w = 0.5, h = 0.5, }
    },
    Process = {
        { name = ""..Config.Jobname.." Process", coords =vec3(357.0, -1015.5, 29.25),heading=0.0, minZ = 29.10, maxZ = 29.30, w = 0.5, h = 0.5, }
    },
    Stash = {
        { name = ""..Config.Jobname.." Stash", coords =vec3(352.75, -1008.0, 29.25),heading=0.0, minZ = 29.10, maxZ = 29.30, w = 0.5, h = 1, }
    },
    BossMenu = {
        { name = ""..Config.Jobname.." BossMenu", coords =vec3(359.05, -1008.2, 29.25),heading=0.0, minZ = 29.20, maxZ = 29.30, w = 0.55, h = 0.25, }
    },
    Clothing = {
        { name = ""..Config.Jobname.." Clothing", coords =vector3(356.0, -1008.75, 29.25),heading=0.0, minZ = 28.8, maxZ = 29.30, w = 0.5, h = 0.5, }
    }
}
```

