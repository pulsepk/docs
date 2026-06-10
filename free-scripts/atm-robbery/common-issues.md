# Common Issues

Solutions to the most frequently reported problems with the ATM Robbery script.

***

### ❌ No interaction option appears on ATMs

**Cause:** Target system not started, or the target resource name doesn't match what pl\_lib detects.

**Fix:**
1. Confirm `ox_target` or `qb-target` is ensured in `server.cfg` **before** `pl-atmrob`.
2. Confirm `pl_lib` is also ensured before `pl-atmrob`.
3. Check the server console for any startup errors from pl\_lib.

***

### ❌ Items are not removed / robbery doesn't start

**Cause:** The item names in `Config.HackingItem`, `Config.DrillItem`, or `Config.RopeItem` don't match the names registered in your inventory.

**Fix:**
1. Open your inventory item file and confirm the exact item names.
2. Make sure they match the values in `config.lua`. Names are case-sensitive.
3. If you want to allow the action without requiring an item, set the value to `false`.

***

### ❌ Item images are missing or broken in inventory

**Cause:** Images were not copied to the correct folder, or file names don't match.

**Fix:**
1. Copy `pl_hackingdevice.png`, `pl_drill.png`, and `pl_rope.png` from `Install_Me_First/Images/` to your inventory's image directory.
2. For ox\_inventory: `ox_inventory/web/images/`
3. For qb-inventory: `qb-inventory/html/images/`
4. Restart the inventory resource after copying.

***

### ❌ Drilling minigame doesn't start

**Cause:** `M-drilling` resource is not started, or `Config.Drilling.Minigame` is set to a resource that isn't running.

**Fix:**
1. Confirm M-drilling is ensured in `server.cfg` before `pl-atmrob`.
2. Check `Config.Drilling.Minigame` in `config.lua` — it must match the exact resource name.

***

### ❌ Hacking minigame doesn't start

**Cause:** The configured minigame resource is not started.

**Fix:**
1. Confirm the minigame resource is ensured in `server.cfg`.
2. Check `Config.Hacking.Minigame` — valid options are: `'utk_fingerprint'`, `'ox_lib'`, `'M-drilling'`, `'ps-ui-circle'`, `'ps-ui-maze'`, `'ps-ui-scrambler'`.
3. Set `Config.Hacking.Minigame = nil` to let pl\_lib auto-detect.

***

### ❌ Rope robbery — no vehicle target appears after attaching rope

**Cause:** No vehicle was within 20 metres of the ATM at the moment you attached the rope.

**Fix:** Park your vehicle within 20m of the ATM **before** using the rope on the ATM. The vehicle scan runs once when the rope is attached.

{% hint style="warning" %}
The rope is attached in two steps: first to the ATM, then to the vehicle. Both steps require you to be near the relevant object.
{% endhint %}

***

### ❌ "You failed the robbery attempt" when attaching rope to vehicle

**Cause:** The server rejected the request because the robbery state expired (5-minute window) or the vehicle was too far from the ATM (over 25m).

**Fix:**
1. Make sure your vehicle is parked within 25m of the ATM before attaching the rope.
2. Complete the rope attachment step within 5 minutes of starting the robbery.

***

### ❌ Police dispatch not triggering

**Cause:** The dispatch resource is not detected by pl\_lib, or `Config.Police.notify` is set to `false`.

**Fix:**
1. Confirm `Config.Police.notify = true` in `config.lua`.
2. Ensure your dispatch resource is started before pl\_lib.
3. Check the pl\_lib config (`pl_lib/config/config.lua`) — set `PLLib.Debug = true` to see which systems are detected on startup.

***

### ❌ Robbery never starts — "Not enough police" even when police are online

**Cause:** The job name in `Config.Police.Job` doesn't match the actual job name on your server.

**Fix:**
Open `config.lua` and update `Config.Police.Job` to match your server's police job name exactly:
```lua
Config.Police = {
    required = 2,
    Job = { 'police' },  -- Change 'police' to match your server's job name
}
```

***

{% hint style="info" %}
Still having trouble? [Join the Discord for support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
