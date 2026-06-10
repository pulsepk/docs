# Config File

The full `config.lua` with descriptions for every option.

***

```lua
Config = {}

Config.WaterMark = true

Config.Debug = false

-- Set to true to use the object_gizmo resource for precise item placement.
-- Download: https://github.com/DemiAutomatic/object_gizmo
Config.UseObjectGizmo = false

-- ─── Item Shop ────────────────────────────────────────────────────────────────
Config.Shop = {
    Enable   = true,
    id       = "frauditems",    -- Internal shop identifier
    name     = "Fraud Market",  -- Display name shown in-game
    coords   = vec3(430.1993, -1559.3730, 32.8),
    heading  = 319.6178,
    pedModel = "a_m_m_og_boss_01",
    blip = {
        enabled = true,
        sprite  = 59,
        color   = 2,
        scale   = 0.8,
    },
}

-- ─── Item Names ───────────────────────────────────────────────────────────────
-- Change these if your server uses different item names.
Config.Items = {
    laptop    = "laptop",
    printer   = "printer",
    generator = "generator",
    fuelCan   = "fuelcan",
    cloneCard = "clone_card",
}

-- ─── Hacking Minigame ─────────────────────────────────────────────────────────
Config.Hacking = {
    -- Minigame used for the fraud hacking step.
    -- Supported: 'datacrack' | 'ps-ui-circle' | 'ps-ui-maze' | 'ps-ui-scrambler'
    Minigame = 'datacrack',
}

-- ─── Rewards ──────────────────────────────────────────────────────────────────
Config.Rewards = {
    amount    = 100,
    -- Account type the reward is added to.
    -- Options: 'money' (cash) | 'black_money' | 'markedbills'
    moneytype = 'black_money',
}

-- ─── General Settings ─────────────────────────────────────────────────────────
-- Amount of fuel units required to power the generator before starting.
Config.RequiredFuel = 10

-- Maximum distance (metres) between placed items for them to be considered close enough.
Config.ProximityDistance = 2.0

-- How long the fraud process takes after starting (milliseconds).
Config.ProcessTime = 3000

-- ─── Object Placement Controls ────────────────────────────────────────────────
-- Only applies when UseObjectGizmo = false (manual placement mode).
-- [← →] Rotate  [↑ ↓] Height  [Scroll] Coarse rotate  [E / Enter] Place  [Backspace] Cancel
Config.Placing = {
    Distance      = 4.0,    -- Max forward distance the object can be placed (metres)
    RotationSpeed = 2.0,    -- Degrees rotated per frame while holding ← or →
    HeightStep    = 0.015,  -- Metres moved per frame while holding ↑ or ↓
}

-- ─── Props ────────────────────────────────────────────────────────────────────
-- The prop models spawned when players place items on the ground.
Config.Props = {
    laptop    = "prop_laptop_01a",
    printer   = "prop_printer_01",
    generator = "prop_generator_01a",
}

-- ─── Police ───────────────────────────────────────────────────────────────────
Config.Police = {
    Job = 'police', -- Job name counted as police (used for future police-required checks)
}

-- ─── ATM Models ───────────────────────────────────────────────────────────────
-- Which ATM props players can target to begin a fraud operation.
Config.atmModels = {
    `prop_atm_01`,
    `prop_atm_02`,
    `prop_atm_03`,
    `prop_fleeca_atm`,
}

-- ─── Target Labels ────────────────────────────────────────────────────────────
Config.TargetOptions = {
    laptop    = { icon = "fas fa-laptop-code", label = "Use Laptop"     },
    generator = { icon = "fas fa-bolt",        label = "Fuel Generator" },
    printer   = { icon = "fas fa-bolt",        label = "Collect Card"   },
    remove    = { icon = "fas fa-trash",       label = "Remove Object"  },
}

-- ─── Dispatch ─────────────────────────────────────────────────────────────────
-- Dispatch system is auto-detected by pl_lib.
-- Supported: ps-dispatch, aty_dispatch, qs-dispatch, rcore_dispatch, op-dispatch, and more.
Config.Dispatch = {
    enable = false, -- Set to true to send a police alert when fraud starts
}
```
