# Installation

## Dependencies

Make Sure all the dependencies are installed.

[<kbd>ox\_lib</kbd>](https://github.com/overextended/ox_lib)

[<kbd>ox-target</kbd>](https://github.com/overextended/ox_target) <kbd>or</kbd> [<kbd>qb-target</kbd>](https://github.com/qbcore-framework/qb-target)

### Config Setup

Adjust config.lua according to your liking

Make sure to set your map, target, clothing, billing, society script

### SQL Installation

Use this if AutoInstallSQL Fails for some reason and doesn't generates the sql database

<details>

<summary>ESX</summary>

```etlua
CREATE TABLE IF NOT EXISTS `pl_beanmachine` (
    `stock` longtext DEFAULT NULL,
    `state` varchar(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;

INSERT INTO `addon_account` (name, label, shared) VALUES
        ('society_beanmachine', 'BeanMachine', 1);

 INSERT INTO `datastore` (name, label, shared) VALUES
        ('society_beanmachine', 'BeanMachine', 1);

INSERT INTO `jobs` (name, label,whitelisted) VALUES
        ('beanmachine', 'BeanMachine',1);

 INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
        ('beanmachine',0,'cashier','Cashier',20,'{}','{}'),
        ('beanmachine',1,'cook','Cook',40,'{}','{}'),
        ('beanmachine',2,'staff','Staff',60,'{}','{}'),
        ('beanmachine',3,'manager','Manager',85,'{}','{}'),
        ('beanmachine',4,'boss','Owner',100,'{}','{}');
```

</details>

<details>

<summary>QBCore or QBox</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_beanmachine` (
  `stock` longtext DEFAULT NULL,
  `state` varchar(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;
```

</details>

### Items

Add the items into your server

<details>

<summary>OX Inventory</summary>

```lua
["bm_cinnamon_sugar_donut"] = {
    label = "Cinnamon Sugar Donut",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_cookiecream_donut"] = {
    label = "Cookie Cream Donut",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_cruller_donut"] = {
    label = "Cruller Donut",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_chocolate_frosted_donut"] = {
    label = "Chocolate Frosted Donut",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_strawberry_iced_donut"] = {
    label = "Strawberry Iced Donut",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_americano"] = {
    label = "Americano",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},
["bm_cappuccino"] = {
    label = "Cappuccino",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},
["bm_iced_coffee"] = {
    label = "Iced Coffee",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},
["bm_iced_macchiato"] = {
    label = "Iced Macchiato",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},
["bm_mocha"] = {
    label = "Mocha",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},
["bm_chocolate_chip_cookie"] = {
    label = "Chocolate Chip Cookie",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_double_chocolate_cookie"] = {
    label = "Double Chocolate Cookie",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_oatmeal_raisin_cookie"] = {
    label = "Oatmeal Raisin Cookie",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_peanut_butter_cookie"] = {
    label = "Peanut Butter Cookie",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_white_chocolate_cookie"] = {
    label = "White Chocolate Cookie",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_blt_sandwich"] = {
    label = "BLT Sandwich",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_chicken_pesto_panini_sandwich"] = {
    label = "Chicken Pesto Panini",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_classicclub_sandwich"] = {
    label = "Classic Club Sandwich",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_grilled_cheese_sandwich"] = {
    label = "Grilled Cheese Sandwich",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_tuna_melt_sandwich"] = {
    label = "Tuna Melt Sandwich",
    weight = 1,
    stack = true,
    close = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious Ramen'
		},
},
["bm_dough"] = {
    label = "Dough",
    weight = 1,
    stack = true,
    close = true,
},
["bm_strawberry_glaze"] = {
    label = "Strawberry Glaze",
    weight = 1,
    stack = true,
    close = true,
},
["bm_chocolate_syrup"] = {
    label = "Chocolate Syrup",
    weight = 1,
    stack = true,
    close = true,
},
["bm_egg_dough"] = {
    label = "Egg Dough",
    weight = 1,
    stack = true,
    close = true,
},
["bm_crushed_cookies"] = {
    label = "Crushed Cookies & Cream",
    weight = 1,
    stack = true,
    close = true,
},
["bm_cinnamon_sugar"] = {
    label = "Cinnamon Sugar",
    weight = 1,
    stack = true,
    close = true,
},
["bm_coffee_beans"] = {
    label = "Coffee Beans",
    weight = 1,
    stack = true,
    close = true,
},
["bm_hot_water"] = {
    label = "Hot Water",
    weight = 1,
    stack = true,
    close = true,
},
["bm_milk"] = {
    label = "Milk",
    weight = 1,
    stack = true,
    close = true,
},
["bm_icecubes"] = {
    label = "Ice Cubes",
    weight = 1,
    stack = true,
    close = true,
},
["bm_waterbottle"] = {
    label = "Water Bottle",
    weight = 1,
    stack = true,
    close = true,
},
["bm_caramel_drizzle"] = {
    label = "Caramel Drizzle",
    weight = 1,
    stack = true,
    close = true,
},
["bm_cookie_dough"] = {
    label = "Cookie Dough",
    weight = 1,
    stack = true,
    close = true,
},
["bm_cocoa_powder"] = {
    label = "Cocoa Powder",
    weight = 1,
    stack = true,
    close = true,
},
["bm_raisins"] = {
    label = "Raisins",
    weight = 1,
    stack = true,
    close = true,
},
["bm_peanut_butter"] = {
    label = " Peanut Butter",
    weight = 1,
    stack = true,
    close = true,
},
["bm_white_chocolate"] = {
    label = "White Chocolate",
    weight = 1,
    stack = true,
    close = true,
},
["bm_chocolate_chip"] = {
    label = "Chocolate Chip",
    weight = 1,
    stack = true,
    close = true,
},
["bm_bread"] = {
    label = "Bread",
    weight = 1,
    stack = true,
    close = true,
},
["bm_tuna_salad"] = {
    label = "Tuna Salad",
    weight = 1,
    stack = true,
    close = true,
},
["bm_pesto_sauce"] = {
    label = "Pesto Sauce",
    weight = 1,
    stack = true,
    close = true,
},
["bm_ham"] = {
    label = "Ham",
    weight = 1,
    stack = true,
    close = true,
},
["bm_cheese"] = {
    label = "Cheese",
    weight = 1,
    stack = true,
    close = true,
},
["bm_crispy_bacon"] = {
    label = "Crispy Bacon",
    weight = 1,
    stack = true,
    close = true,
},
```

</details>

<details>

<summary>QB Inventory</summary>

```lua
['bm_cinnamon_sugar_donut'] = {['name'] = 'bm_cinnamon_sugar_donut', ['label'] = 'Cinnamon Sugar Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_cinnamon_sugar_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_cookiecream_donut'] = {['name'] = 'bm_cookiecream_donut', ['label'] = 'Cookie Cream Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_cookiecream_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_cruller_donut'] = {['name'] = 'bm_cruller_donut', ['label'] = 'Cruller Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_cruller_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_chocolate_frosted_donut'] = {['name'] = 'bm_chocolate_frosted_donut', ['label'] = 'Chocolate Frosted Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_chocolate_frosted_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_strawberry_iced_donut'] = {['name'] = 'bm_strawberry_iced_donut', ['label'] = 'Strawberry Iced Donut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_strawberry_iced_donut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_americano'] = {['name'] = 'bm_americano', ['label'] = 'Americano', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_americano.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_cappuccino'] = {['name'] = 'bm_cappuccino', ['label'] = 'Cappuccino', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_cappuccino.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_iced_coffee'] = {['name'] = 'bm_iced_coffee', ['label'] = 'Iced Coffee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_iced_coffee.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_iced_macchiato'] = {['name'] = 'bm_iced_macchiato', ['label'] = 'Iced Macchiato', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_iced_macchiato.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_mocha'] = {['name'] = 'bm_mocha', ['label'] = 'Mocha', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_mocha.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_chocolate_chip_cookie'] = {['name'] = 'bm_chocolate_chip_cookie', ['label'] = 'Chocolate Chip Cookie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_chocolate_chip_cookie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_double_chocolate_cookie'] = {['name'] = 'bm_double_chocolate_cookie', ['label'] = 'Double Chocolate Cookie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_double_chocolate_cookie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_oatmeal_raisin_cookie'] = {['name'] = 'bm_oatmeal_raisin_cookie', ['label'] = 'Oatmeal Raisin Cookie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_oatmeal_raisin_cookie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_peanut_butter_cookie'] = {['name'] = 'bm_peanut_butter_cookie', ['label'] = 'Peanut Butter Cookie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_peanut_butter_cookie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_white_chocolate_cookie'] = {['name'] = 'bm_white_chocolate_cookie', ['label'] = 'White Chocolate Cookie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_white_chocolate_cookie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_blt_sandwich'] = {['name'] = 'bm_blt_sandwich', ['label'] = 'BLT Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_blt_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_chicken_pesto_panini_sandwich'] = {['name'] = 'bm_chicken_pesto_panini_sandwich', ['label'] = 'Chicken Pesto Panini', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_chicken_pesto_panini_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_classicclub_sandwich'] = {['name'] = 'bm_classicclub_sandwich', ['label'] = 'Classic Club Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_classicclub_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_grilled_cheese_sandwich'] = {['name'] = 'bm_grilled_cheese_sandwich', ['label'] = 'Grilled Cheese Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_grilled_cheese_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_tuna_melt_sandwich'] = {['name'] = 'bm_tuna_melt_sandwich', ['label'] = 'Tuna Melt Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_tuna_melt_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_dough'] = {['name'] = 'bm_dough', ['label'] = 'Dough', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_dough.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_strawberry_glaze'] = {['name'] = 'bm_strawberry_glaze', ['label'] = 'Strawberry Glaze', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_strawberry_glaze.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_chocolate_syrup'] = {['name'] = 'bm_chocolate_syrup', ['label'] = 'Chocolate Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_chocolate_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_egg_dough'] = {['name'] = 'bm_egg_dough', ['label'] = 'Egg Dough', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_egg_dough.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_crushed_cookies'] = {['name'] = 'bm_crushed_cookies', ['label'] = 'Crushed Cookies & Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_crushed_cookies.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_cinnamon_sugar'] = {['name'] = 'bm_cinnamon_sugar', ['label'] = 'Cinnamon Sugar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_cinnamon_sugar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_coffee_beans'] = {['name'] = 'bm_coffee_beans', ['label'] = 'Coffee Beans', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_coffee_beans.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_hot_water'] = {['name'] = 'bm_hot_water', ['label'] = 'Hot Water', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_hot_water.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_milk'] = {['name'] = 'bm_milk', ['label'] = 'Milk', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_milk.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_icecubes'] = {['name'] = 'bm_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_waterbottle'] = {['name'] = 'bm_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_caramel_drizzle'] = {['name'] = 'bm_caramel_drizzle', ['label'] = 'Caramel Drizzle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_caramel_drizzle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_cookie_dough'] = {['name'] = 'bm_cookie_dough', ['label'] = 'Cookie Dough', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_cookie_dough.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_cocoa_powder'] = {['name'] = 'bm_cocoa_powder', ['label'] = 'Cocoa Powder', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_cocoa_powder.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_raisins'] = {['name'] = 'bm_raisins', ['label'] = 'Raisins', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_raisins.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_peanut_butter'] = {['name'] = 'bm_peanut_butter', ['label'] = ' Peanut Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_peanut_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_white_chocolate'] = {['name'] = 'bm_white_chocolate', ['label'] = 'White Chocolate', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_white_chocolate.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_chocolate_chip'] = {['name'] = 'bm_chocolate_chip', ['label'] = 'Chocolate Chip', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_chocolate_chip.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_bread'] = {['name'] = 'bm_bread', ['label'] = 'Bread', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_bread.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_tuna_salad'] = {['name'] = 'bm_tuna_salad', ['label'] = 'Tuna Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_tuna_salad.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_pesto_sauce'] = {['name'] = 'bm_pesto_sauce', ['label'] = 'Pesto Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_pesto_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_ham'] = {['name'] = 'bm_ham', ['label'] = 'Ham', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_ham.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_cheese'] = {['name'] = 'bm_cheese', ['label'] = 'Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['bm_crispy_bacon'] = {['name'] = 'bm_crispy_bacon', ['label'] = 'Crispy Bacon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'bm_crispy_bacon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>ESX Items SQL</summary>

```lua
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
    ('bm_cinnamon_sugar_donut', 'Cinnamon Sugar Donut', 1),
    ('bm_cookiecream_donut', 'Cookie Cream Donut', 1),
    ('bm_cruller_donut', 'Cruller Donut', 1),
    ('bm_chocolate_frosted_donut', 'Chocolate Frosted Donut', 1),
    ('bm_strawberry_iced_donut', 'Strawberry Iced Donut', 1),
    ('bm_americano', 'Americano', 1),
    ('bm_cappuccino', 'Cappuccino', 1),
    ('bm_iced_coffee', 'Iced Coffee', 1),
    ('bm_iced_macchiato', 'Iced Macchiato', 1),
    ('bm_mocha', 'Mocha', 1),
    ('bm_chocolate_chip_cookie', 'Chocolate Chip Cookie', 1),
    ('bm_double_chocolate_cookie', 'Double Chocolate Cookie', 1),
    ('bm_oatmeal_raisin_cookie', 'Oatmeal Raisin Cookie', 1),
    ('bm_peanut_butter_cookie', 'Peanut Butter Cookie', 1),
    ('bm_white_chocolate_cookie', 'White Chocolate Cookie', 1),
    ('bm_blt_sandwich', 'BLT Sandwich', 1),
    ('bm_chicken_pesto_panini_sandwich', 'Chicken Pesto Panini', 1),
    ('bm_classicclub_sandwich', 'Classic Club Sandwich', 1),
    ('bm_grilled_cheese_sandwich', 'Grilled Cheese Sandwich', 1),
    ('bm_tuna_melt_sandwich', 'Tuna Melt Sandwich', 1),
    ('bm_dough', 'Dough', 1),
    ('bm_strawberry_glaze', 'Strawberry Glaze', 1),
    ('bm_chocolate_syrup', 'Chocolate Syrup', 1),
    ('bm_egg_dough', 'Egg Dough', 1),
    ('bm_crushed_cookies', 'Crushed Cookies & Cream', 1),
    ('bm_cinnamon_sugar', 'Cinnamon Sugar', 1),
    ('bm_coffee_beans', 'Coffee Beans', 1),
    ('bm_hot_water', 'Hot Water', 1),
    ('bm_milk', 'Milk', 1),
    ('bm_icecubes', 'Ice Cubes', 1),
    ('bm_waterbottle', 'Water Bottle', 1),
    ('bm_caramel_drizzle', 'Caramel Drizzle', 1),
    ('bm_cookie_dough', 'Cookie Dough', 1),
    ('bm_cocoa_powder', 'Cocoa Powder', 1),
    ('bm_raisins', 'Raisins', 1),
    ('bm_peanut_butter', ' Peanut Butter', 1),
    ('bm_white_chocolate', 'White Chocolate', 1),
    ('bm_chocolate_chip', 'Chocolate Chip', 1),
    ('bm_bread', 'Bread', 1),
    ('bm_tuna_salad', 'Tuna Salad', 1),
    ('bm_pesto_sauce', 'Pesto Sauce', 1),
    ('bm_ham', 'Ham', 1),
    ('bm_cheese', 'Cheese', 1),
    ('bm_crispy_bacon', 'Crispy Bacon', 1);
```

</details>

### For QBCore Only

{% tabs %}
{% tab title="jobs.lua" %}
Add the following in qb-core/shared/jobs.lua

Add the Following in qb-core/shared/jobs.lua

```lua
['beanmachine'] = {
    label = 'BeanMachine',
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
['beanmachine'] = {
    label = 'BeanMachine',
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

```lua
-- qb-smallresources->config.lua

--If using old qb-smallresources
Config.ConsumablesDrink = {
    ['bm_americano'] = math.random(35, 54),
    ['bm_cappuccino'] = math.random(35, 54),
    ['bm_iced_coffee'] = math.random(35, 54),
    ['bm_iced_macchiato'] = math.random(35, 54),
    ['bm_mocha'] = math.random(35, 54),
}

Config.ConsumablesEat = {
    ['bm_cinnamon_sugar_donut'] = math.random(35, 54),
    ['bm_cookiecream_donut'] = math.random(35, 54),
    ['bm_cruller_donut'] = math.random(35, 54),
    ['bm_chocolate_fosted_donut'] = math.random(35, 54),
    ['bm_strawberry_iced_donut'] = math.random(35, 54),

    ['bm_chocolate_chip_cookie'] = math.random(35, 54),
    ['bm_double_chocolate_cookie'] = math.random(35, 54),
    ['bm_oatmeal_raisin_cookie'] = math.random(35, 54),
    ['bm_peanut_butter_cookie'] = math.random(35, 54),
    ['bm_white_chocolate_cookie'] = math.random(35, 54),

    ['bm_blt_sandwich'] = math.random(35, 54),
    ['bm_chicken_pesto_panini_sandwich'] = math.random(35, 54),
    ['bm_classicclub_sandwich'] = math.random(35, 54),
    ['bm_grilled_cheese_sandwich'] = math.random(35, 54),
    ['bm_tuna_melt_sandwich'] = math.random(35, 54),
}

--If using new qb-smallresources
Config.Consumables = {
    eat = {
        ['bm_cinnamon_sugar_donut'] = math.random(35, 54),
        ['bm_cookiecream_donut'] = math.random(35, 54),
        ['bm_cruller_donut'] = math.random(35, 54),
        ['bm_chocolate_fosted_donut'] = math.random(35, 54),
        ['bm_strawberry_iced_donut'] = math.random(35, 54),

        ['bm_chocolate_chip_cookie'] = math.random(35, 54),
        ['bm_double_chocolate_cookie'] = math.random(35, 54),
        ['bm_oatmeal_raisin_cookie'] = math.random(35, 54),
        ['bm_peanut_butter_cookie'] = math.random(35, 54),
        ['bm_white_chocolate_cookie'] = math.random(35, 54),

        ['bm_blt_sandwich'] = math.random(35, 54),
        ['bm_chicken_pesto_panini_sandwich'] = math.random(35, 54),
        ['bm_classicclub_sandwich'] = math.random(35, 54),
        ['bm_grilled_cheese_sandwich'] = math.random(35, 54),
        ['bm_tuna_melt_sandwich'] = math.random(35, 54),
    },
    drink = {
        ['bm_americano'] = math.random(35, 54),
        ['bm_cappuccino'] = math.random(35, 54),
        ['bm_iced_coffee'] = math.random(35, 54),
        ['bm_iced_macchiato'] = math.random(35, 54),
        ['bm_mocha'] = math.random(35, 54),
    },
}
```

</details>

<details>

<summary>Jim Consumables</summary>

```lua
--jim-consumables/shared/consumables.lua
bm_cinnamon_sugar_donut = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_cookiecream_donut = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_cruller_donut = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_chocolate_fosted_donut = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_strawberry_iced_donut = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_chocolate_chip_cookie = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_double_chocolate_cookie = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_oatmeal_raisin_cookie = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_peanut_butter_cookie = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_white_chocolate_cookie = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_blt_sandwich = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_chicken_pesto_panini_sandwich = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_classicclub_sandwich = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_grilled_cheese_sandwich = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
bm_tuna_melt_sandwich = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },

bm_americano = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
bm_cappuccino = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
bm_iced_coffee = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
bm_iced_macchiato = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
bm_mocha = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
```

</details>

### Add Images to Inventory

Copy all the Images folder and paste it in your inventory Images folder

### Log Webhook Setup - Optional

To enable discord logs make sure to add your webhook in the server->Log.lua File

{% embed url="https://www.youtube.com/watch?pp=ygULI2FwcHlxczIwMjM=&v=fKksxz2Gdnc" %}

### Optional Dj Custom Props

If you have purchased the DJ BeanMachine Props https://djscollections.com/package/5977681

&#x20; just install it and set the Config.UseDjItems = true

