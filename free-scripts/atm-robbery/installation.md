# Installation

## 📦 Installation Guide

Follow these steps carefully to install the ATM Robbery script on your FiveM server. If you run into issues, check the [Common Issues](common-issues.md) page or join the [Discord](https://discord.gg/c6gXmtEf3H).

***

### Step 1 — Install pl\_lib

**pl\_lib** is a required bridge library that handles framework detection, inventory, notifications, and targets automatically.

* Download: [https://github.com/pulsepk/pl\_lib](https://github.com/pulsepk/pl_lib)
* Place the `pl_lib` folder inside your resources directory.

***

### Step 2 — Install ox\_lib

**ox\_lib** is required for callbacks, progress bars, and skill checks.

* Download: [https://github.com/overextended/ox\_lib/releases](https://github.com/overextended/ox_lib/releases)
* Place the `ox_lib` folder inside your resources directory.

***

### Step 3 — Install Minigame Resources

Install the minigame(s) you plan to use. You only need the ones you enable in `config.lua`.

| Minigame | Used For | Download |
|---|---|---|
| [M-drilling](https://github.com/MxttDev/M-drilling) | Drill action (default) | Required if `Config.Drilling.Minigame = 'M-drilling'` |
| [utk\_fingerprint](https://github.com/utkuali/Finger-Print-Hacking-Game) | Hack action | Required if `Config.Hacking.Minigame = 'utk_fingerprint'` |
| [ps-ui](https://github.com/Project-Sloth/ps-ui) | Hack action (optional) | Required if using any `ps-ui-*` minigame |

***

### Step 4 — Add Items to Your Inventory

Open the `Install_Me_First` folder inside the script. Use the file that matches your inventory system.

{% tabs %}
{% tab title="ox\_inventory" %}
Open `Install_Me_First/items-ox_inventory.lua` and copy the contents into:

```
ox_inventory/data/items.lua
```

Paste the following entries inside the existing items table:

```lua
["pl_hackingdevice"] = {
    label = "Hacking Device",
    weight = 1,
    stack = true,
    close = true,
},
["pl_drill"] = {
    label = "Drill",
    weight = 1,
    stack = true,
    close = true,
},
["pl_rope"] = {
    label = "Rope",
    weight = 1,
    stack = true,
    close = true,
},
```
{% endtab %}

{% tab title="QBCore (qb-inventory)" %}
Open `Install_Me_First/items-qb-inventory.lua` and copy the contents into:

```
qb-core/shared/items.lua
```

Paste the following entries inside the `QBShared.Items` table:

```lua
['pl_hackingdevice'] = {['name'] = 'pl_hackingdevice', ['label'] = 'Hacking Device', ['weight'] = 10, ['type'] = 'item', ['image'] = 'pl_hackingdevice.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pl_drill']         = {['name'] = 'pl_drill',         ['label'] = 'Drill',           ['weight'] = 10, ['type'] = 'item', ['image'] = 'pl_drill.png',         ['unique'] = false, ['useable'] = true,  ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
['pl_rope']          = {['name'] = 'pl_rope',          ['label'] = 'Rope',            ['weight'] = 10, ['type'] = 'item', ['image'] = 'pl_rope.png',          ['unique'] = false, ['useable'] = true,  ['shouldClose'] = true, ['combinable'] = nil, ['description'] = ''},
```
{% endtab %}

{% tab title="ESX" %}
Open `Install_Me_First/items-esx.sql` and run the SQL against your database using a tool like HeidiSQL or phpMyAdmin.
{% endtab %}
{% endtabs %}

***

### Step 5 — Add Item Images

Open the `Install_Me_First/Images` folder. You will find three images:

* `pl_hackingdevice.png`
* `pl_drill.png`
* `pl_rope.png`

Copy all three images and paste them into your inventory's image directory:

| Inventory | Image Directory |
|---|---|
| ox\_inventory | `ox_inventory/web/images/` |
| qb-inventory | `qb-inventory/html/images/` |
| esx\_inventory | `esx_inventory/html/img/items/` |

{% hint style="warning" %}
If item images don't appear in-game, double-check that the file names match exactly (lowercase, no spaces) and that you restarted the inventory resource after copying.
{% endhint %}

***

### Step 6 — Add to server.cfg

Add the following `ensure` lines to your `server.cfg`. **Order matters** — dependencies must be started before pl-atmrob.

```cfg
ensure ox_lib
ensure pl_lib

# Minigames — only include the ones you use
ensure M-drilling
ensure utk_fingerprint

# Target system — only include the one you use
ensure ox_target
# ensure qb-target

ensure pl-atmrob
```

***

### Step 7 — Configure the Script

Open `shared/config.lua` and adjust the settings to match your server. See the [Config File](config-file.md) page for a full breakdown of every option.

Key things to check first:

* `Config.Hacking.Minigame` — set to the minigame resource you installed
* `Config.Drilling.Minigame` — set to `'M-drilling'` (default) or another minigame
* `Config.Police.required` — set the minimum police count for robberies to start
* `Config.CooldownTimer` — cooldown in seconds between robberies
* `Config.Reward` — set payout amounts to suit your economy

***

{% hint style="success" %}
That's it! Start your server and visit an ATM — you should see the target interaction options appear.
{% endhint %}

{% hint style="info" %}
[Join the Discord in case you need additional support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
