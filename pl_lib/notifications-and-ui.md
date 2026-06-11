# Notifications & UI

***

## Notify

Send a notification to the player. Routes automatically to the configured notify system.

```lua
exports.pl_lib:Notify(title, message, type)
```

| Parameter | Type | Description |
|---|---|---|
| `title` | string | Notification title |
| `message` | string | Notification body text |
| `type` | string | `'success'` \| `'error'` \| `'info'` \| `'warning'` (default: `'success'`) |

**Example:**
```lua
exports.pl_lib:Notify('Bank', 'You received $500', 'success')
exports.pl_lib:Notify('Error', 'Not enough money', 'error')
```

**Supported systems:** ox\_lib, esx\_notify, okokNotify, wasabi\_notify, brutal\_notify, mythic\_notify, lation\_ui

Configure via `PLLib.Notify` in `config.lua`.

***

## TextUI

Show or hide a contextual text prompt near the player's crosshair.

```lua
exports.pl_lib:TextUIShow(text, opts)
exports.pl_lib:TextUIHide()

-- Check if a TextUI is currently open
local isOpen, currentText = exports.pl_lib:TextUIIsOpen()
```

| Parameter | Type | Description |
|---|---|---|
| `text` | string | Text to display |
| `opts` | table | Optional — `{ position, icon, style, align, color }` (ox\_lib fields) |

**Example:**
```lua
exports.pl_lib:TextUIShow('[E] Rob ATM', { position = 'right-center', icon = 'hand' })

-- later
exports.pl_lib:TextUIHide()
```

**Supported systems:** ox\_lib, qb-core, jg-textui, esx\_textui, cd\_drawtextui, brutal\_textui, lation\_ui

***

## ShowInputDialog

Open a multi-field input dialog and return the submitted values.

```lua
-- CLIENT ONLY
local result = exports.pl_lib:ShowInputDialog(title, options, submitText)
-- returns table of values, or nil if cancelled
```

| Parameter | Type | Description |
|---|---|---|
| `title` | string | Dialog title |
| `options` | table | Array of input fields — follows ox\_lib `inputDialog` field spec |
| `submitText` | string | Submit button label (optional) |

**Example:**
```lua
local result = exports.pl_lib:ShowInputDialog('Transfer Money', {
    { type = 'number', label = 'Amount', required = true },
    { type = 'input',  label = 'Reason' },
})

if result then
    local amount = result[1]
    local reason = result[2]
end
```

**Supported systems:** ox\_lib, lation\_ui

***

## ContextMenu

Register and open an ox\_lib-style context menu.

```lua
-- CLIENT ONLY
exports.pl_lib:ContextMenu(id, title, options, menu, header, description)
```

| Parameter | Type | Description |
|---|---|---|
| `id` | string | Unique menu ID |
| `title` | string | Menu title |
| `options` | table | Array of menu items — follows ox\_lib `registerContext` spec |
| `menu` | string | Parent menu ID (optional, for back navigation) |
| `header` | string | Header text (optional) |
| `description` | string | Description text (optional) |

**Example:**
```lua
exports.pl_lib:ContextMenu('atm_menu', 'ATM Options', {
    { title = 'Withdraw', description = 'Take cash from your bank', event = 'bank:withdraw' },
    { title = 'Deposit',  description = 'Put cash into your bank',  event = 'bank:deposit'  },
})
```

**Supported systems:** ox\_lib, lation\_ui

***

## RegisterListMenu

Open a simple scrollable list menu. Fires a client event when an item is selected.

```lua
-- CLIENT ONLY
exports.pl_lib:RegisterListMenu(id, title, items, position)
```

| Parameter | Type | Description |
|---|---|---|
| `id` | string | Unique menu ID |
| `title` | string | Menu title |
| `items` | table | Array of strings or `{ label = '...' }` tables |
| `position` | string | `'top-right'` \| `'top-left'` \| `'bottom-right'` \| `'bottom-left'` |

**Selection event:**
```lua
AddEventHandler('pl_lib:listMenuSelected', function(id, index)
    -- id    = the menu ID passed to RegisterListMenu
    -- index = the 1-based index of the selected item
end)
```

**Example:**
```lua
exports.pl_lib:RegisterListMenu('player_list', 'Nearby Players', { 'Alice', 'Bob', 'Charlie' }, 'top-right')

AddEventHandler('pl_lib:listMenuSelected', function(id, index)
    if id == 'player_list' then
        print('Selected player index: ' .. index)
    end
end)
```
