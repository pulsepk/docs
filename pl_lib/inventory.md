# Inventory

All inventory exports normalise across the supported inventory systems automatically.

**Supported inventories:** ox\_inventory, qb-inventory (2.0.0+), qs-inventory, ps-inventory, codem-inventory, tgiann-inventory, origen\_inventory, jaksam\_inventory

***

## AddItem — Server

Give an item to a player.

```lua
-- SERVER ONLY
local success = exports.pl_lib:AddItem(src, item, amount)
```

| Parameter | Type | Description |
|---|---|---|
| `src` | number | Player server ID |
| `item` | string | Item name (must match your inventory's item name exactly) |
| `amount` | number | Quantity to add |

Returns `true` on success, `false` if the operation failed.

**Example:**
```lua
local given = exports.pl_lib:AddItem(src, 'clone_card', 1)
if not given then
    -- inventory full or item not registered
end
```

***

## RemoveItem — Server

Remove an item from a player.

```lua
-- SERVER ONLY
local success = exports.pl_lib:RemoveItem(src, item, amount)
```

Returns `true` on success, `false` if the player doesn't have enough.

**Example:**
```lua
local removed = exports.pl_lib:RemoveItem(src, 'lockpick', 1)
```

***

## HasItem — Server

Check how many of an item a player is carrying.

```lua
-- SERVER ONLY
local count = exports.pl_lib:HasItem(src, item)
-- returns 0 if the player has none
```

**Example:**
```lua
local picks = exports.pl_lib:HasItem(src, 'lockpick')
if picks < 1 then
    exports.pl_lib:Notify('', 'You need a lockpick', 'error')
    return
end
```

***

## RegisterUsableItem — Server

Register a callback that fires when a player uses an item from their inventory.

```lua
-- SERVER ONLY
exports.pl_lib:RegisterUsableItem(name, cb)
```

| Parameter | Type | Description |
|---|---|---|
| `name` | string | Item name |
| `cb` | function | `function(src, item)` — fires on use |

**Example:**
```lua
exports.pl_lib:RegisterUsableItem('lockpick', function(src, item)
    TriggerClientEvent('lockpick:start', src)
end)
```

***

## OpenStashInventory — Client

Open a stash/secondary inventory for the local player.

```lua
-- CLIENT ONLY
exports.pl_lib:OpenStashInventory(stashName, opts)
```

| Parameter | Type | Description |
|---|---|---|
| `stashName` | string | Unique stash identifier |
| `opts` | table | `{ weight (number), slots (number), label (string) }` |

**Example:**
```lua
exports.pl_lib:OpenStashInventory('atm_stash_' .. netId, {
    weight = 100000,
    slots  = 5,
    label  = 'ATM Contents',
})
```
