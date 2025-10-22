# Installation

### Dependencies

Make Sure all the dependencies are installed.

Required

[<kbd>ox\_lib</kbd>](https://github.com/overextended/ox_lib)

[<kbd>ox-target</kbd>](https://github.com/overextended/ox_target) <kbd>or</kbd> [<kbd>qb-target</kbd>](https://github.com/qbcore-framework/qb-target)

### Config Setup

Adjust config.lua according to your liking

Make sure to set your map, target, clothing, billing, society script

### SQL Installation

Use this if AutoInstallSQL Fails for some reason and doesn't generates the sql database

<details>

<summary>ESX</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_diner` (
   `stock` longtext DEFAULT NULL,
   `state` varchar(5) NOT NULL DEFAULT 'open'
 ) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;

 INSERT INTO `addon_account` (name, label, shared) VALUES
        ('society_diner', 'Diner', 1);

 INSERT INTO `datastore` (name, label, shared) VALUES
        ('society_diner', 'Diner', 1);

INSERT INTO `jobs` (name, label,whitelisted) VALUES
        ('diner', 'Diner',1);

 INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
        ('diner',0,'cashier','Cashier',20,'{}','{}'),
        ('diner',1,'cook','Cook',40,'{}','{}'),
        ('diner',2,'staff','Staff',60,'{}','{}'),
        ('diner',3,'manager','Manager',85,'{}','{}'),
        ('diner',4,'boss','Owner',100,'{}','{}');
```

</details>

<details>

<summary>QBCore or Qbox</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_diner` (
    `stock` LONGTEXT DEFAULT NULL,
    `state` VARCHAR(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;
```

</details>

### Items

Add the items into your server

<details>

<summary>Ox Inventory</summary>

```lua
["diner_classic_burger"] = {
    label = "Classic Burger",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_cheddar_burger"] = {
    label = "Cheddar Burger",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_bacon_burger"] = {
    label = "Bacon Burger",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_spicy_burger"] = {
    label = "Spicy Burger",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_double_burger"] = {
    label = "Double Burger",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_chicken_sandwich"] = {
    label = "Chicken Club Sandwich",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_blt_sandwich"] = {
    label = "BLT Sandwich",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_turkey_avocado_sandwich"] = {
    label = "Turkey Sandwich",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_roast_beef_sandwich"] = {
    label = "Roast Beef Sandwich",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_veggie_sandwich"] = {
    label = "Veggie Sandwich",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_classic_fries"] = {
    label = "Classic Fries",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_cheesy_fries"] = {
    label = "Cheesy Fries",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_chili_fries"] = {
    label = "Chili & Cheese",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_curly_fries"] = {
    label = "Curly Fries",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_loaded_fries"] = {
    label = "Loaded Fries",
    weight = 1,
     client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["diner_vanilla_milkshake"] = {
    label = "Vanilla Milkshake",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},

["diner_chocolate_milkshake"] = {
    label = "Chocolate Milkshake",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},

["diner_strawberry_milkshake"] = {
    label = "Strawberry Milkshake",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},

["diner_caramel_milkshake"] = {
    label = "Caramel Milkshake",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},

["diner_oreo_milkshake"] = {
    label = "Oreo Milkshake",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},

["diner_beef_patty"] = {
    label = "Beef Patty",
    weight = 1,
    stack = true,
    close = true,
},

["diner_sauce"] = {
    label = "Diner Sauce",
    weight = 1,
    stack = true,
    close = true,
},

["diner_melted_cheddar"] = {
    label = "Melted Cheddar",
    weight = 1,
    stack = true,
    close = true,
},

["diner_crispy_bacon"] = {
    label = "Crispy Bacon",
    weight = 1,
    stack = true,
    close = true,
},

["diner_hot_pepper_relish"] = {
    label = "Hot Pepper Relish",
    weight = 1,
    stack = true,
    close = true,
},

["diner_double_special_sauce"] = {
    label = "Double Special Sauce",
    weight = 1,
    stack = true,
    close = true,
},

["diner_sandwich_bread"] = {
    label = "Sandwich Bread",
    weight = 1,
    stack = true,
    close = true,
},

["diner_grilled_chicken"] = {
    label = "Grilled Chicken",
    weight = 1,
    stack = true,
    close = true,
},

["diner_avocado_spread"] = {
    label = "Crispy Bacon",
    weight = 1,
    stack = true,
    close = true,
},

["diner_roast_beef"] = {
    label = "Roast Beef",
    weight = 1,
    stack = true,
    close = true,
},

["diner_veggie_patty"] = {
    label = "Veggie Patty",
    weight = 1,
    stack = true,
    close = true,
},

["diner_fries"] = {
    label = "Fries",
    weight = 1,
    stack = true,
    close = true,
},

["diner_sea_salt"] = {
    label = "Sea Salt",
    weight = 1,
    stack = true,
    close = true,
},

["diner_cheddar_sauce"] = {
    label = "Cheddar Sauce",
    weight = 1,
    stack = true,
    close = true,
},

["diner_chili_cheese"] = {
    label = "Chili & Cheese",
    weight = 1,
    stack = true,
    close = true,
},

["diner_seasoning"] = {
    label = "Diner Seasoning",
    weight = 1,
    stack = true,
    close = true,
},

["diner_loaded_toppings"] = {
    label = "Loaded Toppings",
    weight = 1,
    stack = true,
    close = true,
},

["diner_milk"] = {
    label = "Milk",
    weight = 1,
    stack = true,
    close = true,
},

["diner_vanilla_extract"] = {
    label = "Vanilla Extract",
    weight = 1,
    stack = true,
    close = true,
},

["diner_chocolate_syrup"] = {
    label = "Chocolate Syrup",
    weight = 1,
    stack = true,
    close = true,
},

["diner_strawberry_puree"] = {
    label = "Strawberry Puree",
    weight = 1,
    stack = true,
    close = true,
},

["diner_caramel_sauce"] = {
    label = "Caramel Sauce",
    weight = 1,
    stack = true,
    close = true,
},

["diner_bun"] = {
    label = "Burger Bun",
    weight = 1,
    stack = true,
    close = true,
},

["diner_emptycup"] = {
    label = "Diner Empty Cup",
    weight = 1,
    stack = true,
    close = true,
},

["diner_waterbottle"] = {
    label = "Diner WaterBottle",
    weight = 1,
    stack = true,
    close = true,
},

["diner_icecubes"] = {
    label = "Diner Ice Cubes",
    weight = 1,
    stack = true,
    close = true,
},

["diner_crushed_oreos"] = {
    label = "Crushed Oreos",
    weight = 1,
    stack = true,
    close = true,
},
```

</details>

<details>

<summary>QB Inventory</summary>

```lua

--Diner
['diner_classic_burger'] = {['name'] = 'diner_classic_burger', ['label'] = 'Classic Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_classic_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_cheddar_burger'] = {['name'] = 'diner_cheddar_burger', ['label'] = 'Cheddar Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_cheddar_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_bacon_burger'] = {['name'] = 'diner_bacon_burger', ['label'] = 'Bacon Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_bacon_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_spicy_burger'] = {['name'] = 'diner_spicy_burger', ['label'] = 'Spicy Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_spicy_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_double_burger'] = {['name'] = 'diner_double_burger', ['label'] = 'Double Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_double_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_chicken_sandwich'] = {['name'] = 'diner_chicken_sandwich', ['label'] = 'Chicken Club Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_chicken_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_blt_sandwich']     = {['name'] = 'diner_blt_sandwich',     ['label'] = 'BLT Sandwich',         ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_blt_sandwich.png',     ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_turkey_avocado_sandwich']  = {['name'] = 'diner_turkey_avocado_sandwich',  ['label'] = 'Turkey Avocado Sandwich',      ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_turkey_avocado_sandwich.png',  ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_roast_beef_sandwich'] = {['name'] = 'diner_roast_beef_sandwich', ['label'] = 'Roast Beef Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_roast_beef_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_veggie_sandwich'] = {['name'] = 'diner_veggie_sandwich', ['label'] = 'Veggie Sandwich',       ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_veggie_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_classic_fries'] = {['name'] = 'diner_classic_fries', ['label'] = 'Classic Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_classic_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_cheesy_fries']  = {['name'] = 'diner_cheesy_fries',  ['label'] = 'Cheesy Fries',  ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_cheesy_fries.png',  ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_chili_fries']   = {['name'] = 'diner_chili_fries',   ['label'] = 'Chili & Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_chili_fries.png',   ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_curly_fries']   = {['name'] = 'diner_curly_fries',   ['label'] = 'Curly Fries',    ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_curly_fries.png',   ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_loaded_fries']  = {['name'] = 'diner_loaded_fries',  ['label'] = 'Loaded Fries',   ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_loaded_fries.png',  ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_vanilla_milkshake']   = {['name'] = 'diner_vanilla_milkshake',   ['label'] = 'Vanilla Milkshake',   ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_vanilla_milkshake.png',   ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_chocolate_milkshake'] = {['name'] = 'diner_chocolate_milkshake', ['label'] = 'Chocolate Milkshake', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_chocolate_milkshake.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_strawberry_milkshake']= {['name'] = 'diner_strawberry_milkshake',['label'] = 'Strawberry Milkshake',['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_strawberry_milkshake.png',['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_caramel_milkshake']   = {['name'] = 'diner_caramel_milkshake',   ['label'] = 'Caramel Milkshake',   ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_caramel_milkshake.png',   ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_oreo_milkshake']      = {['name'] = 'diner_oreo_milkshake',      ['label'] = 'Oreo Milkshake',      ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_oreo_milkshake.png',      ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
--Ingredients--
['diner_bun'] = {['name'] = 'diner_bun', ['label'] = 'Bun', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_bun.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_beef_patty'] = {['name'] = 'diner_beef_patty', ['label'] = 'Beef Patty', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_beef_patty.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_sauce'] = {['name'] = 'diner_sauce', ['label'] = 'Diner Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_melted_cheddar'] = {['name'] = 'diner_melted_cheddar', ['label'] = 'Melted Cheddar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_melted_cheddar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_crispy_bacon'] = {['name'] = 'diner_crispy_bacon', ['label'] = 'Crispy Bacon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_crispy_bacon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_hot_pepper_relish'] = {['name'] = 'diner_hot_pepper_relish', ['label'] = 'Hot Pepper Relish', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_hot_pepper_relish.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_double_special_sauce'] = {['name'] = 'diner_double_special_sauce', ['label'] = 'Double Special Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_double_special_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_sandwich_bread'] = {['name'] = 'diner_sandwich_bread', ['label'] = 'Sandwich Bread', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_sandwich_bread.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_grilled_chicken'] = {['name'] = 'diner_grilled_chicken', ['label'] = 'Grilled Chicken', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_grilled_chicken.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_crispy_bacon'] = {['name'] = 'diner_crispy_bacon', ['label'] = 'Crispy Bacon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pd_horseradish_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_avocado_spread'] = {['name'] = 'diner_avocado_spread', ['label'] = 'Avocado Spread', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_crispy_bacon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_roast_beef'] = {['name'] = 'diner_roast_beef', ['label'] = 'Roast Beef', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_roast_beef.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_veggie_patty'] = {['name'] = 'diner_veggie_patty', ['label'] = 'Veggie Patty', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_veggie_patty.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_fries'] = {['name'] = 'diner_fries', ['label'] = 'Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_fries.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_sea_salt'] = {['name'] = 'diner_sea_salt', ['label'] = 'Sea Salt', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_sea_salt.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_cheddar_sauce'] = {['name'] = 'diner_cheddar_sauce', ['label'] = 'Cheddar Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_cheddar_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_chili_cheese'] = {['name'] = 'diner_chili_cheese', ['label'] = 'Chili & Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_chili_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_seasoning'] = {['name'] = 'diner_seasoning', ['label'] = 'Diner Seasoning', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_seasoning.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_loaded_toppings'] = {['name'] = 'diner_loaded_toppings', ['label'] = 'Loaded Toppings', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_loaded_toppings.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_milk'] = {['name'] = 'diner_milk', ['label'] = 'Milk', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_milk.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_vanilla_extract'] = {['name'] = 'diner_vanilla_extract', ['label'] = 'Vanilla Extract', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_vanilla_extract.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_chocolate_syrup'] = {['name'] = 'diner_chocolate_syrup', ['label'] = 'Chocolate Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_chocolate_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_strawberry_puree'] = {['name'] = 'diner_strawberry_puree', ['label'] = 'Strawberry Puree', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_strawberry_puree.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_caramel_sauce'] = {['name'] = 'diner_caramel_sauce', ['label'] = 'Caramel Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_caramel_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_crushed_oreos'] = {['name'] = 'diner_crushed_oreos', ['label'] = 'Crushed Oreos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_crushed_oreos.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_bun'] = {['name'] = 'diner_bun', ['label'] = 'Burger Bun', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_bun.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_emptycup'] = {['name'] = 'diner_emptycup', ['label'] = 'Diner Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_waterbottle'] = {['name'] = 'diner_waterbottle', ['label'] = 'Diner WaterBottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_icecubes'] = {['name'] = 'diner_icecubes', ['label'] = 'Diner Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>Quasar Inventory</summary>

```lua

--Diner
['diner_classic_burger'] = {['name'] = 'diner_classic_burger', ['label'] = 'Classic Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_classic_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_cheddar_burger'] = {['name'] = 'diner_cheddar_burger', ['label'] = 'Cheddar Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_cheddar_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_bacon_burger'] = {['name'] = 'diner_bacon_burger', ['label'] = 'Bacon Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_bacon_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_spicy_burger'] = {['name'] = 'diner_spicy_burger', ['label'] = 'Spicy Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_spicy_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_double_burger'] = {['name'] = 'diner_double_burger', ['label'] = 'Double Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_double_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_chicken_sandwich'] = {['name'] = 'diner_chicken_sandwich', ['label'] = 'Chicken Club Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_chicken_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_blt_sandwich']     = {['name'] = 'diner_blt_sandwich',     ['label'] = 'BLT Sandwich',         ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_blt_sandwich.png',     ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_turkey_avocado_sandwich']  = {['name'] = 'diner_turkey_avocado_sandwich',  ['label'] = 'Turkey Avocado Sandwich',      ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_turkey_avocado_sandwich.png',  ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_roast_beef_sandwich'] = {['name'] = 'diner_roast_beef_sandwich', ['label'] = 'Roast Beef Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_roast_beef_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_veggie_sandwich'] = {['name'] = 'diner_veggie_sandwich', ['label'] = 'Veggie Sandwich',       ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_veggie_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_classic_fries'] = {['name'] = 'diner_classic_fries', ['label'] = 'Classic Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_classic_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_cheesy_fries']  = {['name'] = 'diner_cheesy_fries',  ['label'] = 'Cheesy Fries',  ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_cheesy_fries.png',  ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_chili_fries']   = {['name'] = 'diner_chili_fries',   ['label'] = 'Chili & Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_chili_fries.png',   ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_curly_fries']   = {['name'] = 'diner_curly_fries',   ['label'] = 'Curly Fries',    ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_curly_fries.png',   ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_loaded_fries']  = {['name'] = 'diner_loaded_fries',  ['label'] = 'Loaded Fries',   ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_loaded_fries.png',  ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_vanilla_milkshake']   = {['name'] = 'diner_vanilla_milkshake',   ['label'] = 'Vanilla Milkshake',   ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_vanilla_milkshake.png',   ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_chocolate_milkshake'] = {['name'] = 'diner_chocolate_milkshake', ['label'] = 'Chocolate Milkshake', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_chocolate_milkshake.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_strawberry_milkshake']= {['name'] = 'diner_strawberry_milkshake',['label'] = 'Strawberry Milkshake',['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_strawberry_milkshake.png',['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_caramel_milkshake']   = {['name'] = 'diner_caramel_milkshake',   ['label'] = 'Caramel Milkshake',   ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_caramel_milkshake.png',   ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_oreo_milkshake']      = {['name'] = 'diner_oreo_milkshake',      ['label'] = 'Oreo Milkshake',      ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_oreo_milkshake.png',      ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
--Ingredients--
['diner_bun'] = {['name'] = 'diner_bun', ['label'] = 'Bun', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_bun.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_beef_patty'] = {['name'] = 'diner_beef_patty', ['label'] = 'Beef Patty', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_beef_patty.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_sauce'] = {['name'] = 'diner_sauce', ['label'] = 'Diner Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_melted_cheddar'] = {['name'] = 'diner_melted_cheddar', ['label'] = 'Melted Cheddar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_melted_cheddar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_crispy_bacon'] = {['name'] = 'diner_crispy_bacon', ['label'] = 'Crispy Bacon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_crispy_bacon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_hot_pepper_relish'] = {['name'] = 'diner_hot_pepper_relish', ['label'] = 'Hot Pepper Relish', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_hot_pepper_relish.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_double_special_sauce'] = {['name'] = 'diner_double_special_sauce', ['label'] = 'Double Special Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_double_special_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_sandwich_bread'] = {['name'] = 'diner_sandwich_bread', ['label'] = 'Sandwich Bread', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_sandwich_bread.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_grilled_chicken'] = {['name'] = 'diner_grilled_chicken', ['label'] = 'Grilled Chicken', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_grilled_chicken.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_crispy_bacon'] = {['name'] = 'diner_crispy_bacon', ['label'] = 'Crispy Bacon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pd_horseradish_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_avocado_spread'] = {['name'] = 'diner_avocado_spread', ['label'] = 'Avocado Spread', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_crispy_bacon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_roast_beef'] = {['name'] = 'diner_roast_beef', ['label'] = 'Roast Beef', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_roast_beef.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_veggie_patty'] = {['name'] = 'diner_veggie_patty', ['label'] = 'Veggie Patty', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_veggie_patty.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_fries'] = {['name'] = 'diner_fries', ['label'] = 'Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_fries.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_sea_salt'] = {['name'] = 'diner_sea_salt', ['label'] = 'Sea Salt', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_sea_salt.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_cheddar_sauce'] = {['name'] = 'diner_cheddar_sauce', ['label'] = 'Cheddar Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_cheddar_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_chili_cheese'] = {['name'] = 'diner_chili_cheese', ['label'] = 'Chili & Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_chili_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_seasoning'] = {['name'] = 'diner_seasoning', ['label'] = 'Diner Seasoning', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_seasoning.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_loaded_toppings'] = {['name'] = 'diner_loaded_toppings', ['label'] = 'Loaded Toppings', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_loaded_toppings.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_milk'] = {['name'] = 'diner_milk', ['label'] = 'Milk', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_milk.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_vanilla_extract'] = {['name'] = 'diner_vanilla_extract', ['label'] = 'Vanilla Extract', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_vanilla_extract.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_chocolate_syrup'] = {['name'] = 'diner_chocolate_syrup', ['label'] = 'Chocolate Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_chocolate_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_strawberry_puree'] = {['name'] = 'diner_strawberry_puree', ['label'] = 'Strawberry Puree', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_strawberry_puree.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_caramel_sauce'] = {['name'] = 'diner_caramel_sauce', ['label'] = 'Caramel Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_caramel_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_crushed_oreos'] = {['name'] = 'diner_crushed_oreos', ['label'] = 'Crushed Oreos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_crushed_oreos.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_bun'] = {['name'] = 'diner_bun', ['label'] = 'Burger Bun', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_bun.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_emptycup'] = {['name'] = 'diner_emptycup', ['label'] = 'Diner Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_waterbottle'] = {['name'] = 'diner_waterbottle', ['label'] = 'Diner WaterBottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['diner_icecubes'] = {['name'] = 'diner_icecubes', ['label'] = 'Diner Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'diner_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>ESX ITems Sql</summary>

```lua
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
  ('diner_classic_burger', 'Classic Burger', 1),
  ('diner_cheddar_burger', 'Cheddar Burger', 1),
  ('diner_bacon_burger', 'Bacon Burger', 1),
  ('diner_spicy_burger', 'Spicy Burger', 1),
  ('diner_double_burger', 'Double Burger', 1),
  ('diner_chicken_sandwich', 'Chicken Club Sandwich', 1),
  ('diner_blt_sandwich', 'BLT Sandwich', 1),
  ('diner_turkey_avocado_sandwich', 'Turkey Sandwich', 1),
  ('diner_roast_beef_sandwich', 'Roast Beef Sandwich', 1),
  ('diner_veggie_sandwich', 'Veggie Sandwich', 1),
  ('diner_classic_fries', 'Classic Fries', 1),
  ('diner_cheesy_fries', 'Cheesy Fries', 1),
  ('diner_chili_fries', 'Chili & Cheese', 1),
  ('diner_curly_fries', 'Curly Fries', 1),
  ('diner_loaded_fries', 'Loaded Fries', 1),
  ('diner_vanilla_milkshake', 'Vanilla Milkshake', 1),
  ('diner_chocolate_milkshake', 'Chocolate Milkshake', 1),
  ('diner_strawberry_milkshake', 'Strawberry Milkshake', 1),
  ('diner_caramel_milkshake', 'Caramel Milkshake', 1),
  ('diner_oreo_milkshake', 'Oreo Milkshake', 1),
  ('diner_beef_patty', 'Beef Patty', 1),
  ('diner_sauce', 'Diner Sauce', 1),
  ('diner_melted_cheddar', 'Melted Cheddar', 1),
  ('diner_crispy_bacon', 'Crispy Bacon', 1),
  ('diner_hot_pepper_relish', 'Hot Pepper Relish', 1),
  ('diner_double_special_sauce', 'Double Special Sauce', 1),
  ('diner_sandwich_bread', 'Sandwich Bread', 1),
  ('diner_grilled_chicken', 'Grilled Chicken', 1),
  ('diner_avocado_spread', 'Crispy Bacon', 1),
  ('diner_roast_beef', 'Roast Beef', 1),
  ('diner_veggie_patty', 'Veggie Patty', 1),
  ('diner_fries', 'Fries', 1),
  ('diner_sea_salt', 'Sea Salt', 1),
  ('diner_cheddar_sauce', 'Cheddar Sauce', 1),
  ('diner_chili_cheese', 'Chili & Cheese', 1),
  ('diner_seasoning', 'Diner Seasoning', 1),
  ('diner_loaded_toppings', 'Loaded Toppings', 1),
  ('diner_milk', 'Milk', 1),
  ('diner_vanilla_extract', 'Vanilla Extract', 1),
  ('diner_chocolate_syrup', 'Chocolate Syrup', 1),
  ('diner_strawberry_puree', 'Strawberry Puree', 1),
  ('diner_caramel_sauce', 'Caramel Sauce', 1),
  ('diner_bun', 'Burger Bun', 1),
  ('diner_emptycup', 'Diner Empty Cup', 1),
  ('diner_waterbottle', 'Diner WaterBottle', 1),
  ('diner_icecubes', 'Diner Ice Cubes', 1),
  ('diner_crushed_oreos', 'Crushed Oreos', 1);
```

</details>

### For QBCore Only

{% tabs %}
{% tab title="jobs.lua" %}
Add the Following in qb-core/shared/jobs.lua

```lua
['diner'] = {
    label = 'Diner',
    defaultDuty = true,
    grades = {
        ['0'] = {
            name = 'Cashier',
            payment = 50
        },
        ['1'] = {
            name = 'Cook',
            payment = 75
        },
        ['2'] = {
            name = 'Shift Manager',
            payment = 100
        },
        ['3'] = {
            name = 'Manager',
            payment = 125,
        },
        ['4'] = {
            name = 'Owner',
            payment = 125,
            isboss = true,
        },
    },
},
```

Added in Qbox->shared->jobs.lua

```lua
['diner'] = {
    label = 'Diner',
    defaultDuty = true,
    grades = {
        [0] = {
            name = 'Cashier',
            payment = 50
        },
        [1] = {
            name = 'Cook',
            payment = 75
        },
        [2] = {
            name = 'Shift Manager',
            payment = 100
        },
        [3] = {
            name = 'Manager',
            payment = 125,
        },
        [4] = {
            name = 'Owner',
            payment = 125,
            isboss = true,
        },
    },
},
```
{% endtab %}
{% endtabs %}

### Consumables

<details>

<summary>QB Smallresources</summary>

Add in qb-smallresourcse/config.lua

```lua
--If using old qb-smallresources
Config.ConsumablesDrink = {
    ['diner_vanilla_milkshake'] = math.random(35, 54),
    ['diner_chocolate_milkshake'] = math.random(35, 54),
    ['diner_strawberry_milkshake'] = math.random(35, 54),
    ['diner_crimson_ridge'] = math.random(35, 54),
    ['diner_oreo_milkshake'] = math.random(35, 54),
}

Config.ConsumablesEat = {
    ['diner_classic_burger'] = math.random(35, 54),
    ['diner_cheddar_burger'] = math.random(35, 54),
    ['diner_bacon_burger'] = math.random(35, 54),
    ['diner_spicy_burger'] = math.random(35, 54),
    ['diner_double_burger'] = math.random(35, 54),
    ['diner_chicken_sandwich'] = math.random(35, 54),
    ['diner_blt_sandwich'] = math.random(35, 54),
    ['diner_turkey_avocado_sandwich'] = math.random(35, 54),
    ['diner_roast_beef_sandwich'] = math.random(35, 54),
    ['diner_veggie_sandwich'] = math.random(35, 54),
    ['diner_classic_fries'] = math.random(35, 54),
    ['diner_cheesy_fries'] = math.random(35, 54),
    ['diner_chili_fries'] = math.random(35, 54),
    ['diner_curly_fries'] = math.random(35, 54),
    ['diner_loaded_fries'] = math.random(35, 54),
}

--If using new qb-smallresources
Config.Consumables = {
    eat = {
        ['diner_classic_burger'] = math.random(35, 54),
        ['diner_cheddar_burger'] = math.random(35, 54),
        ['diner_bacon_burger'] = math.random(35, 54),
        ['diner_spicy_burger'] = math.random(35, 54),
        ['diner_double_burger'] = math.random(35, 54),
        ['diner_chicken_sandwich'] = math.random(35, 54),
        ['diner_blt_sandwich'] = math.random(35, 54),
        ['diner_turkey_avocado_sandwich'] = math.random(35, 54),
        ['diner_roast_beef_sandwich'] = math.random(35, 54),
        ['diner_veggie_sandwich'] = math.random(35, 54),
        ['diner_classic_fries'] = math.random(35, 54),
        ['diner_cheesy_fries'] = math.random(35, 54),
        ['diner_chili_fries'] = math.random(35, 54),
        ['diner_curly_fries'] = math.random(35, 54),
        ['diner_loaded_fries'] = math.random(35, 54),
    },
    drink = {
        ['diner_vanilla_milkshake'] = math.random(35, 54),
        ['diner_chocolate_milkshake'] = math.random(35, 54),
        ['diner_strawberry_milkshake'] = math.random(35, 54),
        ['diner_caramel_milkshake'] = math.random(35, 54),
        ['diner_oreo_milkshake'] = math.random(35, 54),
    },
}
    drink = {
        ['bs_chillwave_cola'] = math.random(35, 54),
        ['bs_fizzberry_splash'] = math.random(35, 54),
        ['bs_lemonlush_soda'] = math.random(35, 54),
        ['bs_zesty_zing'] = math.random(35, 54),
    },
}
```

</details>

<details>

<summary>Jim Consumables</summary>

Add the following in jim-consumables/shared/consumables.lua

```lua
--jim-consumables/shared/consumables.lua
diner_classic_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_cheddar_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_bacon_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_spicy_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_double_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_chicken_sandwich = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_blt_sandwich = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_turkey_avocado_sandwich = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_roast_beef_sandwich = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_veggie_sandwich = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_classic_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_cheesy_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_chili_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_curly_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_loaded_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},

diner_vanilla_milkshake = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_chocolate_milkshake = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_strawberry_milkshake = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_caramel_milkshake = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
diner_oreo_milkshake = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
```

</details>

### Add Images to Inventory

Copy all the Images folder and paste it in your inventory Images folder



### Log Webook Setup - Optional

To enable discord logs make sure to add your webhook in the server->Log.lua File

{% embed url="https://www.youtube.com/watch?pp=ygULI2FwcHlxczIwMjM=&v=fKksxz2Gdnc" %}

### Optional Dj Custom Props

If you have purchased the DJ Burgershot Props [https://djscollections.com/package/5764355](https://djscollections.com/package/5764355) just install it and set the Config.UseDjItems = true

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
