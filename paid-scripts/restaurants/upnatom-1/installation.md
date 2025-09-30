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
CREATE TABLE IF NOT EXISTS `pl_upnatom` (
    `stock` longtext DEFAULT NULL,
    `state` varchar(5) NOT NULL DEFAULT 'open'
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;

 INSERT INTO `addon_account` (name, label, shared) VALUES
	('society_upnatom', 'Up n Atom', 1);

INSERT INTO `datastore` (name, label, shared) VALUES
        ('society_upnatom', 'Up n Atom', 1);

INSERT INTO `jobs` (name, label,whitelisted) VALUES
       ('upnatom', 'Up n Atom',1);

 INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
        ('upnatom',0,'cashier','Cashier',20,'{}','{}'),
        ('upnatom',1,'cook','Cook',40,'{}','{}'),
        ('upnatom',2,'staff','Staff',60,'{}','{}'),
        ('upnatom',3,'manager','Manager',85,'{}','{}'),
        ('upnatom',4,'boss','Owner',100,'{}','{}');
```

</details>

<details>

<summary>QBCore or Qbox</summary>

```lua
CREATE TABLE IF NOT EXISTS `pl_upnatom` (
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
["ua_bbq_chicken"] = {
    label = "BBQ Chicken Burger",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["ua_mustard_beef"] = {
    label = "Mustard Beef Burger",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["ua_glazed_turkey"] = {
    label = "Glazed Turkey Burger",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["ua_spicy_lamb"] = {
    label = "Spic  Lamb Burger",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["ua_sweet_smoky_vegan"] = {
    label = "Sweet & Smoky Vegan Burger",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["ua_butter_fries"] = {
    label = "Butter Fries",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["ua_spicy_glazed"] = {
    label = "Spicy Glazed Fries",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["ua_parmesan_fries"] = {
    label = "Parmesan Fries",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["ua_sweet_cajun"] = {
    label = "Sweet Cajun Fries",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["ua_garlic_fries"] = {
    label = "Garlic Fries",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'burger',
			usetime = 2500,
			notification = 'You ate a delicious burger'
		},
},
["ua_lemon_fizz"] = {
    label = "Lemon Fizz",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["ua_mint_cooler"] = {
    label = "Mint Cooler",
    weight = 1,
    stack = true,
    close = true,
},
["ua_ginger_punch"] = {
    label = "Ginger Punch",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["ua_berry_refresher"] = {
    label = "Berry Refresher",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["ua_tropical_splash"] = {
    label = "Tropica Splash",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["ua_green_tea"] = {
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
["ua_ginger_soda"] = {
    label = "Ginger Soda",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["ua_mint_sparkler"] = {
    label = "Mint Sparkler",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["ua_berry_soda"] = {
    label = "Berry Soda",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["ua_pineapple_pop"] = {
    label = "Pineapple Pop",
    weight = 1,
    client = {
			status = { thirst = 200000 },
			anim = { dict = 'mp_player_intdrink', clip = 'loop_bottle' },
			prop = { model = `prop_ld_can_01`, pos = vec3(0.01, 0.01, 0.06), rot = vec3(5.0, 5.0, -180.5) },
			usetime = 2500,
			notification = 'You quenched your thirst with a sprunk'
		},
},
["ua_bun"] = {
    label = "Burger Bun",
    weight = 1,
    stack = true,
    close = true,
},
["ua_potato"] = {
    label = "Potato",
    weight = 1,
    stack = true,
    close = true,
},
["ua_ice"] = {
    label = "Ice",
    weight = 1,
    stack = true,
    close = true,
},
["ua_lemon"] = {
    label = "Lemon",
    weight = 1,
    stack = true,
    close = true,
},
["ua_bbq_sauce"] = {
    label = "BBQ Sauce",
    weight = 1,
    stack = true,
    close = true,
},
["ua_mustard_sauce"] = {
    label = "Mustard Sauce",
    weight = 1,
    stack = true,
    close = true,
},
["ua_glaze"] = {
    label = "Glaze Sauce",
    weight = 1,
    stack = true,
    close = true,
},
["ua_chili"] = {
    label = "Chili Sauce",
    weight = 1,
    stack = true,
    close = true,
},
["ua_smoked"] = {
    label = "Smoked Sauce",
    weight = 1,
    stack = true,
    close = true,
},
["ua_butter"] = {
    label = "Butter",
    weight = 1,
    stack = true,
    close = true,
},
["ua_parmesan"] = {
    label = "Parmesan Drizzle",
    weight = 1,
    stack = true,
    close = true,
},
["ua_cajun"] = {
    label = "Cajun Sauce",
    weight = 1,
    stack = true,
    close = true,
},
["ua_garlic"] = {
    label = "Garlic Sauce",
    weight = 1,
    stack = true,
    close = true,
},
["ua_lemon_syrup"] = {
    label = "Lemon Syrup",
    weight = 1,
    stack = true,
    close = true,
},
["ua_mint"] = {
    label = "Mint",
    weight = 1,
    stack = true,
    close = true,
},
["ua_ginger"] = {
    label = "Ginger",
    weight = 1,
    stack = true,
    close = true,
},
["ua_berry"] = {
    label = "Berry",
    weight = 1,
    stack = true,
    close = true,
},
["ua_tropical"] = {
    label = "Tropica ",
    weight = 1,
    stack = true,
    close = true,
},
["ua_pineapple"] = {
    label = "Pineapple",
    weight = 1,
    stack = true,
    close = true,
},
["ua_icecubes"] = {
    label = "Ice Cubes",
    weight = 1,
    stack = true,
    close = true,
},
["ua_waterbottle"] = {
    label = "Water Bottle",
    weight = 1,
    stack = true,
    close = true,
},
["ua_emptycup"] = {
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
['ua_bbq_chicken'] = {['name'] = 'ua_bbq_chicken', ['label'] = 'BBQ Chicken Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_bbq_chicken.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_mustard_beef'] = {['name'] = 'ua_mustard_beef', ['label'] = 'Mustard Beef Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_mustard_beef.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_glazed_turkey'] = {['name'] = 'ua_glazed_turkey', ['label'] = 'Glazed Turkey Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_glazed_turkey.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_spicy_lamb'] = {['name'] = 'ua_spicy_lamb', ['label'] = 'Spicy Lamb Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_spicy_lamb.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_sweet_smoky_vegan'] = {['name'] = 'ua_sweet_smoky_vegan', ['label'] = 'Sweet & Smoky Vegan Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_sweet_smoky_vegan.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_butter_fries'] = {['name'] = 'ua_butter_fries', ['label'] = 'Butter Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_butter_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_spicy_glazed'] = {['name'] = 'ua_spicy_glazed', ['label'] = 'Spicy Glazed Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_spicy_glazed.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_parmesan_fries'] = {['name'] = 'ua_parmesan_fries', ['label'] = 'Parmesan Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_parmesan_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_sweet_cajun'] = {['name'] = 'ua_sweet_cajun', ['label'] = 'Sweet Cajun Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_sweet_cajun.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_garlic_fries'] = {['name'] = 'ua_garlic_fries', ['label'] = 'Garlic Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_garlic_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_green_tea'] = {['name'] = 'ua_green_tea', ['label'] = 'Iced Green Tea', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_green_tea.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_mint_cooler'] = {['name'] = 'ua_mint_cooler', ['label'] = 'Mint Cooler', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_mint_cooler.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_ginger_punch'] = {['name'] = 'ua_ginger_punch', ['label'] = 'Ginger Punch', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_ginger_punch.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_berry_refresher'] = {['name'] = 'ua_berry_refresher', ['label'] = 'Berry Refresher', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_berry_refresher.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_tropical_splash'] = {['name'] = 'ua_tropical_splash', ['label'] = 'Tropical Splash', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_tropical_splash.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_lemon_fizz'] = {['name'] = 'ua_lemon_fizz', ['label'] = 'Lemon Fizz', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_lemon_fizz.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_ginger_soda'] = {['name'] = 'ua_ginger_soda', ['label'] = 'Ginger Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_ginger_soda.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_mint_sparkler'] = {['name'] = 'ua_mint_sparkler', ['label'] = 'Mint Sparkler', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_mint_sparkler.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_berry_soda'] = {['name'] = 'ua_berry_soda', ['label'] = 'Berry Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_berry_soda.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_pineapple_pop'] = {['name'] = 'ua_pineapple_pop', ['label'] = 'Pineapple Pop', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_pineapple_pop.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_bun'] = {['name'] = 'ua_bun', ['label'] = 'Burger Bun', ['weight'] = 10, ['type'] = 'item', ['image'] = 'burger_ua_bun.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_potato'] = {['name'] = 'ua_potato', ['label'] = 'Potato', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_potato.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_ice'] = {['name'] = 'ua_ice', ['label'] = 'Ice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_ice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_lemon'] = {['name'] = 'ua_lemon', ['label'] = 'Lemon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_lemon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_bbq_sauce'] = {['name'] = 'ua_bbq_sauce', ['label'] = 'BBQ Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_bbq_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_mustard_sauce'] = {['name'] = 'ua_mustard_sauce', ['label'] = 'Mustard Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_mustard_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_glaze'] = {['name'] = 'ua_glaze', ['label'] = 'Glaze Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_glaze.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_chili'] = {['name'] = 'ua_chili', ['label'] = 'Chili Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_chili.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_smoked'] = {['name'] = 'ua_smoked', ['label'] = 'Smoked Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_smoked.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_butter'] = {['name'] = 'ua_butter', ['label'] = 'Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_parmesan'] = {['name'] = 'ua_parmesan', ['label'] = 'Parmesan Drizzle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_parmesan.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_cajun'] = {['name'] = 'ua_cajun', ['label'] = 'Cajun Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_cajun.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_garlic'] = {['name'] = 'ua_garlic', ['label'] = 'Garlic Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_garlic.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_lemon_syrup'] = {['name'] = 'ua_lemon_syrup', ['label'] = 'Lemon Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_lemon_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_mint'] = {['name'] = 'ua_mint', ['label'] = 'Mint', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_mint.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_ginger'] = {['name'] = 'ua_ginger', ['label'] = 'Ginger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_ginger.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_berry'] = {['name'] = 'ua_berry', ['label'] = 'Berry', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_berry.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_tropical'] = {['name'] = 'ua_tropical', ['label'] = 'Tropical', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_tropical.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_pineapple'] = {['name'] = 'ua_pineapple', ['label'] = 'Pineapple', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_pineapple.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_icecubes'] = {['name'] = 'ua_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_waterbottle'] = {['name'] = 'ua_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_emptycup'] = {['name'] = 'ua_emptycup', ['label'] = 'Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>Quasar Inventory</summary>

```lua
['ua_bbq_chicken'] = {['name'] = 'ua_bbq_chicken', ['label'] = 'BBQ Chicken Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_bbq_chicken.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_mustard_beef'] = {['name'] = 'ua_mustard_beef', ['label'] = 'Mustard Beef Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_mustard_beef.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_glazed_turkey'] = {['name'] = 'ua_glazed_turkey', ['label'] = 'Glazed Turkey Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_glazed_turkey.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_spicy_lamb'] = {['name'] = 'ua_spicy_lamb', ['label'] = 'Spicy Lamb Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_spicy_lamb.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_sweet_smoky_vegan'] = {['name'] = 'ua_sweet_smoky_vegan', ['label'] = 'Sweet & Smoky Vegan Burger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_sweet_smoky_vegan.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_butter_fries'] = {['name'] = 'ua_butter_fries', ['label'] = 'Butter Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_butter_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_spicy_glazed'] = {['name'] = 'ua_spicy_glazed', ['label'] = 'Spicy Glazed Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_spicy_glazed.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_parmesan_fries'] = {['name'] = 'ua_parmesan_fries', ['label'] = 'Parmesan Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_parmesan_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_sweet_cajun'] = {['name'] = 'ua_sweet_cajun', ['label'] = 'Sweet Cajun Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_sweet_cajun.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_garlic_fries'] = {['name'] = 'ua_garlic_fries', ['label'] = 'Garlic Fries', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_garlic_fries.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_green_tea'] = {['name'] = 'ua_green_tea', ['label'] = 'Iced Green Tea', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_green_tea.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_mint_cooler'] = {['name'] = 'ua_mint_cooler', ['label'] = 'Mint Cooler', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_mint_cooler.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_ginger_punch'] = {['name'] = 'ua_ginger_punch', ['label'] = 'Ginger Punch', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_ginger_punch.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_berry_refresher'] = {['name'] = 'ua_berry_refresher', ['label'] = 'Berry Refresher', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_berry_refresher.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_tropical_splash'] = {['name'] = 'ua_tropical_splash', ['label'] = 'Tropical Splash', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_tropical_splash.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_lemon_fizz'] = {['name'] = 'ua_lemon_fizz', ['label'] = 'Lemon Fizz', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_lemon_fizz.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_ginger_soda'] = {['name'] = 'ua_ginger_soda', ['label'] = 'Ginger Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_ginger_soda.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_mint_sparkler'] = {['name'] = 'ua_mint_sparkler', ['label'] = 'Mint Sparkler', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_mint_sparkler.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_berry_soda'] = {['name'] = 'ua_berry_soda', ['label'] = 'Berry Soda', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_berry_soda.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_pineapple_pop'] = {['name'] = 'ua_pineapple_pop', ['label'] = 'Pineapple Pop', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_pineapple_pop.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_bun'] = {['name'] = 'ua_bun', ['label'] = 'Burger Bun', ['weight'] = 10, ['type'] = 'item', ['image'] = 'burger_ua_bun.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_potato'] = {['name'] = 'ua_potato', ['label'] = 'Potato', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_potato.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_ice'] = {['name'] = 'ua_ice', ['label'] = 'Ice', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_ice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_lemon'] = {['name'] = 'ua_lemon', ['label'] = 'Lemon', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_lemon.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_bbq_sauce'] = {['name'] = 'ua_bbq_sauce', ['label'] = 'BBQ Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_bbq_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_mustard_sauce'] = {['name'] = 'ua_mustard_sauce', ['label'] = 'Mustard Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_mustard_sauce.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_glaze'] = {['name'] = 'ua_glaze', ['label'] = 'Glaze Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_glaze.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_chili'] = {['name'] = 'ua_chili', ['label'] = 'Chili Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_chili.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_smoked'] = {['name'] = 'ua_smoked', ['label'] = 'Smoked Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_smoked.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_butter'] = {['name'] = 'ua_butter', ['label'] = 'Butter', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_butter.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_parmesan'] = {['name'] = 'ua_parmesan', ['label'] = 'Parmesan Drizzle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_parmesan.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_cajun'] = {['name'] = 'ua_cajun', ['label'] = 'Cajun Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_cajun.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_garlic'] = {['name'] = 'ua_garlic', ['label'] = 'Garlic Sauce', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_garlic.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_lemon_syrup'] = {['name'] = 'ua_lemon_syrup', ['label'] = 'Lemon Syrup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_lemon_syrup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_mint'] = {['name'] = 'ua_mint', ['label'] = 'Mint', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_mint.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_ginger'] = {['name'] = 'ua_ginger', ['label'] = 'Ginger', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_ginger.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_berry'] = {['name'] = 'ua_berry', ['label'] = 'Berry', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_berry.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_tropical'] = {['name'] = 'ua_tropical', ['label'] = 'Tropical', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_tropical.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_pineapple'] = {['name'] = 'ua_pineapple', ['label'] = 'Pineapple', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_pineapple.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_icecubes'] = {['name'] = 'ua_icecubes', ['label'] = 'Ice Cubes', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_icecubes.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_waterbottle'] = {['name'] = 'ua_waterbottle', ['label'] = 'Water Bottle', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_waterbottle.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['ua_emptycup'] = {['name'] = 'ua_emptycup', ['label'] = 'Empty Cup', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ua_emptycup.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```

</details>

<details>

<summary>ESX ITems Sql</summary>

```lua
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
('ua_bbq_chicken', 'BBQ Chicken Burger', 1),
('ua_mustard_beef', 'Mustard Beef Burger', 1),
('ua_glazed_turkey', 'Glazed Turkey Burger', 1),
('ua_spicy_lamb', 'Spic  Lamb Burger', 1),
('ua_sweet_smoky_vegan', 'Sweet & Smoky Vegan Burger', 1),
('ua_butter_fries', 'Butter Fries', 1),
('ua_spicy_glazed', 'Spicy Glazed Fries', 1),
('ua_parmesan_fries', 'Parmesan Fries', 1),
('ua_sweet_cajun', 'Sweet Cajun Fries', 1),
('ua_garlic_fries', 'Garlic Fries', 1),
('ua_lemon_fizz', 'Lemon Fizz', 1),
('ua_mint_cooler', 'Mint Cooler', 1),
('ua_ginger_punch', 'Ginger Punch', 1),
('ua_berry_refresher', 'Berry Refresher', 1),
('ua_tropical_splash', 'Tropica Splash', 1),
('ua_green_tea', 'Iced Green Tea', 1),
('ua_ginger_soda', 'Ginger Soda', 1),
('ua_mint_sparkler', 'Mint Sparkler', 1),
('ua_berry_soda', 'Berry Soda', 1),
('ua_pineapple_pop', 'Pineapple Pop', 1),
('ua_bun', 'Burger Bun', 1),
('ua_potato', 'Potato', 1),
('ua_ice', 'Ice', 1),
('ua_lemon', 'Lemon', 1),
('ua_bbq_sauce', 'BBQ Sauce', 1),
('ua_mustard_sauce', 'Mustard Sauce', 1),
('ua_glaze', 'Glaze Sauce', 1),
('ua_chili', 'Chili Sauce', 1),
('ua_smoked', 'Smoked Sauce', 1),
('ua_butter', 'Butter', 1),
('ua_parmesan', 'Parmesan Drizzle', 1),
('ua_cajun', 'Cajun Sauce', 1),
('ua_garlic', 'Garlic Sauce', 1),
('ua_lemon_syrup', 'Lemon Syrup', 1),
('ua_mint', 'Mint', 1),
('ua_ginger', 'Ginger', 1),
('ua_berry', 'Berry', 1),
('ua_tropical', 'Tropica ', 1),
('ua_pineapple', 'Pineapple', 1),
('ua_icecubes', 'Ice Cubes', 1),
('ua_waterbottle', 'Water Bottle', 1),
('ua_emptycup', 'Empty Cup', 1);
```

</details>

### For QBCore Only

{% tabs %}
{% tab title="jobs.lua" %}
Add the Following in qb-core/shared/jobs.lua

```lua
['upnatom'] = {
    label = 'Up n Atom',
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
['upnatom'] = {
    label = 'Up n Atom',
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
    ['ua_green_tea'] = math.random(35, 54),
    ['ua_mint_cooler'] = math.random(35, 54),
    ['ua_ginger_punch'] = math.random(35, 54),
    ['ua_berry_refresher'] = math.random(35, 54),
    ['ua_tropical_splash'] = math.random(35, 54),

    ['ua_lemon_fizz'] = math.random(35, 54),
    ['ua_ginger_soda'] = math.random(35, 54),
    ['ua_mint_sparkler'] = math.random(35, 54),
    ['ua_berry_soda'] = math.random(35, 54),
    ['ua_pineapple_pop'] = math.random(35, 54),
    
}

Config.ConsumablesEat = {
    ['ua_bbq_chicken'] = math.random(35, 54),
    ['ua_mustard_beef'] = math.random(35, 54),
    ['ua_glazed_turkey'] = math.random(35, 54),
    ['ua_spicy_lamb'] = math.random(35, 54),
    ['ua_sweet_smoky_vegan'] = math.random(35, 54),

    ['ua_butter_fries'] = math.random(35, 54),
    ['ua_spicy_glazed'] = math.random(35, 54),
    ['ua_parmesan_fries'] = math.random(35, 54),
    ['ua_sweet_cajun'] = math.random(35, 54),
    ['ua_garlic_fries'] = math.random(35, 54),
}

--If using new qb-smallresources
Config.Consumables = {
    eat = {
        ['ua_bbq_chicken'] = math.random(35, 54),
        ['ua_mustard_beef'] = math.random(35, 54),
        ['ua_glazed_turkey'] = math.random(35, 54),
        ['ua_spicy_lamb'] = math.random(35, 54),
        ['ua_sweet_smoky_vegan'] = math.random(35, 54),

        ['ua_butter_fries'] = math.random(35, 54),
        ['ua_spicy_glazed'] = math.random(35, 54),
        ['ua_parmesan_fries'] = math.random(35, 54),
        ['ua_sweet_cajun'] = math.random(35, 54),
        ['ua_garlic_fries'] = math.random(35, 54),

    },
    drink = {
        ['ua_green_tea'] = math.random(35, 54),
        ['ua_mint_cooler'] = math.random(35, 54),
        ['ua_ginger_punch'] = math.random(35, 54),
        ['ua_berry_refresher'] = math.random(35, 54),
        ['ua_tropical_splash'] = math.random(35, 54),

        ['ua_lemon_fizz'] = math.random(35, 54),
        ['ua_ginger_soda'] = math.random(35, 54),
        ['ua_mint_sparkler'] = math.random(35, 54),
        ['ua_berry_soda'] = math.random(35, 54),
        ['ua_pineapple_pop'] = math.random(35, 54),
    },
}
```

</details>

<details>

<summary>Jim Consumables</summary>

Add the following in jim-consumables/shared/consumables.lua

```lua
--jim-consumables/shared/consumables.lua
ua_bbq_chicken = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
ua_mustard_beef = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
ua_glazed_turkey = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
ua_spicy_lamb = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
ua_sweet_smoky_vegan = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
ua_butter_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
ua_spicy_glazed = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
ua_parmesan_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
ua_sweet_cajun = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
ua_garlic_fries = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },

ua_green_tea = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
ua_mint_cooler = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
ua_ginger_punch = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
ua_berry_refresher = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
ua_tropical_splash = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},

ua_lemon_fizz = { emote = "ecola", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
ua_ginger_soda = { emote = "ecola", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
ua_mint_sparkler = { emote = "ecola", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
ua_berry_soda = { emote = "ecola", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
ua_pineapple_pop = { emote = "ecola", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
```

</details>

### Add Images to Inventory

Copy all the Images folder and paste it in your inventory Images folder

### Log Webook Setup - Optional

To enable discord logs make sure to add your webhook in the server->Log.lua File

{% embed url="https://www.youtube.com/watch?pp=ygULI2FwcHlxczIwMjM=&v=fKksxz2Gdnc" %}

### Video of Installation:

{% embed url="https://www.youtube.com/watch?v=rkWxUxoF3_s" %}

