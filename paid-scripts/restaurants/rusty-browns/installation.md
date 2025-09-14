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
CREATE TABLE IF NOT EXISTS `pl_rustybrowns` (
  `stock` longtext DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=armscii8 COLLATE=armscii8_bin;

INSERT INTO `addon_account` (name, label, shared) VALUES
	('society_rustybrowns', 'Rusty Browns', 1);

INSERT INTO `datastore` (name, label, shared) VALUES
	('society_rustybrowns', 'Rusty Browns', 1);

INSERT INTO `jobs` (name, label,whitelisted) VALUES
	('rustybrowns', 'Rusty Browns',1)
;

INSERT INTO `job_grades` (job_name, grade, name, label, salary, skin_male, skin_female) VALUES
	('rustybrowns',0,'cashier','Cashier',20,'{}','{}'),
	('rustybrowns',1,'cook','Cook',40,'{}','{}'),
	('rustybrowns',2,'staff','Staff',60,'{}','{}'),
	('rustybrowns',3,'manager','Manager',85,'{}','{}'),
	('rustybrowns',4,'boss','Owner',100,'{}','{}');
```


{% endtab %}

{% tab title="QBCore" %}
```sql
CREATE TABLE IF NOT EXISTS `pl_rustybrowns` (
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
["berry_glazed_donut"] = {
                label = "Berry Glazed Donut",
                weight = 1,
                stack = true,
                close = true,
},
["chococream_donut"] = {
        label = "Cream Filled Donut",
        weight = 1,
        stack = true,
        close = true,
},
["chocfrosted_donut"] = {
        label = "Chocolate Frosted Donut",
        weight = 1,
        stack = true,
        close = true,
},
["sprinkled_donut"] = {
        label = "Chocolate Sprinkled Donut",
        weight = 1,
        stack = true,
        close = true,
},
["cinnamon_sugar_donut"] = {
        label = "Cinnamon Sugar Donut",
        weight = 1,
        stack = true,
        close = true,
},
["cookiecream_donut"] = {
        label = "Cookies and Cream Donut",
        weight = 1,
        stack = true,
        close = true,
},
["cruller_donut"] = {
        label = "Cruller Donut",
        weight = 1,
        stack = true,
        close = true,
},
["lemon_iced_donut"] = {
        label = "Lemon Iced Donut",
        weight = 1,
        stack = true,
        close = true,
},
["mapple_bar_donut"] = {
        label = "Mapple Bar Donut",
        weight = 1,
        stack = true,
        close = true,
},
["strawberry_iced_donut"] = {
        label = "Strawberry Iced Donut",
        weight = 1,
        stack = true,
        close = true,
},
["iced_caramel_latte"] = {
        label = "Iced Caramel Latte",
        weight = 1,
        stack = true,
        close = true,
},
["mocha_frappe"] = {
        label = "Mocha Frappe",
        weight = 1,
        stack = true,
        close = true,
},
["cold_brew_coffee"] = {
        label = "Rusty Cold Brew Coffee",
        weight = 1,
        stack = true,
        close = true,
},
["iced_matcha_latte"] = {
        label = "Rusty Iced Matcha Latte",
        weight = 1,
        stack = true,
        close = true,
},
["vanilla_iced_coffee"] = {
        label = "Rusty Vanilla Iced Coffee",
        weight = 1,
        stack = true,
        close = true,
},
["strawberry_lemonade_slush"] = {
        label = "Rustys Strawberry Lemonade Slush",
        weight = 1,
        stack = true,
        close = true,
},
["iced_chai_tea_latte"] = {
        label = "Rusty Iced Tea Latte",
        weight = 1,
        stack = true,
        close = true,
},
["iced_mocha"] = {
        label = "Rusty Iced Mocha",
        weight = 1,
        stack = true,
        close = true,
},
["iced_coconut_coffee"] = {
        label = "Rusty Iced Coconut Coffee",
        weight = 1,
        stack = true,
        close = true,
},
["mint_chocolate_chip_milkshake"] = {
        label = "Rusty Mint Chocolate Milkshake",
        weight = 1,
        stack = true,
        close = true,
},
["croissant"] = {
        label = "Croissant",
        weight = 1,
        stack = true,
        close = true,
},
["apple_turnover"] = {
        label = "Apple Turnover",
        weight = 1,
        stack = true,
        close = true,
},
["cinnamon_roll"] = {
        label = "Cinnamon Roll",
        weight = 1,
        stack = true,
        close = true,
},
["eclairs"] = {
        label = "Eclairs",
        weight = 1,
        stack = true,
        close = true,
},
["danish_pastry"] = {
        label = "Danish Pastry",
        weight = 1,
        stack = true,
        close = true,
},
["puff_pastry_tarts"] = {
        label = "Puff Pastry Tart",
        weight = 1,
        stack = true,
        close = true,
},
["chocolate_pastry"] = {
        label = "Chocolate Pastry",
        weight = 1,
        stack = true,
        close = true,
},
["cream_puff"] = {
        label = "Cream Puff",
        weight = 1,
        stack = true,
        close = true,
},
["sticky_bun"] = {
        label = "Sticky Bun",
        weight = 1,
        stack = true,
        close = true,
},
["fruit_strudel"] = {
        label = "Fruit Strudel",
        weight = 1,
        stack = true,
        close = true,
},
["box_donut_a"] = {
        label = "Sprinkled Donut Box",
        weight = 1,
        stack = true,
        close = true,
},
["box_donut_b"] = {
        label = "ChocoCream Donut Box",
        weight = 1,
        stack = true,
        close = true,
},
["box_donut_c"] = {
        label = "Cinnamon Sugar Donut Box",
        weight = 1,
        stack = true,
        close = true,
},
["box_donut_d"] = {
        label = "Lemon Iced Donut Box",
        weight = 1,
        stack = true,
        close = true,
},
["box_donut_e"] = {
        label = "Strawberry Iced Donut Box",
        weight = 1,
        stack = true,
        close = true,
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
```


{% endtab %}

{% tab title="qb-inventory" %}
Add the Following Items in qb-core/shared/items.lua

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
```


{% endtab %}

{% tab title="qs-inventory" %}
Add the Following Item in qs-inventory/shared/items.lua

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
```


{% endtab %}

{% tab title="ESX Inventory" %}
Execute the following query into your database

```sql
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
  ('rs_vanilla_syrup', 'Rustys Vanilla Syrup', 1);
```


{% endtab %}
{% endtabs %}

### Step 5 - For QBCore Only

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


{% endtab %}

{% tab title="management.lua" %}
Add the following in qb-management/client/cl\_config.lua

```lua
['rustybrowns'] = {
    vector3(-1235.366, -1049.747, 12.93)
},
```

If your qb-management doesn't have the above file. Then add in the following qb-management/config.lua

```lua
rustybrowns = {
    vector3(-1235.366, -1049.747, 12.93)
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


{% endtab %}

{% tab title="jim-consumables" %}
Add the following in jim-consumables/config.lua

```lua
["berry_glazed_donut"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["chococream_donut"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["chocfrosted_donut"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["sprinkled_donut"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["cinnamon_sugar_donut"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["cookiecream_donut"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["cruller_donut"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["lemon_iced_donut"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["mapple_bar_donut"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["strawberry_iced_donut"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["croissant"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["apple_turnover"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["cinnamon_roll"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["eclairs"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["bg_danish_pastry"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["puff_pastry_tarts"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["chocolate_pastry"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["cream_puff"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["sticky_bun"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },
["fruit_strudel"] = { emote = "donut", canRun = false, time = math.random(5000, 6000), stress = math.random(1, 2), heal = 0, armor = 0, type = "food",stats = { hunger = math.random(10,20) } },

["cc_espresso"] = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["mocha_frappe"] = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["cold_brew_coffee"] = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["iced_matcha_latte"] = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["vanilla_iced_coffee"] = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["strawberry_lemonade_slush"] = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["iced_chai_tea_latte"] = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["iced_mocha"] = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["iced_coconut_coffee"] = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},
["mint_chocolate_chip_milkshake"] = {emote = "coffee",canRun = false,time = math.random(5000, 6000), stress = math.random(2, 4), heal = 0, armor = 0, type = "drink", stats = { effect = "stamina", time = 10000, thirst = math.random(10,20), }},

--Add this in the emotes below
["donut"] = {"mp_player_inteat@burger", "mp_player_int_eat_burger", "Donut", AnimationOptions ={ Prop = "prop_amb_donut", PropBone = 18905, PropPlacement = {0.13, 0.05, 0.02, -50.0, 16.0, 60.0},EmoteMoving = true, EmoteLoop = true, }},
```
{% endtab %}

{% tab title="esx_basicneeds" %}
Add the following in esx\_basicneeds->config.lua

```lua
Config.Items = {
    ["berry_glazed_donut"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["chococream_donut"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["chocfrosted_donut"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["sprinkled_donut"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["cinnamon_sugar_donut"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["cookiecream_donut"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["cruller_donut"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["lemon_iced_donut"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["mapple_bar_donut"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["strawberry_iced_donut"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["croissant"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["apple_turnover"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["cinnamon_roll"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["eclairs"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["bg_danish_pastry"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["puff_pastry_tarts"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["chocolate_pastry"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["cream_puff"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["sticky_bun"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },
    ["fruit_strudel"] = {
        type = "food",
        prop= "prop_cs_burger_01",
        status = 200000,
        remove = true
    },

    --Drinks
    ["iced_caramel_latte"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["mocha_frappe"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["cold_brew_coffee"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["iced_matcha_latte"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["vanilla_iced_coffee"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["strawberry_lemonade_slush"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["iced_chai_tea_latte"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["iced_mocha"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["iced_coconut_coffee"] = {
        type = "drink",
        prop= "prop_ld_flow_bottle",
        status = 200000,
        remove = true
    },
    ["mint_chocolate_chip_milkshake"] = {
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





