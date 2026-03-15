# API

`pl_wheelclamper` exposes server-side exports for integration with other resources such as garage scripts, admin panels, or custom scripts.

***

## IsVehicleClamped

Check whether a vehicle is currently clamped.

```lua
local clamped = exports.pl_wheelclamper:IsVehicleClamped(plate)
```

| Parameter | Type     | Description                |
| --------- | -------- | -------------------------- |
| `plate`   | `string` | The vehicle plate to check |

**Returns:** `boolean` — `true` if the vehicle is clamped, `false` otherwise.

**Example:**

```lua
if exports.pl_wheelclamper:IsVehicleClamped('ABC 123') then
    print('This vehicle is clamped.')
end
```

***

## AddClamp

Programmatically clamp a vehicle. Useful for admin tools or automated systems.

```lua
local success = exports.pl_wheelclamper:AddClamp(plate, fineAmount, clampedBy)
```

| Parameter    | Type     | Description                                                             |
| ------------ | -------- | ----------------------------------------------------------------------- |
| `plate`      | `string` | The vehicle plate to clamp                                              |
| `fineAmount` | `number` | Fine amount in dollars. Defaults to `500` if not provided               |
| `clampedBy`  | `string` | Name or label to record as who placed the clamp. Defaults to `'System'` |

**Returns:** `boolean` — `true` if the clamp was added, `false` if the vehicle was already clamped or plate was invalid.

**Example:**

```lua
local ok = exports.pl_wheelclamper:AddClamp('ABC 123', 1000, 'AdminPanel')
if ok then
    print('Clamp added.')
end
```

***

## RemoveClamp

Programmatically remove a clamp from a vehicle.

```lua
local success = exports.pl_wheelclamper:RemoveClamp(plate)
```

| Parameter | Type     | Description                  |
| --------- | -------- | ---------------------------- |
| `plate`   | `string` | The vehicle plate to unclamp |

**Returns:** `boolean` — `true` if the clamp was removed, `false` if no clamp record was found.

**Example:**

```lua
local ok = exports.pl_wheelclamper:RemoveClamp('ABC 123')
if ok then
    print('Clamp removed.')
end
```

***

## OnVehicleSpawned

Notify `pl_wheelclamper` that a vehicle has been spawned from a garage. If the vehicle is clamped, the clamp visual will be applied on the spawning player's client.

```lua
exports.pl_wheelclamper:OnVehicleSpawned(source, plate)
```

| Parameter | Type     | Description                                         |
| --------- | -------- | --------------------------------------------------- |
| `source`  | `number` | The server ID of the player who spawned the vehicle |
| `plate`   | `string` | The plate of the spawned vehicle                    |

**Returns:** nothing.

> This export is safe to call on every spawn. It does nothing if the vehicle is not clamped.

**Example:**

```lua
-- Inside your garage spawn event/callback
exports.pl_wheelclamper:OnVehicleSpawned(source, plate)
```

***

## OnVehicleStored

Notify `pl_wheelclamper` that a vehicle has been stored back into a garage. If the vehicle is clamped, the clamp visual will be removed from the storing player's client. The clamp **database record is kept** — the vehicle is still considered clamped.

```lua
exports.pl_wheelclamper:OnVehicleStored(source, plate)
```

| Parameter | Type     | Description                                        |
| --------- | -------- | -------------------------------------------------- |
| `source`  | `number` | The server ID of the player who stored the vehicle |
| `plate`   | `string` | The plate of the stored vehicle                    |

**Returns:** nothing.

**Example:**

```lua
-- Inside your garage store event/callback
exports.pl_wheelclamper:OnVehicleStored(source, plate)
```

***

{% hint style="info" %}
* All exports are **server-side only**.
* `plate` must match exactly as stored in your database (including spacing/capitalisation).
* `AddClamp` and `RemoveClamp` automatically sync the clamp state to all connected clients.
{% endhint %}
