# Installation

## Steps

1. Extract the script to your server resources folder.
2. Configure Config.lua according to your liking.
3. Goto installfolder and execute the database.sql file into your server database using heidisql or phpmyadmin.
4. For QBCore copy the items from items\_QBCore.lua and paste into qb-core->shared->items.lua.

> If you are using older version of qb-inventory like less then 2.0.0. You need to add the below code in qb-inventory/html/js/app.js

```javascript
} else if (itemData.name == "paper") {
            $(".item-info-title").html("<p>" + itemData.label + "</p>");
            $(".item-info-description").html(
                "<p><strong>ID: </strong><span>" +
                itemData.info.id +
                "</span></p>"
            );
```

5. For Ox\_inventory add the items in ox\_inventory->data->items.lua.
6. Copy the image paper.png and add it to your inventory images folder.
7. Make sure you have OX\_LIB Installed already.
8. ensure 'pl\_printer' in the server.cfg

> This Script only supports with metadata

{% hint style="info" %}
[Join the Discord in case you need Additional Support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}

