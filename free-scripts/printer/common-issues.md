# Common Issues

***

### ❌ I used a Discord CDN link for an image — it worked at first but stopped working

**Cause:** Discord CDN links expire after a period of time. They are not permanent hosting.

**Fix:** Use [FiveManage](https://fivemanage.com) to host your document images. FiveManage links are permanent and work with FiveM's content policy.

***

### ❌ Paper item does not show its content when used

**Cause:** The `server.export` field is missing from the item definition in ox\_inventory.

**Fix:** Make sure the paper item in `ox_inventory/data/items.lua` includes the export:

```lua
["paper"] = {
    label   = "Paper",
    weight  = 1,
    stack   = false,
    close   = true,
    consume = 0,
    server  = {
        export = 'pl_printer.paper'  -- this line is required
    }
},
```

***

### ❌ Paper image is not showing in inventory

**Cause:** The image was not copied to the right folder, or the inventory resource was not restarted.

**Fix:**
1. Copy `installfolder/paper.png` to your inventory's image folder:
   - ox\_inventory: `ox_inventory/web/images/`
   - qb-inventory: `qb-inventory/html/images/`
2. Restart the inventory resource (`ensure ox_inventory` / `ensure qb-inventory`).

***

### ❌ Printer UI doesn't open / nothing happens when interacting

**Cause:** pl\_lib is not started before pl\_printer, or the target system isn't detected.

**Fix:**
1. Ensure `pl_lib` is ensured in `server.cfg` **before** `pl_printer`.
2. Confirm your target system (`ox_target` or `qb-target`) is also ensured before `pl_printer`.

***

### ❌ Fixed location printers are not appearing in the world

**Cause:** `Config.EnableLocation` is set to `false`.

**Fix:** Set `Config.EnableLocation = true` in `config.lua` and define your coordinates in `Config.Locations`.

***

### ❌ Money is not deducted when printing

**Cause:** `Config.Print.Account` is set to an account type the player doesn't have, or the framework isn't detected correctly.

**Fix:**
1. Check `Config.Print.Account` — valid values are `'bank'` or `'cash'`.
2. Confirm pl\_lib is detecting your framework correctly by setting `PLLib.Debug = true` in `pl_lib/config/config.lua` and checking startup console output.

***

{% hint style="info" %}
[Join the Discord for support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
