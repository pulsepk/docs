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
    BlipName = "Horny Burgers", --Blip Name
    Enable = true,
    Coords = vector3(1242.684, -360.787, 69.082), 
    Options = {
        Sprite = 80,
        Color = 2,
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
Config.Jobname = 'hornyburgers' -- Job Name
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
        Coords = vector3(1245.38, -354.71, 69.08),
    },
    management = vector3(1252.841, -351.536, 69.082), --Where you can manage your shop
    fridge = vector3(1248.912, -352.507, 69.082), -- From where you will buy ingrediants
    process = vector3(1249.802, -354.943, 69.082), --From where you will start making items
    shop = {
        vector3(1249.382, -359.776, 69.082), --Shop buy menu
    },
    storagestash = vector3(1238.1, -351.61, 69.08),
    bossmenu = vector3(1238.393, -348.806, 69.082),
    Storage = {
		label = "Fridge",
		items = {
            Burgers = {
                { name = "hb_bun", label = "Burger Bun", price = 50, amount = 50},
                { name = "hb_sauce", label = "Horny Sauce", price = 50, amount = 50},
                { name = "hb_jalapeno_relish", label = "Jalapeno Relish", price = 50, amount = 50},
                { name = "hb_melted_cheddar", label = "Melted Cheddar", price = 50, amount = 50},
                { name = "hb_crispy_bacon", label = "Crispy Bacon", price = 50, amount = 50},
                { name = "hb_bbq_sauce", label = "Special BBQ Sauce", price = 50, amount = 50},
            },
            
            Drinks = {
                { name = "hb_chocolate_syrup", label = "Chocolate Syrup", price = 50, amount = 50},
                { name = "hb_caramel_drizzle", label = "Caramel Drizzle", price = 50, amount = 50},
                { name = "hb_honey", label = "Honey", price = 50, amount = 50},
                { name = "hb_citrus_blend", label = "Citrus Blend", price = 50, amount = 50},
                { name = "hb_milk", label = "Milk", price = 50, amount = 50},
                { name = "hb_coffee", label = "Coffee", price = 50, amount = 50},
                { name = "hb_mixed_berries", label = "Mixed Berries", price = 50, amount = 50},
                { name = "hb_caffeine_base", label = "Caffeine Base", price = 50, amount = 50},
            },
            
            Fries = {
                { name = "hb_potato_fries", label = "Potato Fries", price = 50, amount = 50},
                { name = "hb_sea_salt", label = "Sea Salt", price = 50, amount = 50},
                { name = "hb_melted_cheese", label = "Melted Cheese", price = 50, amount = 50},
                { name = "hb_sriracha", label = "Sriracha", price = 50, amount = 50},
                { name = "hb_crispy_bacon", label = "Crispy Bacon", price = 50, amount = 50},
                { name = "hb_sour_cream_chives", label = "Sour Cream & Chives", price = 50, amount = 50},
            },
            
            Sodas = {
                { name = "hb_carbonated_water", label = "Carbonated Water", price = 50, amount = 50},
                { name = "hb_cola_flavor", label = "Cola Flavoring", price = 50, amount = 50},
                { name = "hb_root_beer_extract", label = "Root Beer Extract", price = 50, amount = 50},
                { name = "hb_orange_syrup", label = "Orange Syrup", price = 50, amount = 50},
                { name = "hb_grape_syrup", label = "Grape Syrup", price = 50, amount = 50},
                { name = "hb_fresh_lemon", label = "Fresh Lemon", price = 50, amount = 50},
            },     
        }
	},
    ItemOrder = {
        "Burgers",
        "Drinks",
        "Fries",
        "Sodas",
    },
    categories = {
        Burgers = { 
            label = "Burgers", --Donot Change
            icon = "fas fa-pizza-slice",
            workingcoords = vector3(1252.712, -355.742, 69.082),
            
            items = {
                    hb_classic_burger = {
                        label = "Classic Burger",
                        price = 50, -- For Starting Price
                        reward = 1, -- Item reward on completing
                        duration = 10000,
                        required = {  -- Required items for crafting
                            {item = 'hb_bun', label = "Burger Bun", quantity = 1},
                            {item = 'hb_sauce', label = "Horny Sauce", quantity = 1},
                        },
                    },
                    hb_spicy_burger = {
                        label = "Spicy Burger",
                        price = 50, -- For Starting Price
                        reward = 1, -- Item reward on completing
                        duration = 10000,
                        required = {
                            {item = 'hb_bun', label = "Burger Bun", quantity = 1},
                            {item = 'hb_jalapeno_relish', label = "Jalapeno Relish", quantity = 1},
                        },
                    },
                    hb_cheesy_burger = {
                        label = "Cheesy Burger",
                        price = 50, -- For Starting Price
                        reward = 1, -- Item reward on completing
                        duration = 10000,
                        required = {
                            {item = 'hb_bun', label = "Burger Bun", quantity = 1},
                            {item = 'hb_melted_cheddar', label = "Melted Cheddar", quantity = 1},
                        },
                    },
                    hb_bacon_burger = {
                        label = "Bacon Burger",
                        price = 50, -- For Starting Price
                        reward = 1, -- Item reward on completing
                        duration = 10000,
                        required = {
                            {item = 'hb_bun', label = "Burger Bun", quantity = 1},
                            {item = 'hb_crispy_bacon', label = "Crispy Bacon", quantity = 1},
                        },
                    },
                    hb_double_burger = {
                        label = "Double Burger",
                        price = 50, -- For Starting Price
                        reward = 1, -- Item reward on completing
                        duration = 10000,
                        required = {
                            {item = 'hb_bun', label = "Burger Bun", quantity = 1},
                            {item = 'hb_bbq_sauce', label = "Special BBQ Sauce", quantity = 1},
                        },
                    },
                }
            },
                        
        Drinks= { 
            label = "Drinks", --Donot Change
            icon = "fas fa-utensils",
            workingcoords = vector3(1246.745, -357.033, 69.082),
            items = {
                hb_milkshake = {
                    label = "Milkshake",
                    price = 50, -- For Starting Price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = {  -- Required items for crafting
                        {item = 'hb_milk', label = "Milk", quantity = 1},
                        {item = 'hb_chocolate_syrup', label = "Chocolate Syrup", quantity = 1},
                    },
                },
                hb_iced_coffee = {
                    label = "Iced Coffee",
                    price = 50,
                    reward = 1,
                    duration = 10000,
                    required = {
                        {item = 'hb_coffee', label = "Coffee", quantity = 1},
                        {item = 'hb_caramel_drizzle', label = "Caramel Drizzle", quantity = 1},
                    },
                },
                hb_smoothie = {
                    label = "Smoothie",
                    price = 50,
                    reward = 1,
                    duration = 10000,
                    required = {
                        {item = 'hb_mixed_berries', label = "Mixed Berries", quantity = 1},
                        {item = 'hb_honey', label = "Honey", quantity = 1},
                    },
                },
                hb_energy_drink = {
                    label = "Energy Drink",
                    price = 50,
                    reward = 1,
                    duration = 10000,
                    required = {
                        {item = 'hb_caffeine_base', label = "Caffeine Base", quantity = 1},
                        {item = 'hb_citrus_blend', label = "Citrus Blend", quantity = 1},
                    },
               },
           }
        },
        Fries  = { 
            label = "Fries ", --Donot Change
            icon = "fas fa-seedling",
            workingcoords = vector3(1253.335, -353.398, 69.082),
            items = {
                    hb_classic_fries = {
                        label = "Classic Fries",
                        price = 50, -- For Starting Price
                        reward = 1, -- Item reward on completing
                        duration = 10000,
                        required = {  -- Required items for crafting
                            {item = 'hb_potato_fries', label = "Potato Fries", quantity = 1},
                            {item = 'hb_sea_salt', label = "Sea Salt", quantity = 1},
                        },
                    },
                    hb_cheesy_fries = {
                        label = "Cheesy Fries",
                        price = 50,
                        reward = 1,
                        duration = 10000,
                        required = {
                            {item = 'hb_potato_fries', label = "Potato Fries", quantity = 1},
                            {item = 'hb_melted_cheese', label = "Melted Cheese", quantity = 1},
                        },
                    },
                    hb_spicy_fries = {
                        label = "Spicy Fries",
                        price = 50,
                        reward = 1,
                        duration = 10000,
                        required = {
                            {item = 'hb_potato_fries', label = "Potato Fries", quantity = 1},
                            {item = 'hb_sriracha', label = "Sriracha", quantity = 1},
                        },
                    },
                    hb_bacon_fries = {
                        label = "Bacon Fries",
                        price = 50,
                        reward = 1,
                        duration = 10000,
                        required = {
                            {item = 'hb_potato_fries', label = "Potato Fries", quantity = 1},
                            {item = 'hb_crispy_bacon', label = "Crispy Bacon", quantity = 1},
                        },
                    },
                    hb_loaded_fries = {
                        label = "Loaded Fries",
                        price = 50,
                        reward = 1,
                        duration = 10000,
                        required = {
                            {item = 'hb_potato_fries', label = "Potato Fries", quantity = 1},
                            {item = 'hb_sour_cream_chives', label = "Sour Cream & Chives", quantity = 1},
                        },
                    },
                }
            },
                
        Sodas = {
            label = "Sodas", -- Do not change
            icon = "fas fa-bowl-food",
            workingcoords = vector3(1251.428, -361.194, 69.085),
            items = {
                hb_cola = {
                    label = "Cola",
                    price = 50, -- For Starting Price
                    reward = 1, -- Item reward on completing
                    duration = 10000,
                    required = {  -- Required items for crafting
                        {item = 'hb_carbonated_water', label = "Carbonated Water", quantity = 1},
                        {item = 'hb_cola_flavor', label = "Cola Flavoring", quantity = 1},
                    },
                },
                hb_root_beer = {
                    label = "Root Beer",
                    price = 50,
                    reward = 1,
                    duration = 10000,
                    required = {
                        {item = 'hb_carbonated_water', label = "Carbonated Water", quantity = 1},
                        {item = 'hb_root_beer_extract', label = "Root Beer Extract", quantity = 1},
                    },
                },
                hb_orange_soda = {
                    label = "Orange Soda",
                    price = 50,
                    reward = 1,
                    duration = 10000,
                    required = {
                        {item = 'hb_carbonated_water', label = "Carbonated Water", quantity = 1},
                        {item = 'hb_orange_syrup', label = "Orange Syrup", quantity = 1},
                    },
                },
                hb_grape_soda = {
                    label = "Grape Soda",
                    price = 50,
                    reward = 1,
                    duration = 10000,
                    required = {
                        {item = 'hb_carbonated_water', label = "Carbonated Water", quantity = 1},
                        {item = 'hb_grape_syrup', label = "Grape Syrup", quantity = 1},
                    },
                },
                hb_lemonlime = {
                    label = "Lemon Lime",
                    price = 50,
                    reward = 1,
                    duration = 10000,
                    required = {
                        {item = 'hb_carbonated_water', label = "Carbonated Water", quantity = 1},
                        {item = 'hb_fresh_lemon', label = "Fresh Lemon", quantity = 1},
                    },
                },
            }
        },
    },
}
Config.Chairs = {
    --TableSeating
	{ coords = vector4(1250.286, -363.353, 69.05, 172.927), stand = vector3(1249.511, -363.272, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
	{ coords = vector4(1251.263, -363.616, 69.05, 172.927), stand = vector3(1249.511, -363.272, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
	{ coords = vector4(1249.915, -365.232, 69.05, 339.613), stand = vector3(1249.13, -364.976, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
	{ coords = vector4(1250.791, -365.457, 69.05, 337.173), stand = vector3(1249.205, -364.952, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
	{ coords = vector4(1250.458, -366.162, 69.05, 166.417), stand = vector3(1248.917, -365.764, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
	{ coords = vector4(1249.632, -365.931, 69.05, 165.495), stand = vector3(1248.966, -365.823, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
	{ coords = vector4(1250.013, -367.991, 69.05, 351.317), stand = vector3(1248.302, -367.44, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
	{ coords = vector4(1249.239, -367.766, 69.05, 345.855), stand = vector3(1248.461, -367.532, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1244.574, -366.533, 69.05, 348.855), stand = vector3(1246.052, -366.822, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1245.312, -366.736, 69.05, 344.208), stand = vector3(1246.052, -366.822, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1245.029, -364.751, 69.05, 153.647), stand = vector3(1246.854, -365.21, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1245.947, -364.968, 69.05, 155.248), stand = vector3(1246.854, -365.21, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1245.083, -363.938, 69.05, 339.787), stand = vector3(1246.76, -364.383, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1245.883, -364.119, 69.05, 327.344), stand = vector3(1246.76, -364.383, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1245.611, -362.089, 69.05, 155.264), stand =vector3(1247.565, -362.617, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1246.551, -362.352, 69.05, 149.374), stand =vector3(1247.565, -362.617, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1240.546, -360.77, 69.05, 161.294), stand =vector3(1238.69, -360.37, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1239.62, -360.484, 69.05, 160.835), stand =vector3(1238.69, -360.37, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1239.951, -362.571, 69.05, 336.702), stand =vector3(1247.565, -362.617, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1239.071, -362.322, 69.05, 350.517), stand =vector3(1247.565, -362.617, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1239.992, -363.391, 69.05, 170.764), stand =vector3(1238.071, -362.838, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1238.988, -363.092, 69.05, 154.732), stand =vector3(1238.071, -362.838, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1239.447, -365.17, 69.05, 348.214), stand =vector3(1237.441, -364.44, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1238.46, -364.885, 69.05, 350.316), stand =vector3(1237.441, -364.44, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    --minitable seats
    { coords =vector4(1240.539, -353.813, 69.05, 67.723), stand =vector3(1240.166, -355.074, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1240.403, -354.333, 69.05, 65.345), stand =vector3(1240.166, -355.074, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1239.495, -353.336, 69.05, 241.042), stand =vector3(1239.059, -354.644, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1239.316, -354.007, 69.05, 260.33), stand =vector3(1239.059, -354.644, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1238.66, -353.894, 69.05, 83.828) , stand =vector3(1238.402, -354.495, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1238.836, -353.229, 69.05, 65.097) , stand =vector3(1238.402, -354.495, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1237.565, -353.604, 69.05, 252.954) , stand =vector3(1237.375, -354.252, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
    { coords =vector4(1237.735, -352.972, 69.05, 253.433), stand =vector3(1237.375, -354.252, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
   --Single seat by the window
   { coords = vector4(1235.077, -359.796, 69.432, 89.269), stand = vector3(1235.658, -359.904, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
   { coords = vector4(1236.338, -363.778, 69.432, 164.39), stand = vector3(1236.503, -363.2, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
   { coords = vector4(1235.37, -363.44, 69.432, 160.299), stand = vector3(1235.445, -362.917, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
   { coords = vector4(1234.387, -363.051, 69.432, 158.793), stand = vector3(1234.526, -362.564, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
   { coords = vector4(1234.6, -361.855, 69.432, 58.07), stand = vector3(1234.995, -361.987, 69.082-0.5) , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
   { coords = vector4(1234.907, -360.941, 69.432, 55.594), stand =    vector3(1235.231, -360.957, 69.082-0.5)   , minZ = 25.0, maxZ = 27.5, w = 0.5, h = 0.5},
}
Config.Tables = {
    { name = "Horny Table 01", coords = vec3(1246.015, -363.17, 68.9), heading = 345.0, minZ = 68.8, maxZ = 69.7, w = 2, h = 1, },
    { name = "Horny Table 02", coords = vector3(1245.154, -365.677, 68.9), heading = 345.0, minZ = 68.8, maxZ = 69.7, w = 2, h = 1, },
    { name = "Horny Table 03", coords = vector3(1249.799, -367.044, 68.9), heading = 345.0, minZ = 68.8, maxZ = 69.7, w = 2, h = 1, },
    { name = "Horny Table 04", coords = vector3(1250.515, -364.446, 68.9), heading = 345.0, minZ = 68.8, maxZ = 69.7, w = 2, h = 1, },
    { name = "Horny Table 05", coords = vector3(1239.76, -361.497, 68.9), heading = 345.0, minZ = 68.8, maxZ = 69.7, w = 2, h = 1, },
    { name = "Horny Table 06", coords = vector3(1239.052, -364.068, 68.9), heading = 345.0, minZ = 68.8, maxZ = 69.7, w = 2, h = 1, },
    --minitables
    { name = "Horny Table 07", coords = vector3(1239.939, -353.857, 68.9), heading = 345.0, minZ = 68.8, maxZ = 69.5, w = 0.55, h = 1.2, },
    { name = "Horny Table 08", coords = vector3(1238.141, -353.51, 68.9), heading = 345.0, minZ = 68.8, maxZ = 69.5, w = 0.55, h = 1.2, },
    --tables by window
    { name = "Horny Table 09", coords = vec3(1236.15, -364.3, 69.1), heading = 345.5, minZ = 69.00, maxZ = 69.50, w = 0.7, h = 0.5, },
    { name = "Horny Table 10", coords = vec3(1234.10, -363.80, 69.15), heading = 345.0, minZ = 69.00, maxZ = 69.50, w = 0.7, h = 0.5, },
    { name = "Horny Table 11", coords = vector3(1233.872, -361.744, 69.15), heading = 254.0, minZ = 69.00, maxZ = 69.50, w = 0.7, h = 0.5, },
    { name = "Horny Table 12", coords = vector3(1234.1, -360.65, 69.15), heading = 254.0, minZ = 69.00, maxZ = 69.50, w = 0.7, h = 0.5, },
}
Config.Billing = {
    { name = "Horny Burgers Billing Counter 1", coords = vec3(1248.02, -358.69, 69.0), heading = 165, minZ = 68.9, maxZ = 69.2, w = 0.5, h = 0.5, },
    { name = "Horny Burgers Billing Counter 2", coords = vector3(1249.404, -358.99, 69.0), heading = 165, minZ = 68.9, maxZ = 69.2, w = 0.5, h = 0.5, },
    { name = "Horny Burgers Billing Counter 3", coords = vector3(1250.66, -359.54, 69.0), heading = 165, minZ = 68.9, maxZ = 69.2, w = 0.5, h = 0.5, },
}
Config.Counter = {
    { name = "Horny Burgers Counter 01", coords = vector3(1250.105, -359.299, 69.0), heading = 165, minZ = 68.9, maxZ = 69.01, w = 0.5, h = 0.7, },
}
--This is Used When Config.RemoveMarkers = true
Config.TargetCoords = {
    Fridge = {
    { name = ""..Config.Jobname.." Fridge", coords =vector3(1249.0, -352.25, 68.85),heading=345.0, minZ = 68.50, maxZ = 69.45, w = 0.5, h = 1.5, }
    },
    Management = {
        { name = ""..Config.Jobname.." Management", coords =vec3(1253.0, -351.0, 69.0),heading=345.0, minZ = 68.9, maxZ = 69.05, w = 0.5, h = 0.5, }
    },
    Process = {
        { name = ""..Config.Jobname.." Process", coords =vec3(1249.5, -355.5, 69.0),heading=345.0, minZ = 68.9, maxZ = 69.05, w = 0.5, h = 0.5, }
    },
    Stash = {
        { name = ""..Config.Jobname.." Stash", coords =vec3(1238.0, -352.0, 69.0),heading=345.0, minZ = 68.9, maxZ = 69.05, w = 0.5, h = 0.5, }
    },
    BossMenu = {
        { name = ""..Config.Jobname.." BossMenu", coords =vec3(1239.05, -348.4, 69.0),heading=345.0, minZ = 68.9, maxZ = 69.05, w = 0.15, h = 0.5, }
    },
    Clothing = {
        { name = ""..Config.Jobname.." Clothing", coords =vector3(1246.0, -355.0, 69.0),heading=345.0, minZ = 68.9, maxZ = 69.05, w = 1.0, h = 1.0, }
    }
}

```

