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
CREATE TABLE IF NOT EXISTS `pl_bubblegumcafe` (
  `stock` longtext DEFAULT NULL,
  `state` varchar(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;

INSERT INTO `addon_account` (name, label, shared) VALUES
        ('society_bubblegum', 'BubbleGum Cafe', 1);

INSERT INTO `datastore` (name, label, shared) VALUES
        ('society_bubblegum', 'BubbleGum Cafe', 1);

INSERT INTO `jobs` (name, label,whitelisted) VALUES
        ('bubblegum', 'BubbleGum Cafe',1);

INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
        ('bubblegum',0,'cashier','Cashier',20,'{}','{}'),
        ('bubblegum',1,'cook','Cook',40,'{}','{}'),
        ('bubblegum',2,'staff','Staff',60,'{}','{}'),
        ('bubblegum',3,'manager','Manager',85,'{}','{}'),
        ('bubblegum',4,'boss','Owner',100,'{}','{}');
```

</details>

<details>

<summary>QBCore or Qbox</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_bubblegumcafe` (
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
["pearl_grill_salmon"] = {
    label = "Coffee Beans Butter",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["pearl_hibiscus_tea"] = {
    label = "Hibiscus Tea",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["bg_apple_filling"] = {
    label = "Apple filling",
    weight = 1,
    stack = true,
    close = true,
},

["bg_apple_turnover"] = {
    label = "Apple Turnover",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_basil"] = {
    label = "Fresh Basil",
    weight = 1,
    stack = true,
    close = true,
},

["bg_basil_leaves"] = {
    label = "Basil Leaves",
    weight = 1,
    stack = true,
    close = true,
},

["bg_bbq_chicken"] = {
    label = "BBQ Chicken Pizza",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_bbq_sauce"] = {
    label = "Smoky BBQ Sauce",
    weight = 1,
    stack = true,
    close = true,
},

["bg_black_olives"] = {
    label = "Black Olives",
    weight = 1,
    stack = true,
    close = true,
},

["bg_buffalo_sauce"] = {
    label = "Buffalo Sauce",
    weight = 1,
    stack = true,
    close = true,
},

["bg_butter"] = {
    label = "Butter",
    weight = 1,
    stack = true,
    close = true,
},

["bg_Caesar"] = {
    label = "Classic Caesar Salad",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_caprese"] = {
    label = "Caprese Salad",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_caramel_syrup"] = {
    label = "Caramel Syrup",
    weight = 1,
    stack = true,
    close = true,
},

["bg_chicken_caesar"] = {
    label = "Chicken Caesar Salad",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_chocolate_cream"] = {
    label = "Chocolate cream filling",
    weight = 1,
    stack = true,
    close = true,
},

["bg_chocolate_syrup"] = {
    label = "Chocolate Syrup",
    weight = 1,
    stack = true,
    close = true,
},

["bg_cinnamon_roll"] = {
    label = "Cinnamon Roll",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_cinnamon_sugar"] = {
    label = "Cinnamon and Sugar Coating",
    weight = 1,
    stack = true,
    close = true,
},

["bg_coffee_beans"] = {
    label = "Coffee Beans",
    weight = 1,
    stack = true,
    close = true,
},

["bg_cold_brew_coffee"] = {
    label = "Cold Brew Coffee",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_cream_cheese"] = {
    label = "Cream Cheese",
    weight = 1,
    stack = true,
    close = true,
},

["bg_crispy_bread"] = {
    label = "Crispy Bread",
    weight = 1,
    stack = true,
    close = true,
},

["bg_croissant"] = {
    label = "Croissant",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_danish_pastry"] = {
    label = "Danish Pastry",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_dough"] = {
    label = "Dough",
    weight = 1,
    stack = true,
    close = true,
},

["bg_eclairs"] = {
    label = "Eclairs",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_fresh_garden"] = {
    label = "Garden Fresh Salad",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_garlic_butter"] = {
    label = "Garlic Butter",
    weight = 1,
    stack = true,
    close = true,
},

["bg_greek_feta"] = {
    label = "Greek Feta Salad",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_hawaiian"] = {
    label = "Hawaiian Paradise Pizza",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_ice"] = {
    label = "Ice",
    weight = 1,
    stack = true,
    close = true,
},

["bg_iced_caramel_latte"] = {
    label = "Iced Caramel Latte",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_iced_matcha_latte"] = {
    label = "Iced Matcha Latte",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_margherita"] = {
    label = "Classic Margherita Pizza",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_marinara_sauce"] = {
    label = "Marinara Sauce",
    weight = 1,
    stack = true,
    close = true,
},

["bg_matcha_powder"] = {
    label = "Matcha Powder",
    weight = 1,
    stack = true,
    close = true,
},

["bg_mocha_frappe"] = {
    label = "Mocha Frappe",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_mozzarella"] = {
    label = "Melted Mozzarella",
    weight = 1,
    stack = true,
    close = true,
},

["bg_olive_oil"] = {
    label = "Olive Oil",
    weight = 1,
    stack = true,
    close = true,
},

["bg_pastry_cream"] = {
    label = "Pastry Cream",
    weight = 1,
    stack = true,
    close = true,
},

["bg_pepperoni"] = {
    label = "Pepperoni Feast Pizza",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_pineapple_chunks"] = {
    label = "Pineapple Chunks",
    weight = 1,
    stack = true,
    close = true,
},

["bg_Supreme"] = {
    label = "Veggie Supreme Pizza",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_vanilla_iced_coffee"] = {
    label = "Vanilla Iced Coffee",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["bg_vanilla_syrup"] = {
    label = "Vanilla Syrup",
    weight = 1,
    stack = true,
    close = true,
},

["bg_vinegar"] = {
	label = "Vinegar",
	weight = 1,
	stack = true,
	close = true,
},

["bg_parmesan"] = {
	label = "Parmesan Shavings",
	weight = 1,
	stack = true,
	close = true,
},
["bg_kalamata_olives"] = {
	label = "Kalamata Olives",
	weight = 1,
	stack = true,
	close = true,
},
["bg_balsamic_glaze"] = {
	label = "Balsamic Glaze",
	weight = 1,
	stack = true,
	close = true,
},
["bg_garlic_croutons"] = {
	label = "Garlic Croutons",
	weight = 1,
	stack = true,
	close = true,
},
["bg_avocado_slice"] = {
	label = "Avocado Slices",
	weight = 1,
	stack = true,
	close = true,
},
["bg_emptycup"] = {
	label = "Empty Cup",
	weight = 1,
	stack = true,
	close = true,
},
["bg_icecubes"] = {
	label = "Ice Cubes",
	weight = 1,
	stack = true,
	close = true,
},
["bg_waterbottle"] = {
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
--Add in qb-core/shared/items.lua
['bg_margherita'] = {['name'] = 'bg_margherita', ['label'] = 'Classic Margherita Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_margherita.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_pepperoni'] = {['name'] = 'bg_pepperoni', ['label'] = 'Pepperoni Feast Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_pepperoni.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_bbq_chicken'] = {['name'] = 'bg_bbq_chicken', ['label'] = 'BBQ Chicken Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_bbq_chicken.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_Supreme'] = {['name'] = 'bg_Supreme', ['label'] = 'Veggie Supreme Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_Supreme.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_hawaiian'] = {['name'] = 'bg_hawaiian', ['label'] = 'Hawaiian Paradise Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_hawaiian.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_Caesar'] = {['name'] = 'bg_Caesar', ['label'] = 'Classic Caesar Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_Caesar.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_greek_feta'] = {['name'] = 'bg_greek_feta', ['label'] = 'Greek Feta Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_greek_feta.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_caprese'] = {['name'] = 'bg_caprese', ['label'] = 'Caprese Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_caprese.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_chicken_caesar'] = {['name'] = 'bg_chicken_caesar', ['label'] = 'Chicken Caesar Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_chicken_caesar.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_fresh_garden'] = {['name'] = 'bg_fresh_garden', ['label'] = 'Garden Fresh Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_fresh_garden.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_croissant'] = {['name'] = 'bg_croissant', ['label'] = 'Croissant', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_croissant.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_apple_turnover'] = {['name'] = 'bg_apple_turnover', ['label'] = 'Apple Turnover', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_apple_turnover.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_cinnamon_roll'] = {['name'] = 'bg_cinnamon_roll', ['label'] = 'Cinnamon Roll', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_cinnamon_roll.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_eclairs'] = {['name'] = 'bg_eclairs', ['label'] = 'Eclairs', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_eclairs.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_danish_pastry'] = {['name'] = 'bg_danish_pastry', ['label'] = 'Danish Pastry', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_danish_pastry.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_iced_caramel_latte'] = {['name'] = 'bg_iced_caramel_latte', ['label'] = 'Iced Caramel Latte', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_iced_caramel_latte.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_mocha_frappe'] = {['name'] = 'bg_mocha_frappe', ['label'] = 'Mocha Frappe', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_mocha_frappe.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_cold_brew_coffee'] = {['name'] = 'bg_cold_brew_coffee', ['label'] = 'Cold Brew Coffee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_cold_brew_coffee.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_iced_matcha_latte'] = {['name'] = 'bg_iced_matcha_latte', ['label'] = 'Iced Matcha Latte', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_iced_matcha_latte.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_vanilla_iced_coffee'] = {['name'] = 'bg_vanilla_iced_coffee', ['label'] = 'Vanilla Iced Coffee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_vanilla_iced_coffee.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_dough'] = {['name'] = 'bg_dough', ['label'] = 'Dough', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_dough.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_basil_leaves'] = {['name'] = 'bg_basil_leaves', ['label'] = 'Basil Leaves', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_basil_leaves.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_marinara_sauce'] = {['name'] = 'bg_marinara_sauce', ['label'] = 'Marinara Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_marinara_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_bbq_sauce'] = {['name'] = 'bg_bbq_sauce', ['label'] = 'Smoky BBQ Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_bbq_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_black_olives'] = {['name'] = 'bg_black_olives', ['label'] = 'Black Olives', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_black_olives.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_pineapple_chunks'] = {['name'] = 'bg_pineapple_chunks', ['label'] = 'Pineapple Chunks', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_pineapple_chunks.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_olive_oil'] = {['name'] = 'bg_olive_oil', ['label'] = 'Olive Oil', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_olive_oil.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_garlic_butter'] = {['name'] = 'bg_garlic_butter', ['label'] = 'Garlic Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_garlic_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_crispy_bread'] = {['name'] = 'bg_crispy_bread', ['label'] = 'Crispy Bread', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_crispy_bread.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_mozzarella'] = {['name'] = 'bg_mozzarella', ['label'] = 'Melted Mozzarella', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_mozzarella.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_buffalo_sauce'] = {['name'] = 'bg_buffalo_sauce', ['label'] = 'Buffalo Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_buffalo_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_basil'] = {['name'] = 'bg_basil', ['label'] = 'Fresh Basil', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_basil.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_butter'] = {['name'] = 'bg_butter', ['label'] = 'Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_chocolate_cream'] = {['name'] = 'bg_chocolate_cream', ['label'] = 'Chocolate cream filling', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_chocolate_cream.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_apple_filling'] = {['name'] = 'bg_apple_filling', ['label'] = 'Apple filling', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_apple_filling.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_cinnamon_sugar'] = {['name'] = 'bg_cinnamon_sugar', ['label'] = 'Cinnamon and Sugar Coating', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_cinnamon_sugar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_pastry_cream'] = {['name'] = 'bg_pastry_cream', ['label'] = 'Pastry Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_pastry_cream.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_cream_cheese'] = {['name'] = 'bg_cream_cheese', ['label'] = 'Cream Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_cream_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_ice'] = {['name'] = 'bg_ice', ['label'] = 'Ice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_ice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_caramel_syrup'] = {['name'] = 'bg_caramel_syrup', ['label'] = 'Caramel Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_caramel_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_chocolate_syrup'] = {['name'] = 'bg_chocolate_syrup', ['label'] = 'Chocolate Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_chocolate_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_coffee_beans'] = {['name'] = 'bg_coffee_beans', ['label'] = 'Coffee Beans', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_coffee_beans.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_matcha_powder'] = {['name'] = 'bg_matcha_powder', ['label'] = 'Matcha Powder', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_matcha_powder.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_vanilla_syrup'] = {['name'] = 'bg_vanilla_syrup', ['label'] = 'Vanilla Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_vanilla_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_vinegar'] = {['name'] = 'bg_vinegar', ['label'] = 'Vinegar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_vinegar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_parmesan'] = {['name'] = 'bg_parmesan', ['label'] = 'Parmesan Shavings', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_parmesan.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_kalamata_olives'] = {['name'] = 'bg_kalamata_olives', ['label'] = 'Kalamata Olives', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_kalamata_olives.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_balsamic_glaze'] = {['name'] = 'bg_balsamic_glaze', ['label'] = ' Balsamic Glaze', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_balsamic_glaze.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_garlic_croutons'] = {['name'] = 'bg_garlic_croutons', ['label'] = 'Garlic Croutons', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_garlic_croutons.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_avocado_slice'] = {['name'] = 'bg_avocado_slice', ['label'] = 'Avocado Slices', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_avocado_slice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_icecubes'] = {['name'] = 'bg_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_waterbottle'] = {['name'] = 'bg_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bg_emptycup'] = {['name'] = 'bg_emptycup', ['label'] = 'Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bg_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>ESX ITems Sql</summary>

```lua
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
	('bg_margherita', 'Classic Margherita Pizza', 1),
  ('bg_pepperoni', 'Pepperoni Feast Pizza', 1),    
  ('bg_bbq_chicken', 'BBQ Chicken Pizza', 1),      
  ('bg_Supreme', 'Veggie Supreme Pizza', 1),       
  ('bg_hawaiian', 'Hawaiian Paradise Pizza', 1),   
  ('bg_Caesar', 'Classic Caesar Salad', 1),        
  ('bg_greek_feta', 'Greek Feta Salad', 1),        
  ('bg_caprese', 'Caprese Salad', 1),
  ('bg_chicken_caesar', 'Chicken Caesar Salad', 1),
  ('bg_fresh_garden', 'Garden Fresh Salad', 1),
  ('bg_croissant', 'Croissant', 1),
  ('bg_apple_turnover', 'Apple Turnover', 1),
  ('bg_cinnamon_roll', 'Cinnamon Roll', 1),
  ('bg_eclairs', 'Eclairs', 1),
  ('bg_danish_pastry', 'Danish Pastry', 1),
  ('bg_iced_caramel_latte', 'Iced Caramel Latte', 1),
  ('bg_mocha_frappe', 'Mocha Frappe', 1),
  ('bg_cold_brew_coffee', 'Cold Brew Coffee', 1),
  ('bg_iced_matcha_latte', 'Iced Matcha Latte', 1),
  ('bg_vanilla_iced_coffee', 'Vanilla Iced Coffee', 1),
  ('bg_dough', 'Dough', 1),
  ('bg_basil_leaves', 'Basil Leaves', 1),
  ('bg_marinara_sauce', 'Marinara Sauce', 1),
  ('bg_bbq_sauce', 'Smoky BBQ Sauce', 1),
  ('bg_black_olives', 'Black Olives', 1),
  ('bg_pineapple_chunks', 'Pineapple Chunks', 1),
  ('bg_olive_oil', 'Olive Oil', 1),
  ('bg_garlic_butter', 'Garlic Butter', 1),
  ('bg_crispy_bread', 'Crispy Bread', 1),
  ('bg_mozzarella', 'Melted Mozzarella', 1),
  ('bg_buffalo_sauce', 'Buffalo Sauce', 1),
  ('bg_basil', 'Fresh Basil', 1),
  ('bg_butter', 'Butter', 1),
  ('bg_chocolate_cream', 'Chocolate cream filling', 1),
  ('bg_apple_filling', 'Apple filling', 1),
  ('bg_cinnamon_sugar', 'Cinnamon and Sugar Coating', 1),
  ('bg_pastry_cream', 'Pastry Cream', 1),
  ('bg_cream_cheese', 'Cream Cheese', 1),
  ('bg_ice', 'Ice', 1),
  ('bg_caramel_syrup', 'Caramel Syrup', 1),
  ('bg_chocolate_syrup', 'Chocolate Syrup', 1),
  ('bg_coffee_beans', 'Coffee Beans', 1),
  ('bg_matcha_powder', 'Matcha Powder', 1),
  ('bg_vanilla_syrup', 'Vanilla Syrup', 1),
  ('bg_parmesan', 'Parmesan Shavings', 1),
  ('bg_kalamata_olives', 'Kalamata Olives', 1),
  ('bg_balsamic_glaze', 'Balsamic Glaze', 1),
  ('bg_garlic_croutons', 'Garlic Croutons', 1),
  ('bg_avocado_slice', 'Avocado Slices', 1),
  ('bg_vinegar', 'Vinegar', 1),
  ('bg_icecubes', 'Ice Cubes', 1),
  ('bg_waterbottle', 'Water Bottle', 1),
  ('bg_emptycup', 'Empty Cup', 1);
```

</details>

### For QBCore Only

{% tabs %}
{% tab title="jobs.lua" %}
Add the Following in qb-core/shared/jobs.lua

```lua
['bubblegum'] = {
    label = 'BubbleGum Cafe',
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
['bubblegum'] = {
    label = 'BubbleGum Cafe',
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
    ['bg_iced_caramel_latte'] = math.random(35, 54),
    ['bg_mocha_frappe'] = math.random(35, 54),
    ['bg_cold_brew_coffee'] = math.random(35, 54),
    ['bg_iced_matcha_latte'] = math.random(35, 54),
    ['bg_vanilla_iced_coffee'] = math.random(35, 54),
}

Config.ConsumablesEat = {
    ['bg_margherita'] = math.random(35, 54),
    ['bg_pepperoni'] = math.random(35, 54),
    ['bg_bbq_chicken'] = math.random(35, 54),
    ['bg_Supreme'] = math.random(35, 54),
    ['bg_hawaiian'] = math.random(35, 54),

    ['bg_Caesar'] = math.random(35, 54),
    ['bg_greek_feta'] = math.random(35, 54),
    ['bg_caprese'] = math.random(35, 54),
    ['bg_chicken_caesar'] = math.random(35, 54),
    ['bg_fresh_garden'] = math.random(35, 54),

    ['bg_croissant'] = math.random(35, 54),
    ['bg_apple_turnover'] = math.random(35, 54),
    ['bg_cinnamon_roll'] = math.random(35, 54),
    ['bg_eclairs'] = math.random(35, 54),
    ['bg_danish_pastry'] = math.random(35, 54),
}

--If using new qb-smallresources
Config.Consumables = {
    eat = {
        ['bg_margherita'] = math.random(35, 54),
        ['bg_pepperoni'] = math.random(35, 54),
        ['bg_bbq_chicken'] = math.random(35, 54),
        ['bg_Supreme'] = math.random(35, 54),
        ['bg_hawaiian'] = math.random(35, 54),

        ['bg_Caesar'] = math.random(35, 54),
        ['bg_greek_feta'] = math.random(35, 54),
        ['bg_caprese'] = math.random(35, 54),
        ['bg_chicken_caesar'] = math.random(35, 54),
        ['bg_fresh_garden'] = math.random(35, 54),

        ['bg_croissant'] = math.random(35, 54),
        ['bg_apple_turnover'] = math.random(35, 54),
        ['bg_cinnamon_roll'] = math.random(35, 54),
        ['bg_eclairs'] = math.random(35, 54),
        ['bg_danish_pastry'] = math.random(35, 54),
    },
    drink = {
        ['bg_iced_caramel_latte'] = math.random(35, 54),
        ['bg_mocha_frappe'] = math.random(35, 54),
        ['bg_cold_brew_coffee'] = math.random(35, 54),
        ['bg_iced_matcha_latte'] = math.random(35, 54),
        ['bg_vanilla_iced_coffee'] = math.random(35, 54),
    },
}
```

</details>

<details>

<summary>Jim Consumables</summary>

Add the following in jim-consumables/shared/consumables.lua

```lua
--jim-consumables/shared/consumables.lua
bg_margherita = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_pepperoni = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_bbq_chicken = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_Supreme = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_hawaiian = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_Caesar = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_greek_feta = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_caprese = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_chicken_caesar = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_fresh_garden = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_croissant = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_apple_turnover = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_cinnamon_roll = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_eclairs = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_danish_pastry = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},

bg_iced_caramel_latte = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_mocha_frappe = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_cold_brew_coffee = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_iced_matcha_latte = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
bg_vanilla_iced_coffee = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},

--Add in jim-consumables/shared/emotes.lua
pizza = {"mp_player_inteat@burger", "mp_player_int_eat_burger", "Pizza", AnimationOptions ={ Prop = "v_res_tt_pizzaplate", PropBone = 18905, PropPlacement = {0.200000, 0.038000, 0.051000, 15.000000, 155.000000, 0.0},EmoteMoving = true, EmoteLoop = true, }},
```

</details>

### Add Images to Inventory

Copy all the Images folder and paste it in your inventory Images folder

### Log Webook Setup - Optional

To enable discord logs make sure to add your webhook in the server->Log.lua File

{% embed url="https://www.youtube.com/watch?pp=ygULI2FwcHlxczIwMjM=&v=fKksxz2Gdnc" %}
