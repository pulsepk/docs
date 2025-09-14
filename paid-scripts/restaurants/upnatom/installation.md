# Installation

## Step 1

Make Sure all the dependencies are installed.

Required

[<kbd>ox\_lib</kbd>](https://github.com/overextended/ox_lib)

[<kbd>ox-target</kbd>](https://github.com/overextended/ox_target) <kbd>or</kbd> [<kbd>qb-target</kbd>](https://github.com/qbcore-framework/qb-target)

### Step 2

Adjust config.lua according to your liking

Make sure to set your target, clothing, billing, inventory script

### Step 3

Now execute this query into your server database using heidisql or phpmyadmin.

{% tabs %}
{% tab title="ESX" %}
```sql
CREATE TABLE IF NOT EXISTS `pl_upnatom` (
  `stock` longtext DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;

INSERT INTO `addon_account` (name, label, shared) VALUES
	('society_upnatom', 'Up n Atom', 1);

INSERT INTO `datastore` (name, label, shared) VALUES
	('society_upnatom', 'Up n Atom', 1);

INSERT INTO `jobs` (name, label,whitelisted) VALUES
	('upnatom', 'Up n Atom',1)
;

INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
	('upnatom',0,'cashier','Cashier',20,'{}','{}'),
	('upnatom',1,'cook','Cook',40,'{}','{}'),
	('upnatom',2,'staff','Staff',60,'{}','{}'),
	('upnatom',3,'manager','Manager',85,'{}','{}'),
	('upnatom',4,'boss','Owner',100,'{}','{}')
;
```


{% endtab %}

{% tab title="QBCore" %}
```sql
CREATE TABLE IF NOT EXISTS `pl_upnatom` (
  `stock` longtext DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;
```


{% endtab %}
{% endtabs %}

### Step 4

Add the items into your server

{% tabs %}
{% tab title="Ox-Inventory" %}
Add the Following Items in ox\_inventory/data/items.lua

```lua
["ua_bbq_chicken"] = {
    label = "BBQ Chicken Burger",
    weight = 1,
    stack = true,
    close = true,
},
["ua_mustard_beef"] = {
    label = "Mustard Beef Burger",
    weight = 1,
    stack = true,
    close = true,
},
["ua_glazed_turkey"] = {
    label = "Glazed Turkey Burger",
    weight = 1,
    stack = true,
    close = true,
},
["ua_spicy_lamb"] = {
    label = "Spic  Lamb Burger",
    weight = 1,
    stack = true,
    close = true,
},
["ua_sweet_smoky_vegan"] = {
    label = "Sweet & Smoky Vegan Burger",
    weight = 1,
    stack = true,
    close = true,
},
["ua_butter_fries"] = {
    label = "Butter Fries",
    weight = 1,
    stack = true,
    close = true,
},
["ua_spicy_glazed"] = {
    label = "Spicy Glazed Fries",
    weight = 1,
    stack = true,
    close = true,
},
["ua_parmesan_fries"] = {
    label = "Parmesan Fries",
    weight = 1,
    stack = true,
    close = true,
},
["ua_sweet_cajun"] = {
    label = "Sweet Cajun Fries",
    weight = 1,
    stack = true,
    close = true,
},
["ua_garlic_fries"] = {
    label = "Garlic Fries",
    weight = 1,
    stack = true,
    close = true,
},
["ua_lemon_fizz"] = {
    label = "Lemon Fizz",
    weight = 1,
    stack = true,
    close = true,
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
    stack = true,
    close = true,
},
["ua_berry_refresher"] = {
    label = "Berry Refresher",
    weight = 1,
    stack = true,
    close = true,
},
["ua_tropical_splash"] = {
    label = "Tropica Splash",
    weight = 1,
    stack = true,
    close = true,
},
["ua_green_tea"] = {
    label = "Iced Green Tea",
    weight = 1,
    stack = true,
    close = true,
},
["ua_ginger_soda"] = {
    label = "Ginger Soda",
    weight = 1,
    stack = true,
    close = true,
},
["ua_mint_sparkler"] = {
    label = "Mint Sparkler",
    weight = 1,
    stack = true,
    close = true,
},
["ua_berry_soda"] = {
    label = "Berry Soda",
    weight = 1,
    stack = true,
    close = true,
},
["ua_pineapple_pop"] = {
    label = "Pineapple Pop",
    weight = 1,
    stack = true,
    close = true,
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
```


{% endtab %}

{% tab title="qb-inventory" %}
Add the Following Items in qb-core/shared/items.lua

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
```


{% endtab %}

{% tab title="qs-inventory" %}
Add the Following Item in qs-inventory/shared/items.lua

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
```


{% endtab %}

{% tab title="ESX Inventory" %}
Execute the following query into your database

```sql
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
('ua_pineapple', 'Pineapple', 1);
```


{% endtab %}
{% endtabs %}

### Step 5 - For QBCore Only

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


{% endtab %}

{% tab title="management.lua" %}
Add the following in qb-management/client/cl\_config.lua

```lua
['upnatom'] = {
    vector3(81.77, 296.29, 110.25)
},
```

If your qb-management doesn't have the above file. Then add in the following qb-management/config.lua

```lua
upnatom = {
    vector3(81.77, 296.29, 110.25)
},
```


{% endtab %}
{% endtabs %}

### Step 6 - Consumables

{% tabs %}
{% tab title="qb-smallresources" %}
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


{% endtab %}

{% tab title="jim-consumables" %}
Add the following in jim-consumables/config.lua

```lua
["ua_bbq_chicken"] = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["ua_mustard_beef"] = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["ua_glazed_turkey"] = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["ua_spicy_lamb"] = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["ua_sweet_smoky_vegan"] = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["ua_butter_fries"] = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["ua_spicy_glazed"] = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["ua_parmesan_fries"] = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["ua_sweet_cajun"] = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["ua_garlic_fries"] = { emote = "burger", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },

["ua_green_tea"] = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["ua_mint_cooler"] = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["ua_ginger_punch"] = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["ua_berry_refresher"] = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["ua_tropical_splash"] = { emote = "coffee", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},

["ua_lemon_fizz"] = { emote = "ecola", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["ua_ginger_soda"] = { emote = "ecola", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["ua_mint_sparkler"] = { emote = "ecola", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["ua_berry_soda"] = { emote = "ecola", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["ua_pineapple_pop"] = { emote = "ecola", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "drink",stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
```
{% endtab %}

{% tab title="esx_basicneeds" %}
Add the following in esx\_basicneeds->config.lua

```lua
Config.Items = {
    ["ua_bbq_chicken"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["ua_mustard_beef"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["ua_glazed_turkey"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["ua_spicy_lamb"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["ua_sweet_smoky_vegan"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["ua_butter_fries"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["ua_spicy_glazed"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["ua_parmesan_fries"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["ua_sweet_cajun"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["ua_garlic_fries"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    
    ["ua_green_tea"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["ua_mint_cooler"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["ua_ginger_punch"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["ua_berry_refresher"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["ua_tropical_splash"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["ua_lemon_fizz"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["ua_ginger_soda"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["ua_mint_sparkler"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["ua_berry_soda"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["ua_pineapple_pop"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
}
```


{% endtab %}
{% endtabs %}

### Step 7

Copy all the Images folder and paste it in your inventory Images folder

### Step 8 - Optional

To enable discord logs make sure to add your webhook in the server->Log.lua File

{% embed url="https://www.youtube.com/watch?pp=ygULI2FwcHlxczIwMjM=&v=fKksxz2Gdnc" %}





