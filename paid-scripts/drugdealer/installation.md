# Installation

## Steps

1. Extract the script to your server resources folder
2. Configure Config.lua according to your liking
3. If you have enabled **LOG** in Config make sure to add the webhook in the Log.lua
4. Make sure you have [OX\_LIB](https://github.com/overextended/ox_lib) Installed already
5. Run the database.sql file into your server's database.
6. ensure 'pl\_drugdealerv2' in the server.cfg
7. Restart the Server

### Additional Steps For QBCore Users only

Make sure the items that you added to the server are added to the qb-core->shared->items.lua

```lua
['weed_white-widow']= {['name'] = 'weed_white-widow',['label'] = 'White Widow 2g',['weight'] = 200,['type'] = 'item',['image'] = 'weed_baggy.png', ['unique'] = false,['useable'] = true,['shouldClose'] = false,['combinable'] = nil,['description'] = 'A weed bag with 2g White Widow'}, 
['weed_og-kush']= {['name'] = 'weed_og-kush',['label'] = 'OGKush 2g',['weight'] = 200,['type'] = 'item',['image'] = 'weed_baggy.png',['unique'] = false, ['useable'] = true,['shouldClose'] = false,['combinable'] = nil, ['description'] = 'A weed bag with 2g OG Kush'}, 
['weed_skunk']= {['name'] = 'weed_skunk',['label'] = 'Skunk 2g',['weight'] = 200,['type'] = 'item',['image'] = 'weed_baggy.png',['unique'] = false, ['useable'] = true,['shouldClose'] = false,['combinable'] = nil,['description'] = 'A weed bag with 2g Skunk'}, 
['meth'] = {['name'] = 'meth',['label'] = 'Meth',['weight'] = 100,['type'] = 'item', ['image'] = 'meth_baggy.png',['unique'] = false, ['useable'] = true,['shouldClose'] = true,['combinable'] = nil,['description'] = 'A baggie of Meth'},
```



{% hint style="info" %}
[Join the Discord in case you need Additional Support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}

