# Common Issues

***

### ❌ No interaction option appears on the ATM

**Cause:** Target system not started, or pl\_lib / ox\_lib aren't started before pl\_fraud.

**Fix:**
1. Confirm `ox_lib`, `pl_lib`, and your target system (`ox_target` or `qb-target`) are ensured in `server.cfg` **before** `pl_fraud`.
2. Check startup console for errors from pl\_lib or ox\_lib.

***

### ❌ Items are not being recognised / fraud doesn't start

**Cause:** The item names in `Config.Items` don't match the names registered in your inventory.

**Fix:**
1. Open your inventory's item file and confirm the exact item names.
2. Update `Config.Items` in `config.lua` to match. Names are case-sensitive.

***

### ❌ Item images are missing in inventory

**Cause:** Images weren't copied to the correct folder, or inventory wasn't restarted.

**Fix:**
1. Copy all 5 images (`clone_card.png`, `fuelcan.png`, `laptop.png`, `printer.png`, `generator.png`) from `Install/Img/` to your inventory's image directory.
2. Restart the inventory resource.

***

### ❌ Hacking minigame doesn't start

**Cause:** The configured minigame resource is not started, or `Config.Hacking.Minigame` doesn't match the resource name.

**Fix:**
1. Confirm the minigame resource is ensured in `server.cfg` before `pl_fraud`.
2. Valid values for `Config.Hacking.Minigame`: `'datacrack'`, `'ps-ui-circle'`, `'ps-ui-maze'`, `'ps-ui-scrambler'`.

***

### ❌ Generator won't fuel / "not enough fuel" even when holding fuel can

**Cause:** `Config.RequiredFuel` is set higher than the fuel amount in the fuel can item, or the item name for `fuelCan` doesn't match.

**Fix:**
1. Check `Config.RequiredFuel` — default is `10`. Lower it if needed.
2. Confirm `Config.Items.fuelCan` matches the exact item name in your inventory.

***

### ❌ Items placed but the "close enough" check fails

**Cause:** `Config.ProximityDistance` is too small for the area where items are being placed.

**Fix:** Increase `Config.ProximityDistance` in `config.lua`. Default is `2.0` metres. Try `3.0` or `4.0` if players are having trouble aligning items.

***

### ❌ Dispatch alert is not sending

**Cause:** `Config.Dispatch.enable` is set to `false`, or the dispatch resource is not detected by pl\_lib.

**Fix:**
1. Set `Config.Dispatch.enable = true` in `config.lua`.
2. Ensure your dispatch resource is started before pl\_lib.
3. Set `PLLib.Debug = true` in `pl_lib/config/config.lua` to see which systems pl\_lib detects on startup.

***

{% hint style="info" %}
[Join the Discord for support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
