# Common Issues

***

### ❌ HUD is not showing at all

**Cause:** The resource failed to start, or pl\_lib was not started before pl\_hud.

**Fix:**
1. Confirm both `ensure pl_lib` and `ensure pl_hud` are in `server.cfg`, with `pl_lib` **first**.
2. Check the server console for any startup errors from `pl_hud` or `pl_lib`.
3. Confirm the folder on disk is named exactly `pl_hud` — folder names are case-sensitive on Linux servers.

***

### ❌ All stats show as 0 / HUD shows but nothing updates

**Cause:** pl\_lib could not detect your framework, so player data (health, money, job, hunger, thirst) is never sent to the HUD.

**Fix:**
1. Confirm your framework resource (`es_extended`, `qb-core`, or `qbx_core`) is started **before** `pl_lib`.
2. Set `PLLib.Debug = true` in `pl_lib/config/config.lua` to see what pl\_lib detects on startup.
3. Reconnect after fixing the start order — the HUD initialises on player load.

***

### ❌ Minimap is not showing

**Cause:** `Config.AlwaysShowMinimap` is `false` and you are on foot, or the minimap texture failed to stream.

**Fix:**
1. If you want the minimap always visible, set `Config.AlwaysShowMinimap = true` in `shared/config.lua`.
2. If it's missing even in a vehicle, confirm the `stream/` folder is present inside `pl_hud` and the resource restarted after any file changes.

***

### ❌ Minimap is the wrong shape (square when you want circle or vice versa)

**Fix:** Change `Config.Maptype` in `shared/config.lua`:

```lua
Config.Maptype = 'circle'  -- or 'square'
```

Restart the resource after saving.

***

### ❌ Fuel level is always wrong / shows 100% even when empty

**Cause:** Your server uses a custom fuel script, but `GetVehFuel` is still using the default native fuel level.

**Fix:** Override `GetVehFuel` at the bottom of `shared/config.lua` with your fuel resource's export. See the [Config File](config-file.md) page for examples.

***

### ❌ Voice indicator is not showing or not updating

**Cause:** The voice proximity script is not sending the expected control values, or pma-voice / mumble-voip is not started.

**Fix:**
1. Confirm your voice resource is started and working independently.
2. The voice indicator reads FiveM's built-in network voice controls — it works with pma-voice and mumble-voip out of the box. Third-party voice systems that don't use native controls may not be detected.

***

### ❌ Seatbelt or lights key is not working

**Cause:** The configured control index conflicts with another resource, or the key code is wrong.

**Fix:**
1. Change `Config.SeatbeltToggleKey` or `Config.LightToggleKey` in `shared/config.lua` to a different control index.
2. Key values are **FiveM control indices**, not keyboard scan codes. See the [Config File](config-file.md) key reference table.

***

{% hint style="info" %}
[Join the Discord for support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
