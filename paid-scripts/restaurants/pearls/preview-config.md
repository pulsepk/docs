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
    BlipName = "Pearls", --Blip Name
    Enable = true,
    Coords = vector3(-1835.59, -1190.72, 14.31),
    Options = {
        Sprite = 267,
        Color = 3,
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
Config.Jobname = 'pearls' -- Job Name
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
        Coords = vector3(-1837.65, -1186.79, 14.31),
    },
    management = vector3(-1839.95, -1192.68, 14.32), --Where you can manage your shop
    fridge = vector3(-1844.59, -1199.18, 14.31), -- From where you will buy ingrediants
    process = vector3(-1844.3, -1194.62, 14.31), --From where you will start making items
    shop = { --Shop buy menu
    vector3(-1834.02, -1191.02, 14.31),
    },
    storagestash = vector3(-1841.52, -1185.79, 14.31),
    bossmenu = vector3(-1840.16, -1182.86, 14.31),
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
    ItemOrder = { --This Should Matches the Category Name
        "Fish",
        "Appetizers",
        "Beverages",
        "Coffee",
    },
    categories = {
        Fish = { 
            label = "Fish", --Donot Change
            icon = "fas fa-cookie-bite",
            workingcoords = vector3(-1847.16, -1198.95, 14.31),
            
            items = {
                pearl_grill_salmon = {
                    label="Grilled Salmon",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_fillet', label="Fillet", quantity = 1},
                    {item = 'pearl_garlic_butter', label="Garlic Butter Special Sauce", quantity = 1},
				    },
                },
                pearl_seared_cod  = {
                    label="Seared Cod ",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_fillet', label="Fillet", quantity = 1},
                    {item = 'pearl_herb', label="Herb sauce", quantity = 1},
				    },
                },
                pearl_tilapia = {
                    label="Tilapia",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_fillet', label="Fillet", quantity = 1},
                    {item = 'pearl_parmesan_cheese', label="Parmesan cheese", quantity = 1},
				    },
                },
                pearl_red_snapper = {
                    label="Red Snapper",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_fillet', label="Fillet", quantity = 1},
                    {item = 'pearl_blackening_seaon', label="Blackening seasoning ", quantity = 1},
				    },
                },
                pearl_fish_chips = {
                    label="Fish and Chips",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_fillet', label="Fillet", quantity = 1},
                    {item = 'pearl_beer_batter', label="Beer Batter", quantity = 1},
				    },
                },
                pearl_salsa = {
                    label="Mango Salsa",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_fillet', label="Fillet", quantity = 1},
                    {item = 'pearl_mango_salsa', label="Mango salsa", quantity = 1},
				    },
                },
                pearl_sea_bass = {
                    label="Sea Bass",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_fillet', label="Fillet", quantity = 1},
                    {item = 'pearl_ginger', label="Ginger", quantity = 1},
				    },
                },
                pearl_tacos = {
                    label="Tacos",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_fillet', label="Fillet", quantity = 1},
                    {item = 'pearl_lime_slaw', label="Lime Slaw", quantity = 1},
				    },
                },
                pearl_broiled_halibut = {
                    label="Broiled Halibut",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_fillet', label="Fillet", quantity = 1},
                    {item = 'pearl_lemon_sauce', label="Lemon dill sauce", quantity = 1},
				    },
                },
                pearl_swordfish_steak = {
                    label="Swordfish Steak",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_fillet', label="Fillet", quantity = 1},
                    {item = 'pearl_pesto', label="Pesto", quantity = 1},
				    },
                },
            }
        },        
        Appetizers= { 
            label = "Appetizers", --Donot Change
            icon = "fas fa-glass-martini-alt",
            workingcoords = vector3(-1844.32, -1196.83, 14.31),
            items = {
                pearl_ceviche = {
                    label="Fish Ceviche",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_lemon',label="Lemon", quantity = 1},
                    {item = 'pearl_cilantro', label="Cilantro", quantity = 1},
				    },
                },
                pearl_salmon = {
                    label="Smoked Salmon Crostini",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_lemon',label="Lemon", quantity = 1},
                    {item = 'pearl_crostini', label="Crispy Bread", quantity = 1},
				    },
                },
                pearl_tartar = {
                    label="Fish Tartar",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_lemon',label="Lemon", quantity = 1},
                    {item = 'pearl_soy_sauce', label="Soy Sauce", quantity = 1},
				    },
                },
                pearl_fish_cake = {
                    label="Fish Cakes",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_lemon',label="Lemon", quantity = 1},
                    {item = 'pearl_aioli', label="Aioli", quantity = 1},
				    },
                },
                pearl_shrimp = {
                    label="Shrimp Cocktail",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_lemon',label="Lemon", quantity = 1},
                    {item = 'pearl_cocktail_sauce', label="Cocktail Sauce", quantity = 1},
				    },
                },
                pearl_bruschetta = {
                    label="Anchovy Bruschetta",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_lemon',label="Lemon", quantity = 1},
                    {item = 'pearl_garlic', label="Garlic", quantity = 1},
                    },
                },
                pearl_skewers = {
                    label="Fish Skewers",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_lemon',label="Lemon", quantity = 1},
                    {item = 'pearl_chilli_sauce', label="Chili Sauce", quantity = 1},
				    },
                },
                pearl_samosa = {
                    label="Fish Samosas",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_lemon',label="Lemon", quantity = 1},
                    {item = 'pearl_tumeric', label="Tumeric", quantity = 1},
				    },
                },
                pearl_calamari = {
                    label="Calamari",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_lemon',label="Lemon", quantity = 1},
                    {item = 'pearl_wedges', label="Wedges ", quantity = 1},
				    },
                },
                pearl_tuna_bites = {
                    label="Tuna Poke Bites",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_lemon',label="Lemon", quantity = 1},
                    {item = 'pearl_poke_sauce', label="Poke Sauce", quantity = 1},
				    },
                },
            }
        },
        Beverages = { 
            label = "Beverages", --Donot Change
            icon = "fas fa-bread-slice",
            workingcoords = vector3(-1848.67, -1197.98, 14.31),
            items = {
                pearl_lemonade = {
                    label="Freshly Squeezed Lemonade",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_ice',label="Ice", quantity = 1},
                    {item = 'pearl_lemon',label="Lemon", quantity = 1},
				    },
                },
                pearl_iced_tea = {
                    label="Iced Green Tea",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'pearl_ice',label="Ice", quantity = 1},
                    {item = 'pearl_honey',label="Honey", quantity = 1},
				    },
                },
                pearl_citrus_water = {
                    label="Sparkling Water",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'pearl_ice',label="Ice", quantity = 1},
                    {item = 'pearl_citrus',label="Citrus Slices", quantity = 1},
				    },
                },
                pearl_fruit = {
                    label="Fruit Punch",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'pearl_ice',label="Ice", quantity = 1},
                    {item = 'pearl_mixed_fruit',label="Mixed Fruit Juice", quantity = 1},
				    },
                },
                pearl_hibiscus_tea = {
                    label="Hibiscus Tea",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'pearl_ice',label="Ice", quantity = 1},
                    {item = 'pearl_lemon',label="Lemon", quantity = 1},
				    },
                },
                pearl_coconut_water = {
                    label="Fresh Coconut Water",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
                    {item = 'pearl_ice',label="Ice", quantity = 1},
                    {item = 'pearl_coconut',label="Coconut", quantity = 1},
				    },
                },
                pearl_ale = {
                    label="Ginger Ale",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_ice',label="Ice", quantity = 1},
                    {item = 'pearl_sugar',label="Sugar", quantity = 1},
				    },
                },
                pearl_lemon_mint = {
                    label="Lemon and Mint",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_ice',label="Ice", quantity = 1},
                    {item = 'pearl_mint',label="Mint", quantity = 1},
				    },
                },
                pearl_kombucha = {
                    label="Kombucha",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_ice',label="Ice", quantity = 1},
                    {item = 'pearl_ginger',label="Ginger", quantity = 1},
				    },
                },
                pearl_pineapple_juice = {
                    label="Pineapple Juice",
                    price = 50, --For Starting Price
                    reward = 1, --item reward on completing
                    duration = 10000,
                    required = {  -- required items for crafting
					{item = 'pearl_ice',label="Ice", quantity = 1},
                    {item = 'pearl_pineapple',label="Pineapple", quantity = 1},
				    },
                },
            }
        },      
        Coffee = {
            label = "Coffee", -- Do not change
            icon = "fas fa-box",
            workingcoords = vector3(-1848.06, -1197.0, 14.31),
            items = {
                pearl_espresso = {
                    label = "Espresso", 
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'pearl_coffee_beans',label="Coffee Beans", quantity = 5},
                    {item = 'pearl_lemon',label="Lemon", quantity = 5},
                    },
                },
                pearl_americano = {
                    label = "Americano",  
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'pearl_coffee_beans',label="Coffee Beans", quantity = 5},
                    {item = 'pearl_almond',label='Almond Milk', quantity = 5},
                    },
                },
                pearl_cappuccino = {
                    label = "Cappuccino",  
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'pearl_coffee_beans',label="Coffee Beans", quantity = 5},
                    {item = 'pearl_dark_chocolate',label='Dark Chocolate', quantity = 5},
                    },
                },
                pearl_latte = {
                    label = "Latte", 
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'pearl_coffee_beans',label="Coffee Beans", quantity = 5},
                    {item = 'pearl_vanilla_syrup',label='Vanilla Syrup', quantity = 5},
                    },
                },
                pearl_mocha = {
                    label = "Mocha", 
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'pearl_coffee_beans',label="Coffee Beans", quantity = 5},
                    {item = 'pearl_chocolate_syrup',label='Chocolate Syrup  ', quantity = 5},
                    },
                },
                pearl_iced_coffee = {
                    label = "Iced Coffee", 
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'pearl_coffee_beans',label="Coffee Beans", quantity = 5},
                    {item = 'pearl_whipped_cream',label='Whipped Cream', quantity = 5},
                    },
                },
                pearl_brew = {
                    label = "Iced Brew", 
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'pearl_coffee_beans',label="Coffee Beans", quantity = 5},
                    {item = 'pearl_cinnamon_stick',label='Cinnamon Sticks', quantity = 5},
                    },
                },
                pearl_macchiato = {
                    label = "Macchiato", 
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'pearl_coffee_beans',label="Coffee Beans", quantity = 5},
                    {item = 'pearl_caramel_syrup',label='Caramel Syrup', quantity = 5},
                    },
                },
                pearl_flat_white = {
                    label = "Flat White", 
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'pearl_coffee_beans',label="Coffee Beans", quantity = 5},
                    {item = 'pearl_hazelnut_syrup',label='Hazelnut Syrup', quantity = 5},
                    },
                },
                pearl_affogato = {
                    label = "Affogato", 
                    price = 50, -- For starting price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = { -- Required items for crafting
                    {item = 'pearl_coffee_beans',label="Coffee Beans", quantity = 5},
                    {item = 'pearl_vanilla_icecream',label='Vanilla Ice Cream', quantity = 5},
                    },
                },
            },
        },
    },
}
Config.Chairs = {
    --Seating
    --1st Row Right Side
    {coords = vector4(-1833.80, -1195.86, 14.30, 244.25),stand =vector3(-1833.27, -1194.94, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1832.31, -1196.75, 14.30, 60.26),stand =vector3(-1831.71, -1195.7, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},

    {coords = vector4(-1831.92, -1197.12, 14.30, 240.89),stand =vector3(-1831.32, -1195.96, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1830.48, -1198.06, 14.30, 62.45),stand =vector3(-1829.76, -1196.94, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},

    {coords = vector4(-1829.95, -1198.24, 14.30, 239.68),stand =vector3(-1829.29, -1197.1, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1828.48, -1199.14, 14.30, 62.45),stand =vector3(-1827.88, -1197.99, 14.3), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    
    {coords = vector4(-1827.98, -1199.33, 14.30, 240.6),stand =vector3(-1827.27, -1198.29, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1826.47, -1200.15, 14.30, 62.45),stand =vector3(-1825.76, -1199.16, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},

    --1st Row Left Side
    {coords = vector4(-1832.10, -1192.93, 14.30, 241.08),stand =vector3(-1832.3, -1193.69, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1828.74, -1194.82, 14.30, 63.71),stand =vector3(-1829.39, -1195.5, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1830.83, -1192.74, 14.30, 148),stand =vector3(-1830.36, -1193.73, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1829.18, -1193.70, 14.30, 148),stand =vector3(-1830.36, -1193.73, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},

    {coords = vector4(-1825.30, -1195.95, 14.30, 148),stand =vector3(-1826.16, -1196.07, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1824.82, -1197.09, 14.30, 63.71),stand =vector3(-1825.18, -1198.02, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    --2nd Row Left Side
    {coords = vector4(-1829.18, -1187.91, 14.30, 243.26),stand =vector3(-1829.8, -1188.96, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1827.75, -1188.73, 14.30, 60.73),stand =vector3(-1828.27, -1189.9, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},

    {coords = vector4(-1827.21, -1188.96, 14.30, 240.49),stand =vector3(-1827.95, -1190.01, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1825.74, -1189.98, 14.30, 60.72),stand =vector3(-1826.37, -1191.02, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},

    {coords = vector4(-1825.35, -1190.24, 14.30, 241.07),stand =vector3(-1825.78, -1191.25, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1823.77, -1190.97, 14.30, 62.32),stand =vector3(-1824.35, -1192.08, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},

    {coords = vector4(-1823.31, -1191.24, 14.30, 240.16),stand =vector3(-1823.97, -1192.28, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1821.87, -1192.21, 14.30, 65.3),stand =vector3(-1822.54, -1193.1, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    
    --2nd Right Side
    {coords = vector4(-1830.91, -1191.13, 14.30, 241.62),stand =vector3(-1830.44, -1190.27, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1830.44, -1192.15, 14.30, 335.3),stand =vector3(-1829.34, -1192.14, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},

    {coords = vector4(-1826.86, -1193.25, 14.30, 240.45),stand =vector3(-1826.42, -1192.54, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1826.39, -1194.437, 14.30, 331.36),stand =vector3(-1825.36, -1194.34, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1824.84, -1195.26, 14.30, 337.67),stand =vector3(-1825.36, -1194.34, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
    {coords = vector4(-1823.59, -1195.21, 14.30, 63.71),stand =vector3(-1823.33, -1194.33, 14.31), minZ = 13.9, maxZ = 14.4, w = 0.3, h = 0.45},
}

Config.Tables = {
   { name = "Pearls Table 01", coords = vector3(-1833.15, -1196.52, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 0.9, h = 2, },
   { name = "Pearls Table 02", coords = vector3(-1831.15, -1197.52, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 0.9, h = 2, },
   { name = "Pearls Table 03", coords = vector3(-1829.15, -1198.52, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 0.9, h = 2, },
   { name = "Pearls Table 04", coords = vector3(-1827.25, -1199.62, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 0.9, h = 2, },
   
   { name = "Pearls Table 05", coords = vec3(-1828.44, -1188.33, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 0.9, h = 2, },
   { name = "Pearls Table 06", coords = vec3(-1826.41, -1189.38, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 0.9, h = 2, },
   { name = "Pearls Table 07", coords = vec3(-1824.52, -1190.59, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 0.9, h = 2, },
   { name = "Pearls Table 08", coords = vec3(-1822.51, -1191.46, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 0.9, h = 2, },

   { name = "Pearls Table 09", coords = vec3(-1831.19, -1193.43, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 1, h = 1, },
   { name = "Pearls Table 10", coords = vec3(-1829.63, -1194.34, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 1, h = 1, },
   { name = "Pearls Table 11", coords = vec3(-1825.63, -1196.72, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 1, h = 1, },

   
   { name = "Pearls Table 12", coords = vec3(-1830.04, -1191.51, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 1, h = 1, },
   { name = "Pearls Table 13", coords = vector3(-1826.12, -1193.79, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 1, h = 1, },
   { name = "Pearls Table 14", coords = vector3(-1824.51, -1194.69, 14.1), heading = 150, minZ = 13.45, maxZ = 14.2, w = 1, h = 1, },
}
Config.Billing = {
    { name = "Pearls Billing Counter 1", coords = vector3(-1835.18, -1191.73, 14.53), heading = 330, minZ = 14.4, maxZ = 14.64, w = 0.4, h = 0.25, },
    { name = "Pearls Billing Counter 2", coords = vector3(-1834.11, -1190.01, 14.53), heading = 330, minZ = 14.4, maxZ = 14.64, w = 0.4, h = 0.25, },
}
Config.Counter = {
{ name = "Pearls Counter 01", coords = vector3(-1834.66, -1190.83, 14.43), heading = 330, minZ = 14.3, maxZ = 14.64, w = 0.4, h = 0.25, },
}
--This is Used When Config.RemoveMarkers = true
Config.TargetCoords = {
    Fridge = {
    { name = ""..Config.Jobname.." Fridge", coords =vector3(-1844.0, -1199.0, 14.5),heading=240, minZ = 14.1, maxZ = 14.6, w = 0.8, h = 0.8, }
    },
    Management = {
        { name = ""..Config.Jobname.." Management", coords =vec3(-1839.5, -1193.0, 14.3),heading=240, minZ = 14.1, maxZ = 14.4, w = 0.5, h = 0.5, }
    },
    Process = {
        { name = ""..Config.Jobname.." Process", coords =vec3(-1844.48, -1195.06, 14.35),heading=94.85, minZ = 14.1, maxZ = 14.4, w = 0.5, h = 0.6, }
    },
    Stash = {
        { name = ""..Config.Jobname.." Stash", coords =vec3(-1841.5, -1186.5, 14.0),heading=153.55, minZ = 13.8, maxZ = 14.2, w = 0.5, h = 0.6, }
    },
    BossMenu = {
        { name = ""..Config.Jobname.." BossMenu", coords =vec3(-1839.75, -1183.75, 14.0),heading=238.0, minZ = 13.9, maxZ = 14.2, w = 0.25, h = 0.75, }
    },
    Clothing = {
        { name = ""..Config.Jobname.." Clothing", coords =vector3(-1837.5, -1187.5, 14.3),heading=330.0, minZ = 14.0, maxZ = 14.4, w = 1.0, h = 0.5, }
    }
}
```

