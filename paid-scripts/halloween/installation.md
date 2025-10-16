# Installation

### Dependencies

Make Sure all the dependencies are installed.

Required

[<kbd>ox\_lib</kbd>](https://github.com/overextended/ox_lib)

[<kbd>ox-target</kbd>](https://github.com/overextended/ox_target) <kbd>or</kbd> [<kbd>qb-target</kbd>](https://github.com/qbcore-framework/qb-target)

### Config Setup

Adjust config.lua according to your liking

Make sure to set your textui, Progressbar, Menu

### Items

Add the items into your server

<details>

<summary>Ox Inventory</summary>

```lua
["candycorn"] = {
    label = "Candy Corn",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'prop_cs_burger_01',
			usetime = 2500,
			notification = 'You ate a delicious candy'
		},
},

["pumpkin_lollipop"] = {
    label = "Pumpkin Lollipop",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'prop_cs_burger_01',
			usetime = 2500,
			notification = 'You ate a delicious candy'
		},
},

["ghost_lollipop"] = {
    label = "Ghost Lollipop",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'prop_cs_burger_01',
			usetime = 2500,
			notification = 'You ate a delicious candy'
		},
},

["halloween_toffee"] = {
    label = "Halloween Toffe",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'prop_cs_burger_01',
			usetime = 2500,
			notification = 'You ate a delicious candy'
		},
},
["pumpkin_cookies"] = {
    label = "Pumpkin Cookies",
    weight = 1,
    client = {
			status = { hunger = 200000 },
			anim = 'eating',
			prop = 'prop_cs_burger_01',
			usetime = 2500,
			notification = 'You ate a delicious candy'
		},
},
```

</details>

<details>

<summary>QBCore</summary>

```lua
['candycorn'] = {['name'] = 'candycorn', ['label'] = 'Candy Corn', ['weight'] = 10, ['type'] = 'item', ['image'] = 'candycorn.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Halloween Candies'},
['pumpkin_lollipop'] = {['name'] = 'pumpkin_lollipop', ['label'] = 'Pumpkin Lollipop', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pumpkin_lollipop.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Halloween Candies'},
['ghost_lollipop'] = {['name'] = 'ghost_lollipop', ['label'] = 'Ghost Lollipop', ['weight'] = 10, ['type'] = 'item', ['image'] = 'ghost_lollipop.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Halloween Candies'},
['halloween_toffee'] = {['name'] = 'halloween_toffee', ['label'] = 'Halloween Toffee', ['weight'] = 10, ['type'] = 'item', ['image'] = 'halloween_toffee.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Halloween Candies'},
['pumpkin_cookies'] = {['name'] = 'pumpkin_cookies', ['label'] = 'Pumpkin Cookies', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pumpkin_cookies.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Halloween Candies'},
```

</details>

### Consumables

<details>

<summary>Ox Inventory</summary>

No need to add into any consumables script, the items comes with builtin consumable for ox\_inventory

</details>

<details>

<summary>QB Smallresources</summary>

```lua
--If using old qb-smallresources

Config.ConsumablesEat = {
    ['candycorn'] = math.random(35, 54),
    ['pumpkin_lollipop'] = math.random(35, 54),
    ['ghost_lollipop'] = math.random(35, 54),
    ['halloween_toffee'] = math.random(35, 54),
    ['pumpkin_cookies'] = math.random(35, 54),
}

--If using new qb-smallresources
Config.Consumables = {
    eat = {
    ['candycorn'] = math.random(35, 54),
    ['pumpkin_lollipop'] = math.random(35, 54),
    ['ghost_lollipop'] = math.random(35, 54),
    ['halloween_toffee'] = math.random(35, 54),
    ['pumpkin_cookies'] = math.random(35, 54),
    },
}
```

</details>

### Add Images to Inventory

Copy all the Images folder and paste it in your inventory Images folder

### Log Webook Setup - Optional

To enable discord logs make sure to add your webhook in the server->webhook.lua File

{% embed url="https://youtu.be/fKksxz2Gdnc" %}
