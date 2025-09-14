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
CREATE TABLE IF NOT EXISTS `pl_koi` (
  `stock` longtext DEFAULT NULL,
  `state` varchar(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;
        
INSERT INTO `addon_account` (name, label, shared) VALUES
      ('society_koi', 'koi', 1);

INSERT INTO `datastore` (name, label, shared) VALUES
      ('society_koi', 'koi', 1);

INSERT INTO `jobs` (name, label,whitelisted) VALUES
        ('koi', 'koi',1);

INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
        ('koi',0,'cashier','Cashier',20,'{}','{}'),
        ('koi',1,'cook','Cook',40,'{}','{}'),
        ('koi',2,'staff','Staff',60,'{}','{}'),
        ('koi',3,'manager','Manager',85,'{}','{}'),
        ('koi',4,'boss','Owner',100,'{}','{}');
```

</details>

<details>

<summary>QBCore or Qbox</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_koi` (
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
["koi_grilled_salmon"] = {
    label = "Koi Grilled Salmon",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_lobster_tail"] = {
    label = "Koi Lobster Tail",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_shrimp_scampi"] = {
    label = "Koi Shrimp Scampi",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_seared_scallops"] = {
    label = "Koi Seared Scallops",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_crab_cakes"] = {
    label = "Koi Crab Cakes",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_mojito"] = {
    label = "Koi Mojito",
    weight = 1,
    stack = true,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},
["koi_pina_colada"] = {
    label = "Koi Pina Colada",
    weight = 1,
    stack = true,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},
["koi_margarita"] = {
    label = "Koi Margarita",
    weight = 1,
    stack = true,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},
["koi_espresso_martini"] = {
    label = "Koi Espresso Martini",
    weight = 1,
    stack = true,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},
["koi_arnold_palmer"] = {
    label = "Koi Arnold Palmer",
    weight = 1,
    stack = true,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		}
},
["koi_ribeye_steak"] = {
    label = "Koi Ribeye Steak",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_filet_mignon"] = {
    label = "Koi Filet Mignon",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_t_bone_steak"] = {
    label = "Koi T-Bone Steak",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_tomahawk_steak"] = {
    label = "Koi Tomahawk Steak",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_new_york_strip"] = {
    label = "Koi New York Strip",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_tiramisu"] = {
    label = "Koi Tiramisu",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_cheesecake"] = {
    label = "Koi Cheesecake",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_chocolate_lava_cake"] = {
    label = "Koi Chocolate Lava Cake",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_creme_brulee"] = {
    label = "Koi Crème Brulee",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_key_lime_pie"] = {
    label = "Koi Key Lime Pie",
    weight = 1,
    stack = true,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious food'
		},
},
["koi_salt"] = {
    label = "Salt",
    weight = 1,
    stack = true,
    close = true,
},
["koi_dill_butter"] = {
    label = "Dill Butter",
    weight = 1,
    stack = true,
    close = true,
},
["koi_clarified_butter"] = {
    label = "Clarified Butter",
    weight = 1,
    stack = true,
    close = true,
},
["koi_white_wine"] = {
    label = "White Wine",
    weight = 1,
    stack = true,
    close = true,
},
["koi_truffle_oil"] = {
    label = "Truffle Oil",
    weight = 1,
    stack = true,
    close = true,
},
["koi_old_bay_seasoning"] = {
    label = "Old Bay Seasoning",
    weight = 1,
    stack = true,
    close = true,
},
["koi_sugar"] = {
    label = "Sugar",
    weight = 1,
    stack = true,
    close = true,
},
["koi_fresh_mint_leaves"] = {
    label = "Fresh Mint Leaves",
    weight = 1,
    stack = true,
    close = true,
},
["koi_coconut_cream"] = {
    label = "Coconut Cream",
    weight = 1,
    stack = true,
    close = true,
},
["koi_triple_sec"] = {
    label = "Triple Sec",
    weight = 1,
    stack = true,
    close = true,
},
["koi_coffee_liquor_kahlua"] = {
    label = "Coffee Liquor Kahlua",
    weight = 1,
    stack = true,
    close = true,
},
["koi_fresh_lemonade"] = {
    label = "Fresh Lamonade",
    weight = 1,
    stack = true,
    close = true,
},
["koi_black_pepper"] = {
    label = "Black Pepper",
    weight = 1,
    stack = true,
    close = true,
},
["koi_herb_butter"] = {
    label = "Herb Butter",
    weight = 1,
    stack = true,
    close = true,
},
["koi_bearnaise_sauce"] = {
    label = "Béarnaise Sauce",
    weight = 1,
    stack = true,
    close = true,
},
["koi_steakhouse_dry_rub"] = {
    label = "Steakhouse Dry Rub",
    weight = 1,
    stack = true,
    close = true,
},
["koi_smoked_sea_salt"] = {
    label = "Smoked Sea Salt",
    weight = 1,
    stack = true,
    close = true,
},
["koi_red_wine_reduction"] = {
    label = "Red Wine Reduction",
    weight = 1,
    stack = true,
    close = true,
},
["koi_flour"] = {
    label = "Flour",
    weight = 1,
    stack = true,
    close = true,
},
["koi_mascarpone_cheese"] = {
    label = "Mascarpone Cheese",
    weight = 1,
    stack = true,
    close = true,
},
["koi_graham_cracker_crust"] = {
    label = "Graham Cracker Crust",
    weight = 1,
    stack = true,
    close = true,
},
["koi_molten_ganache_filling"] = {
    label = "Molten Ganache Filling",
    weight = 1,
    stack = true,
    close = true,
},
["koi_caramelized_sugar_topping"] = {
    label = "Caramelized Sugar Topping",
    weight = 1,
    stack = true,
    close = true,
},
["koi_key_lime_juice"] = {
    label = "Key Lime Juice",
    weight = 1,
    stack = true,
    close = true,
},
["koi_icecubes"] = {
    label = "Koi IceCubes",
    weight = 1,
    stack = true,
    close = true,
},
["koi_waterbottle"] = {
    label = "Koi WaterBottle",
    weight = 1,
    stack = true,
    close = true,
},
["koi_emptycup"] = {
    label = "Koi Empty Cup",
    weight = 1,
    stack = true,
    close = true,
},
```

</details>

<details>

<summary>QB Inventory</summary>

```lua
['koi_grilled_salmon'] = {['name'] = 'koi_grilled_salmon', ['label'] = 'Koi Grilled Salmon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_grilled_salmon.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_lobster_tail'] = {['name'] = 'koi_lobster_tail', ['label'] = 'Koi Lobster Tail', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_lobster_tail.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_shrimp_scampi'] = {['name'] = 'koi_shrimp_scampi', ['label'] = 'Koi Shrimp Scampi', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_shrimp_scampi.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_seared_scallops'] = {['name'] = 'koi_seared_scallops', ['label'] = 'Koi Seared Scallops', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_seared_scallops.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_crab_cakes'] = {['name'] = 'koi_crab_cakes', ['label'] = 'Koi Crab Cakes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_crab_cakes.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_mojito'] = {['name'] = 'koi_mojito', ['label'] = 'Koi Mojito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_mojito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_pina_colada'] = {['name'] = 'koi_pina_colada', ['label'] = 'Koi Pina Colada', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_pina_colada.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_margarita'] = {['name'] = 'koi_margarita', ['label'] = 'Koi Margarita', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_margarita.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_espresso_martini'] = {['name'] = 'koi_espresso_martini', ['label'] = 'Koi Espresso Martini', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_espresso_martini.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_arnold_palmer'] = {['name'] = 'koi_arnold_palmer', ['label'] = 'Koi Arnold Palmer', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_arnold_palmer.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_ribeye_steak'] = {['name'] = 'koi_ribeye_steak', ['label'] = 'Koi Ribeye Steak', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_ribeye_steak.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_filet_mignon'] = {['name'] = 'koi_filet_mignon', ['label'] = 'Koi Filet Mignon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_filet_mignon.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_t_bone_steak'] = {['name'] = 'koi_t_bone_steak', ['label'] = 'Koi T-Bone Steak', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_t_bone_steak.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_tomahawk_steak'] = {['name'] = 'koi_tomahawk_steak', ['label'] = 'Koi Tomahawk Steak', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_tomahawk_steak.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_new_york_strip'] = {['name'] = 'koi_new_york_strip', ['label'] = 'Koi New York Strip', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_new_york_strip.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_tiramisu'] = {['name'] = 'koi_tiramisu', ['label'] = 'Koi Tiramisu', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_tiramisu.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_cheesecake'] = {['name'] = 'koi_cheesecake', ['label'] = 'Koi Cheesecake', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_cheesecake.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_chocolate_lava_cake'] = {['name'] = 'koi_chocolate_lava_cake', ['label'] = 'Koi Chocolate Lava Cake', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_chocolate_lava_cake.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_creme_brulee'] = {['name'] = 'koi_creme_brulee', ['label'] = 'Koi Creme Brulee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_creme_brulee.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_key_lime_pie'] = {['name'] = 'koi_key_lime_pie', ['label'] = 'Koi Key Lime Pie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_key_lime_pie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_salt'] = {['name'] = 'koi_salt', ['label'] = 'Salt', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_salt.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_dill_butter'] = {['name'] = 'koi_dill_butter', ['label'] = 'Dill Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_dill_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_clarified_butter'] = {['name'] = 'koi_clarified_butter', ['label'] = 'Clarified Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_clarified_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_white_wine'] = {['name'] = 'koi_white_wine', ['label'] = 'White Wine', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_white_wine.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_truffle_oil'] = {['name'] = 'koi_truffle_oil', ['label'] = 'Truffle Oil', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_truffle_oil.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_old_bay_seasoning'] = {['name'] = 'koi_old_bay_seasoning', ['label'] = 'Old Bay Seasoning', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_old_bay_seasoning.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_sugar'] = {['name'] = 'koi_sugar', ['label'] = 'Sugar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_sugar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_fresh_mint_leaves'] = {['name'] = 'koi_fresh_mint_leaves', ['label'] = 'Fresh Mint Leaves', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_fresh_mint_leaves.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_coconut_cream'] = {['name'] = 'koi_coconut_cream', ['label'] = 'Coconut Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_coconut_cream.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_triple_sec'] = {['name'] = 'koi_triple_sec', ['label'] = 'Triple Sec', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_triple_sec.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_coffee_liquor_kahlua'] = {['name'] = 'koi_coffee_liquor_kahlua', ['label'] = 'Coffee Liquor Kahlua', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_coffee_liquor_kahlua.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_fresh_lemonade'] = {['name'] = 'koi_fresh_lemonade', ['label'] = 'Fresh Lamonade', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_fresh_lemonade.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_black_pepper'] = {['name'] = 'koi_black_pepper', ['label'] = 'Black Pepper', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_black_pepper.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_herb_butter'] = {['name'] = 'koi_herb_butter', ['label'] = 'Herb Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_herb_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_bearnaise_sauce'] = {['name'] = 'koi_bearnaise_sauce', ['label'] = 'Bearnaise Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_bearnaise_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_steakhouse_dry_rub'] = {['name'] = 'koi_steakhouse_dry_rub', ['label'] = 'Steakhouse Dry Rub', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_steakhouse_dry_rub.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_smoked_sea_salt'] = {['name'] = 'koi_smoked_sea_salt', ['label'] = 'Smoked Sea Salt', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_smoked_sea_salt.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_red_wine_reduction'] = {['name'] = 'koi_red_wine_reduction', ['label'] = 'Red Wine Reduction', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_red_wine_reduction.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_flour'] = {['name'] = 'koi_flour', ['label'] = 'Flour', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_flour.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_mascarpone_cheese'] = {['name'] = 'koi_mascarpone_cheese', ['label'] = 'Mascarpone Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_mascarpone_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_graham_cracker_crust'] = {['name'] = 'koi_graham_cracker_crust', ['label'] = 'Graham Cracker Crust', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_graham_cracker_crust.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_molten_ganache_filling'] = {['name'] = 'koi_molten_ganache_filling', ['label'] = 'Molten Ganache Filling', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_molten_ganache_filling.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_caramelized_sugar_topping'] = {['name'] = 'koi_caramelized_sugar_topping', ['label'] = 'Caramelized Sugar Topping', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_caramelized_sugar_topping.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_key_lime_juice'] = {['name'] = 'koi_key_lime_juice', ['label'] = 'Key Lime Juice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_key_lime_juice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_icecubes'] = {['name'] = 'koi_icecubes', ['label'] = 'Koi IceCubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_waterbottle'] = {['name'] = 'koi_waterbottle', ['label'] = 'Koi WaterBottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_emptycup'] = {['name'] = 'koi_emptycup', ['label'] = 'Koi Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>Quasar Inventory</summary>

```lua
['koi_grilled_salmon'] = {['name'] = 'koi_grilled_salmon', ['label'] = 'Koi Grilled Salmon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_grilled_salmon.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_lobster_tail'] = {['name'] = 'koi_lobster_tail', ['label'] = 'Koi Lobster Tail', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_lobster_tail.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_shrimp_scampi'] = {['name'] = 'koi_shrimp_scampi', ['label'] = 'Koi Shrimp Scampi', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_shrimp_scampi.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_seared_scallops'] = {['name'] = 'koi_seared_scallops', ['label'] = 'Koi Seared Scallops', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_seared_scallops.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_crab_cakes'] = {['name'] = 'koi_crab_cakes', ['label'] = 'Koi Crab Cakes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_crab_cakes.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_mojito'] = {['name'] = 'koi_mojito', ['label'] = 'Koi Mojito', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_mojito.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_pina_colada'] = {['name'] = 'koi_pina_colada', ['label'] = 'Koi Pina Colada', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_pina_colada.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_margarita'] = {['name'] = 'koi_margarita', ['label'] = 'Koi Margarita', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_margarita.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_espresso_martini'] = {['name'] = 'koi_espresso_martini', ['label'] = 'Koi Espresso Martini', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_espresso_martini.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_arnold_palmer'] = {['name'] = 'koi_arnold_palmer', ['label'] = 'Koi Arnold Palmer', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_arnold_palmer.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_ribeye_steak'] = {['name'] = 'koi_ribeye_steak', ['label'] = 'Koi Ribeye Steak', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_ribeye_steak.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_filet_mignon'] = {['name'] = 'koi_filet_mignon', ['label'] = 'Koi Filet Mignon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_filet_mignon.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_t_bone_steak'] = {['name'] = 'koi_t_bone_steak', ['label'] = 'Koi T-Bone Steak', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_t_bone_steak.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_tomahawk_steak'] = {['name'] = 'koi_tomahawk_steak', ['label'] = 'Koi Tomahawk Steak', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_tomahawk_steak.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_new_york_strip'] = {['name'] = 'koi_new_york_strip', ['label'] = 'Koi New York Strip', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_new_york_strip.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_tiramisu'] = {['name'] = 'koi_tiramisu', ['label'] = 'Koi Tiramisu', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_tiramisu.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_cheesecake'] = {['name'] = 'koi_cheesecake', ['label'] = 'Koi Cheesecake', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_cheesecake.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_chocolate_lava_cake'] = {['name'] = 'koi_chocolate_lava_cake', ['label'] = 'Koi Chocolate Lava Cake', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_chocolate_lava_cake.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_creme_brulee'] = {['name'] = 'koi_creme_brulee', ['label'] = 'Koi Creme Brulee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_creme_brulee.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_key_lime_pie'] = {['name'] = 'koi_key_lime_pie', ['label'] = 'Koi Key Lime Pie', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_key_lime_pie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_salt'] = {['name'] = 'koi_salt', ['label'] = 'Salt', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_salt.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_dill_butter'] = {['name'] = 'koi_dill_butter', ['label'] = 'Dill Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_dill_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_clarified_butter'] = {['name'] = 'koi_clarified_butter', ['label'] = 'Clarified Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_clarified_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_white_wine'] = {['name'] = 'koi_white_wine', ['label'] = 'White Wine', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_white_wine.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_truffle_oil'] = {['name'] = 'koi_truffle_oil', ['label'] = 'Truffle Oil', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_truffle_oil.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_old_bay_seasoning'] = {['name'] = 'koi_old_bay_seasoning', ['label'] = 'Old Bay Seasoning', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_old_bay_seasoning.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_sugar'] = {['name'] = 'koi_sugar', ['label'] = 'Sugar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_sugar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_fresh_mint_leaves'] = {['name'] = 'koi_fresh_mint_leaves', ['label'] = 'Fresh Mint Leaves', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_fresh_mint_leaves.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_coconut_cream'] = {['name'] = 'koi_coconut_cream', ['label'] = 'Coconut Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_coconut_cream.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_triple_sec'] = {['name'] = 'koi_triple_sec', ['label'] = 'Triple Sec', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_triple_sec.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_coffee_liquor_kahlua'] = {['name'] = 'koi_coffee_liquor_kahlua', ['label'] = 'Coffee Liquor Kahlua', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_coffee_liquor_kahlua.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_fresh_lemonade'] = {['name'] = 'koi_fresh_lemonade', ['label'] = 'Fresh Lamonade', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_fresh_lemonade.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_black_pepper'] = {['name'] = 'koi_black_pepper', ['label'] = 'Black Pepper', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_black_pepper.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_herb_butter'] = {['name'] = 'koi_herb_butter', ['label'] = 'Herb Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_herb_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_bearnaise_sauce'] = {['name'] = 'koi_bearnaise_sauce', ['label'] = 'Bearnaise Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_bearnaise_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_steakhouse_dry_rub'] = {['name'] = 'koi_steakhouse_dry_rub', ['label'] = 'Steakhouse Dry Rub', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_steakhouse_dry_rub.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_smoked_sea_salt'] = {['name'] = 'koi_smoked_sea_salt', ['label'] = 'Smoked Sea Salt', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_smoked_sea_salt.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_red_wine_reduction'] = {['name'] = 'koi_red_wine_reduction', ['label'] = 'Red Wine Reduction', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_red_wine_reduction.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_flour'] = {['name'] = 'koi_flour', ['label'] = 'Flour', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_flour.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_mascarpone_cheese'] = {['name'] = 'koi_mascarpone_cheese', ['label'] = 'Mascarpone Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_mascarpone_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_graham_cracker_crust'] = {['name'] = 'koi_graham_cracker_crust', ['label'] = 'Graham Cracker Crust', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_graham_cracker_crust.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_molten_ganache_filling'] = {['name'] = 'koi_molten_ganache_filling', ['label'] = 'Molten Ganache Filling', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_molten_ganache_filling.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_caramelized_sugar_topping'] = {['name'] = 'koi_caramelized_sugar_topping', ['label'] = 'Caramelized Sugar Topping', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_caramelized_sugar_topping.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_key_lime_juice'] = {['name'] = 'koi_key_lime_juice', ['label'] = 'Key Lime Juice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_key_lime_juice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_icecubes'] = {['name'] = 'koi_icecubes', ['label'] = 'Koi IceCubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_waterbottle'] = {['name'] = 'koi_waterbottle', ['label'] = 'Koi WaterBottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['koi_emptycup'] = {['name'] = 'koi_emptycup', ['label'] = 'Koi Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'koi_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>ESX ITems Sql</summary>

```lua
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
	('koi_grilled_salmon', 'Koi Grilled Salmon', 1),
	('koi_lobster_tail', 'Koi Lobster Tail', 1),
	('koi_shrimp_scampi', 'Koi Shrimp Scampi', 1),
	('koi_seared_scallops', 'Koi Seared Scallops', 1),
	('koi_crab_cakes', 'Koi Crab Cakes', 1),
	('koi_mojito', 'Koi Mojito', 1),
	('koi_pina_colada', 'Koi Piña Colada', 1),
	('koi_margarita', 'Koi Margarita', 1),
	('koi_espresso_martini', 'Koi Espresso Martini', 1),
	('koi_arnold_palmer', 'Koi Arnold Palmer', 1),
	('koi_ribeye_steak', 'Koi Ribeye Steak', 1),
	('koi_filet_mignon', 'Koi Filet Mignon', 1),
	('koi_t_bone_steak', 'Koi T-Bone Steak', 1),
	('koi_tomahawk_steak', 'Koi Tomahawk Steak', 1),
	('koi_new_york_strip', 'Koi New York Strip', 1),
	('koi_tiramisu', 'Koi Tiramisu', 1),
	('koi_cheesecake', 'Koi Cheesecake', 1),
	('koi_chocolate_lava_cake', 'Koi Chocolate Lava Cake', 1),
	('koi_creme_brulee', 'Koi Creme Brulee', 1),
	('koi_key_lime_pie', 'Koi Key Lime Pie', 1),
	('koi_salt', 'Salt', 1),
	('koi_dill_butter', 'Dill Butter', 1),
	('koi_clarified_butter', 'Clarified Butter', 1),
	('koi_white_wine', 'White Wine', 1),
	('koi_truffle_oil', 'Truffle Oil', 1),
	('koi_old_bay_seasoning', 'Old Bay Seasoning', 1),
	('koi_sugar', 'Sugar', 1),
	('koi_fresh_mint_leaves', 'Fresh Mint Leaves', 1),
	('koi_coconut_cream', 'Coconut Cream', 1),
	('koi_triple_sec', 'Triple Sec', 1),
	('koi_coffee_liquor_kahlua', 'Coffee Liquor Kahlua', 1),
	('koi_fresh_lemonade', 'Fresh Lamonade', 1),
	('koi_black_pepper', 'Black Pepper', 1),
	('koi_herb_butter', 'Herb Butter', 1),
	('koi_bearnaise_sauce', 'Béarnaise Sauce', 1),
	('koi_steakhouse_dry_rub', 'Steakhouse Dry Rub', 1),
	('koi_smoked_sea_salt', 'Smoked Sea Salt', 1),
	('koi_red_wine_reduction', 'Red Wine Reduction', 1),
	('koi_flour', 'Flour', 1),
	('koi_mascarpone_cheese', 'Mascarpone Cheese', 1),
	('koi_graham_cracker_crust', 'Graham Cracker Crust', 1),
	('koi_molten_ganache_filling', 'Molten Ganache Filling', 1),
	('koi_caramelized_sugar_topping', 'Caramelized Sugar Topping', 1),
	('koi_icecubes', 'Koi Ice Cubes', 1),
	('koi_waterbottle', 'Koi Water bottle', 1),
	('koi_emptycup', 'Koi Empty Cup', 1),
	('koi_key_lime_juice', 'Key Lime Juice', 1);
```

</details>

### For QBCore Only

{% tabs %}
{% tab title="jobs.lua" %}
Add the Following in qb-core/shared/jobs.lua

```lua
['koi'] = {
    label = 'Koi',
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
['koi'] = {
    label = 'Koi',
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
    ['koi_mojito'] = math.random(35, 54),
    ['koi_pina_colada'] = math.random(35, 54),
    ['koi_margarita'] = math.random(35, 54),
    ['koi_espresso_martini'] = math.random(35, 54),
    ['koi_arnold_palmer'] = math.random(35, 54),
}

Config.ConsumablesEat = {
    ['koi_grilled_salmon'] = math.random(35, 54),
    ['koi_lobster_tail'] = math.random(35, 54),
    ['koi_shrimp_scampi'] = math.random(35, 54),
    ['koi_seared_scallops'] = math.random(35, 54),
    ['koi_crab_cakes'] = math.random(35, 54),
    ['koi_ribeye_steak'] = math.random(35, 54),
    ['koi_filet_mignon'] = math.random(35, 54),
    ['koi_t_bone_steak'] = math.random(35, 54),
    ['koi_tomahawk_steak'] = math.random(35, 54),
    ['koi_new_york_strip'] = math.random(35, 54),
    ['koi_tiramisu'] = math.random(35, 54),
    ['koi_cheesecake'] = math.random(35, 54),
    ['koi_chocolate_lava_cake'] = math.random(35, 54),
    ['koi_creme_brulee'] = math.random(35, 54),
    ['koi_key_lime_pie'] = math.random(35, 54),
}

--If using new qb-smallresources
Config.Consumables = {
    eat = {
        ['koi_grilled_salmon'] = math.random(35, 54),
        ['koi_lobster_tail'] = math.random(35, 54),
        ['koi_shrimp_scampi'] = math.random(35, 54),
        ['koi_seared_scallops'] = math.random(35, 54),
        ['koi_crab_cakes'] = math.random(35, 54),
        ['koi_ribeye_steak'] = math.random(35, 54),
        ['koi_filet_mignon'] = math.random(35, 54),
        ['koi_t_bone_steak'] = math.random(35, 54),
        ['koi_tomahawk_steak'] = math.random(35, 54),
        ['koi_new_york_strip'] = math.random(35, 54),
        ['koi_tiramisu'] = math.random(35, 54),
        ['koi_cheesecake'] = math.random(35, 54),
        ['koi_chocolate_lava_cake'] = math.random(35, 54),
        ['koi_creme_brulee'] = math.random(35, 54),
        ['koi_key_lime_pie'] = math.random(35, 54),
    },
    drink = {
        ['koi_mojito'] = math.random(35, 54),
        ['koi_pina_colada'] = math.random(35, 54),
        ['koi_margarita'] = math.random(35, 54),
        ['koi_espresso_martini'] = math.random(35, 54),
        ['koi_arnold_palmer'] = math.random(35, 54),
    },
}hooper_jr'] = math.random(35, 54),
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
koi_grilled_salmon = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_lobster_tail = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_shrimp_scampi = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_seared_scallops = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_crab_cakes = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_ribeye_steak = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_filet_mignon = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_t_bone_steak = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_tomahawk_steak = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_new_york_strip = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_tiramisu = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_cheesecake = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_chocolate_lava_cake = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_creme_brulee = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_key_lime_pie = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},

koi_mojito = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_pina_colada = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_margarita = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_espresso_martini = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
koi_arnold_palmer = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
```

</details>

### Add Images to Inventory

Copy all the Images folder and paste it in your inventory Images folder

### Log Webook Setup - Optional

To enable discord logs make sure to add your webhook in the server->Log.lua File

{% embed url="https://www.youtube.com/watch?pp=ygULI2FwcHlxczIwMjM=&v=fKksxz2Gdnc" %}

### Optional Dj Custom Props

If you have purchased the DJ Chinese Props [Click Here](https://djscollections.com/package/5764357)

&#x20;just install it and set the Config.UseDjItems = true

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
