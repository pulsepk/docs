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

Now execute this query into your server database using heidisql or phpmyadmin.

<details>

<summary>ESX</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_pizzathis` (
          `stock` longtext DEFAULT NULL,
          `state` varchar(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;

INSERT INTO `addon_account` (name, label, shared) VALUES
        ('society_pizzathis', 'Pizza This', 1);

INSERT INTO `datastore` (name, label, shared) VALUES
        ('society_pizzathis', 'Pizza This', 1);

 INSERT INTO `jobs` (name, label,whitelisted) VALUES
        ('pizzathis', 'Pizza This',1);

INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
        ('pizzathis',0,'cashier','Cashier',20,'{}','{}'),
        ('pizzathis',1,'cook','Cook',40,'{}','{}'),
        ('pizzathis',2,'staff','Staff',60,'{}','{}'),
        ('pizzathis',3,'manager','Manager',85,'{}','{}'),
        ('pizzathis',4,'boss','Owner',100,'{}','{}');
```

</details>

<details>

<summary>QBCore or Qbox</summary>

```etlua
CREATE TABLE IF NOT EXISTS `pl_pizzathis` (
   `stock` LONGTEXT DEFAULT NULL,
   `state` VARCHAR(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;
```

</details>

### Items

Add the items into your server

<details>

<summary>OX Inventory</summary>

```lua
["pt_margherita"] = {
	label = "Classic Margherita",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pizza'
	},
},
["pt_pepperoni"] = {
	label = "Pepperoni Feast",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pizza'
	},
},
["pt_bbq_chicken"] = {
	label = "BBq Chicken Pizza",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pizza'
	},
},
["pt_veggie"] = {
	label = "Veggie",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pizza'
	},
},
["pt_hawaiian"] = {
	label = "Hawaiian Paradise",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pizza'
	},
},
["pt_chicken"] = {
	label = "Meat Lovers Special",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pizza'
	},
},
["pt_four_cheese"] = {
	label = "Four Cheese Heaven",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pizza'
	},
},
["pt_sausage"] = {
	label = "Spicy Sausage Sizzle",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pizza'
	},
},
["pt_buffalo"] = {
	label = "Buffalo Chicken Ranch",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pizza'
	},
},
["pt_garlic_spinach"] = {
	label = "Garlic Spinach Alfredo",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pizza'
	},
},
["pt_dough"] = {
	label = "Pizza Base",
	weight = 1,
	stack = true,
	close = true,
},
["pt_basil_leaves"] = {
	label = "Basil Leaves",
	weight = 1,
	stack = true,
	close = true,
},
["pt_marinara_sauce"] = {
	label = "Spicy Marinara Sauce",
	weight = 1,
	stack = true,
	close = true,
},
["pt_bbq_sauce"] = {
	label = "Smoky BBQ Sauce",
	weight = 1,
	stack = true,
	close = true,
},
["pt_black_olives"] = {
	label = "Black Olives",
	weight = 1,
	stack = true,
	close = true,
},
["pt_pineapple_chunks"] = {
	label = "Pineapple Chunks",
	weight = 1,
	stack = true,
	close = true,
},
["pt_bacon_crumbles"] = {
	label = "Bacon Crumbles",
	weight = 1,
	stack = true,
	close = true,
},
["pt_gorgonzola_cheese"] = {
	label = "Gorgonzola Cheese",
	weight = 1,
	stack = true,
	close = true,
},
["pt_italian_suasage"] = {
	label = "Italian Sausage",
	weight = 1,
	stack = true,
	close = true,
},
["pt_ranch_sauce"] = {
	label = "Ranch Sauce",
	weight = 1,
	stack = true,
	close = true,
},
["pt_garlic_alfredo_sauce"] = {
	label = "Garlic Alfredo Sauce",
	weight = 1,
	stack = true,
	close = true,
},
["pt_garlic_knots"] = {
	label = "Garlic Knots",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Garlic Knot'
	},
},
["pt_mozzarella_sticks"] = {
	label = "Mozzarella Sticks",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Mozzarella Sticks'
	},
},

["pt_cheesy_breadsticks"] = {
	label = "Cheesy Breadsticks",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Cheesy Breadsticks'
	},
},
["pt_buffalo_wings"] = {
	label = "Buffalo Chicken Wings",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Wing'
	},
},
["pt_bruschetta_bites"] = {
	label = "Bruschetta Bites",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Bruschetta Bite'
	},
},
["pt_jalapeno_popper"] = {
	label = "Jalapeno Poppers",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Jalapeno Popper'
	},
},
["pt_calamari"] = {
	label = "Fried Calamari",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Fried Calamari'
	},
},
["pt_spinach_dip"] = {
	label = "Spinach & Artichoke Dip",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Spinach Dip'
	},
},
["pt_olive_oil"] = {
	label = "Olive Oil",
	weight = 1,
	stack = true,
	close = true,
},
["pt_crispy_bread"] = {
	label = "Crispy Bread",
	weight = 1,
	stack = true,
	close = true,
},
["pt_mozzarella"] = {
	label = "Melted Mozzarella",
	weight = 1,
	stack = true,
	close = true,
},
["pt_buffalo_sauce"] = {
	label = "Buffalo Sauce",
	weight = 1,
	stack = true,
	close = true,
},
["pt_basil"] = {
	label = "Fresh Basil",
	weight = 1,
	stack = true,
	close = true,
},
["pt_cream_cheese"] = {
	label = "Cream Cheese",
	weight = 1,
	stack = true,
	close = true,
},
["pt_lemon_aioli"] = {
	label = "Lemon Aioli",
	weight = 1,
	stack = true,
	close = true,
},
["pt_artichokes"] = {
	label = "Artichokes",
	weight = 1,
	stack = true,
	close = true,
},

["pt_caesar"] = {
	label = "Classic Caesar Salad",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Salad'
	},
},
["pt_greek_feta"] = {
	label = "Greek Feta Salad",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Salad'
	},
},
["pt_caprese"] = {
	label = "Caprese Salad",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Salad'
	},
},
["pt_chicken_caesar"] = {
	label = "Chicken Caesar Salad",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Salad'
	},
},
["pt_fresh_garden"] = {
	label = "Garden Fresh Salad",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Salad'
	},
},

["pt_mediterranean_quinoa"] = {
	label = "Mediterranean Quinoa Salad",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Salad'
	},
},
["pt_antipasto"] = {
	label = "Antipasto Salad",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Salad'
	},
},
["pt_spinach_bacon"] = {
	label = "Spinach & Bacon Salad",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Salad'
	},
},
["pt_vinegar"] = {
	label = "Vinegar",
	weight = 1,
	stack = true,
	close = true,
},
["pt_parmesan"] = {
	label = "Parmesan Shavings",
	weight = 1,
	stack = true,
	close = true,
},
["pt_kalamata_olives"] = {
	label = "Kalamata Olives",
	weight = 1,
	stack = true,
	close = true,
},
["pt_balsamic_glaze"] = {
	label = "Balsamic Glaze",
	weight = 1,
	stack = true,
	close = true,
},
["pt_garlic_croutons"] = {
	label = "Garlic Croutons",
	weight = 1,
	stack = true,
	close = true,
},
["pt_avocado_slice"] = {
	label = "Avocado Slices",
	weight = 1,
	stack = true,
	close = true,
},
["pt_crispy_bacon"] = {
	label = "Crispy Bacon Bits",
	weight = 1,
	stack = true,
	close = true,
},
["pt_quinoa"] = {
	label = "Quinoa",
	weight = 1,
	stack = true,
	close = true,
},
["pt_marinated_artichokes"] = {
	label = "Marinated Artichokes",
	weight = 1,
	stack = true,
	close = true,
},

["pt_alfredo"] = {
	label = "Creamy Alfredo Pasta",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pasta'
	},
},
["pt_spaghetti"] = {
	label = "Spaghetti Bolognese",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pasta'
	},
},
["pt_penne_arrabbiata"] = {
	label = "Penne Arrabbiata",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pasta'
	},
},
["pt_vegetable"] = {
	label = "Vegetable Primavera",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pasta'
	},
},
["pt_lasagna"] = {
	label = "Lasagna Classico",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pasta'
	},
},
["pt_shrimp_scampi"] = {
	label = "Shrimp Scampi Linguine",
	weight = 1,
	stack = true,
	close = true,
	client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a Pasta'
	},
},
["pt_garlic"] = {
	label = "Garlic",
	weight = 1,
	stack = true,
	close = true,
},

["pt_parmesan_cream_sauce"] = {
	label = "Parmesan Cream Sauce",
	weight = 1,
	stack = true,
	close = true,
},

["pt_beef"] = {
	label = "Beef",
	weight = 1,
	stack = true,
	close = true,
},

["pt_penne_pasta"] = {
	label = "Penne Pasta",
	weight = 1,
	stack = true,
	close = true,
},
["pt_basil_pesto_sauce"] = {
	label = "Basil Pesto Sauce",
	weight = 1,
	stack = true,
	close = true,
},
["pt_mozzarella_cream_sauce"] = {
	label = "Mozzarella-Infused Cream Sauce",
	weight = 1,
	stack = true,
	close = true,
},
["pt_lemon_zest"] = {
	label = "Lemon Zest",
	weight = 1,
	stack = true,
	close = true,
},
["pt_bechamel_sauce"] = {
	label = "Bechamel Sauce",
	weight = 1,
	stack = true,
	close = true,
},
["pt_garlic_butter"] = {
	label = "Garlic Butter Sauce",
	weight = 1,
	stack = true,
	close = true,
},

["pt_citraspark"] = {
	label = "Citra Spark",
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
["pt_berrywhirl"] = {
	label = "Berry Whirl",
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
["pt_rosella_bloom"] = {
	label = "Rosella Bloom",
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
["pt_crimson_ridge"] = {
	label = "Crimson Ridge",
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
["pt_amberwheat"] = {
	label = "AmberWheat Brew",
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
["pt_ironwoord_stout"] = {
	label = "IronWood Stout",
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
["pt_carbonated_water"] = {
	label = "Carbonated Water",
	weight = 1,
	stack = true,
	close = true,
},
["pt_citric_acid"] = {
	label = "Citric Acid",
	weight = 1,
	stack = true,
	close = true,
},
["pt_lime"] = {
	label = "Lemon-Lime Soda",
	weight = 1,
	stack = true,
	close = true,
},
["pt_chardonnay_grapes"] = {
	label = "Chardonnay Grapes",
	weight = 1,
	stack = true,
	close = true,
},
["malted_barley"] = {
	label = "Malted Barley",
	weight = 1,
	stack = true,
	close = true,
},
["plisner_malt"] = {
	label = "Pilsner Malt",
	weight = 1,
	stack = true,
	close = true,
},
["pt_icecubes"] = {
	label = "Ice Cubes",
	weight = 1,
	stack = true,
	close = true,
},
["pt_emptycup"] = {
	label = "Empty Cup",
	weight = 1,
	stack = true,
	close = true,
},
["pt_waterbottle"] = {
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
['pt_margherita'] = {['name'] = 'pt_margherita', ['label'] = 'Classic Margherita Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_margherita.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_pepperoni'] = {['name'] = 'pt_pepperoni', ['label'] = 'Pepperoni Feast Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_pepperoni.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_bbq_chicken'] = {['name'] = 'pt_bbq_chicken', ['label'] = 'BBQ Chicken Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_bbq_chicken.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_veggie'] = {['name'] = 'pt_veggie', ['label'] = 'Veggie Supreme Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_veggie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_hawaiian'] = {['name'] = 'pt_hawaiian', ['label'] = 'Hawaiian Paradise Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_hawaiian.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_chicken'] = {['name'] = 'pt_chicken', ['label'] = 'Meat Lovers Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_chicken.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_four_cheese'] = {['name'] = 'pt_four_cheese', ['label'] = 'Four Cheese Heaven Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_four_cheese.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_sausage'] = {['name'] = 'pt_sausage', ['label'] = 'Spicy Sausage Sizzle Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_sausage.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_buffalo'] = {['name'] = 'pt_buffalo', ['label'] = 'Buffalo Chicken Ranch Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_buffalo.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_garlic_spinach'] = {['name'] = 'pt_garlic_spinach', ['label'] = 'Garlic Spinach Alfredo Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_garlic_spinach.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_garlic_knots'] = {['name'] = 'pt_garlic_knots', ['label'] = 'Garlic Knots', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_garlic_knots.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_mozzarella_sticks'] = {['name'] = 'pt_mozzarella_sticks', ['label'] = 'Mozzarella Sticks', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_mozzarella_sticks.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_cheesy_breadsticks'] = {['name'] = 'pt_cheesy_breadsticks', ['label'] = 'Cheesy Breadsticks', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_cheesy_breadsticks.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_buffalo_wings'] = {['name'] = 'pt_buffalo_wings', ['label'] = 'Buffalo Chicken Wings', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_buffalo_wings.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_bruschetta_bites'] = {['name'] = 'pt_bruschetta_bites', ['label'] = 'Bruschetta Bites', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_bruschetta_bites.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_jalapeno_popper'] = {['name'] = 'pt_jalapeno_popper', ['label'] = 'Jalapeño Poppers', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_jalapeno_popper.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_calamari'] = {['name'] = 'pt_calamari', ['label'] = 'Fried Calamari', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_calamari.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_spinach_dip'] = {['name'] = 'pt_spinach_dip', ['label'] = 'Spinach & Artichoke Dip', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_spinach_dip.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_caesar'] = {['name'] = 'pt_caesar', ['label'] = 'Classic Caesar Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_caesar.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_greek_feta'] = {['name'] = 'pt_greek_feta', ['label'] = 'Greek Feta Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_greek_feta.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_caprese'] = {['name'] = 'pt_caprese', ['label'] = 'Caprese Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_caprese.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_chicken_caesar'] = {['name'] = 'pt_chicken_caesar', ['label'] = 'Chicken Caesar Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_chicken_caesar.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_fresh_garden'] = {['name'] = 'pt_fresh_garden', ['label'] = 'Garden Fresh Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_fresh_garden.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_spinach_bacon'] = {['name'] = 'pt_spinach_bacon', ['label'] = 'Spinach & Bacon Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_spinach_bacon.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_mediterranean_quinoa'] = {['name'] = 'pt_mediterranean_quinoa', ['label'] = 'Mediterranean Quinoa Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_mediterranean_quinoa.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_antipasto'] = {['name'] = 'pt_antipasto', ['label'] = 'Antipasto Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_antipasto.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_alfredo'] = {['name'] = 'pt_alfredo', ['label'] = 'Creamy Alfredo Pasta', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_alfredo.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_spaghetti'] = {['name'] = 'pt_spaghetti', ['label'] = 'Spaghetti Bolognese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_spaghetti.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_penne_arrabbiata'] = {['name'] = 'pt_penne_arrabbiata', ['label'] = 'Penne Arrabbiata', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_penne_arrabbiata.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_chicken_pesto'] = {['name'] = 'pt_chicken_pesto', ['label'] = 'Chicken Pesto Pasta', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_chicken_pesto.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_cheese_ravioli'] = {['name'] = 'pt_cheese_ravioli', ['label'] = 'Four Cheese Ravioli', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_cheese_ravioli.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_lasagna'] = {['name'] = 'pt_lasagna', ['label'] = 'Lasagna Classico', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_lasagna.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_shrimp_scampi'] = {['name'] = 'pt_shrimp_scampi', ['label'] = 'Shrimp Scampi Linguine', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_shrimp_scampi.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_vegetable'] = {['name'] = 'pt_vegetable', ['label'] = 'Vegetable Primavera', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_vegetable.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_citraspark'] = {['name'] = 'pt_citraspark', ['label'] = 'Citra Spark', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_citraspark.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_berrywhirl'] = {['name'] = 'pt_berrywhirl', ['label'] = 'Berry Whirl', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_berrywhirl.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_rosella_bloom'] = {['name'] = 'pt_rosella_bloom', ['label'] = 'Rosella Bloom', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_rosella_bloom.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_crimson_ridge'] = {['name'] = 'pt_crimson_ridge', ['label'] = 'Crimson Ridge', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_crimson_ridge.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_amberwheat'] = {['name'] = 'pt_amberwheat', ['label'] = 'AmberWheat Brew', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_amberwheat.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_ironwoord_stout'] = {['name'] = 'pt_ironwoord_stout', ['label'] = 'IronWood Stout', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_ironwoord_stout.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_dough'] = {['name'] = 'pt_dough', ['label'] = 'Pizza Base', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_dough.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_basil_leaves'] = {['name'] = 'pt_basil_leaves', ['label'] = 'Basil Leaves', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_basil_leaves.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_marinara_sauce'] = {['name'] = 'pt_marinara_sauce', ['label'] = 'Spicy Marinara Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_marinara_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_bbq_sauce'] = {['name'] = 'pt_bbq_sauce', ['label'] = 'Smoky BBQ Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_bbq_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_black_olives'] = {['name'] = 'pt_black_olives', ['label'] = 'Black Olives', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_black_olives.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_pineapple_chunks'] = {['name'] = 'pt_pineapple_chunks', ['label'] = 'Pineapple Chunks', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_pineapple_chunks.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_bacon_crumbles'] = {['name'] = 'pt_bacon_crumbles', ['label'] = 'Bacon Crumbles', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_bacon_crumbles.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_gorgonzola_cheese'] = {['name'] = 'pt_gorgonzola_cheese', ['label'] = 'Gorgonzola Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_gorgonzola_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_italian_suasage'] = {['name'] = 'pt_italian_suasage', ['label'] = 'Italian Sausage', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_italian_suasage.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_ranch_sauce'] = {['name'] = 'pt_ranch_sauce', ['label'] = 'Ranch Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_ranch_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_garlic_alfredo_sauce'] = {['name'] = 'pt_garlic_alfredo_sauce', ['label'] = 'Garlic Alfredo Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_garlic_alfredo_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_olive_oil'] = {['name'] = 'pt_olive_oil', ['label'] = 'Olive Oil', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_olive_oil.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_garlic_butter'] = {['name'] = 'pt_garlic_butter', ['label'] = 'Garlic Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_garlic_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_crispy_bread'] = {['name'] = 'pt_crispy_bread', ['label'] = 'Crispy Bread', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_crispy_bread.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_mozzarella'] = {['name'] = 'pt_mozzarella', ['label'] = 'Melted Mozzarella', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_mozzarella.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_buffalo_sauce'] = {['name'] = 'pt_buffalo_sauce', ['label'] = 'Buffalo Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_buffalo_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_basil'] = {['name'] = 'pt_basil', ['label'] = 'Fresh Basil', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_basil.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_cream_cheese'] = {['name'] = 'pt_cream_cheese', ['label'] = 'Cream Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_cream_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_lemon_aioli'] = {['name'] = 'pt_lemon_aioli', ['label'] = 'Lemon Aioli', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_lemon_aioli.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_artichokes'] = {['name'] = 'pt_artichokes', ['label'] = 'Artichokes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_artichokes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_vinegar'] = {['name'] = 'pt_vinegar', ['label'] = 'Vinegar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_vinegar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_parmesan'] = {['name'] = 'pt_parmesan', ['label'] = 'Parmesan Shavings', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_parmesan.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_kalamata_olives'] = {['name'] = 'pt_kalamata_olives', ['label'] = 'Kalamata Olives', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_kalamata_olives.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_balsamic_glaze'] = {['name'] = 'pt_balsamic_glaze', ['label'] = ' Balsamic Glaze', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_balsamic_glaze.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_garlic_croutons'] = {['name'] = 'pt_garlic_croutons', ['label'] = 'Garlic Croutons', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_garlic_croutons.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_avocado_slice'] = {['name'] = 'pt_avocado_slice', ['label'] = 'Avocado Slices', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_avocado_slice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_crispy_bacon'] = {['name'] = 'pt_crispy_bacon', ['label'] = 'Crispy Bacon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_crispy_bacon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_quinoa'] = {['name'] = 'pt_quinoa', ['label'] = 'Quinoa', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_quinoa.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_marinated_artichokes'] = {['name'] = 'pt_marinated_artichokes', ['label'] = 'Marinated Artichokes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_marinated_artichokes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_garlic'] = {['name'] = 'pt_garlic', ['label'] = 'Garlic', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_garlic.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_alfreparmesan_cream_sauce'] = {['name'] = 'pt_alfreparmesan_cream_sauce', ['label'] = 'Parmesan Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_alfreparmesan_cream_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_beef'] = {['name'] = 'pt_beef', ['label'] = 'Beef', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_beef.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_penne_pasta'] = {['name'] = 'pt_penne_pasta', ['label'] = 'Penne Pasta', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_penne_pasta.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_basil_pesto_sauce'] = {['name'] = 'pt_basil_pesto_sauce', ['label'] = 'Basil Pesto Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_basil_pesto_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_mozzarella_cream_sauce'] = {['name'] = 'pt_mozzarella_cream_sauce', ['label'] = 'Mozzarella-Infused Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_mozzarella_cream_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_bechamel_sauce'] = {['name'] = 'pt_bechamel_sauce', ['label'] = 'Bechamel Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_bechamel_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_lemon_zest'] = {['name'] = 'pt_lemon_zest', ['label'] = 'Lemon Zest', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_lemon_zest.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_carbonated_water'] = {['name'] = 'pt_carbonated_water', ['label'] = 'Carbonated Water', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_carbonated_water.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_lemon_lime'] = {['name'] = 'pt_lemon_lime', ['label'] = 'Lemon Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_lemon_lime.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_mixed_berry'] = {['name'] = 'pt_mixed_berry', ['label'] = 'Mixed Berry', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_mixed_berry.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_strawberry'] = {['name'] = 'pt_strawberry', ['label'] = 'Strawberry', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_strawberry.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_cherry'] = {['name'] = 'pt_cherry', ['label'] = 'Cherry', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_cherry.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_malted_barley'] = {['name'] = 'pt_malted_barley', ['label'] = 'Malted Barley', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_malted_barley.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_coffee_malt'] = {['name'] = 'pt_coffee_malt', ['label'] = 'Coffee Malt', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_coffee_malt.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_icecubes'] = {['name'] = 'pt_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_waterbottle'] = {['name'] = 'pt_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_emptycup'] = {['name'] = 'pt_emptycup', ['label'] = 'Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>Quasar Inventory</summary>

```lua
['pt_margherita'] = {['name'] = 'pt_margherita', ['label'] = 'Classic Margherita Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_margherita.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_pepperoni'] = {['name'] = 'pt_pepperoni', ['label'] = 'Pepperoni Feast Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_pepperoni.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_bbq_chicken'] = {['name'] = 'pt_bbq_chicken', ['label'] = 'BBQ Chicken Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_bbq_chicken.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_veggie'] = {['name'] = 'pt_veggie', ['label'] = 'Veggie Supreme Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_veggie.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_hawaiian'] = {['name'] = 'pt_hawaiian', ['label'] = 'Hawaiian Paradise Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_hawaiian.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_chicken'] = {['name'] = 'pt_chicken', ['label'] = 'Meat Lovers Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_chicken.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_four_cheese'] = {['name'] = 'pt_four_cheese', ['label'] = 'Four Cheese Heaven Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_four_cheese.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_sausage'] = {['name'] = 'pt_sausage', ['label'] = 'Spicy Sausage Sizzle Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_sausage.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_buffalo'] = {['name'] = 'pt_buffalo', ['label'] = 'Buffalo Chicken Ranch Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_buffalo.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_garlic_spinach'] = {['name'] = 'pt_garlic_spinach', ['label'] = 'Garlic Spinach Alfredo Pizza', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_garlic_spinach.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_garlic_knots'] = {['name'] = 'pt_garlic_knots', ['label'] = 'Garlic Knots', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_garlic_knots.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_mozzarella_sticks'] = {['name'] = 'pt_mozzarella_sticks', ['label'] = 'Mozzarella Sticks', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_mozzarella_sticks.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_cheesy_breadsticks'] = {['name'] = 'pt_cheesy_breadsticks', ['label'] = 'Cheesy Breadsticks', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_cheesy_breadsticks.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_buffalo_wings'] = {['name'] = 'pt_buffalo_wings', ['label'] = 'Buffalo Chicken Wings', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_buffalo_wings.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_bruschetta_bites'] = {['name'] = 'pt_bruschetta_bites', ['label'] = 'Bruschetta Bites', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_bruschetta_bites.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_jalapeno_popper'] = {['name'] = 'pt_jalapeno_popper', ['label'] = 'Jalapeño Poppers', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_jalapeno_popper.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_calamari'] = {['name'] = 'pt_calamari', ['label'] = 'Fried Calamari', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_calamari.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_spinach_dip'] = {['name'] = 'pt_spinach_dip', ['label'] = 'Spinach & Artichoke Dip', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_spinach_dip.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_caesar'] = {['name'] = 'pt_caesar', ['label'] = 'Classic Caesar Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_caesar.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_greek_feta'] = {['name'] = 'pt_greek_feta', ['label'] = 'Greek Feta Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_greek_feta.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_caprese'] = {['name'] = 'pt_caprese', ['label'] = 'Caprese Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_caprese.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_chicken_caesar'] = {['name'] = 'pt_chicken_caesar', ['label'] = 'Chicken Caesar Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_chicken_caesar.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_fresh_garden'] = {['name'] = 'pt_fresh_garden', ['label'] = 'Garden Fresh Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_fresh_garden.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_spinach_bacon'] = {['name'] = 'pt_spinach_bacon', ['label'] = 'Spinach & Bacon Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_spinach_bacon.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_mediterranean_quinoa'] = {['name'] = 'pt_mediterranean_quinoa', ['label'] = 'Mediterranean Quinoa Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_mediterranean_quinoa.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_antipasto'] = {['name'] = 'pt_antipasto', ['label'] = 'Antipasto Salad', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_antipasto.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_alfredo'] = {['name'] = 'pt_alfredo', ['label'] = 'Creamy Alfredo Pasta', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_alfredo.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_spaghetti'] = {['name'] = 'pt_spaghetti', ['label'] = 'Spaghetti Bolognese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_spaghetti.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_penne_arrabbiata'] = {['name'] = 'pt_penne_arrabbiata', ['label'] = 'Penne Arrabbiata', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_penne_arrabbiata.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_chicken_pesto'] = {['name'] = 'pt_chicken_pesto', ['label'] = 'Chicken Pesto Pasta', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_chicken_pesto.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_cheese_ravioli'] = {['name'] = 'pt_cheese_ravioli', ['label'] = 'Four Cheese Ravioli', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_cheese_ravioli.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_lasagna'] = {['name'] = 'pt_lasagna', ['label'] = 'Lasagna Classico', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_lasagna.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_shrimp_scampi'] = {['name'] = 'pt_shrimp_scampi', ['label'] = 'Shrimp Scampi Linguine', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_shrimp_scampi.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_vegetable'] = {['name'] = 'pt_vegetable', ['label'] = 'Vegetable Primavera', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_vegetable.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_citraspark'] = {['name'] = 'pt_citraspark', ['label'] = 'Citra Spark', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_citraspark.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_berrywhirl'] = {['name'] = 'pt_berrywhirl', ['label'] = 'Berry Whirl', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_berrywhirl.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_rosella_bloom'] = {['name'] = 'pt_rosella_bloom', ['label'] = 'Rosella Bloom', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_rosella_bloom.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_crimson_ridge'] = {['name'] = 'pt_crimson_ridge', ['label'] = 'Crimson Ridge', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_crimson_ridge.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_amberwheat'] = {['name'] = 'pt_amberwheat', ['label'] = 'AmberWheat Brew', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_amberwheat.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_ironwoord_stout'] = {['name'] = 'pt_ironwoord_stout', ['label'] = 'IronWood Stout', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_ironwoord_stout.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_dough'] = {['name'] = 'pt_dough', ['label'] = 'Pizza Base', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_dough.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_basil_leaves'] = {['name'] = 'pt_basil_leaves', ['label'] = 'Basil Leaves', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_basil_leaves.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_marinara_sauce'] = {['name'] = 'pt_marinara_sauce', ['label'] = 'Spicy Marinara Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_marinara_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_bbq_sauce'] = {['name'] = 'pt_bbq_sauce', ['label'] = 'Smoky BBQ Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_bbq_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_black_olives'] = {['name'] = 'pt_black_olives', ['label'] = 'Black Olives', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_black_olives.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_pineapple_chunks'] = {['name'] = 'pt_pineapple_chunks', ['label'] = 'Pineapple Chunks', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_pineapple_chunks.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_bacon_crumbles'] = {['name'] = 'pt_bacon_crumbles', ['label'] = 'Bacon Crumbles', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_bacon_crumbles.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_gorgonzola_cheese'] = {['name'] = 'pt_gorgonzola_cheese', ['label'] = 'Gorgonzola Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_gorgonzola_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_italian_suasage'] = {['name'] = 'pt_italian_suasage', ['label'] = 'Italian Sausage', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_italian_suasage.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_ranch_sauce'] = {['name'] = 'pt_ranch_sauce', ['label'] = 'Ranch Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_ranch_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_garlic_alfredo_sauce'] = {['name'] = 'pt_garlic_alfredo_sauce', ['label'] = 'Garlic Alfredo Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_garlic_alfredo_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_olive_oil'] = {['name'] = 'pt_olive_oil', ['label'] = 'Olive Oil', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_olive_oil.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_garlic_butter'] = {['name'] = 'pt_garlic_butter', ['label'] = 'Garlic Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_garlic_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_crispy_bread'] = {['name'] = 'pt_crispy_bread', ['label'] = 'Crispy Bread', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_crispy_bread.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_mozzarella'] = {['name'] = 'pt_mozzarella', ['label'] = 'Melted Mozzarella', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_mozzarella.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_buffalo_sauce'] = {['name'] = 'pt_buffalo_sauce', ['label'] = 'Buffalo Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_buffalo_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_basil'] = {['name'] = 'pt_basil', ['label'] = 'Fresh Basil', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_basil.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_cream_cheese'] = {['name'] = 'pt_cream_cheese', ['label'] = 'Cream Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_cream_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_lemon_aioli'] = {['name'] = 'pt_lemon_aioli', ['label'] = 'Lemon Aioli', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_lemon_aioli.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_artichokes'] = {['name'] = 'pt_artichokes', ['label'] = 'Artichokes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_artichokes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_vinegar'] = {['name'] = 'pt_vinegar', ['label'] = 'Vinegar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_vinegar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_parmesan'] = {['name'] = 'pt_parmesan', ['label'] = 'Parmesan Shavings', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_parmesan.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_kalamata_olives'] = {['name'] = 'pt_kalamata_olives', ['label'] = 'Kalamata Olives', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_kalamata_olives.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_balsamic_glaze'] = {['name'] = 'pt_balsamic_glaze', ['label'] = ' Balsamic Glaze', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_balsamic_glaze.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_garlic_croutons'] = {['name'] = 'pt_garlic_croutons', ['label'] = 'Garlic Croutons', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_garlic_croutons.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_avocado_slice'] = {['name'] = 'pt_avocado_slice', ['label'] = 'Avocado Slices', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_avocado_slice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_crispy_bacon'] = {['name'] = 'pt_crispy_bacon', ['label'] = 'Crispy Bacon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_crispy_bacon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_quinoa'] = {['name'] = 'pt_quinoa', ['label'] = 'Quinoa', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_quinoa.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_marinated_artichokes'] = {['name'] = 'pt_marinated_artichokes', ['label'] = 'Marinated Artichokes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_marinated_artichokes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_garlic'] = {['name'] = 'pt_garlic', ['label'] = 'Garlic', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_garlic.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_alfreparmesan_cream_sauce'] = {['name'] = 'pt_alfreparmesan_cream_sauce', ['label'] = 'Parmesan Cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_alfreparmesan_cream_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_beef'] = {['name'] = 'pt_beef', ['label'] = 'Beef', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_beef.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_penne_pasta'] = {['name'] = 'pt_penne_pasta', ['label'] = 'Penne Pasta', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_penne_pasta.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_basil_pesto_sauce'] = {['name'] = 'pt_basil_pesto_sauce', ['label'] = 'Basil Pesto Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_basil_pesto_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_mozzarella_cream_sauce'] = {['name'] = 'pt_mozzarella_cream_sauce', ['label'] = 'Mozzarella-Infused Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_mozzarella_cream_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_bechamel_sauce'] = {['name'] = 'pt_bechamel_sauce', ['label'] = 'Bechamel Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_bechamel_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_lemon_zest'] = {['name'] = 'pt_lemon_zest', ['label'] = 'Lemon Zest', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_lemon_zest.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_carbonated_water'] = {['name'] = 'pt_carbonated_water', ['label'] = 'Carbonated Water', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_carbonated_water.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_lemon_lime'] = {['name'] = 'pt_lemon_lime', ['label'] = 'Lemon Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_lemon_lime.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_mixed_berry'] = {['name'] = 'pt_mixed_berry', ['label'] = 'Mixed Berry', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_mixed_berry.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_strawberry'] = {['name'] = 'pt_strawberry', ['label'] = 'Strawberry', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_strawberry.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_cherry'] = {['name'] = 'pt_cherry', ['label'] = 'Cherry', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_cherry.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_malted_barley'] = {['name'] = 'pt_malted_barley', ['label'] = 'Malted Barley', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_malted_barley.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_coffee_malt'] = {['name'] = 'pt_coffee_malt', ['label'] = 'Coffee Malt', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_coffee_malt.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_icecubes'] = {['name'] = 'pt_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_waterbottle'] = {['name'] = 'pt_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pt_emptycup'] = {['name'] = 'pt_emptycup', ['label'] = 'Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pt_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>ESX Items SQL</summary>

```lua
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
	 ('pt_margherita', 'Classic Margherita', 1),
	('pt_pepperoni', 'Pepperoni Feast', 1),
	('pt_bbq_chicken', 'BBq Chicken Pizza', 1),
	('pt_veggie', 'Veggie', 1),
	('pt_hawaiian', 'Hawaiian Paradise', 1),
	('pt_chicken', 'Meat Lovers Special', 1),
	('pt_four_cheese', 'Four Cheese Heaven', 1),
	('pt_sausage', 'Spicy Sausage Sizzle', 1),
	('pt_buffalo', 'Buffalo Chicken Ranch', 1),
	('pt_garlic_spinach', 'Garlic Spinach Alfredo', 1),
	('pt_dough', 'Pizza Base', 1),
	('pt_basil_leaves', 'Basil Leaves', 1),
	('pt_marinara_sauce', 'Spicy Marinara Sauce', 1),
	('pt_bbq_sauce', 'Smoky BBQ Sauce', 1),
	('pt_black_olives', 'Black Olives', 1),
	('pt_pineapple_chunks', 'Pineapple Chunks', 1),
	('pt_bacon_crumbles', 'Bacon Crumbles', 1),
	('pt_gorgonzola_cheese', 'Gorgonzola Cheese', 1),
	('pt_italian_suasage', 'Italian Sausage', 1),
	('pt_ranch_sauce', 'Ranch Sauce', 1),
	('pt_garlic_alfredo_sauce', 'Garlic Alfredo Sauce', 1),

	('pt_garlic_knots', 'Garlic Knots', 1),
	('pt_mozzarella_sticks', 'Mozzarella Sticks', 1),
	('pt_cheesy_breadsticks', 'Cheesy Breadsticks', 1),
	('pt_buffalo_wings', 'Buffalo Chicken Wings', 1),
	('pt_bruschetta_bites', 'Bruschetta Bites', 1),
	('pt_jalapeno_popper', 'Jalapeno Poppers', 1),
	('pt_calamari', 'Fried Calamari', 1),
	('pt_spinach_dip', 'Spinach & Artichoke Dip', 1),
	('pt_olive_oil', 'Olive Oil', 1),
	('pt_garlic_butter', 'Garlic Butter', 1),
	('pt_crispy_bread', 'Crispy Bread', 1),
	('pt_mozzarella', 'Melted Mozzarella', 1),
	('pt_buffalo_sauce', 'Buffalo Sauce', 1),
	('pt_basil', 'Fresh Basil', 1),
	('pt_cream_cheese', 'Cream Cheese', 1),
	('pt_lemon_aioli', 'Lemon Aioli', 1),
	('pt_artichokes', 'Artichokes', 1),

	('pt_caesar', 'Classic Caesar Salad', 1),
	('pt_greek_feta', 'Greek Feta Salad', 1),
	('pt_caprese', 'Caprese Salad', 1),
	('pt_chicken_caesar', 'Chicken Caesar Salad', 1),
	('pt_fresh_garden', 'Garden Fresh Salad', 1),
	('pt_spinach_bacon', 'Spinach & Bacon Salad', 1),
	('pt_mediterranean_quinoa', 'Mediterranean Quinoa Salad', 1),
	('pt_antipasto', 'Antipasto Salad', 1),
	('pt_vinegar', 'Vinegar', 1),
	('pt_parmesan', 'Parmesan Shavings', 1),
	('pt_kalamata_olives', 'Kalamata Olives', 1),
	('pt_balsamic_glaze', 'Balsamic Glaze', 1),
	('pt_garlic_croutons', 'Garlic Croutons', 1),
	('pt_avocado_slice', 'Avocado Slices', 1),
	('pt_crispy_bacon', 'Crispy Bacon Bits', 1),
	('pt_quinoa', 'Quinoa', 1),
	('pt_marinated_artichokes', 'Marinated Artichokes', 1),

	('pt_alfredo', 'Creamy Alfredo Pasta', 1),
	('pt_spaghetti', 'Spaghetti Bolognese', 1),
	('pt_penne_arrabbiata', 'Penne Arrabbiata', 1),
	('pt_vegetable', 'Vegetable Primavera', 1),
	('pt_lasagna', 'Lasagna Classico', 1),
	('pt_shrimp_scampi', 'Shrimp Scampi Linguine', 1),
	('pt_garlic', 'Garlic', 1),
	('pt_parmesan_cream_sauce', 'Parmesan Cream Sauce', 1),
	('pt_beef', 'Beef', 1),
	('pt_penne_pasta', 'Penne Pasta', 1),
	('pt_basil_pesto_sauce', 'Basil Pesto Sauce', 1),
	('pt_mozzarella_cream_sauce', 'Mozzarella-Infused Cream Sauce', 1),
	('pt_lemon_zest', 'Lemon Zest', 1),
	('pt_bechamel_sauce', 'Bechamel Sauce', 1),
	('pt_garlic_butter', 'Garlic-Butter Sauce', 1),

	('pt_citraspark', 'Citra Spark', 1),
	('pt_berrywhirl', 'Berry Whirl', 1),
	('pt_rosella_bloom', 'Rosella Bloom', 1),
	('pt_crimson_ridge', 'Crimson Ridge', 1),
	('pt_amberwheat', 'AmberWheat Brew', 1),
	('pt_ironwoord_stout', 'IronWood Stout', 1),
	('pt_carbonated_water', 'Carbonated Water', 1),
	('pt_citric_acid', 'Citric Acid', 1),
	('pt_lime', 'Lemon Lime Soda', 1),
	('pt_chardonnay_grapes', 'Chardonnay Grapes', 1),
	('malted_barley', 'Malted Barley', 1),
	('pt_icecubes', 'Ice Cubes', 1),
	('pt_waterbottle', 'Water Bottle', 1),
	('pt_emptycup', 'Empty Cup', 1),
	('plisner_malt', 'Pilsner Malt', 1);
```

</details>

### For QBCore Only

{% tabs %}
{% tab title="jobs.lua" %}
Add the Following in qb-core/shared/jobs.lua

```lua
['pizzathis'] = {
    label = 'Pizza This',
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

For Qbox add in qbx\_core->shared->jobs.lua

```lua
['pizzathis'] = {
    label = 'Pizza This',
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
    ['pt_citraspark'] = math.random(35, 54),
    ['pt_berrywhirl'] = math.random(35, 54),
    ['pt_rosella_bloom'] = math.random(35, 54),
    ['pt_crimson_ridge'] = math.random(35, 54),
    ['pt_amberwheat'] = math.random(35, 54),
    ['pt_ironwoord_stout'] = math.random(35, 54),

}

Config.ConsumablesEat = {
    ['pt_margherita'] = math.random(35, 54),
    ['pt_pepperoni'] = math.random(35, 54),
    ['pt_bbq_chicken'] = math.random(35, 54),
    ['pt_veggie'] = math.random(35, 54),
    ['pt_hawaiian'] = math.random(35, 54),
    ['pt_chicken'] = math.random(35, 54),
    ['pt_four_cheese'] = math.random(35, 54),
    ['pt_sausage'] = math.random(35, 54),
    ['pt_buffalo'] = math.random(35, 54),
    ['pt_garlic_spinach'] = math.random(35, 54),

    ['pt_garlic_knots'] = math.random(35, 54),
    ['pt_mozzarella_sticks'] = math.random(35, 54),
    ['pt_cheesy_breadsticks'] = math.random(35, 54),
    ['pt_buffalo_wings'] = math.random(35, 54),
    ['pt_bruschetta_bites'] = math.random(35, 54),
    ['pt_jalapeno_popper'] = math.random(35, 54),
    ['pt_calamari'] = math.random(35, 54),
    ['pt_spinach_dip'] = math.random(35, 54),

    ['pt_caesar'] = math.random(35, 54),
    ['pt_greek_feta'] = math.random(35, 54),
    ['pt_caprese'] = math.random(35, 54),
    ['pt_chicken_caesar'] = math.random(35, 54),
    ['pt_fresh_garden'] = math.random(35, 54),
    ['pt_spinach_bacon'] = math.random(35, 54),
    ['pt_mediterranean_quinoa'] = math.random(35, 54),
    ['pt_antipasto'] = math.random(35, 54),
    
    ['pt_alfredo'] = math.random(35, 54),
    ['pt_spaghetti'] = math.random(35, 54),
    ['pt_penne_arrabbiata'] = math.random(35, 54),
    ['pt_chicken_pesto'] = math.random(35, 54),
    ['pt_vegetable'] = math.random(35, 54),
    ['pt_lasagna'] = math.random(35, 54),
    ['pt_shrimp_scampi'] = math.random(35, 54),
}
```

</details>

<details>

<summary>Jim Consumables</summary>

Add the following in jim-consumables/shared/consumables.lua

```lua
pt_margherita = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_pepperoni = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_bbq_chicken = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_veggie = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_hawaiian = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_chicken = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_four_cheese = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_sausage = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_buffalo = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_garlic_spinach = { emote = "pizza", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},

pt_garlic_knots = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_mozzarella_sticks = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_cheesy_breadsticks = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_buffalo_wings = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_bruschetta_bites = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_jalapeno_popper = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_calamari = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_spinach_dip = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_caesar = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_caprese = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_fresh_garden = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_spinach_bacon = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_mediterranean_quinoa = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_antipasto = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_alfredo = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_penne_arrabbiata = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_chicken_pesto = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_vegetable = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_lasagna = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_shrimp_scampi = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},

pt_citraspark = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_berrywhirl = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_rosella_bloom = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_crimson_ridge = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_amberwheat = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pt_ironwoord_stout = { emote = "drink", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
```

</details>

### Add Images to Inventory

Copy all the Images folder and paste it in your inventory Images folder

### Log Setup - Optional

To enable discord logs make sure to add your webhook in the server->Log.lua File

{% embed url="https://www.youtube.com/watch?pp=ygULI2FwcHlxczIwMjM=&v=fKksxz2Gdnc" %}

### Optional Dj Custom Props

If you have purchased the DJ Burgershot Props [https://djscollections.com/package/5669923](https://djscollections.com/package/5669923) just install it and set the Config.UseDjItems = true

