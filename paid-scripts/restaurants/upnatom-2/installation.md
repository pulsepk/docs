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
CREATE TABLE IF NOT EXISTS `pl_hornyburgers` (
     `stock` longtext DEFAULT NULL
     `state` varchar(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;

INSERT INTO `addon_account` (name, label, shared) VALUES
     ('society_hornyburgers', 'Horny Burgers', 1);
INSERT INTO `datastore` (name, label, shared) VALUES
     ('society_hornyburgers', 'Horny Burgers', 1);

INSERT INTO `jobs` (name, label,whitelisted) VALUES
     ('hornyburgers', 'Horny Burgers',1);

INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
     ('hornyburgers',0,'cashier','Cashier',20,'{}','{}'),
     ('hornyburgers',1,'cook','Cook',40,'{}','{}'),
     ('hornyburgers',2,'staff','Staff',60,'{}','{}'),
     ('hornyburgers',3,'manager','Manager',85,'{}','{}'),
     ('hornyburgers',4,'boss','Owner',100,'{}','{}');
```

</details>

<details>

<summary>QBCore or Qbox</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_hornyburgers` (
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
["hb_classic_burger"] = {
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
["hb_spicy_burger"] = {
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
["hb_cheesy_burger"] = {
    label = "Cheesy Burger",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["hb_bacon_burger"] = {
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
["hb_double_burger"] = {
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
["hb_milkshake"] = {
    label = "Milkshake",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["hb_lemonade"] = {
    label = "Lemonade",
    weight = 1,
    stack = true,
    close = true,
},
["hb_iced_coffee"] = {
    label = "Iced Coffee",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["hb_smoothie"] = {
    label = "Smoothie",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["hb_energy_drink"] = {
    label = "Energy Drink",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["hb_classic_fries"] = {
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
["hb_cheesy_fries"] = {
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
["hb_spicy_fries"] = {
    label = "Spicy Fries",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["hb_bacon_fries"] = {
    label = "Bacon Fries",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["hb_loaded_fries"] = {
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
["hb_cola"] = {
    label = "Cola",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["hb_root_beer"] = {
    label = "Root Beer",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["hb_orange_soda"] = {
    label = "Orange Soda",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["hb_grape_soda"] = {
    label = "Grape Soda",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["hb_lemonlime"] = {
    label = "Lemon-Lime",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["hb_bun"] = {
    label = "Burger Bun",
    weight = 1,
    stack = true,
    close = true,
},
["hb_sauce"] = {
    label = "Horny Sauce",
    weight = 1,
    stack = true,
    close = true,
},
["hb_jalapeno_relish"] = {
    label = "Jalapeno Relish",
    weight = 1,
    stack = true,
    close = true,
},
["hb_melted_cheddar"] = {
    label = "Melted Cheddar",
    weight = 1,
    stack = true,
    close = true,
},
["hb_crispy_bacon"] = {
    label = "Crispy Bacon",
    weight = 1,
    stack = true,
    close = true,
},
["hb_double_beef_patty"] = {
    label = "Double Beef Patty",
    weight = 1,
    stack = true,
    close = true,
},
["hb_bbq_sauce"] = {
    label = "Special BBQ Sauce",
    weight = 1,
    stack = true,
    close = true,
},
["hb_milk"] = {
    label = "Milk",
    weight = 1,
    stack = true,
    close = true,
},
["hb_chocolate_syrup"] = {
    label = "Chocolate Syrup",
    weight = 1,
    stack = true,
    close = true,
},
["hb_fresh_lemon_juice"] = {
    label = "Fresh Lemon",
    weight = 1,
    stack = true,
    close = true,
},
["hb_mint_infusion"] = {
    label = "Mint Infusion",
    weight = 1,
    stack = true,
    close = true,
},
["hb_coffee"] = {
    label = "Coffee",
    weight = 1,
    stack = true,
    close = true,
},
["hb_caramel_drizzle"] = {
    label = "Caramel Drizzle",
    weight = 1,
    stack = true,
    close = true,
},
["hb_mixed_berries"] = {
    label = "Mixed Berries",
    weight = 1,
    stack = true,
    close = true,
},
["hb_honey"] = {
    label = "Honey",
    weight = 1,
    stack = true,
    close = true,
},
["hb_caffeine_base"] = {
    label = "Caffeine Base",
    weight = 1,
    stack = true,
    close = true,
},
["hb_citrus_blend"] = {
    label = "Citrus Blend",
    weight = 1,
    stack = true,
    close = true,
},
["hb_potato_fries"] = {
    label = "Potato Fries",
    weight = 1,
    stack = true,
    close = true,
},
["hb_sea_salt"] = {
    label = "Sea Salt & Pepper",
    weight = 1,
    stack = true,
    close = true,
},
["hb_melted_cheese"] = {
    label = "Melted Cheese",
    weight = 1,
    stack = true,
    close = true,
},
["hb_sriracha"] = {
    label = "Sriracha",
    weight = 1,
    stack = true,
    close = true,
},
["hb_crispy_bacon"] = {
    label = "Crispy Bacon",
    weight = 1,
    stack = true,
    close = true,
},
["hb_sour_cream_chives"] = {
    label = "Sour Cream & Chives",
    weight = 1,
    stack = true,
    close = true,
},
["hb_carbonated_water"] = {
    label = "Carbonated Water",
    weight = 1,
    stack = true,
    close = true,
},
["hb_cola_flavor"] = {
    label = "Cola Flavoring",
    weight = 1,
    stack = true,
    close = true,
},
["hb_root_beer_extract"] = {
    label = "Root Beer Extract",
    weight = 1,
    stack = true,
    close = true,
},
["hb_orange_syrup"] = {
    label = "Orange Syrup",
    weight = 1,
    stack = true,
    close = true,
},
["hb_grape_syrup"] = {
    label = "Grape Syrup",
    weight = 1,
    stack = true,
    close = true,
},
["hb_fresh_lemon"] = {
    label = "Fresh Lemon",
    weight = 1,
    stack = true,
    close = true,
},
["hb_icecubes"] = {
    label = "Ice Cubes",
    weight = 1,
    stack = true,
    close = true,
},
["hb_waterbottle"] = {
    label = "Water Bottle",
    weight = 1,
    stack = true,
    close = true,
},
["hb_emptycup"] = {
    label = "Empty Cup",
    weight = 1,
    stack = true,
    close = true,
},
```

</details>

<details>

<summary>QB Inventory</summary>

```lua
['hb_classic_burger'] = {['name'] = 'hb_classic_burger', ['label'] = 'Classic Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_classic_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_spicy_burger'] = {['name'] = 'hb_spicy_burger', ['label'] = 'Spicy Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_spicy_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_cheesy_burger'] = {['name'] = 'hb_cheesy_burger', ['label'] = 'Cheesy Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_cheesy_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_bacon_burger'] = {['name'] = 'hb_bacon_burger', ['label'] = 'Bacon Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_bacon_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_double_burger'] = {['name'] = 'hb_double_burger', ['label'] = 'Double Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_double_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_milkshake'] = {['name'] = 'hb_milkshake', ['label'] = 'Milkshake', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_milkshake.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_iced_coffee'] = {['name'] = 'hb_iced_coffee', ['label'] = 'Iced Coffee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_iced_coffee.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_smoothie'] = {['name'] = 'hb_smoothie', ['label'] = 'Smoothie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_smoothie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_energy_drink'] = {['name'] = 'hb_energy_drink', ['label'] = 'Energy Drink', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_energy_drink.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_classic_fries'] = {['name'] = 'hb_classic_fries', ['label'] = 'Classic Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_classic_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_cheesy_fries'] = {['name'] = 'hb_cheesy_fries', ['label'] = 'Cheesy Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_cheesy_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_spicy_fries'] = {['name'] = 'hb_spicy_fries', ['label'] = 'Spicy Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_spicy_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_bacon_fries'] = {['name'] = 'hb_bacon_fries', ['label'] = 'Bacon Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_bacon_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_loaded_fries'] = {['name'] = 'hb_loaded_fries', ['label'] = 'Loaded Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_loaded_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_cola'] = {['name'] = 'hb_cola', ['label'] = 'Cola', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_cola.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_root_beer'] = {['name'] = 'hb_root_beer', ['label'] = 'Root Beer', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_root_beer.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_orange_soda'] = {['name'] = 'hb_orange_soda', ['label'] = 'Orange Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_orange_soda.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_grape_soda'] = {['name'] = 'hb_grape_soda', ['label'] = 'Grape Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_grape_soda.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_lemonlime'] = {['name'] = 'hb_lemonlime', ['label'] = 'Lemon-Lime', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_lemonlime.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_bun'] = {['name'] = 'hb_bun', ['label'] = 'Burger Bun', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_bun.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_sauce'] = {['name'] = 'hb_sauce', ['label'] = 'Horny Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_jalapeno_relish'] = {['name'] = 'hb_jalapeno_relish', ['label'] = 'Jalapeno Relish', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_jalapeno_relish.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_melted_cheddar'] = {['name'] = 'hb_melted_cheddar', ['label'] = 'Melted Cheddar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_melted_cheddar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_double_beef_patty'] = {['name'] = 'hb_double_beef_patty', ['label'] = 'Double Beef Patty', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_double_beef_patty.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_bbq_sauce'] = {['name'] = 'hb_bbq_sauce', ['label'] = 'Special BBQ Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_bbq_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_milk'] = {['name'] = 'hb_milk', ['label'] = 'Milk', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_milk.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_chocolate_syrup'] = {['name'] = 'hb_chocolate_syrup', ['label'] = 'Chocolate Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_chocolate_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_fresh_lemon'] = {['name'] = 'hb_fresh_lemon', ['label'] = 'Fresh Lemon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_fresh_lemon_juice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_mint_infusion'] = {['name'] = 'hb_mint_infusion', ['label'] = 'Mint Infusion', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_mint_infusion.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_coffee'] = {['name'] = 'hb_coffee', ['label'] = 'Coffee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_coffee.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_caramel_drizzle'] = {['name'] = 'hb_caramel_drizzle', ['label'] = 'Caramel Drizzle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_caramel_drizzle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_mixed_berries'] = {['name'] = 'hb_mixed_berries', ['label'] = 'Mixed Berries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_mixed_berries.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_honey'] = {['name'] = 'hb_honey', ['label'] = 'Honey', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_honey.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_caffeine_base'] = {['name'] = 'hb_caffeine_base', ['label'] = 'Caffeine Base', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_caffeine_base.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_citrus_blend'] = {['name'] = 'hb_citrus_blend', ['label'] = 'Citrus Blend', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_citrus_blend.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_potato_fries'] = {['name'] = 'hb_potato_fries', ['label'] = 'Potato Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_potato_fries.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_sea_salt'] = {['name'] = 'hb_sea_salt', ['label'] = 'Sea Salt & Pepper', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_sea_salt.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_melted_cheese'] = {['name'] = 'hb_melted_cheese', ['label'] = 'Melted Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_melted_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_sriracha'] = {['name'] = 'hb_sriracha', ['label'] = 'Sriracha', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_sriracha.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_crispy_bacon'] = {['name'] = 'hb_crispy_bacon', ['label'] = 'Crispy Bacon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_crispy_bacon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_sour_cream_chives'] = {['name'] = 'hb_sour_cream_chives', ['label'] = 'Sour Cream & Chives', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_sour_cream_chives.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_carbonated_water'] = {['name'] = 'hb_carbonated_water', ['label'] = 'Carbonated Water', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_carbonated_water.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_cola_flavor'] = {['name'] = 'hb_cola_flavor', ['label'] = 'Cola Flavoring', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_cola_flavor.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_root_beer_extract'] = {['name'] = 'hb_root_beer_extract', ['label'] = 'Root Beer Extract', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_root_beer_extract.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_orange_syrup'] = {['name'] = 'hb_orange_syrup', ['label'] = 'Orange Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_orange_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_grape_syrup'] = {['name'] = 'hb_grape_syrup', ['label'] = 'Grape Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_grape_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_icecubes'] = {['name'] = 'hb_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_waterbottle'] = {['name'] = 'hb_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_emptycup'] = {['name'] = 'hb_emptycup', ['label'] = 'Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>Quasar Inventory</summary>

```lua
['hb_classic_burger'] = {['name'] = 'hb_classic_burger', ['label'] = 'Classic Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_classic_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_spicy_burger'] = {['name'] = 'hb_spicy_burger', ['label'] = 'Spicy Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_spicy_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_cheesy_burger'] = {['name'] = 'hb_cheesy_burger', ['label'] = 'Cheesy Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_cheesy_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_bacon_burger'] = {['name'] = 'hb_bacon_burger', ['label'] = 'Bacon Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_bacon_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_double_burger'] = {['name'] = 'hb_double_burger', ['label'] = 'Double Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_double_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_milkshake'] = {['name'] = 'hb_milkshake', ['label'] = 'Milkshake', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_milkshake.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_iced_coffee'] = {['name'] = 'hb_iced_coffee', ['label'] = 'Iced Coffee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_iced_coffee.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_smoothie'] = {['name'] = 'hb_smoothie', ['label'] = 'Smoothie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_smoothie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_energy_drink'] = {['name'] = 'hb_energy_drink', ['label'] = 'Energy Drink', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_energy_drink.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_classic_fries'] = {['name'] = 'hb_classic_fries', ['label'] = 'Classic Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_classic_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_cheesy_fries'] = {['name'] = 'hb_cheesy_fries', ['label'] = 'Cheesy Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_cheesy_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_spicy_fries'] = {['name'] = 'hb_spicy_fries', ['label'] = 'Spicy Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_spicy_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_bacon_fries'] = {['name'] = 'hb_bacon_fries', ['label'] = 'Bacon Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_bacon_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_loaded_fries'] = {['name'] = 'hb_loaded_fries', ['label'] = 'Loaded Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_loaded_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_cola'] = {['name'] = 'hb_cola', ['label'] = 'Cola', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_cola.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_root_beer'] = {['name'] = 'hb_root_beer', ['label'] = 'Root Beer', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_root_beer.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_orange_soda'] = {['name'] = 'hb_orange_soda', ['label'] = 'Orange Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_orange_soda.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_grape_soda'] = {['name'] = 'hb_grape_soda', ['label'] = 'Grape Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_grape_soda.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_lemonlime'] = {['name'] = 'hb_lemonlime', ['label'] = 'Lemon-Lime', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_lemonlime.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_bun'] = {['name'] = 'hb_bun', ['label'] = 'Burger Bun', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_bun.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_sauce'] = {['name'] = 'hb_sauce', ['label'] = 'Horny Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_jalapeno_relish'] = {['name'] = 'hb_jalapeno_relish', ['label'] = 'Jalapeno Relish', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_jalapeno_relish.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_melted_cheddar'] = {['name'] = 'hb_melted_cheddar', ['label'] = 'Melted Cheddar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_melted_cheddar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_double_beef_patty'] = {['name'] = 'hb_double_beef_patty', ['label'] = 'Double Beef Patty', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_double_beef_patty.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_bbq_sauce'] = {['name'] = 'hb_bbq_sauce', ['label'] = 'Special BBQ Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_bbq_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_milk'] = {['name'] = 'hb_milk', ['label'] = 'Milk', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_milk.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_chocolate_syrup'] = {['name'] = 'hb_chocolate_syrup', ['label'] = 'Chocolate Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_chocolate_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_fresh_lemon'] = {['name'] = 'hb_fresh_lemon', ['label'] = 'Fresh Lemon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_fresh_lemon_juice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_mint_infusion'] = {['name'] = 'hb_mint_infusion', ['label'] = 'Mint Infusion', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_mint_infusion.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_coffee'] = {['name'] = 'hb_coffee', ['label'] = 'Coffee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_coffee.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_caramel_drizzle'] = {['name'] = 'hb_caramel_drizzle', ['label'] = 'Caramel Drizzle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_caramel_drizzle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_mixed_berries'] = {['name'] = 'hb_mixed_berries', ['label'] = 'Mixed Berries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_mixed_berries.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_honey'] = {['name'] = 'hb_honey', ['label'] = 'Honey', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_honey.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_caffeine_base'] = {['name'] = 'hb_caffeine_base', ['label'] = 'Caffeine Base', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_caffeine_base.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_citrus_blend'] = {['name'] = 'hb_citrus_blend', ['label'] = 'Citrus Blend', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_citrus_blend.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_potato_fries'] = {['name'] = 'hb_potato_fries', ['label'] = 'Potato Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_potato_fries.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_sea_salt'] = {['name'] = 'hb_sea_salt', ['label'] = 'Sea Salt & Pepper', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_sea_salt.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_melted_cheese'] = {['name'] = 'hb_melted_cheese', ['label'] = 'Melted Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_melted_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_sriracha'] = {['name'] = 'hb_sriracha', ['label'] = 'Sriracha', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_sriracha.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_crispy_bacon'] = {['name'] = 'hb_crispy_bacon', ['label'] = 'Crispy Bacon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_crispy_bacon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_sour_cream_chives'] = {['name'] = 'hb_sour_cream_chives', ['label'] = 'Sour Cream & Chives', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_sour_cream_chives.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_carbonated_water'] = {['name'] = 'hb_carbonated_water', ['label'] = 'Carbonated Water', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_carbonated_water.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_cola_flavor'] = {['name'] = 'hb_cola_flavor', ['label'] = 'Cola Flavoring', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_cola_flavor.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_root_beer_extract'] = {['name'] = 'hb_root_beer_extract', ['label'] = 'Root Beer Extract', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_root_beer_extract.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_orange_syrup'] = {['name'] = 'hb_orange_syrup', ['label'] = 'Orange Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_orange_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_grape_syrup'] = {['name'] = 'hb_grape_syrup', ['label'] = 'Grape Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_grape_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_icecubes'] = {['name'] = 'hb_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_waterbottle'] = {['name'] = 'hb_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['hb_emptycup'] = {['name'] = 'hb_emptycup', ['label'] = 'Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'hb_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>ESX ITems Sql</summary>

```lua
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
('hb_classic_burger', 'Classic Burger', 1),
('hb_spicy_burger', 'Spicy Burger', 1),
('hb_cheesy_burger', 'Cheesy Burger', 1),
('hb_bacon_burger', 'Bacon Burger', 1),
('hb_double_burger', 'Double Burger', 1),
('hb_milkshake', 'Milkshake', 1),
('hb_lemonade', 'Lemonade', 1),
('hb_iced_coffee', 'Iced Coffee', 1),
('hb_smoothie', 'Smoothie', 1),
('hb_energy_drink', 'Energy Drink', 1),
('hb_classic_fries', 'Classic Fries', 1),
('hb_cheesy_fries', 'Cheesy Fries', 1),
('hb_spicy_fries', 'Spicy Fries', 1),
('hb_bacon_fries', 'Bacon Fries', 1),
('hb_loaded_fries', 'Loaded Fries', 1),
('hb_cola', 'Cola', 1),
('hb_root_beer', 'Root Beer', 1),
('hb_orange_soda', 'Orange Soda', 1),
('hb_grape_soda', 'Grape Soda', 1),
('hb_lemonlime', 'Lemon-Lime', 1),
('hb_bun', 'Burger Bun', 1),
('hb_sauce', 'Horny Sauce', 1),
('hb_jalapeno_relish', 'Jalapeno Relish', 1),
('hb_melted_cheddar', 'Melted Cheddar', 1),
('hb_crispy_bacon', 'Crispy Bacon', 1),
('hb_double_beef_patty', 'Double Beef Patty', 1),
('hb_bbq_sauce', 'Special BBQ Sauce', 1),
('hb_milk', 'Milk', 1),
('hb_chocolate_syrup', 'Chocolate Syrup', 1),
('hb_fresh_lemon_juice', 'Fresh Lemon', 1),
('hb_mint_infusion', 'Mint Infusion', 1),
('hb_coffee', 'Coffee', 1),
('hb_caramel_drizzle', 'Caramel Drizzle', 1),
('hb_mixed_berries', 'Mixed Berries', 1),
('hb_honey', 'Honey', 1),
('hb_caffeine_base', 'Caffeine Base', 1),
('hb_citrus_blend', 'Citrus Blend', 1),
('hb_potato_fries', 'Potato Fries', 1),
('hb_sea_salt', 'Sea Salt & Pepper', 1),
('hb_melted_cheese', 'Melted Cheese', 1),
('hb_sriracha', 'Sriracha', 1),
('hb_crispy_bacon', 'Crispy Bacon', 1),
('hb_sour_cream_chives', 'Sour Cream & Chives', 1),
('hb_carbonated_water', 'Carbonated Water', 1),
('hb_cola_flavor', 'Cola Flavoring', 1),
('hb_root_beer_extract', 'Root Beer Extract', 1),
('hb_orange_syrup', 'Orange Syrup', 1),
('hb_grape_syrup', 'Grape Syrup', 1),
('hb_fresh_lemon', 'Fresh Lemon', 1),
('hb_icecubes', 'Ice Cubes', 1),
('hb_waterbottle', 'Water Bottle', 1),
('hb_emptycup', 'Empty Cup', 1);
```

</details>

### For QBCore Only

{% tabs %}
{% tab title="jobs.lua" %}
Add the Following in qb-core/shared/jobs.lua

```lua
['hornyburgers'] = {
    label = 'Horny Burgers',
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
['hornyburgers'] = {
    label = 'Horny Burgers',
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
    ['hb_cola'] = math.random(35, 54),
    ['hb_root_beer'] = math.random(35, 54),
    ['hb_orange_soda'] = math.random(35, 54),
    ['hb_grape_soda'] = math.random(35, 54),
    ['hb_lemonlime'] = math.random(35, 54),

    ['hb_milkshake'] = math.random(35, 54),
    ['hb_iced_coffee'] = math.random(35, 54),
    ['hb_smoothie'] = math.random(35, 54),
    ['hb_energy'] = math.random(35, 54),
}

Config.ConsumablesEat = {
    ['hb_classic_burger'] = math.random(35, 54),
    ['hb_spicy_burger'] = math.random(35, 54),
    ['hb_cheesy_burger'] = math.random(35, 54),
    ['hb_bacon_burger'] = math.random(35, 54),
    ['hb_double_burger'] = math.random(35, 54),

    ['hb_classic_fries'] = math.random(35, 54),
    ['hb_cheesy_fries'] = math.random(35, 54),
    ['hb_spicy_fries'] = math.random(35, 54),
    ['hb_bacon_fries'] = math.random(35, 54),
    ['hb_loaded_fries'] = math.random(35, 54),

}

--If using new qb-smallresources
Config.Consumables = {
    eat = {
        ['hb_classic_burger'] = math.random(35, 54),
        ['hb_spicy_burger'] = math.random(35, 54),
        ['hb_cheesy_burger'] = math.random(35, 54),
        ['hb_bacon_burger'] = math.random(35, 54),
        ['hb_double_burger'] = math.random(35, 54),

        ['hb_classic_fries'] = math.random(35, 54),
        ['hb_cheesy_fries'] = math.random(35, 54),
        ['hb_spicy_fries'] = math.random(35, 54),
        ['hb_bacon_fries'] = math.random(35, 54),
        ['hb_loaded_fries'] = math.random(35, 54),

    },
    drink = {
        ['hb_cola'] = math.random(35, 54),
        ['hb_root_beer'] = math.random(35, 54),
        ['hb_orange_soda'] = math.random(35, 54),
        ['hb_grape_soda'] = math.random(35, 54),
        ['hb_lemonlime'] = math.random(35, 54),
        
        ['hb_milkshake'] = math.random(35, 54),
        ['hb_iced_coffee'] = math.random(35, 54),
        ['hb_smoothie'] = math.random(35, 54),
        ['hb_energy'] = math.random(35, 54),

    },
}
```

</details>

<details>

<summary>Jim Consumables</summary>

Add the following in jim-consumables/shared/consumables.lua

```lua
--jim-consumables/shared/consumables.lua
hb_classic_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_spicy_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_cheesy_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_bacon_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_double_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_classic_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_cheesy_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_spicy_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_bacon_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_loaded_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },

hb_cola = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_root_beer = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_orange_soda = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_grape_soda = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_lemonlime = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_milkshake = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_iced_coffee = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_smoothie = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
hb_energy = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
```

</details>

### Add Images to Inventory

Copy all the Images folder and paste it in your inventory Images folder

### Log Webook Setup - Optional

To enable discord logs make sure to add your webhook in the server->Log.lua File

{% embed url="https://www.youtube.com/watch?pp=ygULI2FwcHlxczIwMjM=&v=fKksxz2Gdnc" %}

{% embed url="https://www.youtube.com/watch?v=rkWxUxoF3_s" %}

