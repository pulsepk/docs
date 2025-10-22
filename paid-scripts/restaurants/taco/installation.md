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
CREATE TABLE IF NOT EXISTS `pl_tacoshop` (
          `stock` longtext DEFAULT NULL,
          `state` varchar(5) NOT NULL DEFAULT 'open'
        ) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;

INSERT INTO `addon_account` (name, label, shared) VALUES
	('society_taco', 'Taco', 1);

 INSERT INTO `datastore` (name, label, shared) VALUES
        ('society_taco', 'Taco', 1);

INSERT INTO `jobs` (name, label,whitelisted) VALUES
        ('taco', 'Taco',1);

INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
        ('taco',0,'cashier','Cashier',20,'{}','{}'),
        ('taco',1,'cook','Cook',40,'{}','{}'),
        ('taco',2,'staff','Staff',60,'{}','{}'),
        ('taco',3,'manager','Manager',85,'{}','{}'),
        ('taco',4,'boss','Owner',100,'{}','{}');
```

</details>

<details>

<summary>QBCore or Qbox</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_tacoshop` (
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
["taco_carnitas_burrito"] = {
    label = "Carnitas Burrito",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_carnitas"] = {
    label = "Carnitas Tacos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_al_pastor"] = {
    label = "Al Pastor Tacos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_pork_shoulder"] = {
    label = "Slow Cooked Pork Shoulder",
    weight = 1,
    stack = true,
    close = true,
},

["taco_mexican_sausage"] = {
    label = "Spicy Mexican Chorizo Sausage",
    weight = 1,
    stack = true,
    close = true,
},

["taco_grilled_chicken"] = {
    label = "Grilled Chicken",
    weight = 1,
    stack = true,
    close = true,
},

["taco_grilled_skirt"] = {
    label = "Grilled Skirt",
    weight = 1,
    stack = true,
    close = true,
},

["taco_grilled_steak"] = {
    label = "Grilled Steak",
    weight = 1,
    stack = true,
    close = true,
},

["taco_ground_beef"] = {
    label = "Ground Beef",
    weight = 1,
    stack = true,
    close = true,
},

["taco_chicken_nachos"] = {
    label = "Chicken Nachos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_barbacoa"] = {
    label = "Barbacoa Tacos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_bbqchicken_burrito"] = {
    label = "Bbq Chicken Burrito",
    weight = 1,
    stack = true,
    close = true,
},

["taco_chorizo"] = {
    label = "Chorizo Tacos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_beef_burrito"] = {
    label = "Classic Beef Burrito",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_jalapenos"] = {
    label = "Jalapenos",
    weight = 1,
    stack = true,
    close = true,
},

["taco_classic_nachos"] = {
    label = "Classic Nachos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_cheese_burrito"] = {
    label = "Bean and Cheese Burrito",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_pulled_pork"] = {
    label = "Pulled Pork",
    weight = 1,
    stack = true,
    close = true,
},

["taco_pork_nachos"] = {
    label = "Pulled Pork Nachos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_cooked_quinoa"] = {
    label = "Cooked Quinoa",
    weight = 1,
    stack = true,
    close = true,
},

["taco_black_beans"] = {
    label = "Black Beans",
    weight = 1,
    stack = true,
    close = true,
},

["taco_tortilla_chips"] = {
    label = "Tortilla Chips",
    weight = 1,
    stack = true,
    close = true,
},

["taco_cooked_beef"] = {
    label = "Slow Cooked Beef",
    weight = 1,
    stack = true,
    close = true,
},

["taco_steak_burrito"] = {
    label = "Steak Burrito",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_refried_beans"] = {
    label = "Refried Beans",
    weight = 1,
    stack = true,
    close = true,
},

["taco_vegetarian_burrito"] = {
    label = "Vegetarian Burrito",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_tortillas"] = {
    label = "taco_tortillas",
    weight = 1,
    stack = true,
    close = true,
},

["taco_tilapia"] = {
    label = "taco_tilapia",
    weight = 1,
    stack = true,
    close = true,
},

["taco_stewed_beef"] = {
    label = "Stewed Beef",
    weight = 1,
    stack = true,
    close = true,
},

["taco_beef_nachos"] = {
    label = "Loaded Beef Nachos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_vegetarian_nachos"] = {
    label = "Vegetarian Nachos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_vegetarian"] = {
    label = "Vegetarian Tacos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_sauteed_shrimp"] = {
    label = "Sauteed Shrimp",
    weight = 1,
    stack = true,
    close = true,
},

["taco_marinated_pork"] = {
    label = "Marinated Pork",
    weight = 1,
    stack = true,
    close = true,
},

["taco_breakfast_nachos"] = {
    label = "Breakfast Nachos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_breakfast_sausage"] = {
    label = "Breakfast Sausage",
    weight = 1,
    stack = true,
    close = true,
},

["taco_sauteed_vegetables"] = {
    label = "Sauteed Vegetables",
    weight = 1,
    stack = true,
    close = true,
},

["taco_scrambled_eggs"] = {
    label = "Scrambled Eggs",
    weight = 1,
    stack = true,
    close = true,
},

["taco_birria"] = {
    label = "Birria Tacos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_seafood_nachos"] = {
    label = "Seafood Nachos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_fish_burrito"] = {
    label = "Fish Burrito",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_bbq_chicken"] = {
    label = "Shredded Bbq Chicken",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_fish"] = {
    label = "Fish Tacos",
    weight = 1,
    stack = true,
    close = true,
},

["taco_shredded_chicken"] = {
    label = "Shredded Chicken Cooked",
    weight = 1,
    stack = true,
    close = true,
},

["taco_breakfast_burrito"] = {
    label = "Breakfast Burrito",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_shrimp_burrito"] = {
    label = "Shrimp Burrito",
    weight = 1,
    stack = true,
    close = true,
},

["taco_shrimp"] = {
    label = "Taco Shrimp",
    weight = 1,
    stack = true,
    close = true,
},

["taco_shrimp"] = {
    label = "Shrimp Tacos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_carne"] = {
    label = "Carne Asada Tacos",
    weight = 1,
    stack = true,
    close = true,
},

["taco_chicken"] = {
    label = "Chicken Tacos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a something delicious'
		},
},

["taco_lemonlush_soda"] = {
    label = "Taco Lemonlush Soda",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},

["taco_zesty_zing"] = {
    label = "Taco Zesty Zing",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},

["taco_chillwave_cola"] = {
    label = "Taco ChillWave Cola",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},

["taco_fizzberry_splash"] = {
    label = "Taco Fizzberry Splash",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},

["taco_emptycup"] = {
    label = "Taco Empty Cup",
    weight = 1,
    stack = true,
    close = true,
},

["taco_icecubes"] = {
    label = "Ice Cubes",
    weight = 1,
    stack = true,
    close = true,
},
["taco_waterbottle"] = {
    label = "Water Bottle",
    weight = 1,
    stack = true,
    close = true,
},
```

</details>

<details>

<summary>QB Inventory</summary>

```lua
['taco_carne'] = {['name'] = 'taco_carne', ['label'] = 'Carne Asada Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_carne.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_grilled_skirt'] = {['name'] = 'taco_grilled_skirt', ['label'] = 'Grilled Skirt', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_grilled_skirt.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_tortillas'] = {['name'] = 'taco_tortillas', ['label'] = 'taco_tortillas', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_tortillas.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_al_pastor'] = {['name'] = 'taco_al_pastor', ['label'] = 'Al Pastor Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_al_pastor.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_marinated_pork'] = {['name'] = 'taco_marinated_pork', ['label'] = 'Marinated Pork', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_marinated_pork.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_fish'] = {['name'] = 'taco_fish', ['label'] = 'Fish Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_fish.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_tilapia'] = {['name'] = 'taco_tilapia', ['label'] = 'taco_tilapia', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_tilapia.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_carnitas'] = {['name'] = 'taco_carnitas', ['label'] = 'Carnitas Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_carnitas.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_pork_shoulder'] = {['name'] = 'taco_pork_shoulder', ['label'] = 'Slow Cooked Pork Shoulder', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_pork_shoulder.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_barbacoa'] = {['name'] = 'taco_barbacoa', ['label'] = 'Barbacoa Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_barbacoa.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_cooked_beef'] = {['name'] = 'taco_cooked_beef', ['label'] = 'Slow Cooked Beef', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_cooked_beef.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_chicken'] = {['name'] = 'taco_chicken', ['label'] = 'Chicken Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_chicken.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_shredded_chicken'] = {['name'] = 'taco_shredded_chicken', ['label'] = 'Shredded Chicken Cooked', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_shredded_chicken.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_chorizo'] = {['name'] = 'taco_chorizo', ['label'] = 'Chorizo Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_chorizo.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_mexican_sausage'] = {['name'] = 'taco_mexican_sausage', ['label'] = 'Spicy Mexican Chorizo Sausage', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_mexican_sausage.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_vegetarian'] = {['name'] = 'taco_vegetarian', ['label'] = 'Vegetarian Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_vegetarian.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_sauteed_vegetables'] = {['name'] = 'taco_sauteed_vegetables', ['label'] = 'Sauteed Vegetables', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_sauteed_vegetables.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_shrimp'] = {['name'] = 'taco_shrimp', ['label'] = 'Shrimp Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_shrimp.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_sauteed_shrimp'] = {['name'] = 'taco_sauteed_shrimp', ['label'] = 'Sauteed Shrimp', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_sauteed_shrimp.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_birria'] = {['name'] = 'taco_birria', ['label'] = 'Birria Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_birria.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_stewed_beef'] = {['name'] = 'taco_stewed_beef', ['label'] = 'Stewed Beef', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_stewed_beef.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_beef_burrito'] = {['name'] = 'taco_beef_burrito', ['label'] = 'Classic Beef Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_beef_burrito.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_ground_beef'] = {['name'] = 'taco_ground_beef', ['label'] = 'Ground Beef', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_ground_beef.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_chicken_burrito'] = {['name'] = 'taco_chicken_burrito', ['label'] = 'Chicken Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_chicken_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_vegetarian_burrito'] = {['name'] = 'taco_vegetarian_burrito', ['label'] = 'Vegetarian Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_vegetarian_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_cooked_quinoa'] = {['name'] = 'taco_cooked_quinoa', ['label'] = 'Cooked Quinoa', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_cooked_quinoa.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_breakfast_burrito'] = {['name'] = 'taco_breakfast_burrito', ['label'] = 'Breakfast Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_breakfast_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_breakfast_sausage'] = {['name'] = 'taco_breakfast_sausage', ['label'] = 'Breakfast Sausage', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_breakfast_sausage.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_carnitas_burrito'] = {['name'] = 'taco_carnitas_burrito', ['label'] = 'Carnitas Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_carnitas_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_fish_burrito'] = {['name'] = 'taco_fish_burrito', ['label'] = 'Fish Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_fish_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_steak_burrito'] = {['name'] = 'taco_steak_burrito', ['label'] = 'Steak Buurrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_steak_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_grilled_steak'] = {['name'] = 'taco_grilled_steak', ['label'] = 'Grilled Steak', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_grilled_steak.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_shrimp_burrito'] = {['name'] = 'taco_shrimp_burrito', ['label'] = 'Shrimp Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_shrimp_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_cheese_burrito'] = {['name'] = 'taco_cheese_burrito', ['label'] = 'Bean and Cheese burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_cheese_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_refried_beans'] = {['name'] = 'taco_refried_beans', ['label'] = 'Refried Beans', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_refried_beans.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_bbqchicken_burrito'] = {['name'] = 'taco_bbqchicken_burrito', ['label'] = 'Bbq Chicken Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_bbqchicken_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_bbq_chicken'] = {['name'] = 'taco_bbq_chicken', ['label'] = 'Shredded Bbq Chicken', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_bbq_chicken.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_classic_nachos'] = {['name'] = 'taco_classic_nachos', ['label'] = 'Classic Nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_classic_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_jalapenos'] = {['name'] = 'taco_jalapenos', ['label'] = 'Jalapenos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_jalapenos.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_tortilla_chips'] = {['name'] = 'taco_tortilla_chips', ['label'] = 'Tortilla Chips', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_tortilla_chips.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_beef_nachos'] = {['name'] = 'taco_beef_nachos', ['label'] = 'Loaded Beef Nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_beef_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_chicken_nachos'] = {['name'] = 'taco_chicken_nachos', ['label'] = 'chicken nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_chicken_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_grilled_chicken'] = {['name'] = 'taco_grilled_chicken', ['label'] = 'Grilled Chicken', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_grilled_chicken.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_pork_nachos'] = {['name'] = 'taco_pork_nachos', ['label'] = 'Pulled Pork Nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_pork_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_pulled_pork'] = {['name'] = 'taco_pulled_pork', ['label'] = 'Pulled Pork', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_pulled_pork.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_vegetarian_nachos'] = {['name'] = 'taco_vegetarian_nachos', ['label'] = 'Vegetarian Nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_vegetarian_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_black_beans'] = {['name'] = 'taco_black_beans', ['label'] = 'Black Beans', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_black_beans.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_seafood_nachos'] = {['name'] = 'taco_seafood_nachos', ['label'] = 'Seafood Nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_seafood_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_shrimp'] = {['name'] = 'taco_shrimp', ['label'] = 'Taco Shrimp', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_shrimp.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_breakfast_nachos'] = {['name'] = 'taco_breakfast_nachos', ['label'] = 'Breakfast Nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_breakfast_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_scrambled_eggs'] = {['name'] = 'taco_scrambled_eggs', ['label'] = 'Scrambled Eggs', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_scrambled_eggs.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_chillwave_cola'] = {['name'] = 'taco_chillwave_cola', ['label'] = 'Taco Chillwave Cola', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_chillwave_cola.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_fizzberry_splash'] = {['name'] = 'taco_fizzberry_splash', ['label'] = 'Taco Fizzberry Splash', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_fizzberry_splash.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_lemonlush_soda'] = {['name'] = 'taco_lemonlush_soda', ['label'] = 'Taco Lemonlush Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_lemonlush_soda.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_zesty_zing'] = {['name'] = 'taco_zesty_zing', ['label'] = 'Taco Zesty Zing', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_zesty_zing.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_emptycup'] = {['name'] = 'taco_emptycup', ['label'] = 'Taco Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_emptycup.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_icecubes'] = {['name'] = 'taco_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_icecubes.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_waterbottle'] = {['name'] = 'taco_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_waterbottle.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>Quasar Inventory</summary>

```lua
['taco_carne'] = {['name'] = 'taco_carne', ['label'] = 'Carne Asada Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_carne.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_grilled_skirt'] = {['name'] = 'taco_grilled_skirt', ['label'] = 'Grilled Skirt', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_grilled_skirt.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_tortillas'] = {['name'] = 'taco_tortillas', ['label'] = 'taco_tortillas', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_tortillas.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_al_pastor'] = {['name'] = 'taco_al_pastor', ['label'] = 'Al Pastor Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_al_pastor.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_marinated_pork'] = {['name'] = 'taco_marinated_pork', ['label'] = 'Marinated Pork', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_marinated_pork.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_fish'] = {['name'] = 'taco_fish', ['label'] = 'Fish Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_fish.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_tilapia'] = {['name'] = 'taco_tilapia', ['label'] = 'taco_tilapia', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_tilapia.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_carnitas'] = {['name'] = 'taco_carnitas', ['label'] = 'Carnitas Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_carnitas.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_pork_shoulder'] = {['name'] = 'taco_pork_shoulder', ['label'] = 'Slow Cooked Pork Shoulder', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_pork_shoulder.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_barbacoa'] = {['name'] = 'taco_barbacoa', ['label'] = 'Barbacoa Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_barbacoa.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_cooked_beef'] = {['name'] = 'taco_cooked_beef', ['label'] = 'Slow Cooked Beef', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_cooked_beef.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_chicken'] = {['name'] = 'taco_chicken', ['label'] = 'Chicken Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_chicken.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_shredded_chicken'] = {['name'] = 'taco_shredded_chicken', ['label'] = 'Shredded Chicken Cooked', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_shredded_chicken.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_chorizo'] = {['name'] = 'taco_chorizo', ['label'] = 'Chorizo Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_chorizo.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_mexican_sausage'] = {['name'] = 'taco_mexican_sausage', ['label'] = 'Spicy Mexican Chorizo Sausage', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_mexican_sausage.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_vegetarian'] = {['name'] = 'taco_vegetarian', ['label'] = 'Vegetarian Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_vegetarian.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_sauteed_vegetables'] = {['name'] = 'taco_sauteed_vegetables', ['label'] = 'Sauteed Vegetables', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_sauteed_vegetables.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_shrimp'] = {['name'] = 'taco_shrimp', ['label'] = 'Shrimp Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_shrimp.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_sauteed_shrimp'] = {['name'] = 'taco_sauteed_shrimp', ['label'] = 'Sauteed Shrimp', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_sauteed_shrimp.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_birria'] = {['name'] = 'taco_birria', ['label'] = 'Birria Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_birria.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_stewed_beef'] = {['name'] = 'taco_stewed_beef', ['label'] = 'Stewed Beef', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_stewed_beef.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_beef_burrito'] = {['name'] = 'taco_beef_burrito', ['label'] = 'Classic Beef Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_beef_burrito.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_ground_beef'] = {['name'] = 'taco_ground_beef', ['label'] = 'Ground Beef', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_ground_beef.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_chicken_burrito'] = {['name'] = 'taco_chicken_burrito', ['label'] = 'Chicken Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_chicken_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_vegetarian_burrito'] = {['name'] = 'taco_vegetarian_burrito', ['label'] = 'Vegetarian Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_vegetarian_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_cooked_quinoa'] = {['name'] = 'taco_cooked_quinoa', ['label'] = 'Cooked Quinoa', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_cooked_quinoa.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_breakfast_burrito'] = {['name'] = 'taco_breakfast_burrito', ['label'] = 'Breakfast Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_breakfast_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_breakfast_sausage'] = {['name'] = 'taco_breakfast_sausage', ['label'] = 'Breakfast Sausage', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_breakfast_sausage.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_carnitas_burrito'] = {['name'] = 'taco_carnitas_burrito', ['label'] = 'Carnitas Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_carnitas_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_fish_burrito'] = {['name'] = 'taco_fish_burrito', ['label'] = 'Fish Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_fish_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_steak_burrito'] = {['name'] = 'taco_steak_burrito', ['label'] = 'Steak Buurrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_steak_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_grilled_steak'] = {['name'] = 'taco_grilled_steak', ['label'] = 'Grilled Steak', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_grilled_steak.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_shrimp_burrito'] = {['name'] = 'taco_shrimp_burrito', ['label'] = 'Shrimp Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_shrimp_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_cheese_burrito'] = {['name'] = 'taco_cheese_burrito', ['label'] = 'Bean and Cheese burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_cheese_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_refried_beans'] = {['name'] = 'taco_refried_beans', ['label'] = 'Refried Beans', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_refried_beans.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_bbqchicken_burrito'] = {['name'] = 'taco_bbqchicken_burrito', ['label'] = 'Bbq Chicken Burrito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_bbqchicken_burrito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_bbq_chicken'] = {['name'] = 'taco_bbq_chicken', ['label'] = 'Shredded Bbq Chicken', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_bbq_chicken.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_classic_nachos'] = {['name'] = 'taco_classic_nachos', ['label'] = 'Classic Nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_classic_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_jalapenos'] = {['name'] = 'taco_jalapenos', ['label'] = 'Jalapenos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_jalapenos.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_tortilla_chips'] = {['name'] = 'taco_tortilla_chips', ['label'] = 'Tortilla Chips', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_tortilla_chips.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_beef_nachos'] = {['name'] = 'taco_beef_nachos', ['label'] = 'Loaded Beef Nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_beef_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_chicken_nachos'] = {['name'] = 'taco_chicken_nachos', ['label'] = 'chicken nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_chicken_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_grilled_chicken'] = {['name'] = 'taco_grilled_chicken', ['label'] = 'Grilled Chicken', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_grilled_chicken.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_pork_nachos'] = {['name'] = 'taco_pork_nachos', ['label'] = 'Pulled Pork Nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_pork_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_pulled_pork'] = {['name'] = 'taco_pulled_pork', ['label'] = 'Pulled Pork', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_pulled_pork.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_vegetarian_nachos'] = {['name'] = 'taco_vegetarian_nachos', ['label'] = 'Vegetarian Nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_vegetarian_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_black_beans'] = {['name'] = 'taco_black_beans', ['label'] = 'Black Beans', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_black_beans.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_seafood_nachos'] = {['name'] = 'taco_seafood_nachos', ['label'] = 'Seafood Nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_seafood_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_shrimp'] = {['name'] = 'taco_shrimp', ['label'] = 'Taco Shrimp', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_shrimp.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_breakfast_nachos'] = {['name'] = 'taco_breakfast_nachos', ['label'] = 'Breakfast Nachos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_breakfast_nachos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_scrambled_eggs'] = {['name'] = 'taco_scrambled_eggs', ['label'] = 'Scrambled Eggs', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_scrambled_eggs.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_chillwave_cola'] = {['name'] = 'taco_chillwave_cola', ['label'] = 'Taco Chillwave Cola', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_chillwave_cola.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_fizzberry_splash'] = {['name'] = 'taco_fizzberry_splash', ['label'] = 'Taco Fizzberry Splash', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_fizzberry_splash.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_lemonlush_soda'] = {['name'] = 'taco_lemonlush_soda', ['label'] = 'Taco Lemonlush Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_lemonlush_soda.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_zesty_zing'] = {['name'] = 'taco_zesty_zing', ['label'] = 'Taco Zesty Zing', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_zesty_zing.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_emptycup'] = {['name'] = 'taco_emptycup', ['label'] = 'Taco Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_emptycup.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_icecubes'] = {['name'] = 'taco_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_icecubes.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['taco_waterbottle'] = {['name'] = 'taco_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'taco_waterbottle.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>ESX ITems Sql</summary>

```lua
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
    RT INTO `items` (`name`, `label`, `weight`) VALUES
    ('taco_carne', 'Carne Asada Tacos', 1),
    ('taco_grilled_skirt', 'Grilled Skirt', 1),
    ('taco_tortillas', 'taco_tortillas', 1),
    ('taco_al_pastor', 'Al Pastor Tacos', 1),
    ('taco_marinated_pork', 'Marinated Pork', 1),
    ('taco_fish', 'Fish Tacos', 1),
    ('taco_tilapia', 'taco_tilapia', 1),
    ('taco_carnitas', 'Carnitas Tacos', 1),
    ('taco_pork_shoulder', 'Slow Cooked Pork Shoulder', 1),
    ('taco_barbacoa', 'Barbacoa Tacos', 1),
    ('taco_cooked_beef', 'Slow Cooked Beef', 1),
    ('taco_chicken', 'Chicken Tacos', 1),
    ('taco_shredded_chicken', 'Shredded Chicken Cooked', 1),
    ('taco_chorizo', 'Chorizo Tacos', 1),
    ('taco_mexican_sausage', 'Spicy Mexican Chorizo Sausage', 1),
   ('taco_vegetarian', 'Vegetarian Tacos', 1),
   ('taco_sauteed_vegetables', 'Sauteed Vegetables', 1),
   ('taco_shrimp', 'Shrimp Tacos', 1),
   ('taco_sauteed_shrimp', 'Sauteed Shrimp', 1),
   ('taco_birria', 'Birria Tacos', 1),
   ('taco_stewed_beef', 'Stewed Beef', 1),
   ('taco_beef_burrito', 'Classic Beef Burrito', 1),
   ('taco_ground_beef', 'Ground Beef', 1),
   ('taco_chicken_burrito', 'Chicken Burrito', 1),
   ('taco_vegetarian_burrito', 'Vegetarian Burrito', 1),
   ('taco_cooked_quinoa', 'Cooked Quinoa', 1),
   ('taco_breakfast_burrito', 'Breakfast Burrito', 1),
   ('taco_breakfast_sausage', 'Breakfast Sausage', 1),
   ('taco_carnitas_burrito', 'Carnitas Burrito', 1),
   ('taco_fish_burrito', 'Fish Burrito', 1),
   ('taco_steak_burrito', 'Steak Burrito', 1),
   ('taco_grilled_steak', 'Grilled Steak', 1),
   ('taco_shrimp_burrito', 'Shrimp Burrito', 1),
   ('taco_cheese_burrito', 'Bean and Cheese Burrito', 1),
   ('taco_refried_beans', 'Refried Beans', 1),
   ('taco_bbqchicken_burrito', 'Bbq Chicken Burrito', 1),
   ('taco_bbq_chicken', 'Shredded Bbq Chicken', 1),
   ('taco_classic_nachos', 'Classic Nachos', 1),
   ('taco_jalapenos', 'Jalapenos', 1),
   ('taco_tortilla_chips', 'Tortilla Chips', 1),
   ('taco_beef_nachos', 'Loaded Beef Nachos', 1),
   ('taco_chicken_nachos', 'Chicken Nachos', 1),
   ('taco_grilled_chicken', 'Grilled Chicken', 1),
   ('taco_pork_nachos', 'Pulled Pork Nachos', 1),
   ('taco_pulled_pork', 'Pulled Pork', 1),
   ('taco_vegetarian_nachos', 'Vegetarian Nachos', 1),
   ('taco_black_beans', 'Black Beans', 1),
   ('taco_seafood_nachos', 'Seafood Nachos', 1),
   ('taco_shrimp', 'Taco Shrimp', 1),
   ('taco_breakfast_nachos', 'Breakfast Nachos', 1),
   ('taco_scrambled_eggs', 'Scrambled Eggs', 1),
   ('taco_chillwave_cola', 'Taco Jurritos', 1),
   ('taco_fizzberry_splash', 'Taco Fizzberry Splash', 1),
   ('taco_lemonlush_soda', 'Taco Lemonlush Soda', 1),
   ('taco_zesty_zing', 'Taco Zesty Zing', 1),
   ('taco_icecubes', 'Ice Cubes', 1),
   ('taco_waterbottle', 'Water Bottle', 1),
   ('taco_emptycup', 'Taco Empty Cup', 1);
```

</details>

### For QBCore Only

{% tabs %}
{% tab title="jobs.lua" %}
Add the Following in qb-core/shared/jobs.lua

```lua
['taco'] = {
    label = 'Taco Shop',
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
['taco'] = {
    label = 'Taco Shop',
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
    ['taco_chillwave_cola'] = math.random(35, 54),
    ['taco_fizzberry_splash'] = math.random(35, 54),
    ['taco_lemonlush_soda'] = math.random(35, 54),
    ['taco_zesty_zing'] = math.random(35, 54),
}

Config.ConsumablesEat = {
    ['taco_carne'] = math.random(35, 54),
    ['taco_al_pastor'] = math.random(35, 54),
    ['taco_fish'] = math.random(35, 54),
    ['taco_carnitas'] = math.random(35, 54),
    ['taco_barbacoa'] = math.random(35, 54),
    ['taco_chicken'] = math.random(35, 54),
    ['taco_chorizo'] = math.random(35, 54),
    ['taco_vegetarian'] = math.random(35, 54),
    ['taco_shrimp'] = math.random(35, 54),
    ['taco_birria'] = math.random(35, 54),

    ['taco_beef_burrito'] = math.random(35, 54),
    ['taco_chicken_burrito'] = math.random(35, 54),
    ['taco_vegetarian_burrito'] = math.random(35, 54),
    ['taco_breakfast_burrito'] = math.random(35, 54),
    ['taco_carnitas_burrito'] = math.random(35, 54),
    ['taco_fish_burrito'] = math.random(35, 54),
    ['taco_steak_burrito'] = math.random(35, 54),
    ['taco_shrimp_burrito'] = math.random(35, 54),
    ['taco_cheese_burrito'] = math.random(35, 54),
    ['taco_bbqchicken_burrito'] = math.random(35, 54),

    ['taco_classic_nachos'] = math.random(35, 54),
    ['taco_beef_nachos'] = math.random(35, 54),
    ['taco_chicken_nachos'] = math.random(35, 54),
    ['taco_pork_nachos'] = math.random(35, 54),
    ['taco_vegetarian_nachos'] = math.random(35, 54),
    ['taco_seafood_nachos'] = math.random(35, 54),
    ['taco_breakfast_nachos'] = math.random(35, 54),
}
```

</details>

<details>

<summary>Jim Consumables</summary>

Add the following in jim-consumables/shared/consumables.lua

```lua
taco_carne = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_al_pastor = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_fish = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_carnitas = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_barbacoa = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_chicken = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_chorizo = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_vegetarian = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_shrimp = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_birria = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_beef_burrito = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_chicken_burrito = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_vegetarian_burrito = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_breakfast_burrito = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_carnitas_burrito = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_fish_burrito = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_steak_burrito = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_shrimp_burrito = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_cheese_burrito = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_bbqchicken_burrito = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_classic_nachos = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_beef_nachos = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_chicken_nachos = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_pork_nachos = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_vegetarian_nachos = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_seafood_nachos = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
taco_breakfast_nachos = { emote = "taco", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },

taco_chillwave_cola = {emote = "drink",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
taco_fizzberry_splash = {emote = "drink",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
taco_lemonlush_soda = {emote = "drink",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
taco_zesty_zing = {emote = "drink",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},

--Add in jim-consumables/shared/emotes.lua
taco = {"mp_player_inteat@burger", "mp_player_int_eat_burger", "Taco", AnimationOptions ={ Prop = "prop_taco_01", PropBone = 60309, PropPlacement = {-0.0170, 0.0070, -0.0210, 107.9846, -105.0251, 55.7779},EmoteMoving = true, EmoteLoop = true, }},
```

</details>

### Add Images to Inventory

Copy all the Images folder and paste it in your inventory Images folder

### Log Webook Setup - Optional

To enable discord logs make sure to add your webhook in the server->Log.lua File

{% embed url="https://www.youtube.com/watch?pp=ygULI2FwcHlxczIwMjM=&v=fKksxz2Gdnc" %}

