# Installation

### Dependencies

Make Sure all the dependencies are installed.

Required

[<kbd>ox\_lib</kbd>](https://github.com/overextended/ox_lib)

[pl\_christmas\_assets](https://portal.cfx.re/) (Included in Portal or Keymaster)

### Server CFG

```lua
ensure pl_christmas_assets
ensure pl_christmas
```

### Config Setup

Adjust config.lua according to your liking

Make sure to set your textui, Progressbar, Menu

### Items

Add the items into your server

<details>

<summary>Ox Inventory</summary>

```lua
['pl_christmas_gift_red'] = {
    label = 'Christmas Gift Red',
    weight = 1,
    stack = true,
    close = true,
    description = 'A festive red Christmas gift.'
},
['pl_christmas_gift_green'] = {
    label = 'Christmas Gift Green',
    weight = 1,
    stack = true,
    close = true,
    description = 'A festive green Christmas gift.'
},
['pl_christmas_gift_gold'] = {
    label = 'Christmas Gift Gold',
    weight = 1,
    stack = true,
    close = true,
    description = 'A festive gold Christmas gift.'
},
['pl_candy_cane'] = {
    label = 'Christmas Candy Cane',
    weight = 1,
    stack = true,
    close = true,
    description = 'A sweet candy cane.'
},
['pl_christmas_cookie'] = {
    label = 'Christmas Cookie',
    weight = 1,
    stack = true,
    close = true,
    description = 'A tasty Christmas cookie.'
},
['pl_gingerbread'] = {
    label = 'Christmas Gingerbread',
    weight = 1,
    stack = true,
    close = true,
    description = 'A gingerbread treat.'
},
['pl_location_clue'] = {
    label = 'Christmas Location Clue',
    weight = 1,
    stack = true,
    close = true,
    description = 'A clue that hints at a festive location.'
},
['pl_hot_chocolate'] = {
    label = 'Christmas Hot Chocolate',
    weight = 1,
    stack = true,
    close = true,
    description = 'A warm cup of hot chocolate.'
},
```

</details>

<details>

<summary>QBCore</summary>

```lua
['pl_christmas_gift_red'] = {
    ['name'] = 'pl_christmas_gift_red',
    ['label'] = 'Christmas Gift Red',
    ['weight'] = 1,
    ['type'] = 'item',
    ['image'] = 'pl_christmas_gift_red.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'A festive red Christmas gift.'
},

['pl_christmas_gift_green'] = {
    ['name'] = 'pl_christmas_gift_green',
    ['label'] = 'Christmas Gift Green',
    ['weight'] = 1,
    ['type'] = 'item',
    ['image'] = 'pl_christmas_gift_green.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'A festive green Christmas gift.'
},

['pl_christmas_gift_gold'] = {
    ['name'] = 'pl_christmas_gift_gold',
    ['label'] = 'Christmas Gift Gold',
    ['weight'] = 1,
    ['type'] = 'item',
    ['image'] = 'pl_christmas_gift_gold.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'A festive gold Christmas gift.'
},

['pl_candy_cane'] = {
    ['name'] = 'pl_candy_cane',
    ['label'] = 'Christmas Candy Cane',
    ['weight'] = 1,
    ['type'] = 'item',
    ['image'] = 'pl_candy_cane.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'A sweet candy cane.'
},

['pl_christmas_cookie'] = {
    ['name'] = 'pl_christmas_cookie',
    ['label'] = 'Christmas Cookie',
    ['weight'] = 1,
    ['type'] = 'item',
    ['image'] = 'pl_christmas_cookie.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'A tasty Christmas cookie.'
},

['pl_gingerbread'] = {
    ['name'] = 'pl_gingerbread',
    ['label'] = 'Christmas Gingerbread',
    ['weight'] = 1,
    ['type'] = 'item',
    ['image'] = 'pl_gingerbread.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'A gingerbread treat.'
},

['pl_location_clue'] = {
    ['name'] = 'pl_location_clue',
    ['label'] = 'Christmas Location Clue',
    ['weight'] = 1,
    ['type'] = 'item',
    ['image'] = 'pl_location_clue.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'A clue that hints at a festive location.'
},

['pl_hot_chocolate'] = {
    ['name'] = 'pl_hot_chocolate',
    ['label'] = 'Christmas Hot Chocolate',
    ['weight'] = 1,
    ['type'] = 'item',
    ['image'] = 'pl_hot_chocolate.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'A warm cup of hot chocolate.'
},

```

</details>

### Add Images to Inventory

{% file src="../../.gitbook/assets/images.zip" %}

Copy all the Images from above or pl\_christmas->installfolder->images and paste it in your inventory Images folder.

### Log Webook Setup - Optional

To enable discord logs make sure to add your webhook in the server->webhook.lua File

{% embed url="https://youtu.be/fKksxz2Gdnc" %}
