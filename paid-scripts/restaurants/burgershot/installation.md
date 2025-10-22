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
CREATE TABLE IF NOT EXISTS `pl_burgershot` (
  `stock` longtext DEFAULT NULL,
  `state` varchar(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;

INSERT INTO `addon_account` (name, label, shared) VALUES
	('society_burgershot', 'BurgerShot', 1);

INSERT INTO `datastore` (name, label, shared) VALUES
	('society_burgershot', 'BurgerShot', 1);

INSERT INTO `jobs` (name, label,whitelisted) VALUES
	('burgershot', 'BurgerShot',1);

INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
	('burgershot',0,'cashier','Cashier',20,'{}','{}'),
	('burgershot',1,'cook','Cook',40,'{}','{}'),
	('burgershot',2,'staff','Staff',60,'{}','{}'),
	('burgershot',3,'manager','Manager',85,'{}','{}'),
	('burgershot',4,'boss','Owner',100,'{}','{}');
```

</details>

<details>

<summary>QBCore or Qbox</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_burgershot` (
  `stock` longtext DEFAULT NULL,
  `state` varchar(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;
```

</details>

### Items

Add the items into your server

<details>

<summary>Ox Inventory</summary>

```lua
["bs_buffalo_wings"] = {
    label = "Buffalo Wings",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_chicken_piece"] = {
    label = "Chicken Piece",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_chillwave_cola"] = {
    label = "Chillwave Cola",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},

["bs_classic_salted_fries"] = {
    label = "Classic Salted Fries",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_double_cheese_burger"] = {
    label = "Double Cheese Burger",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_fish_burger"] = {
    label = "Fish Burger",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},


["bs_fizzberry_splash"] = {
    label = "Fizzberry Splash",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},

["bs_garlic_parmesan_fries"] = {
    label = "Garlic Parmesan Fries",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},


["bs_honey_wings"] = {
    label = "Honey Wings",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_kentucky_burger"] = {
    label = "Kentucky Burger",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_lemonlush_soda"] = {
    label = "Lemonlush Soda",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},

["bs_mighty_zinger"] = {
    label = "Mighty Zinger",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_mushroom_veggie_burger"] = {
    label = "Mushroom Veggie Burger",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_nuggets"] = {
    label = "Nuggets",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_rice"] = {
    label = "Rice Label",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_signature_whooper"] = {
    label = "Signature Whooper",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_spicy_cajun_fries"] = {
    label = "Spicy Cajun Fries",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_spicy_rice"] = {
    label = "Spicy Rice",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_steakhouse_whooper"] = {
    label = "Steakhouse Whooper",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_sweet_potato_fries"] = {
    label = "Sweet Potato Fries",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_tortilla"] = {
    label = "Tortilla Label",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_truffle_fries"] = {
    label = "Truffle Fries",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_twister"] = {
    label = "Twister",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_whooper_jr"] = {
    label = "Whooper Jr",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_wings"] = {
    label = "Wings",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_zesty_zing"] = {
    label = "Zesty Zing",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},

["bs_zinger_burger"] = {
    label = "Zinger Burger",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_zinger_stacker"] = {
    label = "Zinger Stacker",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bs_long_cheesy_onion_beef"] = {
    label = "Long Cheesy Onion Beef",
    weight = 1,
    stack = true,
    close = true,
},

["bs_jalapeno"] = {
    label = "Jalapeno Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_honey"] = {
    label = "Honey Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_fish_fillet"] = {
    label = "Fish Fillet Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_bun"] = {
    label = "Bun Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_cajun_seasoning"] = {
    label = "Cajun Seasoning Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_cheese_slice"] = {
    label = "Cheese Slice Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_chicken"] = {
    label = "Chicken Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_mushroom"] = {
    label = "Mushroom Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_onion"] = {
    label = "Onion Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_parmesan_cheese"] = {
    label = "Parmesan Cheese Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_pepperoni"] = {
    label = "Pepperoni Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_piece"] = {
    label = "Piece Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_potato"] = {
    label = "Potato Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_truffle_oil"] = {
    label = "Truffle Oil Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_bbq_burger"] = {
    label = "BBQ Burger",
    weight = 1,
    stack = true,
    close = true,
},

["bs_bbq_sauce"] = {
    label = "BBQ Sauce Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_beef_patty"] = {
    label = "Beef Patty Label",
    weight = 1,
    stack = true,
    close = true,
},

["bs_buffalo_sauce"] = {
    label = "Buffalo Sauce Label",
    weight = 1,
    stack = true,
    close = true,
},
["bs_emptycup"] = {
    label = "BurgerShot EmptyCup",
    weight = 1,
    stack = true,
    close = true,
},
["bs_icecubes"] = {
    label = "Ice Cubes",
    weight = 1,
    stack = true,
    close = true,
},
["bs_waterbottle"] = {
    label = "Water Bottle",
    weight = 1,
    stack = true,
    close = true,
},

["bs_tomato"] = {
    label = "Tomato Label",
    weight = 1,
    stack = true,
    close = true,
},
```

</details>

<details>

<summary>QB Inventory</summary>

```lua
['bs_zinger_burger'] = {['name'] = 'bs_zinger_burger', ['label'] = 'Zinger Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_zinger_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_zinger_stacker'] = {['name'] = 'bs_zinger_stacker', ['label'] = 'Zinger Stacker', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_zinger_stacker.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_kentucky_burger'] = {['name'] = 'bs_kentucky_burger', ['label'] = 'Kentucky Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_kentucky_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_mighty_zinger'] = {['name'] = 'bs_mighty_zinger', ['label'] = 'Mighty Zinger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_mighty_zinger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_twister'] = {['name'] = 'bs_twister', ['label'] = 'Twister', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_twister.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_nuggets'] = {['name'] = 'bs_nuggets', ['label'] = 'Nuggets', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_nuggets.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_wings'] = {['name'] = 'bs_wings', ['label'] = 'Wings', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_wings.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_honey_wings'] = {['name'] = 'bs_honey_wings', ['label'] = 'Honey Wings', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_wings.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_buffalo_wings'] = {['name'] = 'bs_buffalo_wings', ['label'] = 'Buffalo Wings', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_wings.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_chicken_piece'] = {['name'] = 'bs_chicken_piece', ['label'] = 'Chicken Piece', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_chicken_piece.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_fries'] = {['name'] = 'bs_fries', ['label'] = 'Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_spicy_rice'] = {['name'] = 'bs_spicy_rice', ['label'] = 'Spicy Rice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_spicy_rice.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_piece'] = {['name'] = 'bs_piece', ['label'] = 'Piece', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_piece.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_bun'] = {['name'] = 'bs_bun', ['label'] = 'Bun', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_bun.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_jalapeno'] = {['name'] = 'bs_jalapeno', ['label'] = 'Jalapeno', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_jalapeno.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_pepperoni'] = {['name'] = 'bs_pepperoni', ['label'] = 'Pepperoni', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_pepperoni.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_cheese_slice'] = {['name'] = 'bs_cheese_slice', ['label'] = 'Cheese Slice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_cheese_slice.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_tortilla'] = {['name'] = 'bs_tortilla', ['label'] = 'Tortilla', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_tortilla.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_tomato'] = {['name'] = 'bs_tomato', ['label'] = 'Tomato', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_tomato.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_chicken'] = {['name'] = 'bs_chicken', ['label'] = 'Chicken', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_chicken.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_honey'] = {['name'] = 'bs_honey', ['label'] = 'Honey', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_honey.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_buffalo_sauce'] = {['name'] = 'bs_buffalo_sauce', ['label'] = 'Buggalo Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_buffalo_sauce.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_potato'] = {['name'] = 'bs_potato', ['label'] = 'Potato', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_potato.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_rice'] = {['name'] = 'bs_rice', ['label'] = 'Rice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_rice.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_mushroom_veggie_burger'] = {['name'] = 'bs_mushroom_veggie_burger', ['label'] = 'Mushroom Veggie Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_mushroom_veggie_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_beef_patty'] = {['name'] = 'bs_beef_patty', ['label'] = 'Beef Patty', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_beef_patty.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_mushroom'] = {['name'] = 'bs_mushroom', ['label'] = 'Mushroom', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_mushroom.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_steakhouse_whooper'] = {['name'] = 'bs_steakhouse_whooper', ['label'] = 'Steakhouse Whooper', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_steakhouse_whooper.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_fish_burger'] = {['name'] = 'bs_fish_burger', ['label'] = 'Fish Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_fish_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_fish_fillet'] = {['name'] = 'bs_fish_fillet', ['label'] = 'Fish Fillet', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_fish_fillet.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_double_cheese_burger'] = {['name'] = 'bs_double_cheese_burger', ['label'] = 'Dobule Cheese Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_double_cheese_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_bbq_burger'] = {['name'] = 'bs_bbq_burger', ['label'] = 'BBQ Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_bbq_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_bbq_sauce'] = {['name'] = 'bs_bbq_sauce', ['label'] = 'BBQ Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_bbq_sauce.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_signature_whooper'] = {['name'] = 'bs_signature_whooper', ['label'] = 'Signature Whooper', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_signature_whooper.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_whooper_jr'] = { ['name'] = 'bs_whooper_jr', ['label'] = 'Whooper JR', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_whooper_jr.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_long_cheesy_onion_beef'] = { ['name'] = 'bs_long_cheesy_onion_beef', ['label'] = 'Long Cheesy Onion Beef', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_long_cheesy_onion_beef.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_onion'] = { ['name'] = 'bs_onion', ['label'] = 'Onion', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_onion.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_chillwave_cola'] = { ['name'] = 'bs_ochillwave_cola', ['label'] = 'ChillWave Cola', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_chillwave_cola.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_fizzberry_splash'] = { ['name'] = 'bs_fizzberry_splash', ['label'] = 'FizzBerry Splash', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_fizzberry_splash.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_lemonlush_soda'] = { ['name'] = 'bs_lemonlush_soda', ['label'] = 'LemonLush Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_lemonlush_soda.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_zesty_zing'] = { ['name'] = 'bs_zesty_zing', ['label'] = 'Zesty Zing', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_zesty_zing.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_classic_salted_fries'] = { ['name'] = 'bs_classic_salted_fries', ['label'] = 'Classic Salted Fires', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_classic_salted_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_garlic_parmesan_fries'] = { ['name'] = 'bs_garlic_parmesan_fries', ['label'] = 'Garlic Parmesan Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_garlic_parmesan_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_spicy_cajun_fries'] = { ['name'] = 'bs_spicy_cajun_fries', ['label'] = 'Spicy Cajun Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_spicy_cajun_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_truffle_fries'] = { ['name'] = 'bs_truffle_fries', ['label'] = 'Truffle Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_truffle_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_sweet_potato_fries'] = { ['name'] = 'bs_sweet_potato_fries', ['label'] = 'Sweet Potato Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_sweet_potato_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_potatoes'] = { ['name'] = 'bs_potatoes', ['label'] = 'Potatoes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_potatoes.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_parmesan_cheese'] = { ['name'] = 'bs_parmesan_cheese', ['label'] = 'Parmesan Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_parmesan_cheese.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_cajun_seasoning'] = { ['name'] = 'bs_cajun_seasoning', ['label'] = 'Cajun Seasoning', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_cajun_seasoning.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_truffle_oil'] = { ['name'] = 'bs_truffle_oil', ['label'] = 'Truffle Oil', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_truffle_oil.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_emptycup'] = { ['name'] = 'bs_emptycup', ['label'] = 'Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_icecubes'] = { ['name'] = 'bs_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_waterbottle'] = { ['name'] = 'bs_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
```

</details>

<details>

<summary>Quasar Inventory</summary>

```lua
['bs_zinger_burger'] = {['name'] = 'bs_zinger_burger', ['label'] = 'Zinger Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_zinger_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_zinger_stacker'] = {['name'] = 'bs_zinger_stacker', ['label'] = 'Zinger Stacker', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_zinger_stacker.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_kentucky_burger'] = {['name'] = 'bs_kentucky_burger', ['label'] = 'Kentucky Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_kentucky_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_mighty_zinger'] = {['name'] = 'bs_mighty_zinger', ['label'] = 'Mighty Zinger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_mighty_zinger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_twister'] = {['name'] = 'bs_twister', ['label'] = 'Twister', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_twister.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_nuggets'] = {['name'] = 'bs_nuggets', ['label'] = 'Nuggets', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_nuggets.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_wings'] = {['name'] = 'bs_wings', ['label'] = 'Wings', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_wings.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_honey_wings'] = {['name'] = 'bs_honey_wings', ['label'] = 'Honey Wings', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_wings.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_buffalo_wings'] = {['name'] = 'bs_buffalo_wings', ['label'] = 'Buffalo Wings', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_wings.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_chicken_piece'] = {['name'] = 'bs_chicken_piece', ['label'] = 'Chicken Piece', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_chicken_piece.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_fries'] = {['name'] = 'bs_fries', ['label'] = 'Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_spicy_rice'] = {['name'] = 'bs_spicy_rice', ['label'] = 'Spicy Rice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_spicy_rice.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_piece'] = {['name'] = 'bs_piece', ['label'] = 'Piece', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_piece.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_bun'] = {['name'] = 'bs_bun', ['label'] = 'Bun', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_bun.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_jalapeno'] = {['name'] = 'bs_jalapeno', ['label'] = 'Jalapeno', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_jalapeno.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_pepperoni'] = {['name'] = 'bs_pepperoni', ['label'] = 'Pepperoni', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_pepperoni.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_cheese_slice'] = {['name'] = 'bs_cheese_slice', ['label'] = 'Cheese Slice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_cheese_slice.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_tortilla'] = {['name'] = 'bs_tortilla', ['label'] = 'Tortilla', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_tortilla.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_tomato'] = {['name'] = 'bs_tomato', ['label'] = 'Tomato', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_tomato.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_chicken'] = {['name'] = 'bs_chicken', ['label'] = 'Chicken', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_chicken.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_honey'] = {['name'] = 'bs_honey', ['label'] = 'Honey', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_honey.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_buffalo_sauce'] = {['name'] = 'bs_buffalo_sauce', ['label'] = 'Buggalo Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_buffalo_sauce.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_potato'] = {['name'] = 'bs_potato', ['label'] = 'Potato', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_potato.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_rice'] = {['name'] = 'bs_rice', ['label'] = 'Rice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_rice.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_mushroom_veggie_burger'] = {['name'] = 'bs_mushroom_veggie_burger', ['label'] = 'Mushroom Veggie Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_mushroom_veggie_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_beef_patty'] = {['name'] = 'bs_beef_patty', ['label'] = 'Beef Patty', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_beef_patty.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_mushroom'] = {['name'] = 'bs_mushroom', ['label'] = 'Mushroom', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_mushroom.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_steakhouse_whooper'] = {['name'] = 'bs_steakhouse_whooper', ['label'] = 'Steakhouse Whooper', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_steakhouse_whooper.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_fish_burger'] = {['name'] = 'bs_fish_burger', ['label'] = 'Fish Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_fish_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_fish_fillet'] = {['name'] = 'bs_fish_fillet', ['label'] = 'Fish Fillet', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_fish_fillet.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_double_cheese_burger'] = {['name'] = 'bs_double_cheese_burger', ['label'] = 'Dobule Cheese Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_double_cheese_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_bbq_burger'] = {['name'] = 'bs_bbq_burger', ['label'] = 'BBQ Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_bbq_burger.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_bbq_sauce'] = {['name'] = 'bs_bbq_sauce', ['label'] = 'BBQ Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_bbq_sauce.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_signature_whooper'] = {['name'] = 'bs_signature_whooper', ['label'] = 'Signature Whooper', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_signature_whooper.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bs_whooper_jr'] = { ['name'] = 'bs_whooper_jr', ['label'] = 'Whooper JR', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_whooper_jr.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_long_cheesy_onion_beef'] = { ['name'] = 'bs_long_cheesy_onion_beef', ['label'] = 'Long Cheesy Onion Beef', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_long_cheesy_onion_beef.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_onion'] = { ['name'] = 'bs_onion', ['label'] = 'Onion', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_onion.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_chillwave_cola'] = { ['name'] = 'bs_ochillwave_cola', ['label'] = 'ChillWave Cola', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_chillwave_cola.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_fizzberry_splash'] = { ['name'] = 'bs_fizzberry_splash', ['label'] = 'FizzBerry Splash', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_fizzberry_splash.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_lemonlush_soda'] = { ['name'] = 'bs_lemonlush_soda', ['label'] = 'LemonLush Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_lemonlush_soda.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_zesty_zing'] = { ['name'] = 'bs_zesty_zing', ['label'] = 'Zesty Zing', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_zesty_zing.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_classic_salted_fries'] = { ['name'] = 'bs_classic_salted_fries', ['label'] = 'Classic Salted Fires', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_classic_salted_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_garlic_parmesan_fries'] = { ['name'] = 'bs_garlic_parmesan_fries', ['label'] = 'Garlic Parmesan Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_garlic_parmesan_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_spicy_cajun_fries'] = { ['name'] = 'bs_spicy_cajun_fries', ['label'] = 'Spicy Cajun Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_spicy_cajun_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_truffle_fries'] = { ['name'] = 'bs_truffle_fries', ['label'] = 'Truffle Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_truffle_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_sweet_potato_fries'] = { ['name'] = 'bs_sweet_potato_fries', ['label'] = 'Sweet Potato Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_sweet_potato_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_potatoes'] = { ['name'] = 'bs_potatoes', ['label'] = 'Potatoes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_potatoes.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_parmesan_cheese'] = { ['name'] = 'bs_parmesan_cheese', ['label'] = 'Parmesan Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_parmesan_cheese.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_cajun_seasoning'] = { ['name'] = 'bs_cajun_seasoning', ['label'] = 'Cajun Seasoning', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_cajun_seasoning.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_truffle_oil'] = { ['name'] = 'bs_truffle_oil', ['label'] = 'Truffle Oil', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_truffle_oil.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_emptycup'] = { ['name'] = 'bs_emptycup', ['label'] = 'Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_icecubes'] = { ['name'] = 'bs_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['bs_waterbottle'] = { ['name'] = 'bs_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bs_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
```

</details>

<details>

<summary>ESX ITems Sql</summary>

```lua
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
	('bs_piece', 'Piece Label', 1),
    ('bs_bun', 'Bun Label', 1),
    ('bs_jalapeno', 'Jalapeno Label', 1),
    ('bs_pepperoni', 'Pepperoni Label', 1),
    ('bs_cheese_slice', 'Cheese Slice Label', 1),
    ('bs_tortilla', 'Tortilla Label', 1),
    ('bs_tomato', 'Tomato Label', 1),
    ('bs_chicken', 'Chicken Label', 1),
    ('bs_honey', 'Honey Label', 1),
    ('bs_buffalo_sauce', 'Buffalo Sauce Label', 1),
    ('bs_potato', 'Potato Label', 1),
    ('bs_rice', 'Rice Label', 1),
    ('bs_beef_patty', 'Beef Patty Label', 1),
    ('bs_mushroom', 'Mushroom Label', 1),
    ('bs_fish_fillet', 'Fish Fillet Label', 1),
    ('bs_bbq_sauce', 'BBQ Sauce Label', 1),
    ('bs_onion', 'Onion Label', 1),
    ('bs_parmesan_cheese', 'Parmesan Cheese Label', 1),
    ('bs_cajun_seasoning', 'Cajun Seasoning Label', 1),
    ('bs_truffle_oil', 'Truffle Oil Label', 1),
    ('bs_zinger_burger', 'Zinger Burger', 1),
    ('bs_zinger_stacker', 'Zinger Stacker', 1),
    ('bs_kentucky_burger', 'Kentucky Burger', 1),
    ('bs_mighty_zinger', 'Mighty Zinger', 1),
    ('bs_twister', 'Twister', 1),
    ('bs_nuggets', 'Nuggets', 1),
    ('bs_wings', 'Wings', 1),
    ('bs_honey_wings', 'Honey Wings', 1),
    ('bs_buffalo_wings', 'Buffalo Wings', 1),
    ('bs_chicken_piece', 'Chicken Piece', 1),
    ('bs_spicy_rice', 'Spicy Rice', 1),
    ('bs_mushroom_veggie_burger', 'Mushroom Veggie Burger', 1),
    ('bs_steakhouse_whooper', 'Steakhouse Whooper', 1),
    ('bs_fish_burger', 'Fish Burger', 1),
    ('bs_double_cheese_burger', 'Double Cheese Burger', 1),
    ('bs_bbq_burger', 'BBQ Burger', 1),
    ('bs_signature_whooper', 'Signature Whooper', 1),
    ('bs_whooper_jr', 'Whooper Jr', 1),
    ('bs_long_cheesy_onion_beef', 'Long Cheesy Onion Beef', 1),
    ('bs_chillwave_cola', 'Chillwave Cola', 1),
    ('bs_fizzberry_splash', 'Fizzberry Splash', 1),
    ('bs_lemonlush_soda', 'Lemonlush Soda', 1),
    ('bs_classic_salted_fries', 'Classic Salted Fries', 1),
    ('bs_garlic_parmesan_fries', 'Garlic Parmesan Fries', 1),
    ('bs_spicy_cajun_fries', 'Spicy Cajun Fries', 1),
    ('bs_truffle_fries', 'Truffle Fries', 1),
    ('bs_sweet_potato_fries', 'Sweet Potato Fries', 1),
    ('bs_emptycup', 'EmptyCup', 1),
 ('bs_zesty_zing', 'Zesty Zing', 1),
    ('bs_icecubes', 'Ice Cubes', 1),
    ('bs_waterbottle', 'Water Bottle', 1);
```

</details>

### For QBCore Only

{% tabs %}
{% tab title="jobs.lua" %}
Add the Following in qb-core/shared/jobs.lua

```lua
['burgershot'] = {
    label = 'BurgerShot',
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
['burgershot'] = {
    label = 'BurgerShot',
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
    ['bs_chillwave_cola'] = math.random(35, 54),
    ['bs_fizzberry_splash'] = math.random(35, 54),
    ['bs_lemonlush_soda'] = math.random(35, 54),
    ['bs_zesty_zing'] = math.random(35, 54),
}

Config.ConsumablesEat = {
    ['bs_zinger_burger'] = math.random(35, 54),
    ['bs_zinger_stacker'] = math.random(35, 54),
    ['bs_kentucky_burger'] = math.random(35, 54),
    ['bs_mighty_zinger'] = math.random(35, 54),
    ['bs_mushroom_veggie_burger'] = math.random(35, 54),
    ['bs_steakhouse_whooper'] = math.random(35, 54),
    ['bs_fish_burger'] = math.random(35, 54),
    ['bs_double_cheese_burger'] = math.random(35, 54),
    ['bs_bbq_burger'] = math.random(35, 54),
    ['bs_signature_whooper'] = math.random(35, 54),
    ['bs_whooper_jr'] = math.random(35, 54),
    ['bs_long_cheesy_onion_beef'] = math.random(35, 54),

    ['bs_classic_salted_fries'] = math.random(35, 54),
    ['bs_garlic_parmesan_fries'] = math.random(35, 54),
    ['bs_spicy_cajun_fries'] = math.random(35, 54),
    ['bs_truffle_fries'] = math.random(35, 54),
    ['bs_sweet_potato_fries'] = math.random(35, 54),
    ['bs_twister'] = math.random(35, 54),
    ['bs_nuggets'] = math.random(35, 54),
    ['bs_wings'] = math.random(35, 54),
    ['bs_honey_wings'] = math.random(35, 54),
    ['bs_buffalo_wings'] = math.random(35, 54),
    ['bs_chicken_piece'] = math.random(35, 54),
    ['bs_spicy_rice'] = math.random(35, 54),
}

--If using new qb-smallresources
Config.Consumables = {
    eat = {
        ['bs_zinger_burger'] = math.random(35, 54), 
        ['bs_zinger_stacker'] = math.random(35, 54),
        ['bs_kentucky_burger'] = math.random(35, 54),
        ['bs_mighty_zinger'] = math.random(35, 54),
        ['bs_mushroom_veggie_burger'] = math.random(35, 54),
        ['bs_steakhouse_whooper'] = math.random(35, 54),
        ['bs_fish_burger'] = math.random(35, 54),
        ['bs_double_cheese_burger'] = math.random(35, 54),
        ['bs_bbq_burger'] = math.random(35, 54),
        ['bs_signature_whooper'] = math.random(35, 54),
        ['bs_whooper_jr'] = math.random(35, 54),
        ['bs_long_cheesy_onion_beef'] = math.random(35, 54),

        ['bs_classic_salted_fries'] = math.random(35, 54),
        ['bs_garlic_parmesan_fries'] = math.random(35, 54),
        ['bs_spicy_cajun_fries'] = math.random(35, 54),
        ['bs_truffle_fries'] = math.random(35, 54),
        ['bs_sweet_potato_fries'] = math.random(35, 54),
        ['bs_twister'] = math.random(35, 54),
        ['bs_nuggets'] = math.random(35, 54),
        ['bs_wings'] = math.random(35, 54),
        ['bs_honey_wings'] = math.random(35, 54),
        ['bs_buffalo_wings'] = math.random(35, 54),
        ['bs_chicken_piece'] = math.random(35, 54),
        ['bs_spicy_rice'] = math.random(35, 54),
    },
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
bs_zinger_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_zinger_stacker = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_kentucky_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_mighty_zinger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_mushroom_veggie_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_steakhouse_whooper = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_fish_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_double_cheese_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_bbq_burger = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_signature_whooper = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_whooper_jr = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_long_cheesy_onion_beef = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_classic_salted_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_garlic_parmesan_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_spicy_cajun_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_truffle_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_sweet_potato_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_twister = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_nuggets = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_wings = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_honey_wings = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_buffalo_wings = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_chicken_piece = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_spicy_rice = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_chillwave_cola = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_fizzberry_splash = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_lemonlush_soda = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bs_zesty_zing = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
```

</details>

### Add Images to Inventory

Copy all the Images folder and paste it in your inventory Images folder

### Livery

Download the vehicle and livery from the below links and install. Make sure to add the .ytd file from the livery into the resource.

Vehicle - [Download](https://www.gta5-mods.com/vehicles/vapid-speedo-express-add-on-liveries)

Livery - [Download](https://www.gta5-mods.com/paintjobs/vapid-speedo-express-burgershot-livery)

### Log Webook Setup - Optional

To enable discord logs make sure to add your webhook in the server->Log.lua File

{% embed url="https://www.youtube.com/watch?pp=ygULI2FwcHlxczIwMjM=&v=fKksxz2Gdnc" %}

### Optional Dj Custom Props

If you have purchased the DJ Burgershot Props [https://djscollections.com/package/6098332](https://djscollections.com/package/6098332) just install it and set the Config.UseDjItems = true

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

### Video of Installation:

{% embed url="https://www.youtube.com/watch?v=rkWxUxoF3_s" %}
