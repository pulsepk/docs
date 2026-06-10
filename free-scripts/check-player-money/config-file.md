# Config File

The `config.lua` for Check Player Money is intentionally minimal — framework detection, notifications, and database access are all handled automatically by pl\_lib and oxmysql.

***

```lua
Config = {}

-- The in-game command players use to open the money check menu.
-- Requires the 'checkplayermoney' ACE permission to use.
-- Change this to any name you prefer (e.g. 'moneytool', 'admincheck').
Config.Command = 'checkplayermoney'

-- Framework and notify system are auto-detected by pl_lib (no manual config needed).
```

***

## ACE Permission

Access to the command is controlled by a FiveM ACE permission, not by the config file. Set this in your `server.cfg`:

```cfg
# Grant all admins access
add_ace group.admin checkplayermoney allow
```

See the [Installation](installation.md) page for more permission examples.

***

## Notification & UI Settings

Notification system and input dialogs are configured in `pl_lib/config/config.lua` via `PLLib.Notify` and `PLLib.InputDialog` — not in this config file.
