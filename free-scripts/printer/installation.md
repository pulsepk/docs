# Installation

## 📦 Installation Guide

Follow these steps to install the Printer script on your FiveM server. If you run into problems, check the [Common Issues](common-issues.md) page or join the [Discord](https://discord.gg/c6gXmtEf3H).

***

### Step 1 — Install Dependencies

**pl\_lib** and **oxmysql** are required. Install them if you haven't already.

* [pl\_lib](https://github.com/pulsepk/pl_lib) — framework bridge (handles notifications, inventory, framework detection)
* [oxmysql](https://github.com/overextended/oxmysql/releases) — database connector for storing print history

Place both folders inside your resources directory.

***

### Step 2 — Run the Database Migration

Open the `installfolder/database.sql` file and run it against your server database using HeidiSQL, phpMyAdmin, or any SQL client. This creates the table used to store printed documents.

***

### Step 3 — Add the Paper Item

Open the `installfolder` folder. Use the file that matches your inventory system.

{% tabs %}
{% tab title="ox\_inventory" %}
Open `installfolder/items_Oxinventory.lua` and paste the contents into:

```
ox_inventory/data/items.lua
```

```lua
["paper"] = {
    label   = "Paper",
    weight  = 1,
    stack   = false,
    close   = true,
    consume = 0,
    server  = {
        export = 'pl_printer.paper'
    }
},
```

{% hint style="warning" %}
The `server.export` line is required — it tells ox\_inventory to call the printer's export when the item is used, which displays the document content. Do not remove it.
{% endhint %}
{% endtab %}

{% tab title="QBCore (qb-inventory)" %}
Open `installfolder/items_QBCore.lua` and paste the contents into:

```
qb-core/shared/items.lua
```
{% endtab %}

{% tab title="ESX" %}
ESX does not require a separate item file. Paper items are created dynamically via the database. No item registration step needed.
{% endtab %}
{% endtabs %}

***

### Step 4 — Add the Paper Image

Copy `installfolder/paper.png` into your inventory's image directory:

| Inventory | Image Directory |
|---|---|
| ox\_inventory | `ox_inventory/web/images/` |
| qb-inventory | `qb-inventory/html/images/` |

Restart your inventory resource after copying.

***

### Step 5 — Add to server.cfg

```cfg
ensure oxmysql
ensure pl_lib
ensure pl_printer
```

***

### Step 6 — Configure the Script

Open `config.lua` and adjust the settings. See the [Config File](config-file.md) page for a full breakdown.

Key settings to check:

* `Config.Print.Price` — how much is deducted per print
* `Config.Print.Account` — `'bank'` or `'cash'`
* `Config.EnableLocation` — `true` to spawn printers at fixed coords, `false` for portable item mode
* `Config.Locations` — add printer spawn locations when `EnableLocation = true`

***

{% hint style="success" %}
Done! Players can now interact with printer props to print documents.
{% endhint %}

{% hint style="info" %}
[Join the Discord in case you need additional support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
