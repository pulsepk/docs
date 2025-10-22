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
CREATE TABLE IF NOT EXISTS `pl_pearls` (
      `stock` longtext DEFAULT NULL,
      `state` varchar(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;

INSERT INTO `addon_account` (name, label, shared) VALUES
	('society_pearls', 'Pearls', 1);
	
INSERT INTO `datastore` (name, label, shared) VALUES
       ('society_pearls', 'Pearls', 1);
       
INSERT INTO `jobs` (name, label,whitelisted) VALUES
       ('pearls', 'Pearls',1);
       
INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
        ('pearls',0,'cashier','Cashier',20,'{}','{}'),
        ('pearls',1,'cook','Cook',40,'{}','{}'),
        ('pearls',2,'staff','Staff',60,'{}','{}'),
        ('pearls',3,'manager','Manager',85,'{}','{}'),
        ('pearls',4,'boss','Owner',100,'{}','{}');
```

</details>

<details>

<summary>QBCore or Qbox</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_pearls` (
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

["pearl_hazelnut_syrup"] = {
    label = "Hazelnut Syrup",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_herb"] = {
    label = "Herb sauce",
    weight = 1,
    stack = true,
    close = true,
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

["pearl_honey"] = {
    label = "Honey",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_ice"] = {
    label = "Pearls Ice",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_iced_coffee"] = {
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

["pearl_iced_tea"] = {
    label = "Iced Green Tea",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_kombucha"] = {
    label = "Kombucha",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_latte"] = {
    label = "Latte",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_lemon"] = {
    label = "Lemon",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_lemonade"] = {
    label = "Freshly Squeezed Lemonade",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_lemon_mint"] = {
    label = "Lemon and Mint",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_lemon_sauce"] = {
    label = "Lemon Sauce",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_lime_slaw"] = {
    label = "Lime Slaw",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_macchiato"] = {
    label = "Macchiato",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_mango_salsa"] = {
    label = "Mango Salsa",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_mint"] = {
    label = "Mint",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_mixed_fruit"] = {
    label = "Mixed Fruit Juice",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_mocha"] = {
    label = "Mocha",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_parmesan_cheese"] = {
    label = "Parmesan cheese",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_pesto"] = {
    label = "Pesto",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_pineapple"] = {
    label = "Pineapple",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_pineapple_juice"] = {
    label = "Pineapple Juice",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_poke_sauce"] = {
    label = "Poke Sauce",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_red_snapper"] = {
    label = "Red Snapper",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_salmon"] = {
    label = "Grilled Salmon",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_salsa"] = {
    label = "Mango Salsa",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_samosa"] = {
    label = "Fish Samosas",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_seared_cod"] = {
    label = "Seared Cod",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_sea_bass"] = {
    label = "Sea Bass",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_shrimp"] = {
    label = "Shrimp Cocktail",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_skewers"] = {
    label = "Fish Skewers",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_soy_sauce"] = {
    label = "Soy Sauce",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_sugar"] = {
    label = "Sugar",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_swordfish_steak"] = {
    label = "Swordfish Steak",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_tacos"] = {
    label = "Tacos",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_tartar"] = {
    label = "Fish Tartar",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_tilapia"] = {
    label = "Tilapia",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_tumeric"] = {
    label = "Tumeric",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_tuna_bites"] = {
    label = "Tuna Poke Bites",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_vanilla_icecream"] = {
    label = "Vanilla Ice Cream",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_vanilla_syrup"] = {
    label = "Vanilla Syrup",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_wedges"] = {
    label = "Wedges",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_whipped_cream"] = {
    label = "Whipped Cream",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_affogato"] = {
    label = "Affogato",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_aioli"] = {
    label = "Aioli",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_ale"] = {
    label = "Ginger Ale",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_almond"] = {
    label = "Almond Milk",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_americano"] = {
    label = "Americano",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_beer_batter"] = {
    label = "Beer batter",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_blackening_seaon"] = {
    label = "Blackening seasoning",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_brew"] = {
    label = "Iced Brew",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_broiled_halibut"] = {
    label = "Broiled Halibut",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_bruschetta"] = {
    label = "Anchovy Bruschetta",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_calamari"] = {
    label = "Calamari",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_cappuccino"] = {
    label = "Cappuccino",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_caramel_syrup"] = {
    label = "Caramel Syrup",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_ceviche"] = {
    label = "Smoked Salmon Crostini",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_chilli_sauce"] = {
    label = "Chili Sauce",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_chocolate_syrup"] = {
    label = "Chocolate Syrup",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_cilantro"] = {
    label = "Grilled Salmon",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_cinnamon_stick"] = {
    label = "Cinnamon Stick",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_citrus"] = {
    label = "Citrus Slices",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_citrus_water"] = {
    label = "Sparkling Water",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_cocktail_sauce"] = {
    label = "Cocktail Sauce",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_coconut"] = {
    label = "Coconut",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_coconut_water"] = {
    label = "Fresh Coconut Water",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_coffee_bean"] = {
    label = "Coffee Beans",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_crostini"] = {
    label = "Crispy Bread",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_dark_chocolate"] = {
    label = "Dark Chocolate",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_espresso"] = {
    label = "Espresso",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_fillet"] = {
    label = "Fillet",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_fish_cake"] = {
    label = "Fish Cakes",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_fish_chips"] = {
    label = "Fish and Chips",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},

["pearl_flat_white"] = {
    label = "Flat White",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_fruit"] = {
    label = "Fruit Punch",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},

["pearl_garlic"] = {
    label = "Garlic",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_garlic_butter"] = {
    label = "Garlic Butter Special Sauce",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_ginger"] = {
    label = "Ginger",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_icecubes"] = {
    label = "Ice Cubes",
    weight = 1,
    stack = true,
    close = true,
},


["pearl_waterbottle"] = {
    label = "Water Bottle",
    weight = 1,
    stack = true,
    close = true,
},

["pearl_emptycup"] = {
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
['pearl_grill_salmon'] = {['name'] = 'pearl_grill_salmon', ['label'] = 'Grilled Salmon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_grill_salmon.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_seared_cod'] = {['name'] = 'pearl_seared_cod', ['label'] = 'Seared Cod', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_seared_cod.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_tilapia'] = {['name'] = 'pearl_tilapia', ['label'] = 'Tilapia', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_tilapia.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_red_snapper'] = {['name'] = 'pearl_red_snapper', ['label'] = 'Red Snapper', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_red_snapper.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_fish_chips'] = {['name'] = 'pearl_fish_chips', ['label'] = 'Fish and Chips', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_fish_chips.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_salsa'] = {['name'] = 'pearl_salsa', ['label'] = 'Mango Salsa', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_salsa.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_sea_bass'] = {['name'] = 'pearl_sea_bass', ['label'] = 'Sea Bass', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_sea_bass.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_tacos'] = {['name'] = 'pearl_tacos', ['label'] = 'Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_tacos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_broiled_halibut'] = {['name'] = 'pearl_broiled_halibut', ['label'] = 'Broiled Halibut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_broiled_halibut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_swordfish_steak'] = {['name'] = 'pearl_swordfish_steak', ['label'] = 'Swordfish Steak', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_swordfish_steak.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_ceviche'] = {['name'] = 'pearl_ceviche', ['label'] = 'Fish Ceviche', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_ceviche.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_salmon'] = {['name'] = 'pearl_salmon', ['label'] = 'Smoked Salmon Crostini', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_salmon.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_tartar'] = {['name'] = 'pearl_tartar', ['label'] = 'Fish Tartar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_tartar.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_fish_cake'] = {['name'] = 'pearl_fish_cake', ['label'] = 'Fish Cakes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_fish_cake.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_shrimp'] = {['name'] = 'pearl_shrimp', ['label'] = 'Shrimp Cocktail', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_shrimp.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_bruschetta'] = {['name'] = 'pearl_bruschetta', ['label'] = 'Anchovy Bruschetta', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_bruschetta.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_skewers'] = {['name'] = 'pearl_skewers', ['label'] = 'Fish Skewers', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_skewers.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_samosa'] = {['name'] = 'pearl_samosa', ['label'] = 'Fish Samosas', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_samosa.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_calamari'] = {['name'] = 'pearl_calamari', ['label'] = 'Calamari', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_calamari.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_tuna_bites'] = {['name'] = 'pearl_tuna_bites', ['label'] = 'Tuna Poke Bites', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_tuna_bites.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_lemonade'] = {['name'] = 'pearl_lemonade', ['label'] = 'Freshly Squeezed Lemonade', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_lemonade.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_iced_tea'] = {['name'] = 'pearl_iced_tea', ['label'] = 'Iced Green Tea', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_iced_tea.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_citrus_water'] = {['name'] = 'pearl_citrus_water', ['label'] = 'Sparkling Water', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_citrus_water.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_fruit'] = {['name'] = 'pearl_fruit', ['label'] = 'Fruit Punch', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_fruit.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_hibiscus_tea'] = {['name'] = 'pearl_hibiscus_tea', ['label'] = 'Hibiscus Tea', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_hibiscus_tea.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_coconut_water'] = {['name'] = 'pearl_coconut_water', ['label'] = 'Fresh Coconut Water', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_coconut_water.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_ale'] = {['name'] = 'pearl_ale', ['label'] = 'Ginger Ale', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_ale.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_lemon_mint'] = {['name'] = 'pearl_lemon_mint', ['label'] = 'Lemon and Mint', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_lemon_mint.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_kombucha'] = {['name'] = 'pearl_kombucha', ['label'] = 'Kombucha', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_kombucha.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_pineapple_juice'] = {['name'] = 'pearl_pineapple_juice', ['label'] = 'Pineapple Juice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_pineapple_juice.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_espresso'] = {['name'] = 'pearl_espresso', ['label'] = 'Espresso', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_espresso.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_americano'] = {['name'] = 'pearl_americano', ['label'] = 'Americano', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_americano.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_cappuccino'] = {['name'] = 'pearl_cappuccino', ['label'] = 'Cappuccino', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_cappuccino.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_latte'] = {['name'] = 'pearl_latte', ['label'] = 'Latte', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_latte.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_mocha'] = {['name'] = 'pearl_mocha', ['label'] = 'Mocha', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_mocha.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_iced_coffee'] = {['name'] = 'pearl_iced_coffee', ['label'] = 'Iced Coffee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_iced_coffee.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_brew'] = {['name'] = 'pearl_brew', ['label'] = 'Iced Brew', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_brew.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_macchiato'] = {['name'] = 'pearl_macchiato', ['label'] = 'Macchiato', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_macchiato.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_flat_white'] = {['name'] = 'pearl_flat_white', ['label'] = 'Flat White', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_flat_white.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_affogato'] = {['name'] = 'pearl_affogato', ['label'] = 'Affogato', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_affogato.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_fillet'] = {['name'] = 'pearl_fillet', ['label'] = 'Fillet', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_fillet.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_garlic_butter'] = {['name'] = 'pearl_garlic_butter', ['label'] = 'Garlic Butter Special Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_garlic_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_herb'] = {['name'] = 'pearl_herb', ['label'] = 'Herb sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_herb.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_parmesan_cheese'] = {['name'] = 'pearl_parmesan_cheese', ['label'] = 'Parmesan cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_parmesan_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_blackening_seaon'] = {['name'] = 'pearl_blackening_seaon', ['label'] = 'Blackening seasoning ', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_blackening_seaon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_beer_batter'] = {['name'] = 'pearl_beer_batter', ['label'] = 'Beer batter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_beer_batter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_mango_salsa'] = {['name'] = 'pearl_mango_salsa', ['label'] = 'Mango Salsa', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_mango_salsa.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_ginger'] = {['name'] = 'pearl_ginger', ['label'] = 'Ginger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_ginger.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_lime_slaw'] = {['name'] = 'pearl_lime_slaw', ['label'] = 'Lime Slaw ', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_lime_slaw.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_lemon_sauce'] = {['name'] = 'pearl_lemon_sauce', ['label'] = 'Lemon Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_lemon_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_pesto'] = {['name'] = 'pearl_pesto', ['label'] = 'Pesto', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_pesto.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_lemon'] = {['name'] = 'pearl_lemon', ['label'] = 'Lemon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_lemon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_cilantro'] = {['name'] = 'pearl_cilantro', ['label'] = 'Coffee Beans Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_cilantro.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_crostini'] = {['name'] = 'pearl_crostini', ['label'] = 'Crispy Bread', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_crostini.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_soy_sauce'] = {['name'] = 'pearl_soy_sauce', ['label'] = 'Soy Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_soy_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_aioli'] = {['name'] = 'pearl_aioli', ['label'] = 'Aioli', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_aioli.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_cocktail_sauce'] = {['name'] = 'pearl_cocktail_sauce', ['label'] = 'Cocktail Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_cocktail_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_garlic'] = {['name'] = 'pearl_garlic', ['label'] = 'Garlic', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_garlic.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_chilli_sauce'] = {['name'] = 'pearl_chilli_sauce', ['label'] = 'Chili Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_chilli_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_tumeric'] = {['name'] = 'pearl_tumeric', ['label'] = 'Tumeric', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_tumeric.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_wedges'] = {['name'] = 'pearl_wedges', ['label'] = 'Wedges', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_wedges.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_poke_sauce'] = {['name'] = 'pearl_poke_sauce', ['label'] = 'Poke Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_poke_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_ice'] = {['name'] = 'pearl_ice', ['label'] = 'Ice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_ice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_honey'] = {['name'] = 'pearl_honey', ['label'] = 'Honey', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_honey.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_citrus'] = {['name'] = 'pearl_citrus', ['label'] = 'Citrus Slices', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_citrus.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_mixed_fruit'] = {['name'] = 'pearl_mixed_fruit', ['label'] = 'Mixed Fruit Juice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_mixed_fruit.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_coconut'] = {['name'] = 'pearl_coconut', ['label'] = 'Coconut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_coconut.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_sugar'] = {['name'] = 'pearl_sugar', ['label'] = 'Sugar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_sugar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_mint'] = {['name'] = 'pearl_mint', ['label'] = 'Mint', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_mint.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_pineapple'] = {['name'] = 'pearl_pineapple', ['label'] = 'Pineapple', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_pineapple.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_coffee_bean'] = {['name'] = 'pearl_coffee_bean', ['label'] = 'Coffee Beans', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_coffee_bean.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_almond'] = {['name'] = 'pearl_almond', ['label'] = 'Almond Milk', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_almond.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_dark_chocolate'] = {['name'] = 'pearl_dark_chocolate', ['label'] = 'Dark Chocolate', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_dark_chocolate.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_vanilla_syrup'] = {['name'] = 'pearl_vanilla_syrup', ['label'] = 'Vanilla Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_vanilla_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_chocolate_syrup'] = {['name'] = 'pearl_chocolate_syrup', ['label'] = 'Chocolate Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_chocolate_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_whipped_cream'] = {['name'] = 'pearl_whipped_cream', ['label'] = 'Whipped Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_whipped_cream.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_cinnamon_stick'] = {['name'] = 'pearl_cinnamon_stick', ['label'] = 'Cinnamon Stick', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_cinnamon_stick.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_caramel_syrup'] = {['name'] = 'pearl_caramel_syrup', ['label'] = 'Caramel Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_caramel_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_hazelnut_syrup'] = {['name'] = 'pearl_hazelnut_syrup', ['label'] = 'Hazelnut Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_hazelnut_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_vanilla_icecream'] = {['name'] = 'pearl_vanilla_icecream', ['label'] = 'Vanilla Ice Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_vanilla_icecream.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_icecubes'] = {['name'] = 'pearl_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_waterbottle'] = {['name'] = 'pearl_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_emptycup'] = {['name'] = 'pearl_emptycup', ['label'] = 'Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>Quasar Inventory</summary>

```lua
['pearl_grill_salmon'] = {['name'] = 'pearl_grill_salmon', ['label'] = 'Grilled Salmon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_grill_salmon.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_seared_cod'] = {['name'] = 'pearl_seared_cod', ['label'] = 'Seared Cod', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_seared_cod.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_tilapia'] = {['name'] = 'pearl_tilapia', ['label'] = 'Tilapia', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_tilapia.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_red_snapper'] = {['name'] = 'pearl_red_snapper', ['label'] = 'Red Snapper', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_red_snapper.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_fish_chips'] = {['name'] = 'pearl_fish_chips', ['label'] = 'Fish and Chips', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_fish_chips.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_salsa'] = {['name'] = 'pearl_salsa', ['label'] = 'Mango Salsa', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_salsa.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_sea_bass'] = {['name'] = 'pearl_sea_bass', ['label'] = 'Sea Bass', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_sea_bass.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_tacos'] = {['name'] = 'pearl_tacos', ['label'] = 'Tacos', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_tacos.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_broiled_halibut'] = {['name'] = 'pearl_broiled_halibut', ['label'] = 'Broiled Halibut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_broiled_halibut.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_swordfish_steak'] = {['name'] = 'pearl_swordfish_steak', ['label'] = 'Swordfish Steak', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_swordfish_steak.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_ceviche'] = {['name'] = 'pearl_ceviche', ['label'] = 'Fish Ceviche', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_ceviche.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_salmon'] = {['name'] = 'pearl_salmon', ['label'] = 'Smoked Salmon Crostini', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_salmon.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_tartar'] = {['name'] = 'pearl_tartar', ['label'] = 'Fish Tartar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_tartar.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_fish_cake'] = {['name'] = 'pearl_fish_cake', ['label'] = 'Fish Cakes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_fish_cake.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_shrimp'] = {['name'] = 'pearl_shrimp', ['label'] = 'Shrimp Cocktail', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_shrimp.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_bruschetta'] = {['name'] = 'pearl_bruschetta', ['label'] = 'Anchovy Bruschetta', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_bruschetta.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_skewers'] = {['name'] = 'pearl_skewers', ['label'] = 'Fish Skewers', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_skewers.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_samosa'] = {['name'] = 'pearl_samosa', ['label'] = 'Fish Samosas', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_samosa.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_calamari'] = {['name'] = 'pearl_calamari', ['label'] = 'Calamari', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_calamari.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_tuna_bites'] = {['name'] = 'pearl_tuna_bites', ['label'] = 'Tuna Poke Bites', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_tuna_bites.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_lemonade'] = {['name'] = 'pearl_lemonade', ['label'] = 'Freshly Squeezed Lemonade', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_lemonade.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_iced_tea'] = {['name'] = 'pearl_iced_tea', ['label'] = 'Iced Green Tea', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_iced_tea.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_citrus_water'] = {['name'] = 'pearl_citrus_water', ['label'] = 'Sparkling Water', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_citrus_water.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_fruit'] = {['name'] = 'pearl_fruit', ['label'] = 'Fruit Punch', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_fruit.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_hibiscus_tea'] = {['name'] = 'pearl_hibiscus_tea', ['label'] = 'Hibiscus Tea', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_hibiscus_tea.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_coconut_water'] = {['name'] = 'pearl_coconut_water', ['label'] = 'Fresh Coconut Water', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_coconut_water.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_ale'] = {['name'] = 'pearl_ale', ['label'] = 'Ginger Ale', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_ale.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_lemon_mint'] = {['name'] = 'pearl_lemon_mint', ['label'] = 'Lemon and Mint', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_lemon_mint.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_kombucha'] = {['name'] = 'pearl_kombucha', ['label'] = 'Kombucha', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_kombucha.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_pineapple_juice'] = {['name'] = 'pearl_pineapple_juice', ['label'] = 'Pineapple Juice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_pineapple_juice.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_espresso'] = {['name'] = 'pearl_espresso', ['label'] = 'Espresso', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_espresso.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_americano'] = {['name'] = 'pearl_americano', ['label'] = 'Americano', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_americano.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_cappuccino'] = {['name'] = 'pearl_cappuccino', ['label'] = 'Cappuccino', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_cappuccino.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_latte'] = {['name'] = 'pearl_latte', ['label'] = 'Latte', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_latte.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_mocha'] = {['name'] = 'pearl_mocha', ['label'] = 'Mocha', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_mocha.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_iced_coffee'] = {['name'] = 'pearl_iced_coffee', ['label'] = 'Iced Coffee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_iced_coffee.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_brew'] = {['name'] = 'pearl_brew', ['label'] = 'Iced Brew', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_brew.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_macchiato'] = {['name'] = 'pearl_macchiato', ['label'] = 'Macchiato', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_macchiato.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_flat_white'] = {['name'] = 'pearl_flat_white', ['label'] = 'Flat White', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_flat_white.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_affogato'] = {['name'] = 'pearl_affogato', ['label'] = 'Affogato', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_affogato.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_fillet'] = {['name'] = 'pearl_fillet', ['label'] = 'Fillet', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_fillet.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_garlic_butter'] = {['name'] = 'pearl_garlic_butter', ['label'] = 'Garlic Butter Special Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_garlic_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_herb'] = {['name'] = 'pearl_herb', ['label'] = 'Herb sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_herb.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_parmesan_cheese'] = {['name'] = 'pearl_parmesan_cheese', ['label'] = 'Parmesan cheese', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_parmesan_cheese.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_blackening_seaon'] = {['name'] = 'pearl_blackening_seaon', ['label'] = 'Blackening seasoning ', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_blackening_seaon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_beer_batter'] = {['name'] = 'pearl_beer_batter', ['label'] = 'Beer batter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_beer_batter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_mango_salsa'] = {['name'] = 'pearl_mango_salsa', ['label'] = 'Mango Salsa', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_mango_salsa.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_ginger'] = {['name'] = 'pearl_ginger', ['label'] = 'Ginger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_ginger.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_lime_slaw'] = {['name'] = 'pearl_lime_slaw', ['label'] = 'Lime Slaw ', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_lime_slaw.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_lemon_sauce'] = {['name'] = 'pearl_lemon_sauce', ['label'] = 'Lemon Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_lemon_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_pesto'] = {['name'] = 'pearl_pesto', ['label'] = 'Pesto', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_pesto.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_lemon'] = {['name'] = 'pearl_lemon', ['label'] = 'Lemon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_lemon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_cilantro'] = {['name'] = 'pearl_cilantro', ['label'] = 'Coffee Beans Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_cilantro.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_crostini'] = {['name'] = 'pearl_crostini', ['label'] = 'Crispy Bread', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_crostini.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_soy_sauce'] = {['name'] = 'pearl_soy_sauce', ['label'] = 'Soy Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_soy_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_aioli'] = {['name'] = 'pearl_aioli', ['label'] = 'Aioli', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_aioli.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_cocktail_sauce'] = {['name'] = 'pearl_cocktail_sauce', ['label'] = 'Cocktail Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_cocktail_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_garlic'] = {['name'] = 'pearl_garlic', ['label'] = 'Garlic', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_garlic.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_chilli_sauce'] = {['name'] = 'pearl_chilli_sauce', ['label'] = 'Chili Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_chilli_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_tumeric'] = {['name'] = 'pearl_tumeric', ['label'] = 'Tumeric', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_tumeric.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_wedges'] = {['name'] = 'pearl_wedges', ['label'] = 'Wedges', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_wedges.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_poke_sauce'] = {['name'] = 'pearl_poke_sauce', ['label'] = 'Poke Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_poke_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_ice'] = {['name'] = 'pearl_ice', ['label'] = 'Ice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_ice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_honey'] = {['name'] = 'pearl_honey', ['label'] = 'Honey', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_honey.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_citrus'] = {['name'] = 'pearl_citrus', ['label'] = 'Citrus Slices', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_citrus.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_mixed_fruit'] = {['name'] = 'pearl_mixed_fruit', ['label'] = 'Mixed Fruit Juice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_mixed_fruit.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_coconut'] = {['name'] = 'pearl_coconut', ['label'] = 'Coconut', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_coconut.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_sugar'] = {['name'] = 'pearl_sugar', ['label'] = 'Sugar', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_sugar.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_mint'] = {['name'] = 'pearl_mint', ['label'] = 'Mint', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_mint.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_pineapple'] = {['name'] = 'pearl_pineapple', ['label'] = 'Pineapple', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_pineapple.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_coffee_bean'] = {['name'] = 'pearl_coffee_bean', ['label'] = 'Coffee Beans', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_coffee_bean.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_almond'] = {['name'] = 'pearl_almond', ['label'] = 'Almond Milk', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_almond.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_dark_chocolate'] = {['name'] = 'pearl_dark_chocolate', ['label'] = 'Dark Chocolate', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_dark_chocolate.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_vanilla_syrup'] = {['name'] = 'pearl_vanilla_syrup', ['label'] = 'Vanilla Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_vanilla_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_chocolate_syrup'] = {['name'] = 'pearl_chocolate_syrup', ['label'] = 'Chocolate Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_chocolate_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_whipped_cream'] = {['name'] = 'pearl_whipped_cream', ['label'] = 'Whipped Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_whipped_cream.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_cinnamon_stick'] = {['name'] = 'pearl_cinnamon_stick', ['label'] = 'Cinnamon Stick', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_cinnamon_stick.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_caramel_syrup'] = {['name'] = 'pearl_caramel_syrup', ['label'] = 'Caramel Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_caramel_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_hazelnut_syrup'] = {['name'] = 'pearl_hazelnut_syrup', ['label'] = 'Hazelnut Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_hazelnut_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_vanilla_icecream'] = {['name'] = 'pearl_vanilla_icecream', ['label'] = 'Vanilla Ice Cream', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_vanilla_icecream.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_icecubes'] = {['name'] = 'pearl_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_waterbottle'] = {['name'] = 'pearl_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pearl_emptycup'] = {['name'] = 'pearl_emptycup', ['label'] = 'Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pearl_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>ESX ITems Sql</summary>

```lua
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
    ('pearl_grill_salmon', 'Grilled Salmon', 1, 0, 1),
    ('pearl_seared_cod', 'Seared Cod', 1, 0, 1),
    ('pearl_tilapia', 'Tilapia', 1, 0, 1),
    ('pearl_red_snapper', 'Red Snapper', 1, 0, 1),
    ('pearl_fish_chips', 'Fish and Chips', 1, 0, 1),
    ('pearl_salsa', 'Mango Salsa', 1, 0, 1),
    ('pearl_sea_bass', 'Sea Bass', 1, 0, 1),
    ('pearl_tacos', 'Tacos', 1, 0, 1),
    ('pearl_broiled_halibut', 'Broiled Halibut', 1, 0, 1),
    ('pearl_swordfish_steak', 'Swordfish Steak', 1, 0, 1),
    ('pearl_ceviche', 'Smoked Salmon Crostini', 1, 0, 1),
    ('pearl_salmon', 'Grilled Salmon', 1, 0, 1),
    ('pearl_tartar', 'Fish Tartar', 1, 0, 1),
    ('pearl_fish_cake', 'Fish Cakes', 1, 0, 1),
    ('pearl_shrimp', 'Shrimp Cocktail', 1, 0, 1),
    ('pearl_bruschetta', 'Anchovy Bruschetta', 1, 0, 1),
    ('pearl_skewers', 'Fish Skewers', 1, 0, 1),
    ('pearl_samosa', 'Fish Samosas', 1, 0, 1),
    ('pearl_calamari', 'Calamari', 1, 0, 1),
    ('pearl_tuna_bites', 'Tuna Poke Bites', 1, 0, 1),
    ('pearl_lemonade', 'Freshly Squeezed Lemonade', 1, 0, 1),
    ('pearl_iced_tea', 'Iced Green Tea', 1, 0, 1),
    ('pearl_citrus_water', 'Sparkling Water', 1, 0, 1),
    ('pearl_fruit', 'Fruit Punch', 1, 0, 1),
    ('pearl_hibiscus_tea', 'Hibiscus Tea', 1, 0, 1),
    ('pearl_coconut_water', 'Fresh Coconut Water', 1, 0, 1),
    ('pearl_ale', 'Ginger Ale', 1, 0, 1),
    ('pearl_lemon_mint', 'Lemon and Mint', 1, 0, 1),
    ('pearl_kombucha', 'Kombucha', 1, 0, 1),
    ('pearl_pineapple_juice', 'Pineapple Juice', 1, 0, 1),
    ('pearl_espresso', 'Espresso', 1, 0, 1),
    ('pearl_americano', 'Americano', 1, 0, 1),
    ('pearl_cappuccino', 'Cappuccino', 1, 0, 1),
    ('pearl_latte', 'Latte', 1, 0, 1),
    ('pearl_mocha', 'Mocha', 1, 0, 1),
    ('pearl_iced_coffee', 'Iced Coffee', 1, 0, 1),
    ('pearl_brew', 'Iced Brew', 1, 0, 1),
    ('pearl_macchiato', 'Macchiato', 1, 0, 1),
    ('pearl_flat_white', 'Flat White', 1, 0, 1),
    ('pearl_affogato', 'Affogato', 1, 0, 1),
    ('pearl_fillet', 'Fillet', 1, 0, 1),
    ('pearl_garlic_butter', 'Garlic Butter Special Sauce', 1, 0, 1),
    ('pearl_herb', 'Herb sauce', 1, 0, 1),
    ('pearl_parmesan_cheese', 'Parmesan cheese', 1, 0, 1),
    ('pearl_blackening_seaon', 'Blackening seasoning', 1, 0, 1),
    ('pearl_beer_batter', 'Beer batter', 1, 0, 1),
    ('pearl_mango_salsa', 'Mango Salsa', 1, 0, 1),
    ('pearl_ginger', 'Ginger', 1, 0, 1),
    ('pearl_lime_slaw', 'Lime Slaw', 1, 0, 1),
    ('pearl_lemon_sauce', 'Lemon Sauce', 1, 0, 1),
    ('pearl_pesto', 'Pesto', 1, 0, 1),
    ('pearl_lemon', 'Lemon', 1, 0, 1),
    ('pearl_cilantro', 'Grilled Salmon', 1, 0, 1),
    ('pearl_grill_salmon', 'Coffee Beans Butter', 1, 0, 1),
    ('pearl_crostini', 'Crispy Bread', 1, 0, 1),
    ('pearl_soy_sauce', 'Soy Sauce', 1, 0, 1),
    ('pearl_aioli', 'Aioli', 1, 0, 1),
    ('pearl_cocktail_sauce', 'Cocktail Sauce', 1, 0, 1),
    ('pearl_garlic', 'Garlic', 1, 0, 1),
    ('pearl_chilli_sauce', 'Chili Sauce', 1, 0, 1),
    ('pearl_tumeric', 'Tumeric', 1, 0, 1),
    ('pearl_wedges', 'Wedges', 1, 0, 1),
    ('pearl_poke_sauce', 'Poke Sauce', 1, 0, 1),
    ('pearl_ice', 'Pearls Ice', 1, 0, 1),
    ('pearl_honey', 'Honey', 1, 0, 1),
    ('pearl_citrus', 'Citrus Slices', 1, 0, 1),
    ('pearl_mixed_fruit', 'Mixed Fruit Juice', 1, 0, 1),
    ('pearl_coconut', 'Coconut', 1, 0, 1),
    ('pearl_sugar', 'Sugar', 1, 0, 1),
    ('pearl_mint', 'Mint', 1, 0, 1),
    ('pearl_pineapple', 'Pineapple', 1, 0, 1),
    ('pearl_coffee_bean', 'Coffee Beans', 1, 0, 1),
    ('pearl_almond', 'Almond Milk', 1, 0, 1),
    ('pearl_dark_chocolate', 'Dark Chocolate', 1, 0, 1),
    ('pearl_vanilla_syrup', 'Vanilla Syrup', 1, 0, 1),
    ('pearl_chocolate_syrup', 'Chocolate Syrup', 1, 0, 1),
    ('pearl_whipped_cream', 'Whipped Cream', 1, 0, 1),
    ('pearl_cinnamon_stick', 'Cinnamon Stick', 1, 0, 1),
    ('pearl_caramel_syrup', 'Caramel Syrup', 1, 0, 1),
    ('pearl_hazelnut_syrup', 'Hazelnut Syrup', 1, 0, 1),
    ('pearl_vanilla_icecream', 'Vanilla Ice Cream', 1, 0, 1),
    ('pearl_icecubes', 'Ice Cubes', 1),
    ('pearl_waterbottle', 'Water Bottle', 1),
    ('pearl_emptycup', 'Empty Cup', 1);
```

</details>

### For QBCore Only

{% tabs %}
{% tab title="jobs.lua" %}
Add the Following in qb-core/shared/jobs.lua

```lua
['pearls'] = {
    label = 'Pearls',
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
['pearls'] = {
    label = 'Pearls',
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
    ['pearl_espresso'] = math.random(35, 54),
    ['pearl_americano'] = math.random(35, 54),
    ['pearl_cappuccino'] = math.random(35, 54),
    ['pearl_latte'] = math.random(35, 54),
    ['pearl_mocha'] = math.random(35, 54),
    ['pearl_iced_coffee'] = math.random(35, 54),
    ['pearl_brew'] = math.random(35, 54),
    ['pearl_macchiato'] = math.random(35, 54),
    ['pearl_flat_white'] = math.random(35, 54),
    ['pearl_affogato'] = math.random(35, 54),

    ['pearl_lemonade'] = math.random(35, 54),
    ['pearl_iced_tea'] = math.random(35, 54),
    ['pearl_citrus_water'] = math.random(35, 54),
    ['pearl_fruit'] = math.random(35, 54),
    ['pearl_hibiscus_tea'] = math.random(35, 54),
    ['pearl_coconut_water'] = math.random(35, 54),
    ['pearl_ale'] = math.random(35, 54),
    ['pearl_lemon_mint'] = math.random(35, 54),
    ['pearl_kombucha'] = math.random(35, 54),
    ['pearl_pineapple_juice'] = math.random(35, 54),


}

Config.ConsumablesEat = {
    ['pearl_grill_salmon'] = math.random(35, 54),
    ['pearl_seared_cod'] = math.random(35, 54),
    ['pearl_tilapia'] = math.random(35, 54),
    ['pearl_red_snapper'] = math.random(35, 54),
    ['pearl_fish_chips'] = math.random(35, 54),
    ['pearl_salsa'] = math.random(35, 54),
    ['pearl_sea_bass'] = math.random(35, 54),
    ['pearl_tacos'] = math.random(35, 54),
    ['pearl_broiled_halibut'] = math.random(35, 54),
    ['pearl_swordfish_steak'] = math.random(35, 54),


    ['pearl_ceviche'] = math.random(35, 54),
    ['pearl_salmon'] = math.random(35, 54),
    ['pearl_tartar'] = math.random(35, 54),
    ['pearl_fish_cake'] = math.random(35, 54),
    ['pearl_shrimp'] = math.random(35, 54),
    ['pearl_bruschetta'] = math.random(35, 54),
    ['pearl_skewers'] = math.random(35, 54),
    ['pearl_samosa'] = math.random(35, 54),
    ['pearl_calamari'] = math.random(35, 54),
    ['pearl_tuna_bites'] = math.random(35, 54),


    
}

--If using new qb-smallresources
Config.Consumables = {
    eat = {
        ['pearl_grill_salmon'] = math.random(35, 54),
        ['pearl_seared_cod'] = math.random(35, 54),
        ['pearl_tilapia'] = math.random(35, 54),
        ['pearl_red_snapper'] = math.random(35, 54),
        ['pearl_fish_chips'] = math.random(35, 54),
        ['pearl_salsa'] = math.random(35, 54),
        ['pearl_sea_bass'] = math.random(35, 54),
        ['pearl_tacos'] = math.random(35, 54),
        ['pearl_broiled_halibut'] = math.random(35, 54),
        ['pearl_swordfish_steak'] = math.random(35, 54),


        ['pearl_ceviche'] = math.random(35, 54),
        ['pearl_salmon'] = math.random(35, 54),
        ['pearl_tartar'] = math.random(35, 54),
        ['pearl_fish_cake'] = math.random(35, 54),
        ['pearl_shrimp'] = math.random(35, 54),
        ['pearl_bruschetta'] = math.random(35, 54),
        ['pearl_skewers'] = math.random(35, 54),
        ['pearl_samosa'] = math.random(35, 54),
        ['pearl_calamari'] = math.random(35, 54),
        ['pearl_tuna_bites'] = math.random(35, 54),


        
    },
    drink = {
        ['pearl_espresso'] = math.random(35, 54),
        ['pearl_americano'] = math.random(35, 54),
        ['pearl_cappuccino'] = math.random(35, 54),
        ['pearl_latte'] = math.random(35, 54),
        ['pearl_mocha'] = math.random(35, 54),
        ['pearl_iced_coffee'] = math.random(35, 54),
        ['pearl_brew'] = math.random(35, 54),
        ['pearl_macchiato'] = math.random(35, 54),
        ['pearl_flat_white'] = math.random(35, 54),
        ['pearl_affogato'] = math.random(35, 54),

        ['pearl_lemonade'] = math.random(35, 54),
        ['pearl_iced_tea'] = math.random(35, 54),
        ['pearl_citrus_water'] = math.random(35, 54),
        ['pearl_fruit'] = math.random(35, 54),
        ['pearl_hibiscus_tea'] = math.random(35, 54),
        ['pearl_coconut_water'] = math.random(35, 54),
        ['pearl_ale'] = math.random(35, 54),
        ['pearl_lemon_mint'] = math.random(35, 54),
        ['pearl_kombucha'] = math.random(35, 54),
        ['pearl_pineapple_juice'] = math.random(35, 54),

    },
}
```

</details>

<details>

<summary>Jim Consumables</summary>

Add the following in jim-consumables/shared/consumables.lua

```lua
--jim-consumables/shared/consumables.lua
pearl_grill_salmon = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_seared_cod = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_tilapia = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_red_snapper = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_fish_chips = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_salsa = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_sea_bass = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_tacos = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_broiled_halibut = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_swordfish_steak = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_ceviche = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_salmon = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_tartar = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_fish_cake = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_shrimp = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_bruschetta = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_skewers = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_samosa = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_calamari = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},
pearl_tuna_bites = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20), }},

pearl_lemonade = {emote = "drink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_iced_tea = {emote = "drink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_citrus_water = {emote = "drink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_fruit = {emote = "drink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_hibiscus_tea = {emote = "drink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_coconut_water = {emote = "drink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_ale = {emote = "drink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_lemon_mint = {emote = "drink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_kombucha = {emote = "drink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_pineapple_juice = {emote = "drink", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_espresso = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_americano = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_cappuccino = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_latte = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_mocha = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_iced_coffee = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_brew = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_macchiato = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_flat_white = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
pearl_affogato = {emote = "coffee", 		canRun = false, 	time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { thirst = math.random(10,20), }},
```

</details>

### Add Images to Inventory

Copy all the Images folder and paste it in your inventory Images folder

### Log Webook Setup - Optional

To enable discord logs make sure to add your webhook in the server->Log.lua File

{% embed url="https://www.youtube.com/watch?pp=ygULI2FwcHlxczIwMjM=&v=fKksxz2Gdnc" %}

