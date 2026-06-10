# Installation

## 📦 Installation Guide

Follow these steps to install the Fraud script on your FiveM server. If you run into problems, check the [Common Issues](common-issues.md) page or join the [Discord](https://discord.gg/c6gXmtEf3H).

***

### Step 1 — Install Dependencies

**pl\_lib** and **ox\_lib** are required.

* [pl\_lib](https://github.com/pulsepk/pl_lib) — framework bridge (handles notifications, targets, framework detection)
* [ox\_lib](https://github.com/overextended/ox_lib/releases) — required for callbacks and progress bars

Place both folders inside your resources directory.

***

### Step 2 — Install the Hacking Minigame

Install the minigame you plan to use. You only need one.

| Minigame | Download |
|---|---|
| [datacrack](https://github.com/utkuali/datacrack) | Default — required unless you switch to another |
| [ps-ui](https://github.com/Project-Sloth/ps-ui) | Required if using any `ps-ui-*` minigame |

***

### Step 3 — Add Items to Your Inventory

Open the `Install` folder inside the script. Use the file that matches your inventory system.

{% tabs %}
{% tab title="ox\_inventory" %}
Open `Install/items_ox_inventory.lua` and paste the contents into:

```
ox_inventory/data/items.lua
```

```lua
["clone_card"] = {
    label  = "Clone Card",
    weight = 5,
    stack  = true,
    close  = true,
},
["fuelcan"] = {
    label  = "Fuel Can",
    weight = 10,
    stack  = true,
    close  = true,
},
["laptop"] = {
    label  = "Laptop",
    weight = 10,
    stack  = true,
    close  = true,
    server = { export = "pl_fraud.laptop" }
},
["printer"] = {
    label  = "Printer",
    weight = 10,
    stack  = true,
    close  = true,
    server = { export = "pl_fraud.printer" }
},
["generator"] = {
    label  = "Generator",
    weight = 10,
    stack  = true,
    close  = true,
    server = { export = "pl_fraud.generator" }
},
```
{% endtab %}

{% tab title="QBCore (qb-inventory)" %}
Open `Install/items_qb-inventory.lua` and paste the contents into:

```
qb-core/shared/items.lua
```
{% endtab %}

{% tab title="ESX" %}
Open `Install/items.sql` and run it against your server database using HeidiSQL or phpMyAdmin.
{% endtab %}
{% endtabs %}

***

### Step 4 — Add Item Images

Copy all images from `Install/Img/` into your inventory's image directory:

| Inventory | Image Directory |
|---|---|
| ox\_inventory | `ox_inventory/web/images/` |
| qb-inventory | `qb-inventory/html/images/` |
| esx\_inventory | `esx_inventory/html/img/items/` |

The images to copy are: `clone_card.png`, `fuelcan.png`, `laptop.png`, `printer.png`, `generator.png`

Restart your inventory resource after copying.

***

### Step 5 — Add to server.cfg

```cfg
ensure ox_lib
ensure pl_lib

# Minigame — only include the one you use
ensure datacrack
# ensure ps-ui

ensure pl_fraud
```

***

### Step 6 — Configure the Script

Open `config.lua` and adjust the settings. See the [Config File](config-file.md) page for a full breakdown.

Key things to check first:

* `Config.Hacking.Minigame` — set to the minigame resource you installed
* `Config.Rewards.amount` — payout for a successful fraud
* `Config.Rewards.moneytype` — `'money'`, `'black_money'`, or `'markedbills'`
* `Config.Shop.coords` — move the NPC shop to a location that suits your server
* `Config.Dispatch.enable` — set to `true` if you want police alerts

***

{% hint style="success" %}
Done! Players can now purchase fraud items from the shop and begin scam operations near ATMs.
{% endhint %}

{% hint style="info" %}
[Join the Discord in case you need additional support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
