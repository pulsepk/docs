# Installation

### Dependencies

Make Sure all the dependencies are installed.

Required

[<kbd>ox\_lib</kbd>](https://github.com/overextended/ox_lib)

[<kbd>ox-target</kbd>](https://github.com/overextended/ox_target) <kbd>or</kbd> [<kbd>qb-target</kbd>](https://github.com/qbcore-framework/qb-target)

### Config Setup

Adjust config.lua according to your liking

Make sure to set your target, clothing, billing, society script or use the autodetect feature

### SQL Installations

Use this if AutoInstallSQL Fails for some reason and doesn't generates the sql database

<details>

<summary>ESX</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_uwucafe` (
    `stock` longtext DEFAULT NULL,
    `state` varchar(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;
        
INSERT INTO `addon_account` (name, label, shared) VALUES
      ('society_uwu', 'Uwu Cafe', 1);
        
INSERT INTO `datastore` (name, label, shared) VALUES
        ('society_uwu', 'Uwu Cafe', 1);
        
INSERT INTO `jobs` (name, label,whitelisted) VALUES
        ('uwu', 'UwU Cafe',1);
        
 INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
        ('uwu',0,'cashier','Cashier',20,'{}','{}'),
        ('uwu',1,'cook','Cook',40,'{}','{}'),
        ('uwu',2,'staff','Staff',60,'{}','{}'),
        ('uwu',3,'manager','Manager',85,'{}','{}'),
        ('uwu',4,'boss','Owner',100,'{}','{}');
```

</details>

<details>

<summary>QBCore or Qbox</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_uwucafe` (
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
["cc_tonkotsu_ramen"] = {
	label = "Tonkotsu Ramen",
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
["cc_shoyu_ramen"] = {
	label = "Shoyu Ramen",
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
["cc_nagoya_taiwan_ramen"] = {
	label = "Nagoya Taiwan Ramen",
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
["cc_tropicalparadisesmoothie"] = {
	label = "Tropical Paradise Smoothie",
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

["cc_turkey_sandwich"] = {
	label = "Turkey Sandwich",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious snadwich'
		},
},

["cc_turkey_slices"] = {
	label = "Turkey Slices",
	weight = 1,
	stack = true,
	close = true,
},

["cc_vanilla_icecream"] = {
	label = "Vanilla Icecream",
	weight = 1,
	stack = true,
	close = true,
},

["cc_wheat_noodles"] = {
	label = "Wheat Noodles",
	weight = 1,
	stack = true,
	close = true,
},

["cc_yogurtcup"] = {
	label = "Yogurt Cup",
	weight = 1,
	stack = true,
	close = true,
},

["cc_avocado"] = {
	label = "Avocado",
	weight = 1,
	stack = true,
	close = true,
},

["cc_avocado_sandwich"] = {
	label = "Avocado Sandwich",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious snadwich'
		},
},

["cc_bacon_strips"] = {
	label = "Bacon Strips",
	weight = 1,
	stack = true,
	close = true,
},

["cc_berryblastsmoothie"] = {
	label = "BerryBlast Smoothie",
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

["cc_black_garlic_ramen"] = {
	label = "Black Garlic Ramen",
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

["cc_black_tapioca_pearls"] = {
	label = "Black Tapioca Pearls",
	weight = 1,
	stack = true,
	close = true,
},

["cc_brewed_black_tea"] = {
	label = "Brewed Black Tea",
	weight = 1,
	stack = true,
	close = true,
},

["cc_bubbletea"] = {
	label = "Bubble Tea",
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

["cc_butter"] = {
	label = "Butter",
	weight = 1,
	stack = true,
	close = true,
},

["cc_cappuccino"] = {
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

["cc_caprese_sandwich"] = {
	label = "Caprese Sandwich",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious snadwich'
		},
},

["cc_chashu_pork"] = {
	label = "Chashu Pork",
	weight = 1,
	stack = true,
	close = true,
},

["cc_cheddar_cheese"] = {
	label = "Cheddar Cheese",
	weight = 1,
	stack = true,
	close = true,
},

["cc_cheese_sandwich"] = {
	label = "Cheese Sandwich",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious snadwich'
		},
},

["cc_chocolatemilkshake"] = {
	label = "Chocolate MilkShake",
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

["cc_chocolate_chips"] = {
	label = "Chocolate Chips",
	weight = 1,
	stack = true,
	close = true,
},

["cc_chocolate_cookies"] = {
	label = "Chocolate Cookies",
	weight = 1,
	stack = true,
	close = true,
},

["cc_chocolate_icecream"] = {
	label = "Chocolate Icecream",
	weight = 1,
	stack = true,
	close = true,
},

["cc_chocolate_syrup"] = {
	label = "Chocolate Syrup",
	weight = 1,
	stack = true,
	close = true,
},

["cc_classic_blt_sandwich"] = {
	label = "Classic Blt Sandwich",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious snadwich'
		},
},

["cc_cocao_powder"] = {
	label = "Cocoa Powder",
	weight = 1,
	stack = true,
	close = true,
},

["cc_coconut_milk"] = {
	label = "Coconut Milk",
	weight = 1,
	stack = true,
	close = true,
},

["cc_coffee_icecream"] = {
	label = "Coffee Icecream",
	weight = 1,
	stack = true,
	close = true,
},

["cc_coffee_powder"] = {
	label = "Coffee Powder",
	weight = 1,
	stack = true,
	close = true,
},

["cc_cuporangejuice"] = {
	label = "Cup of Orange Juice",
	weight = 1,
	stack = true,
	close = true,
},

["cc_espresso"] = {
	label = "Espresso",
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

["cc_fukuoka_hakata_ramen"] = {
	label = "Fukuoka Hakata Ramen",
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

["cc_green_onions"] = {
	label = "Green Onions",
	weight = 1,
	stack = true,
	close = true,
},

["cc_heavy_cream"] = {
	label = "Heavy Cream",
	weight = 1,
	stack = true,
	close = true,
},

["cc_hotchocolate"] = {
	label = "Hot Chocolate",
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

["cc_iekei_ramen"] = {
	label = "Iekei Ramen",
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

["cc_latte"] = {
	label = "Latte",
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

["cc_lettuce"] = {
	label = "Lettuce",
	weight = 1,
	stack = true,
	close = true,
},

["cc_mango_chunks"] = {
	label = "Mango Chunks",
	weight = 1,
	stack = true,
	close = true,
},

["cc_milk"] = {
	label = "Milk",
	weight = 1,
	stack = true,
	close = true,
},

["cc_mintchoco_icecream"] = {
	label = "Mintchoco Icecream",
	weight = 1,
	stack = true,
	close = true,
},

["cc_miso_broth"] = {
	label = "Miso Broth",
	weight = 1,
	stack = true,
	close = true,
},

["cc_miso_ramen"] = {
	label = "Miso Ramen",
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

["cc_mixedberries"] = {
	label = "Mixed Berries",
	weight = 1,
	stack = true,
	close = true,
},

["cc_mocha"] = {
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

["cc_mozzarella_cheese"] = {
	label = "Mozzarella Cheese",
	weight = 1,
	stack = true,
	close = true,
},

["cc_osaka_shio_ramen"] = {
	label = "Osaka Shio Ramen",
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

["cc_pineapple_chunks"] = {
	label = "Pineapple Chunks",
	weight = 1,
	stack = true,
	close = true,
},

["cc_pure_vanilla"] = {
	label = "Pure Vanilla",
	weight = 1,
	stack = true,
	close = true,
},

["cc_ripebanana"] = {
	label = "Ripe Banana",
	weight = 1,
	stack = true,
	close = true,
},

["cc_slices_of_bread"] = {
	label = "Slices of Bread",
	weight = 1,
	stack = true,
	close = true,
},

["cc_soft_boiled_egg"] = {
	label = "Soft Boiled Egg",
	weight = 1,
	stack = true,
	close = true,
},

["cc_spinach"] = {
	label = "Spinach",
	weight = 1,
	stack = true,
	close = true,
},

["cc_strawberries"] = {
	label = "Strawberries",
	weight = 1,
	stack = true,
	close = true,
},

["cc_strawberrysmoothie"] = {
	label = "Strawberry Smoothie",
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

["cc_strawberry_icecream"] = {
	label = "Strawberry Icecream",
	weight = 1,
	stack = true,
	close = true,
},

["cc_sugar"] = {
	label = "Sugar",
	weight = 1,
	stack = true,
	close = true,
},

["cc_icecubes"] = {
	label = "Ice Cubes",
	weight = 1,
	stack = true,
	close = true,
},

["cc_waterbottle"] = {
	label = "Water Bottle",
	weight = 1,
	stack = true,
	close = true,
},
["cc_emptycup"] = {
	label = "Water Bottle",
	weight = 1,
	stack = true,
	close = true,
},

['plush_01a'] = {
    label = 'Plush Toy 01',
    weight = 100,
    stack = true,
    close = true,
    description = 'A cute collectible arcade plush.',
    client = {
        event = 'pl_uwucafe:shouldertoy:useToy',
        args = { model = 'sum_prop_sum_arcade_plush_01a' }
    }
},

['plush_02a'] = {
    label = 'Plush Toy 02',
    weight = 100,
    stack = true,
    close = true,
    description = 'A fuzzy little friend from the arcade.',
    client = {
        event = 'pl_uwucafe:shouldertoy:useToy',
        args = { model = 'sum_prop_sum_arcade_plush_02a' }
    }
},

['plush_03a'] = {
    label = 'Plush Toy 03',
    weight = 100,
    stack = true,
    close = true,
    description = 'Soft and snuggly collectible.',
    client = {
        event = 'pl_uwucafe:shouldertoy:useToy',
        args = { model = 'sum_prop_sum_arcade_plush_03a' }
    }
},

['plush_04a'] = {
    label = 'Plush Toy 04',
    weight = 100,
    stack = true,
    close = true,
    description = 'Another arcade machine prize!',
    client = {
        event = 'pl_uwucafe:shouldertoy:useToy',
        args = { model = 'sum_prop_sum_arcade_plush_04a' }
    }
},

['plush_05a'] = {
    label = 'Plush Toy 05',
    weight = 100,
    stack = true,
    close = true,
    description = 'Perfect shoulder companion.',
    client = {
        event = 'pl_uwucafe:shouldertoy:useToy',
        args = { model = 'sum_prop_sum_arcade_plush_05a' }
    }
},

['plush_06a'] = {
    label = 'Plush Toy 06',
    weight = 100,
    stack = true,
    close = true,
    description = 'Looks like it came from a claw machine.',
    client = {
        event = 'pl_uwucafe:shouldertoy:useToy',
        args = { model = 'sum_prop_sum_arcade_plush_06a' }
    }
},

['plush_07a'] = {
    label = 'Plush Toy 07',
    weight = 100,
    stack = true,
    close = true,
    description = 'Looks handmade with love.',
    client = {
        event = 'pl_uwucafe:shouldertoy:useToy',
        args = { model = 'sum_prop_sum_arcade_plush_07a' }
    }
},

['plush_08a'] = {
    label = 'Plush Toy 08',
    weight = 100,
    stack = true,
    close = true,
    description = 'A tiny plush to carry around.',
    client = {
        event = 'pl_uwucafe:shouldertoy:useToy',
        args = { model = 'sum_prop_sum_arcade_plush_08a' }
    }
},


```

</details>

<details>

<summary>QB Inventory</summary>

```lua
--Add in qb-core/shared/items.lua
['cc_sugar'] = {['name'] = 'cc_sugar', ['label'] = 'Sugar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_sugar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_espresso'] = {['name'] = 'cc_espresso', ['label'] = 'Espresso', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_espresso.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_cappuccino'] = {['name'] = 'cc_cappuccino', ['label'] = 'Cappuccino', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_cappuccino.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_milk'] = {['name'] = 'cc_milk', ['label'] = 'Milk', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_milk.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_cocao_powder'] = {['name'] = 'cc_cocao_powder', ['label'] = 'Cocao Powder', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_cocao_powder.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_latte'] = {['name'] = 'cc_latte', ['label'] = 'Latte', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_latte.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_mocha'] = {['name'] = 'cc_mocha', ['label'] = 'Mocha', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_mocha.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_chocolate_syrup'] = {['name'] = 'cc_chocolate_syrup', ['label'] = 'Chocolate Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_chocolate_syrup.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_hotchocolate'] = {['name'] = 'cc_hotchocolate', ['label'] = 'Hot Chocolate', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_hotchocolate.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_bubbletea'] = {['name'] = 'cc_bubbletea', ['label'] = 'Bubble Tea', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_bubbletea.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_chocolatemilkshake'] = {['name'] = 'cc_chocolatemilkshake', ['label'] = 'Chocolate Milkshake', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_chocolatemilkshake.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_strawberrysmoothie'] = {['name'] = 'cc_strawberrysmoothie', ['label'] = 'Strawberry Smoothie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_strawberrysmoothie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_berryblastsmoothie'] = {['name'] = 'cc_berryblastsmoothie', ['label'] = 'Berry Blast Smoothie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_berryblastsmoothie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_tropicalparadisesmoothie'] = {['name'] = 'cc_tropicalparadisesmoothie', ['label'] = 'Tropical Paradise Smoothie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_tropicalparadisesmoothie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_mixedberries'] = {['name'] = 'cc_mixedberries', ['label'] = 'Cup of Mixed Berries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_mixedberries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_yogurtcup'] = {['name'] = 'cc_yogurtcup', ['label'] = 'Yogurt Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_yogurtcup.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_cuporangejuice'] = {['name'] = 'cc_cuporangejuice', ['label'] = 'Yogurt Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cup_orange_juice.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_ripebanana'] = {['name'] = 'cc_ripebanana', ['label'] = 'Ripe Banana', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ripe_banana.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_coconut_milk'] = {['name'] = 'cc_coconut_milk', ['label'] = 'Coconut Milk', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_coconut_milk.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_pineapple_chunks'] = {['name'] = 'cc_pineapple_chunks', ['label'] = 'Pineapple Chunks', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_pineapple_chunks.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_mango_chunks'] = {['name'] = 'cc_mango_chunks', ['label'] = 'Mango Chunks', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_pineapple_chunks.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_black_tapioca_pearls'] = {['name'] = 'cc_black_tapioca_pearls', ['label'] = 'Black Tapioca Pearls', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_black_tapioca_pearls.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_brewed_black_tea'] = {['name'] = 'cc_brewed_black_tea', ['label'] = 'Brewed Black Tea', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_brewed_black_tea.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_vanilla_icecream'] = {['name'] = 'cc_vanilla_icecream', ['label'] = 'Vanilla Icecream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_vanilla_icecream.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_strawberries'] = {['name'] = 'cc_strawberries', ['label'] = 'Strawberries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_strawberries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_fukuoka_hakata_ramen'] = {['name'] = 'cc_fukuoka_hakata_ramen', ['label'] = 'Fukuoka Hakata Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_fukuoka_hakata_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_miso_ramen'] = {['name'] = 'cc_miso_ramen', ['label'] = 'Miso Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_miso_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_nagoya_taiwan_ramen'] = {['name'] = 'cc_nagoya_taiwan_ramen', ['label'] = 'Nagoya Taiwan Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_nagoya_taiwan_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_osaka_shio_ramen'] = {['name'] = 'cc_osaka_shio_ramen', ['label'] = 'Osaka Shio Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_osaka_shio_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_shoyu_ramen'] = {['name'] = 'cc_shoyu_ramen', ['label'] = 'Shoyu Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_shoyu_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_tonkotsu_ramen'] = {['name'] = 'cc_tonkotsu_ramen', ['label'] = 'Tonkotsu Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_tonkotsu_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_iekei_ramen'] = {['name'] = 'cc_iekei_ramen', ['label'] = 'Iekei Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'Iekei_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_black_garlic_ramen'] = { ['name'] = 'cc_black_garlic_ramen', ['label'] = 'Black Garlic Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_black_garlic_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_wheat_noodles'] = { ['name'] = 'cc_wheat_noodles', ['label'] = 'Wheat Noodles', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_wheat_noodles.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_green_onions'] = { ['name'] = 'green_onions', ['label'] = 'Green Onions', ['weight'] = 10, ['type'] = 'item', ['image'] = 'green_onions.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_chashu_pork'] = { ['name'] = 'cc_chashu_pork', ['label'] = 'Chashu Pork', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_chashu_pork.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_miso_broth'] = { ['name'] = 'cc_miso_broth', ['label'] = 'Miso Broth', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_miso_broth.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_butter'] = { ['name'] = 'cc_butter', ['label'] = 'Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_butter.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_spinach'] = { ['name'] = 'cc_spinach', ['label'] = 'Spinach', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_spinach.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_soft_boiled_egg'] = { ['name'] = 'cc_soft_boiled_egg', ['label'] = 'Soft Boiled Eggs', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_soft_boiled_egg.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_pure_vanilla'] = { ['name'] = 'cc_pure_vanilla', ['label'] = 'Pure Vanilla', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_pure_vanilla.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_heavy_cream'] = { ['name'] = 'cc_heavy_cream', ['label'] = 'Cup of Heavy Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_heavy_cream.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_chocolate_chips'] = { ['name'] = 'cc_chocolate_chips', ['label'] = 'Chocolate Chips', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_chocolate_chips.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_coffee_powder'] = { ['name'] = 'cc_coffee_powder', ['label'] = 'Coffee Powder', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_coffee_powder.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_chocolate_cookies'] = { ['name'] = 'cc_chocolate_cookies', ['label'] = 'Chocolate Cookies', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_chocolate_cookies.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_chocolate_icecream'] = { ['name'] = 'cc_chocolate_icecream', ['label'] = 'Chocolate IceCream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_chocolate_icecream.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_strawberry_icecream'] = { ['name'] = 'cc_strawberry_icecream', ['label'] = 'Strawberry IceCream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_strawberry_icecream.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_mintchoco_icecream'] = { ['name'] = 'cc_mintchoco_icecream', ['label'] = 'Mint Chocolate Chip Ice Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_mintchoco_icecream.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_coffee_icecream'] = { ['name'] = 'cc_coffee_icecream', ['label'] = 'Coffee Ice Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_coffee_icecream.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_classic_blt_sandwich'] = { ['name'] = 'cc_classic_blt_sandwich', ['label'] = 'Classic BLT Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_classic_blt_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_bacon_strips'] = { ['name'] = 'cc_bacon_strips', ['label'] = 'Bacon strips', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_bacon_strips.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_slices_of_bread'] = { ['name'] = 'cc_slices_of_bread', ['label'] = 'Slices of Bread', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_slices_of_bread.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_lettuce'] = { ['name'] = 'cc_lettuce', ['label'] = 'Lettuce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_lettuce.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_cheese_sandwich'] = { ['name'] = 'cc_cheese_sandwich', ['label'] = 'Cheese Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_cheese_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_cheddar_cheese'] = { ['name'] = 'cc_cheddar_cheese', ['label'] = 'Cheddar Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_cheddar_cheese.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_turkey_sandwich'] = { ['name'] = 'cc_turkey_sandwich', ['label'] = 'Turkey Club Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_turkey_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_turkey_slices'] = { ['name'] = 'cc_turkey_slices', ['label'] = 'Turkey Slices', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_turkey_slices.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_caprese_sandwich'] = { ['name'] = 'cc_caprese_sandwich', ['label'] = 'Caprese Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_caprese_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_mozzarella_cheese'] = { ['name'] = 'cc_mozzarella_cheese', ['label'] = 'Fresh mozzarella cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_mozzarella_cheese.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_avocado_sandwich'] = { ['name'] = 'cc_avocado_sandwich', ['label'] = 'Chicken Avocado Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_avocado_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_avocado'] = { ['name'] = 'cc_avocado', ['label'] = 'Avocado', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_avocado.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_icecubes'] = { ['name'] = 'cc_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_icecubes.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_waterbottle'] = { ['name'] = 'cc_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_waterbottle.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_emptycup'] = { ['name'] = 'cc_emptycup', ['label'] = 'Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_emptycup.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
--toys
['plush_01a'] = {['name'] = 'plush_01a', ['label'] = 'Plush Toy 01', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_01a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_02a'] = {['name'] = 'plush_02a', ['label'] = 'Plush Toy 02', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_02a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_03a'] = {['name'] = 'plush_03a', ['label'] = 'Plush Toy 03', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_03a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_04a'] = {['name'] = 'plush_04a', ['label'] = 'Plush Toy 04', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_04a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_05a'] = {['name'] = 'plush_05a', ['label'] = 'Plush Toy 05', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_05a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_06a'] = {['name'] = 'plush_06a', ['label'] = 'Plush Toy 06', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_06a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_07a'] = {['name'] = 'plush_07a', ['label'] = 'Plush Toy 07', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_07a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_08a'] = {['name'] = 'plush_08a', ['label'] = 'Plush Toy 08', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_08a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},

```

</details>

<details>

<summary>QS Inventory</summary>

```lua
['cc_sugar'] = {['name'] = 'cc_sugar', ['label'] = 'Sugar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_sugar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_espresso'] = {['name'] = 'cc_espresso', ['label'] = 'Espresso', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_espresso.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_cappuccino'] = {['name'] = 'cc_cappuccino', ['label'] = 'Cappuccino', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_cappuccino.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_milk'] = {['name'] = 'cc_milk', ['label'] = 'Milk', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_milk.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_cocao_powder'] = {['name'] = 'cc_cocao_powder', ['label'] = 'Cocao Powder', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_cocao_powder.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_latte'] = {['name'] = 'cc_latte', ['label'] = 'Latte', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_latte.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_mocha'] = {['name'] = 'cc_mocha', ['label'] = 'Mocha', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_mocha.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_chocolate_syrup'] = {['name'] = 'cc_chocolate_syrup', ['label'] = 'Chocolate Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_chocolate_syrup.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_hotchocolate'] = {['name'] = 'cc_hotchocolate', ['label'] = 'Hot Chocolate', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_hotchocolate.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_bubbletea'] = {['name'] = 'cc_bubbletea', ['label'] = 'Bubble Tea', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_bubbletea.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_chocolatemilkshake'] = {['name'] = 'cc_chocolatemilkshake', ['label'] = 'Chocolate Milkshake', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_chocolatemilkshake.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_strawberrysmoothie'] = {['name'] = 'cc_strawberrysmoothie', ['label'] = 'Strawberry Smoothie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_strawberrysmoothie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_berryblastsmoothie'] = {['name'] = 'cc_berryblastsmoothie', ['label'] = 'Berry Blast Smoothie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_berryblastsmoothie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_tropicalparadisesmoothie'] = {['name'] = 'cc_tropicalparadisesmoothie', ['label'] = 'Tropical Paradise Smoothie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_tropicalparadisesmoothie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_mixedberries'] = {['name'] = 'cc_mixedberries', ['label'] = 'Cup of Mixed Berries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_mixedberries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_yogurtcup'] = {['name'] = 'cc_yogurtcup', ['label'] = 'Yogurt Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_yogurtcup.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_cuporangejuice'] = {['name'] = 'cc_cuporangejuice', ['label'] = 'Yogurt Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cup_orange_juice.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_ripebanana'] = {['name'] = 'cc_ripebanana', ['label'] = 'Ripe Banana', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ripe_banana.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_coconut_milk'] = {['name'] = 'cc_coconut_milk', ['label'] = 'Coconut Milk', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_coconut_milk.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_pineapple_chunks'] = {['name'] = 'cc_pineapple_chunks', ['label'] = 'Pineapple Chunks', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_pineapple_chunks.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_mango_chunks'] = {['name'] = 'cc_mango_chunks', ['label'] = 'Mango Chunks', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_pineapple_chunks.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_black_tapioca_pearls'] = {['name'] = 'cc_black_tapioca_pearls', ['label'] = 'Black Tapioca Pearls', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_black_tapioca_pearls.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_brewed_black_tea'] = {['name'] = 'cc_brewed_black_tea', ['label'] = 'Brewed Black Tea', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_brewed_black_tea.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_vanilla_icecream'] = {['name'] = 'cc_vanilla_icecream', ['label'] = 'Vanilla Icecream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_vanilla_icecream.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_strawberries'] = {['name'] = 'cc_strawberries', ['label'] = 'Strawberries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_strawberries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_fukuoka_hakata_ramen'] = {['name'] = 'cc_fukuoka_hakata_ramen', ['label'] = 'Fukuoka Hakata Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_fukuoka_hakata_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_miso_ramen'] = {['name'] = 'cc_miso_ramen', ['label'] = 'Miso Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_miso_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_nagoya_taiwan_ramen'] = {['name'] = 'cc_nagoya_taiwan_ramen', ['label'] = 'Nagoya Taiwan Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_nagoya_taiwan_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_osaka_shio_ramen'] = {['name'] = 'cc_osaka_shio_ramen', ['label'] = 'Osaka Shio Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_osaka_shio_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_shoyu_ramen'] = {['name'] = 'cc_shoyu_ramen', ['label'] = 'Shoyu Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_shoyu_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_tonkotsu_ramen'] = {['name'] = 'cc_tonkotsu_ramen', ['label'] = 'Tonkotsu Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_tonkotsu_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_iekei_ramen'] = {['name'] = 'cc_iekei_ramen', ['label'] = 'Iekei Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'Iekei_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['cc_black_garlic_ramen'] = { ['name'] = 'cc_black_garlic_ramen', ['label'] = 'Black Garlic Ramen', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_black_garlic_ramen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_wheat_noodles'] = { ['name'] = 'cc_wheat_noodles', ['label'] = 'Wheat Noodles', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_wheat_noodles.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_green_onions'] = { ['name'] = 'green_onions', ['label'] = 'Green Onions', ['weight'] = 10, ['type'] = 'item', ['image'] = 'green_onions.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_chashu_pork'] = { ['name'] = 'cc_chashu_pork', ['label'] = 'Chashu Pork', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_chashu_pork.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_miso_broth'] = { ['name'] = 'cc_miso_broth', ['label'] = 'Miso Broth', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_miso_broth.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_butter'] = { ['name'] = 'cc_butter', ['label'] = 'Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_butter.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_spinach'] = { ['name'] = 'cc_spinach', ['label'] = 'Spinach', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_spinach.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_soft_boiled_egg'] = { ['name'] = 'cc_soft_boiled_egg', ['label'] = 'Soft Boiled Eggs', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_soft_boiled_egg.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_pure_vanilla'] = { ['name'] = 'cc_pure_vanilla', ['label'] = 'Pure Vanilla', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_pure_vanilla.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_heavy_cream'] = { ['name'] = 'cc_heavy_cream', ['label'] = 'Cup of Heavy Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_heavy_cream.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_chocolate_chips'] = { ['name'] = 'cc_chocolate_chips', ['label'] = 'Chocolate Chips', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_chocolate_chips.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_coffee_powder'] = { ['name'] = 'cc_coffee_powder', ['label'] = 'Coffee Powder', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_coffee_powder.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_chocolate_cookies'] = { ['name'] = 'cc_chocolate_cookies', ['label'] = 'Chocolate Cookies', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_chocolate_cookies.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_chocolate_icecream'] = { ['name'] = 'cc_chocolate_icecream', ['label'] = 'Chocolate IceCream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_chocolate_icecream.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_strawberry_icecream'] = { ['name'] = 'cc_strawberry_icecream', ['label'] = 'Strawberry IceCream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_strawberry_icecream.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_mintchoco_icecream'] = { ['name'] = 'cc_mintchoco_icecream', ['label'] = 'Mint Chocolate Chip Ice Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_mintchoco_icecream.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_coffee_icecream'] = { ['name'] = 'cc_coffee_icecream', ['label'] = 'Coffee Ice Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_coffee_icecream.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_classic_blt_sandwich'] = { ['name'] = 'cc_classic_blt_sandwich', ['label'] = 'Classic BLT Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_classic_blt_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_bacon_strips'] = { ['name'] = 'cc_bacon_strips', ['label'] = 'Bacon strips', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_bacon_strips.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_slices_of_bread'] = { ['name'] = 'cc_slices_of_bread', ['label'] = 'Slices of Bread', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_slices_of_bread.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_lettuce'] = { ['name'] = 'cc_lettuce', ['label'] = 'Lettuce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_lettuce.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_cheese_sandwich'] = { ['name'] = 'cc_cheese_sandwich', ['label'] = 'Cheese Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_cheese_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_cheddar_cheese'] = { ['name'] = 'cc_cheddar_cheese', ['label'] = 'Cheddar Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_cheddar_cheese.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_turkey_sandwich'] = { ['name'] = 'cc_turkey_sandwich', ['label'] = 'Turkey Club Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_turkey_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_turkey_slices'] = { ['name'] = 'cc_turkey_slices', ['label'] = 'Turkey Slices', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_turkey_slices.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_caprese_sandwich'] = { ['name'] = 'cc_caprese_sandwich', ['label'] = 'Caprese Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_caprese_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_mozzarella_cheese'] = { ['name'] = 'cc_mozzarella_cheese', ['label'] = 'Fresh mozzarella cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_mozzarella_cheese.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_avocado_sandwich'] = { ['name'] = 'cc_avocado_sandwich', ['label'] = 'Chicken Avocado Sandwich', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_avocado_sandwich.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_avocado'] = { ['name'] = 'cc_avocado', ['label'] = 'Avocado', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_avocado.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_icecubes'] = { ['name'] = 'cc_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_icecubes.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_waterbottle'] = { ['name'] = 'cc_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_waterbottle.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
['cc_emptycup'] = { ['name'] = 'cc_emptycup', ['label'] = 'Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'cc_emptycup.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = '' },
--toys
['plush_01a'] = {['name'] = 'plush_01a', ['label'] = 'Plush Toy 01', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_01a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_02a'] = {['name'] = 'plush_02a', ['label'] = 'Plush Toy 02', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_02a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_03a'] = {['name'] = 'plush_03a', ['label'] = 'Plush Toy 03', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_03a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_04a'] = {['name'] = 'plush_04a', ['label'] = 'Plush Toy 04', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_04a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_05a'] = {['name'] = 'plush_05a', ['label'] = 'Plush Toy 05', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_05a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_06a'] = {['name'] = 'plush_06a', ['label'] = 'Plush Toy 06', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_06a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_07a'] = {['name'] = 'plush_07a', ['label'] = 'Plush Toy 07', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_07a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},
['plush_08a'] = {['name'] = 'plush_08a', ['label'] = 'Plush Toy 08', ['weight'] = 100, ['type'] = 'item', ['image'] = 'plush_08a.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true},

```

</details>

<details>

<summary>ESX Inventory</summary>

```lua
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
  ('cc_bubbletea', 'Bubble Tea', 1),
  ('cc_chocolatemilkshake', 'Chocolate MilkShake', 1),
  ('cc_strawberrysmoothie', 'Strawberry Smoothie', 1),
  ('cc_berryblastsmoothie', 'BerryBlast Smoothie', 1),
  ('cc_tropicalparadisesmoothie', 'Tropical Paradise Smoothie', 1),
  ('cc_fukuoka_hakata_ramen', 'Fukuoka Hakata Ramen', 1),
  ('cc_miso_ramen', 'Miso Ramen', 1),
  ('cc_osaka_shio_ramen', 'Osaka Shio Ramen', 1),
  ('cc_tonkotsu_ramen', 'Tonkotsu Ramen', 1),
  ('cc_iekei_ramen', 'Iekei Ramen', 1),
  ('cc_black_garlic_ramen', 'Black Garlic Ramen', 1),
  ('cc_shoyu_ramen', 'Shoyu Ramen', 1),
  ('cc_nagoya_taiwan_ramen','Nagoya Taiwan Ramen',1),
  ('cc_espresso', 'Espresso', 1),
  ('cc_cappuccino', 'Cappuccino', 1),
  ('cc_latte', 'Latte', 1),
  ('cc_mocha', 'Mocha', 1),
  ('cc_hotchocolate', 'Hot Chocolate', 1),
  ('cc_vanilla_icecream', 'Vanilla Icecream', 1),
  ('cc_chocolate_icecream', 'Chocolate Icecream', 1),
  ('cc_strawberry_icecream', 'Strawberry Icecream', 1),
  ('cc_mintchoco_icecream', 'Mintchoco Icecream', 1),
  ('cc_coffee_icecream', 'Coffee Icecream', 1),
  ('cc_classic_blt_sandwich', 'Classic Blt Sandwich', 1),
  ('cc_cheese_sandwich', 'Cheese Sandwich', 1),
  ('cc_turkey_sandwich', 'Turkey Sandwich', 1),
  ('cc_caprese_sandwich', 'Caprese Sandwich', 1),
  ('cc_avocado_sandwich', 'Avocado Sandwich', 1),
  ('cc_miso_broth', 'Miso Broth', 1),
  ('cc_cocao_powder', 'Cocoa Powder',1),
  ('cc_black_tapioca_pearls', 'Black Tapioca Pearls', 1),
  ('cc_brewed_black_tea', 'Brewed Black Tea', 1),
  ('cc_milk', 'Milk', 1),
  ('cc_chocolate_syrup', 'Chocolate Syrup', 1),
  ('cc_strawberries', 'Strawberries', 1),
  ('cc_ripebanana', 'Ripe Banana', 1),
  ('cc_yogurtcup', 'Yogurt Cup', 1),
  ('cc_cuporangejuice', 'Cup of Orange Juice', 1),
  ('cc_mixedberries', 'Mixed Berries', 1),
  ('cc_pineapple_chunks', 'Pineapple Chunks', 1),
  ('cc_mango_chunks', 'Mango Chunks', 1),
  ('cc_coconut_milk', 'Coconut Milk', 1),
  ('cc_pure_vanilla', 'Pure Vanilla', 1),
  ('cc_heavy_cream', 'Heavy Cream', 1),
  ('cc_chocolate_chips', 'Chocolate Chips', 1),
  ('cc_coffee_powder', 'Coffee Powder', 1),
  ('cc_chocolate_cookies', 'Chocolate Cookies', 1),
  ('cc_wheat_noodles', 'Wheat Noodles', 1),
  ('cc_green_onions', 'Green Onions', 1),
  ('cc_chashu_pork', 'Chashu Pork', 1),
  ('cc_butter', 'Butter', 1),
  ('cc_spinach', 'Spinach', 1),
  ('cc_soft_boiled_egg', 'Soft Boiled Egg', 1),
  ('cc_sugar', 'Sugar', 1),
  ('cc_bacon_strips', 'Bacon Strips', 1),
  ('cc_slices_of_bread', 'Slices of Bread', 1),
  ('cc_lettuce', 'Lettuce', 1),
  ('cc_cheddar_cheese', 'Cheddar Cheese', 1),
  ('cc_turkey_slices', 'Turkey Slices', 1),
  ('cc_mozzarella_cheese', 'Mozzarella Cheese', 1),
  ('cc_avocado', 'Avocado', 1),
  ('cc_icecubes', 'Ice Cubes', 1),
  ('cc_emptycup', 'Empty Cup', 1),
  ('cc_waterbottle', 'Water Bottle', 1),
  --toys
  ('plush_01a', 'Plush Toy 01', 1),
  ('plush_02a', 'Plush Toy 02', 1),
  ('plush_03a', 'Plush Toy 03', 1),
  ('plush_04a', 'Plush Toy 04', 1),
  ('plush_05a', 'Plush Toy 05', 1),
  ('plush_06a', 'Plush Toy 06', 1),
  ('plush_07a', 'Plush Toy 07', 1),
  ('plush_08a', 'Plush Toy 08', 1);
  
```

</details>

### For QBCore/Qbox Only

{% tabs %}
{% tab title="jobs.lua" %}
Add the Following in qb-core/shared/jobs.lua

```lua
['uwu'] = {
    label = 'Uwu Cafe',
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

#### Added in Qbox->shared->jobs.lua

```lua
['uwu'] = {
    label = 'Uwu Cafe',
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

<summary>QB Smallresource</summary>

```lua

--If using old qb-smallresources
Config.ConsumablesDrink = {
    ['cc_bubbletea'] = math.random(35, 54),
    ['cc_chocolatemilkshake'] = math.random(35, 54),
    ['cc_strawberrysmoothie'] = math.random(35, 54),
    ['cc_berryblastsmoothie'] = math.random(35, 54),
    ['cc_tropicalparadisesmoothie'] = math.random(35, 54),
    ['cc_espresso'] = math.random(35, 54),
    ['cc_cappuccino'] = math.random(35, 54),
    ['cc_latte'] = math.random(35, 54),
    ['cc_mocha'] = math.random(35, 54),
    ['cc_hotchocolate'] = math.random(35, 54),
}

Config.ConsumablesEat = {
    ['cc_fukuoka_hakata_ramen'] = math.random(35, 54),
    ['cc_miso_ramen'] = math.random(35, 54),
    ['cc_nagoya_taiwan_ramen'] = math.random(35, 54),
    ['cc_osaka_shio_ramen'] = math.random(35, 54),
    ['cc_shoyu_ramen'] = math.random(35, 54),
    ['cc_tonkotsu_ramen'] = math.random(35, 54),
    ['cc_iekei_ramen'] = math.random(35, 54),
    ['cc_black_garlic_ramen'] = math.random(35, 54),

    ['cc_vanilla_icecream'] = math.random(35, 54),
    ['cc_chocolate_icecream'] = math.random(35, 54),
    ['cc_strawberry_icecream'] = math.random(35, 54),
    ['cc_mintchoco_icecream'] = math.random(35, 54),
    ['cc_coffee_icecream'] = math.random(35, 54),

    ['cc_classic_blt_sandwich'] = math.random(35, 54),
    ['cc_cheese_sandwich'] = math.random(35, 54),
    ['cc_turkey_sandwich'] = math.random(35, 54),
    ['cc_caprese_sandwich'] = math.random(35, 54),
    ['cc_avocado_sandwich'] = math.random(35, 54),
}

--If using new qb-smallresources
Config.Consumables = {
    eat = {
        ['cc_fukuoka_hakata_ramen'] = math.random(35, 54),
        ['cc_miso_ramen'] = math.random(35, 54),
        ['cc_nagoya_taiwan_ramen'] = math.random(35, 54),
        ['cc_osaka_shio_ramen'] = math.random(35, 54),
        ['cc_shoyu_ramen'] = math.random(35, 54),
        ['cc_tonkotsu_ramen'] = math.random(35, 54),
        ['cc_iekei_ramen'] = math.random(35, 54),
        ['cc_black_garlic_ramen'] = math.random(35, 54),

        ['cc_vanilla_icecream'] = math.random(35, 54),
        ['cc_chocolate_icecream'] = math.random(35, 54),
        ['cc_strawberry_icecream'] = math.random(35, 54),
        ['cc_mintchoco_icecream'] = math.random(35, 54),
        ['cc_coffee_icecream'] = math.random(35, 54),

        ['cc_classic_blt_sandwich'] = math.random(35, 54),
        ['cc_cheese_sandwich'] = math.random(35, 54),
        ['cc_turkey_sandwich'] = math.random(35, 54),
        ['cc_caprese_sandwich'] = math.random(35, 54),
        ['cc_avocado_sandwich'] = math.random(35, 54),
    },
    drink = {
        ['cc_bubbletea'] = math.random(35, 54),
        ['cc_chocolatemilkshake'] = math.random(35, 54),
        ['cc_strawberrysmoothie'] = math.random(35, 54),
        ['cc_berryblastsmoothie'] = math.random(35, 54),
        ['cc_tropicalparadisesmoothie'] = math.random(35, 54),

        ['cc_espresso'] = math.random(35, 54),
        ['cc_cappuccino'] = math.random(35, 54),
        ['cc_latte'] = math.random(35, 54),
        ['cc_mocha'] = math.random(35, 54),
        ['cc_hotchocolate'] = math.random(35, 54),
    },
}

```

</details>

<details>

<summary>Jim Consumables</summary>

```lua
--jim-consumables/shared/consumables.lua

cc_fukuoka_hakata_ramen = { emote = "uwuramen", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
cc_miso_ramen = { emote = "uwuramen", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
cc_nagoya_taiwan_ramen = { emote = "uwuramen", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
cc_osaka_shio_ramen = { emote = "uwuramen", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
cc_shoyu_ramen = { emote = "uwuramen", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
cc_tonkotsu_ramen = { emote = "uwuramen", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
cc_iekei_ramen = { emote = "uwuramen", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
cc_black_garlic_ramen = { emote = "uwuramen", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},

cc_vanilla_icecream = {emote = "sandwich", 	canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "food", stats = { hunger = math.random(10,20), }},
cc_chocolate_icecream = {emote = "sandwich", 	canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "food", stats = { hunger = math.random(10,20), }},
cc_strawberry_icecream = {emote = "sandwich", 	canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "food", stats = { hunger = math.random(10,20), }},
cc_mintchoco_icecream = {emote = "sandwich", 	canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "food", stats = { hunger = math.random(10,20), }},
cc_coffee_icecream = {emote = "sandwich", 	canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "food", stats = { hunger = math.random(10,20), }},

cc_classic_blt_sandwich = {emote = "sandwich", 	canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "food", stats = { hunger = math.random(10,20), }},
cc_cheese_sandwich = {emote = "sandwich", 	canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "food", stats = { hunger = math.random(10,20), }},
cc_turkey_sandwich = {emote = "sandwich", 	canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "food", stats = { hunger = math.random(10,20), }},
cc_caprese_sandwich = {emote = "sandwich", 	canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "food", stats = { hunger = math.random(10,20), }},
cc_avocado_sandwich = {emote = "sandwich", 	canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "food", stats = { hunger = math.random(10,20), }},

cc_bubbletea = {emote = "uwudrink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
cc_chocolatemilkshake = {emote = "uwudrink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
cc_strawberrysmoothie = {emote = "uwudrink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
cc_berryblastsmoothie = {emote = "uwudrink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
cc_tropicalparadisesmoothie = {emote = "uwudrink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},

cc_espresso = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
cc_cappuccino = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
cc_latte = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
cc_mocha = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
cc_hotchocolate = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},

--jim-consumables/shared/emotes.lua
uwudrink = {"amb@world_human_drinking@coffee@male@idle_a", "idle_c", "Drink", AnimationOptions ={ Prop = "prop_cs_paper_cup", PropBone = 28422, PropPlacement = {0.0, 0.0, 0.0, 0.0, 0.0, 0.0},EmoteMoving = true, EmoteLoop = true, }},
uwuramen = {"anim@scripted@island@special_peds@pavel@hs4_pavel_ig5_caviar_p1", "base_idle", "Ramen", AnimationOptions ={ Prop = "prop_cs_bowl_01b", PropBone = 60309, PropPlacement = {0.0, 0.0300, 0.0100, 0.0, 0.0, 0.0},EmoteMoving = true, EmoteLoop = true, }},

```

</details>

### Add Images to Inventory

Copy all the Images folder and paste it in your inventory Images folder

### Log Webook Setup - Optional

To enable discord logs make sure to add your webhook in the server->Log.lua File

{% embed url="https://www.youtube.com/watch?pp=ygULI2FwcHlxczIwMjM=&v=fKksxz2Gdnc" %}

### Optional Custom Props

**If you’ve purchased either of the following prop packs:**

* **DJ Burgershot Props** → [https://djscollections.com/package/6098332](https://djscollections.com/package/6098332)
* **Bzzz Burgershot Pack** → [https://bzzz.tebex.io/package/6271356](https://bzzz.tebex.io/package/6271356)

Simply install the pack and enable it by setting the corresponding config flag:

* `Config.UseDjItems = true` _for DJ's pack_
* `Config.UseBzzzItems = true` _for Bzzz's pac_

### Video of Installation

{% embed url="https://www.youtube.com/watch?v=ahXuBfC6jmQ" %}





