# Config File

The full `config.lua` with descriptions for every option.

***

```lua
Config = {}

-- Language for in-game text.
-- Available: 'en', 'es', 'de', 'fr', 'it', 'pt', 'tr'
Config.Locale = 'en'

Config.Debug = false

-- Require a player to have a specific item before they can open the printer UI.
-- Set to false to allow anyone to use printers without an item requirement.
Config.CheckItem = false

-- The prop models used for the printer object.
Config.PrinterModel = { `prop_printer_02`, `prop_printer_01` }

-- The inventory item name for printed documents.
Config.ItemName = 'paper'

Config.Print = {
    Price   = 50,     -- Amount deducted from the player's account per print
    Account = 'bank', -- Account to deduct from: 'bank' or 'cash'
}

-- true  = spawn printer props at the coordinates defined in Config.Locations below
-- false = players place the printer as a portable item anywhere in the world
Config.EnableLocation = false

-- Only used when EnableLocation = true.
-- Add as many locations as you need.
Config.Locations = {
    { coords = vector3(451.53, -923.32, 28.44), heading = 190.0, object = "prop_printer_02" },
    -- { coords = vector3(x, y, z), heading = 0.0, object = "prop_printer_01" },
}
```

***

{% hint style="info" %}
**Notifications and input dialogs** are configured in `pl_lib/config/config.lua` via `PLLib.Notify` and `PLLib.InputDialog` — not in this config file.
{% endhint %}
