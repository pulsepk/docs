# Installation

## 📦 Installation Guide

Follow these simple steps to set up the Wheel Lock on your FiveM server.

***

### Step 1: Install Dependencies

* Add the following resources to your `server.cfg`:
  * [ox\_lib](https://github.com/overextended/ox_lib)

### Step 2: Add Items

* Open the file:

```
items_ox_inventory.lua, items_qb_inventory.lua
```

* Copy its contents into your inventory item configuration:
  * **For QBCore**: `qb-core/shared/items.lua`
  * **For ox\_inventory**: `ox_inventory/data/items.lua`

### Step 3: Add Inventory Images

* Open the folder:\
  `Install/Img`
* Copy all images and paste them into your inventory's image directory:
  * **For QBCore**: `qb-inventory/html/images/`
  * **For ox\_inventory**: `ox_inventory/web/images/`

### Step 4: Configure the Script

* Open the `config.lua` file in the script directory.
* Adjust the settings according to your server's setup:
  * **Choose the framework:** `esx` or `qbcore or qbox`
  * **Choose the target system:** `qb-target or ox_target`
  * **Select the dispatch system:** `ps-dispatch`, `aty_dispatch, qbcore`

{% hint style="info" %}
[Join the Discord in case you need Additional Support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}

