# Configuration

All settings live in `pl_lib/config/config.lua` under the `PLLib` global.

Every setting supports `'autodetect'` (the default) which scans running resources on startup. Override only when autodetect picks the wrong system.

***

```lua
-- Print detected systems on resource start.
-- Set true temporarily to verify detection, then disable.
PLLib.Debug = false

-- ─── Framework ────────────────────────────────────────────
-- 'autodetect' | 'qbox' | 'qb' | 'esx'
PLLib.Framework = 'autodetect'

-- ─── UI Systems ───────────────────────────────────────────
-- Notification system
-- 'autodetect' | 'ox_lib' | 'esx_notify' | 'okokNotify' | 'wasabi_notify'
--             | 'brutal_notify' | 'mythic_notify' | 'lation_ui'
PLLib.Notify = 'autodetect'

-- TextUI system
-- 'autodetect' | 'ox_lib' | 'qb-core' | 'jg-textui' | 'esx_textui'
--             | 'cd_drawtextui' | 'brutal_textui' | 'lation_ui'
PLLib.TextUI = 'autodetect'

-- Input dialog
-- 'ox_lib' | 'lation_ui'
PLLib.InputDialog = 'ox_lib'

-- Context menu
-- 'ox_lib' | 'lation_ui'
PLLib.ContextMenu = 'ox_lib'

-- ─── Gameplay Systems ─────────────────────────────────────
-- Target system
-- 'autodetect' | 'ox_target' | 'qb-target'
PLLib.Target = 'autodetect'

-- Minigame (used by DoMinigame when no system override is passed)
-- 'autodetect' detects ox_lib, utk_fingerprint, or ps-ui only.
-- M-drilling is NOT in autodetect — scripts must pass it explicitly via opts.system.
-- 'autodetect' | 'ox_lib' | 'utk_fingerprint' | 'ps-ui-circle' | 'ps-ui-maze' | 'ps-ui-scrambler'
PLLib.Minigame = 'autodetect'

-- Progressbar
-- 'ox_lib' | 'ox_lib_circle' | 'qb' | 'lation_ui'
PLLib.Progressbar = 'ox_lib'

-- Skill check
-- 'ox_lib' | 'lation_ui'
PLLib.SkillCheck = 'ox_lib'

-- ─── Economy ──────────────────────────────────────────────
-- Society / org banking resource
-- { resourcename = 'autodetect' | 'esx_addonaccount' | 'qb-management' | 'qb-banking'
--                | 'okokBanking' | 'Renewed-Banking' | 'snipe-banking' | 'tgiann-bank' }
PLLib.Society = { resourcename = 'autodetect' }

-- ─── Other ────────────────────────────────────────────────
-- Dispatch system
-- 'autodetect' | 'ps' | 'aty' | 'rcore' | 'cd' | 'op'
PLLib.Dispatch = 'autodetect'

-- Clothing / appearance system
-- 'autodetect' | 'esx_skin' | 'illenium-appearance' | 'fivem-appearance'
--             | 'qb-clothing' | 'tgiann-clothing' | 'rcore_clothing'
PLLib.Clothing = 'autodetect'

-- Phone resource
-- 'autodetect' | 'lb-phone' | 'gksphone'
PLLib.Phone = 'autodetect'
```

***

{% hint style="info" %}
After changing any setting, restart pl\_lib and all dependent resources for the change to take effect.
{% endhint %}
