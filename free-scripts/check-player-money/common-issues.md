# Common Issues

***

### ❌ "You are not allowed to use this command" when running /checkplayermoney

**Cause:** The `checkplayermoney` ACE permission has not been granted to your player or group.

**Fix:** Add the following to your `server.cfg`:

```cfg
add_ace group.admin checkplayermoney allow
```

If you are not in the `admin` group, grant it directly to your identifier instead:

```cfg
add_ace identifier.license:YOUR_LICENSE checkplayermoney allow
```

Restart the server after making changes to `server.cfg`.

***

### ❌ Command opens but returns no results / empty list

**Cause:** The balance threshold entered is higher than any player's balance, or no players match the filter.

**Fix:** Try entering `0` as the amount to return all players, then narrow down from there.

***

### ❌ Script prints "No compatible framework detected — script disabled" on startup

**Cause:** pl\_lib could not detect your framework (ESX, QBCore, or Qbox).

**Fix:**
1. Confirm `pl_lib` is ensured in `server.cfg` **before** `pl-checkplayermoney`.
2. Confirm your framework resource (`es_extended`, `qb-core`, or `qbx_core`) is also started.
3. Set `PLLib.Debug = true` in `pl_lib/config/config.lua` to see what pl\_lib detects at startup.

***

### ❌ Database error on startup or queries returning nothing

**Cause:** oxmysql is not started, or started after pl-checkplayermoney.

**Fix:**
1. Ensure `oxmysql` is the **first** ensure in `server.cfg`.
2. Confirm the server database connection string in `server.cfg` is correct.

***

### ❌ ESX: player names show as "nil nil"

**Cause:** Your ESX `users` table stores names differently (some older versions use a single `name` column instead of `firstname` / `lastname`).

**Fix:** This is a known limitation with non-standard ESX database schemas. The script reads `firstname` and `lastname` columns — if your schema differs, the names column may need adjusting.

***

{% hint style="info" %}
[Join the Discord for support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
