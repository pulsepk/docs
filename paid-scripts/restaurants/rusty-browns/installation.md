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
CREATE TABLE IF NOT EXISTS `pl_rustybrowns` (
     `stock` longtext DEFAULT NULL,
     `state` varchar(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;

INSERT INTO `addon_account` (name, label, shared) VALUES
       ('society_rustybrowns', 'Rusty Browns', 1);
       
INSERT INTO `datastore` (name, label, shared) VALUES
       ('society_rustybrowns', 'Rusty Browns', 1);
       
INSERT INTO `jobs` (name, label,whitelisted) VALUES
       ('rustybrowns', 'Rusty Browns',1);
       
INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
        ('rustybrowns',0,'cashier','Cashier',20,'{}','{}'),
        ('rustybrowns',1,'cook','Cook',40,'{}','{}'),
        ('rustybrowns',2,'staff','Staff',60,'{}','{}'),
        ('rustybrowns',3,'manager','Manager',85,'{}','{}'),
        ('rustybrowns',4,'boss','Owner',100,'{}','{}');
```

</details>

<details>

<summary>QBCore or Qbox</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_rustybrowns` (
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
["berry_glazed_donut"] = {
                label = "Berry Glazed Donut",
                weight = 1,
                 client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a donut'
		},
},
["chococream_donut"] = {
        label = "Cream Filled Donut",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a donut'
		},
},
["chocfrosted_donut"] = {
        label = "Chocolate Frosted Donut",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a donut'
		},
},
["sprinkled_donut"] = {
        label = "Chocolate Sprinkled Donut",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a donut'
		},
},
["cinnamon_sugar_donut"] = {
        label = "Cinnamon Sugar Donut",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a donut'
		},
},
["cookiecream_donut"] = {
        label = "Cookies and Cream Donut",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a donut'
		},
},
["cruller_donut"] = {
        label = "Cruller Donut",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a donut'
		},
},
["lemon_iced_donut"] = {
        label = "Lemon Iced Donut",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a donut'
		},
},
["mapple_bar_donut"] = {
        label = "Mapple Bar Donut",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a donut'
		},
},
["strawberry_iced_donut"] = {
        label = "Strawberry Iced Donut",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a donut'
		},
},
["iced_caramel_latte"] = {
        label = "Iced Caramel Latte",
        weight = 1,
        client = {
		status = { thirst = 200000 },
		anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
		prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
		usetime = 2500,
		notification = 'You quenched your thirst with a sprunk'
	}
},
["mocha_frappe"] = {
        label = "Mocha Frappe",
        weight = 1,
        client = {
		status = { thirst = 200000 },
		anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
		prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
		usetime = 2500,
		notification = 'You quenched your thirst with a sprunk'
	}
},
["cold_brew_coffee"] = {
        label = "Rusty Cold Brew Coffee",
        weight = 1,
        client = {
		status = { thirst = 200000 },
		anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
		prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
		usetime = 2500,
		notification = 'You quenched your thirst with a sprunk'
	}
},
["iced_matcha_latte"] = {
        label = "Rusty Iced Matcha Latte",
        weight = 1,
        client = {
		status = { thirst = 200000 },
		anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
		prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
		usetime = 2500,
		notification = 'You quenched your thirst with a sprunk'
	}
},
["vanilla_iced_coffee"] = {
        label = "Rusty Vanilla Iced Coffee",
        weight = 1,
        client = {
		status = { thirst = 200000 },
		anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
		prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
		usetime = 2500,
		notification = 'You quenched your thirst with a sprunk'
	}
},
["strawberry_lemonade_slush"] = {
        label = "Rustys Strawberry Lemonade Slush",
        weight = 1,
        client = {
		status = { thirst = 200000 },
		anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
		prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
		usetime = 2500,
		notification = 'You quenched your thirst with a sprunk'
	}
},
["iced_chai_tea_latte"] = {
        label = "Rusty Iced Tea Latte",
        weight = 1,
        client = {
		status = { thirst = 200000 },
		anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
		prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
		usetime = 2500,
		notification = 'You quenched your thirst with a sprunk'
	}
},
["iced_mocha"] = {
        label = "Rusty Iced Mocha",
        weight = 1,
        client = {
		status = { thirst = 200000 },
		anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
		prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
		usetime = 2500,
		notification = 'You quenched your thirst with a sprunk'
	}
},
["iced_coconut_coffee"] = {
        label = "Rusty Iced Coconut Coffee",
        weight = 1,
        client = {
		status = { thirst = 200000 },
		anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
		prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
		usetime = 2500,
		notification = 'You quenched your thirst with a sprunk'
	}
},
["mint_chocolate_chip_milkshake"] = {
        label = "Rusty Mint Chocolate Milkshake",
        weight = 1,
        client = {
		status = { thirst = 200000 },
		anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
		prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
		usetime = 2500,
		notification = 'You quenched your thirst with a sprunk'
	}
},
["croissant"] = {
        label = "Croissant",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a pastry'
		},
},
["apple_turnover"] = {
        label = "Apple Turnover",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a pastry'
		},
},
["cinnamon_roll"] = {
        label = "Cinnamon Roll",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a pastry'
		},
},
["eclairs"] = {
        label = "Eclairs",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a pastry'
		},
},
["danish_pastry"] = {
        label = "Danish Pastry",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a pastry'
		},
},
["puff_pastry_tarts"] = {
        label = "Puff Pastry Tart",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a pastry'
		},
},
["chocolate_pastry"] = {
        label = "Chocolate Pastry",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a pastry'
		},
},
["cream_puff"] = {
        label = "Cream Puff",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a pastry'
		},
},
["sticky_bun"] = {
        label = "Sticky Bun",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a pastry'
		},
},
["fruit_strudel"] = {
        label = "Fruit Strudel",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a pastry'
		},
},
["box_donut_a"] = {
        label = "Sprinkled Donut Box",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate alot of Donuts'
		},
},
["box_donut_b"] = {
        label = "ChocoCream Donut Box",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate alot of Donuts'
		},
},
["box_donut_c"] = {
        label = "Cinnamon Sugar Donut Box",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate alot of Donuts'
		},
},
["box_donut_d"] = {
        label = "Lemon Iced Donut Box",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate alot of Donuts'
		},
},
["box_donut_e"] = {
        label = "Strawberry Iced Donut Box",
        weight = 1,
        client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate alot of Donuts'
		},
},
["rs_flour"] = {
        label = "Rustys Donut Base",
        weight = 1,
        stack = true,
        close = true,
},
["rs_berries"] = {
        label = "Rustys Berries",
        weight = 1,
        stack = true,
        close = true,
},
["rs_chocolate_cream"] = {
        label = "Rustys Chocolate cream filling",
        weight = 1,
        stack = true,
        close = true,
},
["rs_chocolate_glaze"] = {
        label = "Rustys Chocolate glaze",
        weight = 1,
        stack = true,
        close = true,
},
["rs_sprinkling_chocolate"] = {
        label = "Rustys Sprinkling Chocolate",
        weight = 1,
        stack = true,
        close = true,
},
["rs_cinnamon_sugar"] = {
        label = "Rustys Cinnamon and Sugar Coating",
        weight = 1,
        stack = true,
        close = true,
},
["rs_choco_cookies"] = {
        label = "Rustys Chocolate Cookies",
        weight = 1,
        stack = true,
        close = true,
},
["rs_sugar_glaze"] = {
        label = "Rustys Sugar Glaze",
        weight = 1,
        stack = true,
        close = true,
},
["rs_lemon"] = {
        label = "Rustys Lemon",
        weight = 1,
        stack = true,
        close = true,
},
["rs_maple_glaze"] = {
        label = "Rustys Maple Glaze",
        weight = 1,
        stack = true,
        close = true,
},
["rs_strawberry"] = {
        label = "Rustys Strawberry",
        weight = 1,
        stack = true,
        close = true,
},
["rs_ice"] = {
        label = "Rustys Ice",
        weight = 1,
        stack = true,
        close = true,
},
["rs_caramel_syrup"] = {
        label = "Rustys Chocolate Syrup",
        weight = 1,
        stack = true,
        close = true,
},
["rs_chocolate_syrup"] = {
        label = "Black Beans",
        weight = 1,
        stack = true,
        close = true,
},
["rs_coffee_beans"] = {
        label = "Rustys Coffee Beans",
        weight = 1,
        stack = true,
        close = true,
},
["rs_matcha_powder"] = {
        label = "Rustys Matcha Powder",
        weight = 1,
        stack = true,
        close = true,
},
["rs_chai_tea"] = {
        label = "Rustys Tea Concentrate",
        weight = 1,
        stack = true,
        close = true,
},
["rs_espresso"] = {
        label = "Rustys Espresso",
        weight = 1,
        stack = true,
        close = true,
},
["rs_coconut_milk"] = {
        label = "Rustys Coconut Milk",
        weight = 1,
        stack = true,
        close = true,
},
["rs_mint_icecream"] = {
        label = "Rustys Mint IceCream",
        weight = 1,
        stack = true,
        close = true,
},
["rs_butter"] = {
        label = "Rustys Butter",
        weight = 1,
        stack = true,
        close = true,
},
["rs_apple_filling"] = {
        label = "Rustys Apple filling",
        weight = 1,
        stack = true,
        close = true,
},
["rs_pastry_cream"] = {
        label = "Rustys Pastry cream",
        weight = 1,
        stack = true,
        close = true,
},
["rs_cream_cheese"] = {
        label = "Rustys Cream cheese",
        weight = 1,
        stack = true,
        close = true,
},
["rs_chocolate_sticks"] = {
        label = "Rustys Chocolate sticks",
        weight = 1,
        stack = true,
        close = true,
},
["rs_whipped_cream"] = {
        label = "Rustys Whipped cream",
        weight = 1,
        stack = true,
        close = true,
},
["rs_brownbutter_cinnamon"] = {
        label = "Rustys Brown Sugar",
        weight = 1,
        stack = true,
        close = true,
},
["rs_vanilla_syrup"] = {
        label = "Rustys Vanilla Syrup",
        weight = 1,
        stack = true,
        close = true,
},
["rs_emptycup"] = {
        label = "Rustys Empty Cup",
        weight = 1,
        stack = true,
        close = true,
},
["rs_icecubes"] = {
        label = "Rustys Ice Cubes",
        weight = 1,
        stack = true,
        close = true,
},
["rs_waterbottle"] = {
        label = "Rustys Water Bottle",
        weight = 1,
        stack = true,
        close = true,
},
```

</details>

<details>

<summary>QB Inventory</summary>

```lua
['berry_glazed_donut'] = {['name'] = 'berry_glazed_donut', ['label'] = 'Berry Glazed Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'berry_glazed_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['chococream_donut'] = {['name'] = 'choccream_donut', ['label'] = 'Cream Filled Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'choco_cream_filled_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['chocfrosted_donut'] = {['name'] = 'chocfrosted_donut', ['label'] = 'Chocolate Frosted Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'chocfrosted_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['sprinkled_donut'] = {['name'] = 'sprinkled_donut', ['label'] = 'Chocolate Sprinkled Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'chocolate_sprinkled_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cinnamon_sugar_donut'] = {['name'] = 'cinnamon_sugar_donut', ['label'] = 'Cinnamon Sugar Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cinnamon_sugar_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cookiecream_donut'] = {['name'] = 'cookiecream_donut', ['label'] = 'Cookies and Cream Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cookies_and_cream_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cruller_donut'] = {['name'] = 'cruller_donut', ['label'] = 'Cruller Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cruller_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['lemon_iced_donut'] = {['name'] = 'lemon_iced_donut', ['label'] = 'Lemon Iced Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'lemon_iced_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['mapple_bar_donut'] = {['name'] = 'mapple_bar_donut', ['label'] = 'Mapple Bar Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'mapple_bar_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['strawberry_iced_donut'] = {['name'] = 'strawberry_iced_donut', ['label'] = 'Strawberry Iced Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'strawberry_iced_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['iced_caramel_latte'] = {['name'] = 'iced_caramel_latte', ['label'] = 'Iced Caramel Latte', ['weight'] = 10, ['type'] = 'item', ['image'] = 'iced_caramel_latte.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['mocha_frappe'] = {['name'] = 'mocha_frappe', ['label'] = 'Mocha Frappe', ['weight'] = 10, ['type'] = 'item', ['image'] = 'mocha_frappe.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cold_brew_coffee'] = {['name'] = 'cold_brew_coffee', ['label'] = 'Rusty Cold Brew Coffee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cold_brew_coffee.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['iced_matcha_latte'] = {['name'] = 'iced_matcha_latte', ['label'] = 'Rusty Iced Matcha Latte', ['weight'] = 10, ['type'] = 'item', ['image'] = 'iced_matcha_latte.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['vanilla_iced_coffee'] = {['name'] = 'vanilla_iced_coffee', ['label'] = 'Rusty Vanilla Iced Coffee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'vanilla_iced_coffee.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['strawberry_lemonade_slush'] = {['name'] = 'strawberry_lemonade_slush', ['label'] = 'Rustys Strawberry Lemonade Slush', ['weight'] = 10, ['type'] = 'item', ['image'] = 'strawberry_lemonade_slush.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['iced_chai_tea_latte'] = {['name'] = 'iced_chai_tea_latte', ['label'] = 'Rusty Iced Tea Latte', ['weight'] = 10, ['type'] = 'item', ['image'] = 'iced_chai_tea_latte.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['iced_mocha'] = {['name'] = 'iced_mocha', ['label'] = 'Rusty Iced Mocha', ['weight'] = 10, ['type'] = 'item', ['image'] = 'iced_mocha.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['iced_coconut_coffee'] = {['name'] = 'iced_coconut_coffee', ['label'] = 'Rusty Iced Coconut Coffee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'iced_coconut_coffee.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['mint_chocolate_chip_milkshake'] = {['name'] = 'mint_chocolate_chip_milkshake', ['label'] = 'Rusty Mint Chocolate Milkshake', ['weight'] = 10, ['type'] = 'item', ['image'] = 'mint_chocolate_chip_milkshake.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['croissant'] = {['name'] = 'croissant', ['label'] = 'Croissant', ['weight'] = 10, ['type'] = 'item', ['image'] = 'croissant.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['apple_turnover'] = {['name'] = 'apple_turnover', ['label'] = 'Apple Turnover', ['weight'] = 10, ['type'] = 'item', ['image'] = 'apple_turnover.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cinnamon_roll'] = {['name'] = 'cinnamon_roll', ['label'] = 'Cinnamon Roll', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cinnamon_roll.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['eclairs'] = {['name'] = 'eclairs', ['label'] = 'eclairs', ['weight'] = 10, ['type'] = 'item', ['image'] = 'eclairs.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['danish_pastry'] = {['name'] = 'danish_pastry', ['label'] = 'Danish Pastry', ['weight'] = 10, ['type'] = 'item', ['image'] = 'danish_pastry.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['puff_pastry_tarts'] = {['name'] = 'puff_pastry_tarts', ['label'] = 'Puff Pastry Tart', ['weight'] = 10, ['type'] = 'item', ['image'] = 'puff_pastry_tarts.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['chocolate_pastry'] = {['name'] = 'chocolate_pastry', ['label'] = 'Chocolate Pastry', ['weight'] = 10, ['type'] = 'item', ['image'] = 'chocolate_pastry.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cream_puff'] = {['name'] = 'cream_puff', ['label'] = 'Cream Puff', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cream_puff.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['sticky_bun'] = {['name'] = 'sticky_bun', ['label'] = 'Sticky Bun', ['weight'] = 10, ['type'] = 'item', ['image'] = 'sticky_bun.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['fruit_strudel'] = {['name'] = 'fruit_strudel', ['label'] = 'Fruit Strudel', ['weight'] = 10, ['type'] = 'item', ['image'] = 'fruit_strudel.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['box_donut_a'] = {['name'] = 'box_donut_a', ['label'] = 'Sprinkled Donut Box', ['weight'] = 10, ['type'] = 'item', ['image'] = 'box_donut_a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['box_donut_b'] = {['name'] = 'box_donut_b', ['label'] = 'ChocoCream Donut Box', ['weight'] = 10, ['type'] = 'item', ['image'] = 'box_donut_b.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['box_donut_c'] = {['name'] = 'box_donut_c', ['label'] = 'Cinnamon Sugar Donut Box', ['weight'] = 10, ['type'] = 'item', ['image'] = 'box_donut_c.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['box_donut_d'] = {['name'] = 'box_donut_d', ['label'] = 'Lemon Iced Donut Box', ['weight'] = 10, ['type'] = 'item', ['image'] = 'box_donut_d.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['box_donut_e'] = {['name'] = 'box_donut_e', ['label'] = 'Strawberry Iced Donut Box', ['weight'] = 10, ['type'] = 'item', ['image'] = 'box_donut_e.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_flour'] = {['name'] = 'rs_flour', ['label'] = 'Rustys Donut Base', ['weight'] = 10, ['type'] = 'item', ['image'] = 'donut_base.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_berries'] = {['name'] = 'rs_berries', ['label'] = 'Rustys Berries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_berries.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_chocolate_cream'] = {['name'] = 'rs_chocolate_cream', ['label'] = 'Rustys Chocolate cream filling', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_chocolate_cream.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_chocolate_glaze'] = {['name'] = 'rs_chocolate_glaze', ['label'] = 'Rustys Chocolate glaze', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_chocolate_glaze.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_sprinkling_chocolate'] = {['name'] = 'rs_sprinkling_chocolate', ['label'] = 'Rustys Sprinkling Chocolate', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_sprinkling_chocolate.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_cinnamon_sugar'] = {['name'] = 'rs_cinnamon_sugar', ['label'] = 'Rustys Cinnamon and Sugar Coating', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cinnamon_sugar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_choco_cookies'] = {['name'] = 'rs_choco_cookies', ['label'] = 'Rustys Chocolate Cookies', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cookies_and_cream.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_sugar_glaze'] = {['name'] = 'rs_sugar_glaze', ['label'] = 'Rustys Sugar Glaze', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_sugar_glaze.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_lemon'] = {['name'] = 'rs_lemon', ['label'] = 'Rustys Lemon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'lemon_icing.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_maple_glaze'] = {['name'] = 'rs_maple_glaze', ['label'] = 'Rustys Maple Glaze', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_maple_glaze.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_strawberry'] = {['name'] = 'rs_strawberry', ['label'] = 'Rustys Strawberry', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_strawberry.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_ice'] = {['name'] = 'rs_ice', ['label'] = 'Rustys Ice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_ice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_caramel_syrup'] = {['name'] = 'rs_caramel_syrup', ['label'] = 'Rustys Caramel Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_caramel_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_chocolate_syrup'] = {['name'] = 'rs_chocolate_syrup', ['label'] = 'Rustys Chocolate Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_chocolate_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_coffee_beans'] = {['name'] = 'rs_coffee_beans', ['label'] = 'Rustys Coffee Beans', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_coffee_beans.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_matcha_powder'] = {['name'] = 'rs_matcha_powder', ['label'] = 'Rustys Matcha Powder', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_matcha_powder.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_chai_tea'] = {['name'] = 'rs_chai_tea', ['label'] = 'Rustys Tea Concentrate', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_chai_tea.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_espresso'] = {['name'] = 'rs_espresso', ['label'] = 'Rustys Espresso', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_espresso.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_coconut_milk'] = {['name'] = 'rs_coconut_milk', ['label'] = 'Rustys Coconut Milk', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_coconut_milk.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_mint_icecream'] = {['name'] = 'rs_mint_icecream', ['label'] = 'Rustys Mint IceCream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_mint_icecream.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_butter'] = {['name'] = 'rs_butter', ['label'] = ' Rustys Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_apple_filling'] = {['name'] = 'rs_apple_filling', ['label'] = 'Rustys Apple filling', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_apple_filling.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_pastry_cream'] = {['name'] = 'rs_pastry_cream', ['label'] = 'Rustys Pastry cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_pastry_cream.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_cream_cheese'] = {['name'] = 'rs_cream_cheese', ['label'] = 'Rustys Cream cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_cream_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_chocolate_sticks'] = {['name'] = 'rs_chocolate_sticks', ['label'] = 'Rustys Chocolate sticks', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_chocolate_sticks.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_whipped_cream'] = {['name'] = 'rs_whipped_cream', ['label'] = 'Rustys Whipped cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_whipped_cream.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_brownbutter_cinnamon'] = {['name'] = 'rs_brownbutter_cinnamon', ['label'] = 'Rustys Brown Sugar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_brownbutter_cinnamon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_vanilla_syrup'] = {['name'] = 'rs_vanilla_syrup', ['label'] = 'Rustys Vanilla Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_vanilla_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_icecubes'] = {['name'] = 'rs_icecubes', ['label'] = 'Rustys Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_emptycup'] = {['name'] = 'rs_emptycup', ['label'] = 'Rustys Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['rs_waterbottle'] = {['name'] = 'rs_waterbottle', ['label'] = 'Rustys Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'rs_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
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
  ('berry_glazed_donut', 'Berry Glazed Donut', 1),
  ('chococream_donut', 'Cream Filled Donut', 1),
  ('chocfrosted_donut', 'Chocolate Frosted Donut', 1),
  ('sprinkled_donut', 'Chocolate Sprinkled Donut', 1),
  ('cinnamon_sugar_donut', 'Cinnamon Sugar Donut', 1),
  ('cookiecream_donut', 'Cookies and Cream Donut', 1),
  ('cruller_donut', 'Cruller Donut', 1),
  ('lemon_iced_donut', 'Lemon Iced Donut', 1),
  ('mapple_bar_donut', 'Mapple Bar Donut', 1),
  ('strawberry_iced_donut', 'Strawberry Iced Donut', 1),
  ('iced_caramel_latte', 'Iced Caramel Latte', 1),
  ('mocha_frappe', 'Mocha Frappe', 1),
  ('cold_brew_coffee', 'Rusty Cold Brew Coffee', 1),
  ('iced_matcha_latte', 'Rusty Iced Matcha Latte', 1),
  ('vanilla_iced_coffee', 'Rusty Vanilla Iced Coffee', 1),
  ('strawberry_lemonade_slush', 'Rustys Strawberry Lemonade Slush', 1),
  ('iced_chai_tea_latte', 'Rusty Iced Tea Latte', 1),
  ('iced_mocha', 'Rusty Iced Mocha', 1),
  ('iced_coconut_coffee', 'Rusty Iced Coconut Coffee', 1),
  ('mint_chocolate_chip_milkshake', 'Rusty Mint Chocolate Milkshake', 1),
  ('croissant', 'Croissant', 1),
  ('apple_turnover', 'Apple Turnover', 1),
  ('cinnamon_roll', 'Cinnamon Roll', 1),
  ('eclairs', 'Eclairs', 1),
  ('danish_pastry', 'Danish Pastry', 1),
  ('puff_pastry_tarts', 'Puff Pastry Tart', 1),
  ('chocolate_pastry', 'Chocolate Pastry', 1),
  ('cream_puff', 'Cream Puff', 1),
  ('sticky_bun', 'Sticky Bun', 1),
  ('fruit_strudel', 'Fruit Strudel', 1),
  ('box_donut_a', 'Sprinkled Donut Box', 1),
  ('box_donut_b', 'ChocoCream Donut Box', 1),
  ('box_donut_c', 'Cinnamon Sugar Donut Box', 1),
  ('box_donut_d', 'Lemon Iced Donut Box', 1),
  ('box_donut_e', 'Strawberry Iced Donut Box', 1),
  ('rs_flour', 'Rustys Donut Base', 1),
  ('rs_berries', 'Rustys Berries', 1),
  ('rs_chocolate_cream', 'Rustys Chocolate cream filling', 1),
  ('rs_chocolate_glaze', 'Rustys Chocolate glaze', 1),
  ('rs_sprinkling_chocolate', 'Rustys Sprinkling Chocolate', 1),
  ('rs_cinnamon_sugar', 'Rustys Cinnamon and Sugar Coating', 1),
  ('rs_choco_cookies', 'Rustys Chocolate Cookies', 1),
  ('rs_sugar_glaze', 'Rustys Sugar Glaze', 1),
  ('rs_lemon', 'Rustys Lemon', 1),
  ('rs_maple_glaze', 'Rustys Maple Glaze', 1),
  ('rs_strawberry', 'Rustys Strawberry', 1),
  ('rs_ice', 'Rustys Ice', 1),
  ('rs_caramel_syrup', 'Rustys Chocolate Syrup', 1),
  ('rs_chocolate_syrup', 'Black Beans', 1),
  ('rs_coffee_beans', 'Rustys Coffee Beans', 1),
  ('rs_matcha_powder', 'Rustys Matcha Powder', 1),
  ('rs_chai_tea', 'Rustys Tea Concentrate', 1),
  ('rs_espresso', 'Rustys Espresso', 1),
  ('rs_coconut_milk', 'Rustys Coconut Milk', 1),
  ('rs_mint_icecream', 'Rustys Mint IceCream', 1),
  ('rs_butter', 'Rustys Butter', 1),
  ('rs_apple_filling', 'Rustys Apple filling', 1),
  ('rs_pastry_cream', 'Rustys Pastry cream', 1),
  ('rs_cream_cheese', 'Rustys Cream cheese', 1),
  ('rs_chocolate_sticks', 'Rustys Chocolate sticks', 1),
  ('rs_whipped_cream', 'Rustys Whipped cream', 1),
  ('rs_brownbutter_cinnamon', 'Rustys Brown Sugar', 1),
  ('rs_emptycup', 'Rustys Empty Cup', 1),
  ('rs_waterbottle', 'Rustys Water Bottle', 1),
  ('rs_icecubes', 'Rustys Ice Cubes', 1),
  ('rs_vanilla_syrup', 'Rustys Vanilla Syrup', 1);
```

</details>

### For QBCore Only

{% tabs %}
{% tab title="jobs.lua" %}
Add the Following in qb-core/shared/jobs.lua

```lua
['rustybrowns'] = {
    label = 'Rusty Browns',
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
['rustybrowns'] = {
    label = 'Rusty Browns',
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
    ['iced_caramel_latte'] = math.random(35, 54),
    ['mocha_frappe'] = math.random(35, 54),
    ['cold_brew_coffee'] = math.random(35, 54),
    ['iced_matcha_latte'] = math.random(35, 54),
    ['vanilla_iced_coffee'] = math.random(35, 54),
    ['strawberry_lemonade_slush'] = math.random(35, 54),
    ['iced_chai_tea_latte'] = math.random(35, 54),
    ['iced_mocha'] = math.random(35, 54),
    ['iced_coconut_coffee'] = math.random(35, 54),
    ['mint_chocolate_chip_milkshake'] = math.random(35, 54),
    
}

Config.ConsumablesEat = {
    ['berry_glazed_donut'] = math.random(35, 54),
    ['chococream_donut'] = math.random(35, 54),
    ['chocfrosted_donut'] = math.random(35, 54),
    ['sprinkled_donut'] = math.random(35, 54),
    ['cinnamon_sugar_donut'] = math.random(35, 54),
    ['cookiecream_donut'] = math.random(35, 54),
    ['cruller_donut'] = math.random(35, 54),
    ['lemon_iced_donut'] = math.random(35, 54),
    ['mapple_bar_donut'] = math.random(35, 54),
    ['strawberry_iced_donut'] = math.random(35, 54),

    ['croissant'] = math.random(35, 54),
    ['apple_turnover'] = math.random(35, 54),
    ['cinnamon_roll'] = math.random(35, 54),
    ['eclairs'] = math.random(35, 54),
    ['bg_danish_pastry'] = math.random(35, 54),
    ['puff_pastry_tarts'] = math.random(35, 54),
    ['chocolate_pastry'] = math.random(35, 54),
    ['cream_puff'] = math.random(35, 54),
    ['sticky_bun'] = math.random(35, 54),
    ['fruit_strudel'] = math.random(35, 54),

    ['box_donut_a'] = math.random(90, 95),
    ['box_donut_b'] = math.random(90, 95),
    ['box_donut_c'] = math.random(90, 95),
    ['box_donut_d'] = math.random(90, 95),
    ['box_donut_e'] = math.random(90, 95),

}

--If using new qb-smallresources
Config.Consumables = {
    eat = {
        ['berry_glazed_donut'] = math.random(35, 54),
        ['chococream_donut'] = math.random(35, 54),
        ['chocfrosted_donut'] = math.random(35, 54),
        ['sprinkled_donut'] = math.random(35, 54),
        ['cinnamon_sugar_donut'] = math.random(35, 54),
        ['cookiecream_donut'] = math.random(35, 54),
        ['cruller_donut'] = math.random(35, 54),
        ['lemon_iced_donut'] = math.random(35, 54),
        ['mapple_bar_donut'] = math.random(35, 54),
        ['strawberry_iced_donut'] = math.random(35, 54),

        ['croissant'] = math.random(35, 54),
        ['apple_turnover'] = math.random(35, 54),
        ['cinnamon_roll'] = math.random(35, 54),
        ['eclairs'] = math.random(35, 54),
        ['bg_danish_pastry'] = math.random(35, 54),
        ['puff_pastry_tarts'] = math.random(35, 54),
        ['chocolate_pastry'] = math.random(35, 54),
        ['cream_puff'] = math.random(35, 54),
        ['sticky_bun'] = math.random(35, 54),
        ['fruit_strudel'] = math.random(35, 54),

        ['box_donut_a'] = math.random(90, 95),
        ['box_donut_b'] = math.random(90, 95),
        ['box_donut_c'] = math.random(90, 95),
        ['box_donut_d'] = math.random(90, 95),
        ['box_donut_e'] = math.random(90, 95),
    },
    drink = {
        ['iced_caramel_latte'] = math.random(35, 54),
        ['mocha_frappe'] = math.random(35, 54),
        ['cold_brew_coffee'] = math.random(35, 54),
        ['iced_matcha_latte'] = math.random(35, 54),
        ['vanilla_iced_coffee'] = math.random(35, 54),
        ['strawberry_lemonade_slush'] = math.random(35, 54),
        ['iced_chai_tea_latte'] = math.random(35, 54),
        ['iced_mocha'] = math.random(35, 54),
        ['iced_coconut_coffee'] = math.random(35, 54),
        ['mint_chocolate_chip_milkshake'] = math.random(35, 54),
    },
}
```

</details>

<details>

<summary>Jim Consumables</summary>

Add the following in jim-consumables/shared/consumables.lua

```lua
berry_glazed_donut = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
chococream_donut = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
chocfrosted_donut = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
sprinkled_donut = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
cinnamon_sugar_donut = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
cookiecream_donut = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
cruller_donut = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
lemon_iced_donut = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
mapple_bar_donut = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
strawberry_iced_donut = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
croissant = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
apple_turnover = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
cinnamon_roll = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
eclairs = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bg_danish_pastry = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
puff_pastry_tarts = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
chocolate_pastry = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
cream_puff = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
sticky_bun = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
fruit_strudel = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },

box_donut_a = { emote = "donut", canRun = false, time = math.random(9000, 9500), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
box_donut_b = { emote = "donut", canRun = false, time = math.random(9000, 9500), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
box_donut_c = { emote = "donut", canRun = false, time = math.random(9000, 9500), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
box_donut_d = { emote = "donut", canRun = false, time = math.random(9000, 9500), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
box_donut_e = { emote = "donut", canRun = false, time = math.random(9000, 9500), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },

cc_espresso = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
mocha_frappe = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
cold_brew_coffee = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
iced_matcha_latte = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
vanilla_iced_coffee = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
strawberry_lemonade_slush = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
iced_chai_tea_latte = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
iced_mocha = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
iced_coconut_coffee = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
mint_chocolate_chip_milkshake = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},


--Add this in jim-consumables->shared->emotes.lua
donut = {"mp_player_inteat@burger", "mp_player_int_eat_burger", "Donut", AnimationOptions ={ Prop = "prop_amb_donut", PropBone = 18905, PropPlacement = {0.13, 0.05, 0.02, -50.0, 16.0, 60.0},EmoteMoving = true, EmoteLoop = true, }},
```

</details>

### Add Images to Inventory

Copy all the Images folder and paste it in your inventory Images folder

### Log Webook Setup - Optional

To enable discord logs make sure to add your webhook in the server->Log.lua File

{% embed url="https://www.youtube.com/watch?pp=ygULI2FwcHlxczIwMjM=&v=fKksxz2Gdnc" %}

### Optional Dj Custom Props

If you have purchased the DJ Donut Props [https://djscollections.com/package/5681293](https://djscollections.com/package/5681293)  just install it and set the Config.UseDjItems = true&#x20;

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
