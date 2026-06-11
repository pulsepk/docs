# Installation

***

### Step 1 — Download

Clone or download from GitHub:

[https://github.com/pulsepk/pl_lib](https://github.com/pulsepk/pl_lib)

Place the `pl_lib` folder inside your server's `resources` directory.

***

### Step 2 — Add to server.cfg

pl\_lib requires **ox\_lib** as a dependency. Both must be ensured before any script that depends on pl\_lib.

```cfg
ensure oxmysql       # if used by your scripts
ensure ox_lib
ensure pl_lib

# your scripts below
ensure pl_fraud
ensure pl_hud
ensure pl-atmrob
```

{% hint style="danger" %}
`pl_lib` must be started **before every script that uses it**. If pl\_lib is not running when a dependent script starts, framework detection will fail and all features will silently not work.
{% endhint %}

***

### Step 3 — Verify detection

Open `pl_lib/config/config.lua` and temporarily enable debug mode:

```lua
PLLib.Debug = true
```

Restart the server. On startup, pl\_lib will print which framework, inventory, target, notify, and other systems it detected. Confirm the output matches your server setup, then set `PLLib.Debug = false`.

***

### Step 4 — Configure (optional)

By default everything is set to `'autodetect'`. You only need to change a setting if autodetect picks the wrong system or you want to force a specific one.

See the [Configuration](configuration.md) page for all available options.

***

{% hint style="success" %}
Done. All Pulse scripts and any resource that depends on pl\_lib will now use the detected systems automatically.
{% endhint %}

{% hint style="info" %}
[Join the Discord for support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
