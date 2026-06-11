# Installation

## 📦 Installation Guide

***

### Step 1 — Download

Choose your version from the [README](./):

* **Escrow (Free)** — [pulsescripts.com/product/hudv1](https://pulsescripts.com/product/hudv1)
* **Open Source (Paid)** — [pulsescripts.com/product/hudv1opensource](https://pulsescripts.com/product/hudv1opensource)

Extract the folder and place `pl_hud` inside your server's `resources` directory.

***

### Step 2 — Add to server.cfg

```cfg
ensure pl_lib
ensure pl_hud
```

{% hint style="warning" %}
`pl_lib` must be ensured **before** `pl_hud`. If pl\_lib hasn't loaded yet, framework detection will fail and all HUD stats will show as 0.
{% endhint %}

***

### Step 3 — Configure

Open `shared/config.lua` and adjust the settings to your server:

**Minimap**

```lua
Config.AlwaysShowMinimap = false  -- true = always visible, false = only in vehicles
Config.Maptype           = 'square'  -- 'square' or 'circle'
```

**Speed**

```lua
Config.SpeedUnit = 'mph'  -- 'mph' or 'kmh'
```

**Seatbelt**

```lua
Config.SeatbeltEnabled      = true   -- enable/disable the seatbelt mechanic entirely
Config.SeatbeltNotification = true   -- show a notification when seatbelt is toggled
Config.SeatbeltToggleKey    = 29     -- 29 = B key
```

**Lights toggle key**

```lua
Config.LightToggleKey = 74  -- 74 = H key
```

{% hint style="info" %}
Key values are FiveM control indices, not keyboard scan codes. You can find the full list at the [FiveM controls reference](https://docs.fivem.net/docs/game-references/controls/).
{% endhint %}

**Custom fuel resource**

By default, the HUD reads fuel using the native `GetVehicleFuelLevel`. If you use a custom fuel script, override the function at the bottom of `config.lua`:

{% tabs %}
{% tab title="LegacyFuel" %}
```lua
GetVehFuel = function(veh)
    return exports['LegacyFuel']:GetFuel(veh)
end
```
{% endtab %}

{% tab title="ox_fuel" %}
```lua
GetVehFuel = function(veh)
    return Entity(veh).state.fuel
end
```
{% endtab %}

{% tab title="Default (no custom fuel)" %}
```lua
GetVehFuel = function(veh)
    return GetVehicleFuelLevel(veh)
end
```
{% endtab %}
{% endtabs %}

***

### Step 4 — Restart and test

Start or restart your server. Join in-game — the HUD will appear automatically once your character loads. Enter a vehicle to see the vehicle dashboard.

***

{% hint style="success" %}
Done! No database setup, no items, and no additional dependencies beyond pl\_lib.
{% endhint %}

{% hint style="info" %}
[Join the Discord in case you need additional support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
