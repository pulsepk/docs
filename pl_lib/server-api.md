# Server API

This page covers: framework detection, player money, player status, society banking, dispatch, and logging.

***

## Framework Detection

Detect which framework and systems are running. Available on both client and server.

```lua
local framework = exports.pl_lib:GetFramework()
-- returns: 'qbox' | 'qb' | 'esx' | nil

local target  = exports.pl_lib:GetTarget()
local notify  = exports.pl_lib:GetNotify()
local dispatch = exports.pl_lib:GetDispatch()
```

**Check if a specific resource is running:**
```lua
local ok = exports.pl_lib:CheckDependency('ox_inventory', '2.0.0')
-- returns true if the resource is running and meets minimum version
```

***

## GetPlayerData — Client

Get the local player's framework data (job, money, identity).

```lua
-- CLIENT ONLY
local playerData = exports.pl_lib:GetPlayerData()
local job        = exports.pl_lib:GetPlayerDataJob()
local gender     = exports.pl_lib:GetPlayerGender()
-- gender returns: 'male' | 'female'
```

The shape of `playerData` matches your framework's native player object (QB PlayerData / ESX PlayerData).

***

## Player Money — Server

Add or remove money from a player's account.

```lua
-- SERVER ONLY
exports.pl_lib:AddPlayerMoney(src, account, amount, reason)
exports.pl_lib:RemovePlayerMoney(src, account, amount, reason)
```

| Parameter | Type | Description |
|---|---|---|
| `src` | number | Player server ID |
| `account` | string | `'money'` (cash) \| `'bank'` \| `'dirty'` |
| `amount` | number | Amount to add/remove |
| `reason` | string | Transaction reason (optional, used for logs) |

**Check if a player has enough:**
```lua
-- SERVER ONLY
local hasEnough = exports.pl_lib:GetPlayerAccountMoney(src, 'bank', 500)
-- returns true if the player has at least 500 in bank
```

**Examples:**
```lua
-- Pay a player $1,000 in cash
exports.pl_lib:AddPlayerMoney(src, 'money', 1000, 'ATM robbery reward')

-- Charge $500 from bank
local canAfford = exports.pl_lib:GetPlayerAccountMoney(src, 'bank', 500)
if canAfford then
    exports.pl_lib:RemovePlayerMoney(src, 'bank', 500, 'Purchase')
end
```

{% hint style="info" %}
`'dirty'` maps to `markedbills` (QBox via ox\_inventory), or `black_money` (ESX). Use it for illegal activity payouts.
{% endhint %}

***

## SetPlayerStatus — Server

Modify a player's hunger and thirst.

```lua
-- SERVER ONLY
exports.pl_lib:SetPlayerStatus(src, hunger, thirst)
```

| Parameter | Type | Description |
|---|---|---|
| `src` | number | Player server ID |
| `hunger` | number | Points to ADD to hunger (0 = no change) |
| `thirst` | number | Points to ADD to thirst (0 = no change) |

**Example:**
```lua
-- Increase hunger by 20, leave thirst unchanged
exports.pl_lib:SetPlayerStatus(src, 20, 0)
```

***

## Society Banking — Server

Manage money in a job/organisation account.

```lua
-- SERVER ONLY
exports.pl_lib:AddSocietyMoney(account, amount)
exports.pl_lib:RemoveSocietyMoney(account, amount)
local balance = exports.pl_lib:GetSocietyMoney(account)
```

| Parameter | Type | Description |
|---|---|---|
| `account` | string | Society account name (e.g. `'police'`, `'ambulance'`) |
| `amount` | number | Amount to add/remove |

**Example:**
```lua
-- Fine collected — add to police society
exports.pl_lib:AddSocietyMoney('police', 500)

local funds = exports.pl_lib:GetSocietyMoney('police')
print('Police funds: $' .. funds)
```

**Supported systems:** Renewed-Banking, esx\_addonaccount, qb-management, qb-banking, okokBanking, snipe-banking, tgiann-bank

Configure via `PLLib.Society` in `config.lua`.

***

## SendDispatch — Client

Send an alert to police dispatch.

```lua
-- CLIENT ONLY
exports.pl_lib:SendDispatch(opts)
```

| Field | Type | Default | Description |
|---|---|---|---|
| `title` | string | — | Alert title shown to officers |
| `code` | string | — | Police code (e.g. `'10-90'`) |
| `message` | string | — | Alert description |
| `coords` | vector3 | player position | Location of the incident |
| `jobs` | table | `{ 'police' }` | Which jobs receive the alert |
| `sprite` | number | `431` | Map blip sprite |
| `color` | number | `1` | Map blip color |
| `scale` | number | `1.0` | Map blip scale |
| `radius` | number | `0` | Blip radius |
| `length` | number | `3` | Blip duration in minutes |

**Example:**
```lua
exports.pl_lib:SendDispatch({
    title   = 'ATM Robbery',
    code    = '10-90',
    message = 'ATM robbery in progress near the bank.',
    coords  = GetEntityCoords(cache.ped),
    jobs    = { 'police', 'sheriff' },
    sprite  = 431,
    color   = 1,
    length  = 5,
})
```

**Supported systems:** ps-dispatch, aty\_dispatch, rcore\_dispatch, cd\_dispatch, Opto\_dispatch

***

## Logger — Server

Log events to Discord, fivemanage, or fivemerr.

```lua
-- SERVER ONLY
exports.pl_lib:Log(message, opts)
```

| Field | Type | Description |
|---|---|---|
| `message` | string | Log message |
| `opts.type` | string | `'fivemanage'` \| `'fivemerr'` \| `'discord'` |
| `opts.enable` | bool | Whether logging is active |
| `opts.webhook` | string | Discord webhook URL (required for `'discord'` type) |
| `opts.jobname` | string | Tag/category label |

**Example:**
```lua
exports.pl_lib:Log('Player robbed ATM #' .. atmId, {
    type    = 'discord',
    enable  = true,
    webhook = 'https://discord.com/api/webhooks/...',
    jobname = 'ATM Robbery',
})
```
