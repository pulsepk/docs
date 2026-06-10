# Installation

## 📦 Installation Guide

Follow these steps to install Check Player Money on your FiveM server.

***

### Step 1 — Install Dependencies

Three dependencies are required:

* [pl\_lib](https://github.com/pulsepk/pl_lib) — framework detection, notifications
* [ox\_lib](https://github.com/overextended/ox_lib/releases) — callbacks and UI
* [oxmysql](https://github.com/overextended/oxmysql/releases) — database queries

Place all three folders inside your resources directory.

***

### Step 2 — Add to server.cfg

Add the following `ensure` lines. **Order matters** — dependencies must be started first.

```cfg
ensure oxmysql
ensure ox_lib
ensure pl_lib
ensure pl-checkplayermoney
```

***

### Step 3 — Grant ACE Permission

The command is locked behind the `checkplayermoney` ACE permission. Add the following to your `server.cfg` to grant access:

**Grant to all admins:**
```cfg
add_ace group.admin checkplayermoney allow
```

**Grant to a specific player by Steam ID:**
```cfg
add_principal identifier.steam:YOUR_STEAM_ID_HERE group.admin
```

**Grant to a specific FiveM licence:**
```cfg
add_ace identifier.license:YOUR_LICENSE checkplayermoney allow
```

{% hint style="warning" %}
Without this ACE permission line, no one will be able to use the command — including server owners. Make sure it is added to `server.cfg`.
{% endhint %}

***

### Step 4 — Configure

Open `config.lua`. The only setting is the command name:

```lua
Config.Command = 'checkplayermoney'
```

Change `'checkplayermoney'` to any command name you prefer.

***

### Step 5 — Using the Command

In-game, any player with the `checkplayermoney` ACE runs:

```
/checkplayermoney
```

A menu opens with three options:

| Option | What it does |
|---|---|
| **Check Bank** | Find all players with bank balance above an amount you enter |
| **Check Cash & Crypto** | View bank, cash, and crypto for filtered players |
| **Top Players** | List the top N players ranked by bank balance |

***

{% hint style="success" %}
Done! Admin staff can now run the command to check player money.
{% endhint %}

{% hint style="info" %}
[Join the Discord in case you need additional support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
