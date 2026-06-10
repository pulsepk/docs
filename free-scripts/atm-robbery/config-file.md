# Config File

The full `shared/config.lua` file with descriptions for every option.

***

```lua
Config = {}

-- Set to true to print debug information to the server console
Config.DebugPrints = false

-- Language for in-game text. Available: 'en', 'es', 'de', 'fr', 'it', 'tr', 'da'
Config.Locale = 'en'

Config.WaterMark = true

-- ─── Items ────────────────────────────────────────────────────────────────────
-- The inventory item names required for each action.
-- Set to false to allow the action without needing an item.
Config.HackingItem = 'pl_hackingdevice'
Config.DrillItem   = 'pl_drill'
Config.RopeItem    = 'pl_rope'

-- ─── Enable / Disable Actions ─────────────────────────────────────────────────
Config.EnableHacking      = true  -- Allow the hack interaction on ATMs
Config.EnableDrilling     = true  -- Allow the drill interaction on ATMs
Config.EnableRopeRobbery  = true  -- Allow the rope + vehicle pull method

-- ─── Rope Robbery Physics ─────────────────────────────────────────────────────
Config.RopeRobbery = {
    DragForce        = 0.2,   -- How much the rope slows the vehicle when taut (0.0–1.0)
    ResistanceForce  = 0.05,  -- How hard the ATM resists being pulled
    RequiredDistance = 4.0,   -- How far the vehicle must drive to rip the ATM loose (metres)
    MaxRopeLength    = 25.0,  -- Maximum rope length before it snaps (metres)
    TautRopeLength   = 8.0,   -- Distance at which the rope goes taut and starts applying drag
}

-- ─── Cash Drops ───────────────────────────────────────────────────────────────
-- true  = cash prop objects drop on the ground and must be picked up individually
-- false = the full reward is added directly to the player's inventory
Config.MoneyDrop = true

-- ─── ATM Models ───────────────────────────────────────────────────────────────
-- Which prop models are treated as robbable ATMs.
-- Rope robbery is only available on: prop_fleeca_atm, prop_atm_02, prop_atm_03
Config.AtmModels = { 'prop_fleeca_atm', 'prop_atm_01', 'prop_atm_02', 'prop_atm_03' }

-- ─── Hacking Minigame ─────────────────────────────────────────────────────────
Config.Hacking = {
    -- nil = auto-detect via pl_lib. Set to a value to force a specific minigame.
    -- Supported: 'utk_fingerprint' | 'ox_lib' | 'M-drilling' | 'ps-ui-circle' | 'ps-ui-maze' | 'ps-ui-scrambler'
    Minigame            = nil,
    InitialHackDuration = 2000,   -- Duration of the initial hacking animation (ms)
    LootAtmDuration     = 20000,  -- Duration of the loot animation when MoneyDrop is false (ms)
}

-- ─── Drilling Minigame ────────────────────────────────────────────────────────
Config.Drilling = {
    -- Defaults to M-drilling. Change to use a different minigame for the drill action.
    -- Supported: 'M-drilling' | 'ox_lib' | 'utk_fingerprint' | 'ps-ui-circle' | 'ps-ui-maze' | 'ps-ui-scrambler'
    Minigame = 'M-drilling',
}

-- ─── Item Shop ────────────────────────────────────────────────────────────────
Config.Shop = {
    Enable   = true,
    id       = "atmitems",          -- Internal shop identifier
    name     = "ATM Robbery Shop",  -- Display name shown in-game
    coords   = vec3(-59.34, -1207.93, 28.30),
    heading  = 135.09,
    pedModel = "a_m_m_og_boss_01",
    blip = {
        enabled = true,
        sprite  = 59,
        color   = 2,
        scale   = 0.8,
    },
    items = {
        { name = 'pl_hackingdevice', amount = 50, price = 50  },
        { name = 'pl_drill',         amount = 50, price = 100 },
        { name = 'pl_rope',          amount = 50, price = 20  },
    },
}

-- ─── Cooldown ─────────────────────────────────────────────────────────────────
-- Server-wide cooldown between robberies, in seconds.
-- Example: 600 = 10 minutes
Config.CooldownTimer = 600

-- ─── Rewards ──────────────────────────────────────────────────────────────────
Config.Reward = {
    -- Where the money is added. Options: 'cash' | 'bank' | 'dirty'
    account         = 'dirty',

    -- Value of each individual cash pile prop (when MoneyDrop = true)
    cash_prop_value = 100,

    -- Total reward when MoneyDrop = false (added directly to inventory)
    reward          = 1000,

    -- Number of cash piles dropped for the hack method
    hack_cash_pile  = 10,

    -- Number of cash piles dropped for the drill method
    drill_cash_pile = 5,
}

-- ─── Police ───────────────────────────────────────────────────────────────────
Config.Police = {
    notify   = true,       -- Send a dispatch alert when a robbery starts
    required = 0,          -- Minimum number of police online for robberies to be allowed
    Job      = { 'police' }, -- Job names counted as police
}
```
