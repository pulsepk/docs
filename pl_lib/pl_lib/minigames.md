# Minigames

***

## DoMinigame

Run a hacking/skill minigame. The callback always fires exactly once with a `success` boolean.

```lua
-- CLIENT ONLY
exports.pl_lib:DoMinigame(callback, opts)
```

| Parameter  | Type     | Description                                            |
| ---------- | -------- | ------------------------------------------------------ |
| `callback` | function | `function(success)` — called when minigame ends        |
| `opts`     | table    | Optional. Override system and pass per-system settings |

**`opts` fields:**

| Field             | Type   | Description                                                               |
| ----------------- | ------ | ------------------------------------------------------------------------- |
| `system`          | string | Force a specific minigame (overrides `PLLib.Minigame`). See values below. |
| `ox_lib`          | table  | ox\_lib skill check options                                               |
| `utk_fingerprint` | table  | utk\_fingerprint options                                                  |
| `ps-ui-circle`    | table  | ps-ui circle options                                                      |
| `ps-ui-maze`      | table  | ps-ui maze options                                                        |
| `ps-ui-scrambler` | table  | ps-ui scrambler options                                                   |

**Supported `system` values:** `'ox_lib'` | `'utk_fingerprint'` | `'ps-ui-circle'` | `'ps-ui-maze'` | `'ps-ui-scrambler'` | `'M-drilling'`

{% hint style="warning" %}
`M-drilling` is **not** included in `'autodetect'`. Scripts must explicitly pass `opts.system = 'M-drilling'` or set it in the dependent script's own config.
{% endhint %}

***

### Examples

{% tabs %}
{% tab title="ox_lib" %}
```lua
exports.pl_lib:DoMinigame(function(success)
    if success then print('Hacked!') end
end, {
    system  = 'ox_lib',
    ox_lib  = {
        difficulty = { 'easy', 'medium', 'hard' },
        keys       = { 'w', 'a', 's', 'd' },
    }
})
```
{% endtab %}

{% tab title="utk_fingerprint" %}
```lua
exports.pl_lib:DoMinigame(function(success)
    if success then print('Fingerprint matched!') end
end, {
    system          = 'utk_fingerprint',
    utk_fingerprint = { circles = 5, matches = 3, time = 10 },
})
```
{% endtab %}

{% tab title="ps-ui circle" %}
```lua
exports.pl_lib:DoMinigame(function(success)
    if success then print('Circle passed!') end
end, {
    system        = 'ps-ui-circle',
    ['ps-ui-circle'] = { circles = 3, speed = 2 },
})
```
{% endtab %}

{% tab title="M-drilling" %}
```lua
exports.pl_lib:DoMinigame(function(success)
    if success then print('Drilling complete!') end
end, {
    system = 'M-drilling',
})
```
{% endtab %}

{% tab title="autodetect" %}
```lua
-- Uses PLLib.Minigame from config — no opts needed
exports.pl_lib:DoMinigame(function(success)
    if success then print('Success!') end
end)
```
{% endtab %}
{% endtabs %}

***

## ProgressBar

Show a progress bar with an optional animation. Returns `true` when complete.

```lua
-- CLIENT ONLY
local done = exports.pl_lib:ProgressBar(label, duration, animDict, anim, opts)
```

| Parameter  | Type          | Description                                                                             |
| ---------- | ------------- | --------------------------------------------------------------------------------------- |
| `label`    | string        | Text shown on the progress bar                                                          |
| `duration` | number        | Duration in milliseconds                                                                |
| `animDict` | string \| nil | Animation dictionary to play (pass `nil` for none)                                      |
| `anim`     | string \| nil | Animation clip name                                                                     |
| `opts`     | table         | Disable controls during progress: `{ move, car, combat, mouse }` — set `false` to allow |

**Example:**

```lua
exports.pl_lib:ProgressBar('Picking lock...', 5000, 'anim@amb@clubhouse@tutorial@bkr_tut_ig3@', 'machinic_loop_mechandplayer', {
    move   = false,
    combat = false,
})
```

**Supported systems:** ox\_lib, ox\_lib\_circle, qb, lation\_ui

Configure via `PLLib.Progressbar` in `config.lua`.

***

## DoSkillCheck

Run a skill check mini-interaction. Returns `true` if passed, `false` if failed.

```lua
-- CLIENT ONLY
local passed = exports.pl_lib:DoSkillCheck(opts)
```

| Parameter | Type  | Description                  |
| --------- | ----- | ---------------------------- |
| `opts`    | table | See per-system options below |

**ox\_lib opts:**

```lua
{
    difficulty = { 'easy', 'medium' },  -- array of difficulty stages
    keys       = { 'w', 'a', 's', 'd' }
}
```

**lation\_ui opts:**

```lua
{
    lation = {
        Title        = 'Skill Check',
        Difficulties = { 'easy' },
        Keys         = { 'e' },
    }
}
```

**Example:**

```lua
local passed = exports.pl_lib:DoSkillCheck({
    difficulty = { 'easy', 'medium' },
    keys       = { 'e' },
})

if passed then
    -- success
end
```

**Supported systems:** ox\_lib, lation\_ui

Configure via `PLLib.SkillCheck` in `config.lua`.
