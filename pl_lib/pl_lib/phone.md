# Phone

pl\_lib provides a unified phone API that works across **lb-phone** and **gksphone**. Use these exports to send phone notifications and SMS messages without writing per-resource logic in your scripts.

Supported systems are detected automatically. Override detection in `pl_lib/config/config.lua`:

```lua
-- Phone: 'autodetect' | 'lb-phone' | 'gksphone'
PLLib.Phone = 'autodetect'
```

***

## Client Exports

### ShowPhoneNotification

Pops a phone notification on the **local player's** screen.

```lua
exports.pl_lib:ShowPhoneNotification(title, message, icon)
```

| Parameter | Type   | Description                                    |
| --------- | ------ | ---------------------------------------------- |
| `title`   | string | Notification title                             |
| `message` | string | Notification body text                         |
| `icon`    | string | Font Awesome icon class (default: `fas fa-bell`) |

**Example:**

```lua
-- client-side
exports.pl_lib:ShowPhoneNotification('Bank', 'Your transfer was received.', 'fas fa-university')
```

{% hint style="info" %}
For lb-phone, client-side `ShowPhoneNotification` routes through the server internally — you do not need to call a server event yourself.
{% endhint %}

***

## Server Exports

### SendPhoneNotification

Pushes a phone notification to a **specific player** by server source.

```lua
exports.pl_lib:SendPhoneNotification(source, title, message, icon)
```

| Parameter | Type   | Description                                    |
| --------- | ------ | ---------------------------------------------- |
| `source`  | number | Player server ID                               |
| `title`   | string | Notification title                             |
| `message` | string | Notification body text                         |
| `icon`    | string | Font Awesome icon class (default: `fas fa-bell`) |

**Example:**

```lua
-- server-side
exports.pl_lib:SendPhoneNotification(source, 'Police', 'You have a new warrant.', 'fas fa-shield-alt')
```

***

### GetPlayerPhoneNumber

Returns the phone number string for a player, or `nil` if unavailable.

```lua
local number = exports.pl_lib:GetPlayerPhoneNumber(source)
```

| Parameter | Type   | Description      |
| --------- | ------ | ---------------- |
| `source`  | number | Player server ID |

**Returns:** `string | nil`

**Example:**

```lua
local number = exports.pl_lib:GetPlayerPhoneNumber(source)
if number then
    print('Player phone: ' .. number)
end
```

***

### SendPhoneMessage

Sends an SMS from one phone number to another.

```lua
exports.pl_lib:SendPhoneMessage(fromNumber, toNumber, message)
```

| Parameter    | Type   | Description               |
| ------------ | ------ | ------------------------- |
| `fromNumber` | string | Sender's phone number     |
| `toNumber`   | string | Recipient's phone number  |
| `message`    | string | SMS body text             |

**Example:**

```lua
-- server-side
local senderNumber = exports.pl_lib:GetPlayerPhoneNumber(source)
local targetNumber = exports.pl_lib:GetPlayerPhoneNumber(targetSrc)

if senderNumber and targetNumber then
    exports.pl_lib:SendPhoneMessage(senderNumber, targetNumber, 'Meet me at the docks.')
end
```

***

## Supported Systems

| Phone Resource | ShowPhoneNotification | SendPhoneNotification | GetPlayerPhoneNumber | SendPhoneMessage |
| -------------- | :-------------------: | :-------------------: | :------------------: | :--------------: |
| **lb-phone**   | ✅                    | ✅                    | ✅                   | ✅               |
| **gksphone**   | ✅                    | ✅                    | ✅                   | ✅               |
