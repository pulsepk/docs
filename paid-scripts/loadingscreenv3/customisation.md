# Customisation

Nearly everything you'll want to change is in **`config.lua`**. Button labels and other interface text live in **`locales/`**. The look and the behaviour are in **`web/`**. Every file is unlocked, so if something isn't in the config you can still change it in the code.

{% hint style="info" %}
Remember to restart `pl_loadingscreenv3` and reconnect after editing, or use the [browser preview](installation.md#optional-preview-it-in-your-browser) and just refresh the page.
{% endhint %}

***

## Quick finder

Look for what you want to change on the left. The right-hand column tells you where to edit it.

| I want to change...                                       | File                     | Look for                                       |
| --------------------------------------------------------- | ------------------------ | ---------------------------------------------- |
| Server name, tagline, logo                                | `config.lua`             | `Config.Branding`                              |
| Main colours                                              | `config.lua`             | `Config.Branding.PrimaryColor / SecondaryColor` |
| The big outlined word behind the cards                    | `config.lua`             | `Config.Branding.BackdropWord`                 |
| Default language / letting players switch                 | `config.lua`             | `Config.Locale`, `Config.AllowLanguageSwitch`  |
| Seasonal theme (Winter, Halloween...)                     | `config.lua`             | `Config.Season`                                |
| Which panel is open when the screen appears               | `config.lua`             | `Config.DefaultSection`                        |
| Hover / click sounds                                      | `config.lua`             | `Config.UISounds`, `Config.UISoundVolume`      |
| Whether links get copied or opened                        | `config.lua`             | `Config.LinkAction`                            |
| Social buttons (bottom left)                              | `config.lua`             | `Config.Socials`                               |
| The three cards in the middle                             | `config.lua`             | `Config.Home`                                  |
| Characters on the left and right                          | `config.lua`             | `Config.Characters`                            |
| Background video or images                                | `config.lua`             | `Config.Background`                            |
| Music                                                     | `config.lua`             | `Config.Music`                                 |
| Tips and rules under the progress bar                     | `config.lua`             | `Config.Tips`, `Config.TipInterval`            |
| Changelog                                                 | `config.lua`             | `Config.Changelog`                             |
| News posts                                                | `config.lua`             | `Config.Updates`                               |
| Gallery                                                   | `config.lua`             | `Config.Gallery`                               |
| Keybinds                                                  | `config.lua`             | `Config.Keybinds`                              |
| Staff team                                                | `config.lua`             | `Config.Staff`                                 |
| Version check message in console                          | `config.lua`             | `Config.CheckVersion`                          |
| Any button, heading or label text                         | `locales/en.lua` (etc.)  | the matching key, e.g. `nav_staff`             |
| Loading stage names ("Loading the map"...)                | `locales/en.lua` (etc.)  | `stage_*`                                      |
| Season greeting ("Happy Holidays"...)                     | `locales/en.lua` (etc.)  | `season_*`                                     |
| Fonts, base colours, overall size                         | `web/css/base.css`       | `:root`                                        |
| Colours and decorations of a season                       | `web/js/seasons.js`      | `THEMES`                                       |
| What happens when the player spawns (fade in)             | `client/main.lua`        |                                                |

Your images, videos and music go in **`web/assets/`**. Every path in the config starts from the `web/` folder, so a file at `web/assets/staff/john.jpg` is written as `'assets/staff/john.jpg'`.

***

## Text and translations

Any text you write in the config can be a plain string:

```lua
title = 'New garage system'
```

or a table with one entry per language:

```lua
title = { en = 'New garage system', de = 'Neues Garagensystem', ar = 'نظام كراجات جديد' }
```

Players see the version for their language. If there's no translation for it, they get the English one, or whichever one you wrote first. If your server only uses one language, plain strings are fine and you can ignore all of this.

***

## Branding

```lua
Config.Branding = {
    ServerName = 'Pulse Scripts',
    Tagline = 'Premium roleplay, crafted with care.',
    Logo = 'assets/logo/logo.png',
    ShowName = true,
    BackdropWord = nil,
    PrimaryColor = '#1FE0C6',
    SecondaryColor = '#FFB547',
}
```

* **Logo**: a PNG, SVG or WebP with a transparent background. Replace `web/assets/logo/logo.png` or point this at your own file.
* **ShowName**: if your logo already has your server name written in it, set this to `false` and the logo is shown on its own without the name and tagline next to it.
* **BackdropWord**: the huge outlined word behind the cards. Leave it as `nil` to use the first word of your server name, write your own word, or set it to `false` to hide it.
* **PrimaryColor / SecondaryColor**: the two accent colours used everywhere: buttons, the progress line, highlights. When a seasonal theme is on, its colours take over unless you set `Config.Season.OverrideColors = false`.

***

## Language

```lua
Config.Locale = 'en'
Config.AllowLanguageSwitch = true
```

`en`, `de`, `fr`, `es` and `ar` come with the script. When `AllowLanguageSwitch` is on, players get a language picker in Settings, and whatever they pick is remembered on their PC from then on.

**Adding a language** takes one file:

1. Copy `locales/en.lua` and name the copy after the language code, e.g. `locales/it.lua`.
2. At the top of the file, change `Locales['en']` to `Locales['it']` and set `_name = 'Italiano'`. If the language reads right to left, also set `_dir = 'rtl'`.
3. Translate the text and you're done. It shows up in the language picker straight away.

You can then add `it = '...'` to any text in the config as well.

{% hint style="info" %}
The browser preview only loads the five languages that come with the script. To see your new one in the preview as well, add its code to the list in `web/js/dev.js` (search for `['en', 'de', 'fr', 'es', 'ar']`). This is only for the preview. In game every locale file is loaded automatically.
{% endhint %}

***

## Seasonal themes

```lua
Config.Season = {
    Theme = 'none',
    OverrideColors = true,
    Intensity = 1.0,
    ShowGreeting = true,
}
```

* **Theme**: `none`, `fall`, `winter`, `spring`, `summer`, `halloween`, `ramadan` or `newyear`. You can see all of them on the [overview page](README.md#seasonal-themes).
* **OverrideColors**: use the season's colours instead of your branding colours.
* **Intensity**: how many particles there are, from `0.0` (none) to `2.0` (double).
* **ShowGreeting**: the small greeting at the top, like "Happy Holidays". The wording comes from the `season_*` lines in the locale files.

Players who don't like the effects can turn them off under Settings.

***

## General

```lua
Config.CheckVersion = true
Config.DefaultSection = 'home'
Config.UISounds = true
Config.UISoundVolume = 0.25
Config.LinkAction = 'copy'
```

* **CheckVersion**: on startup, prints in the server console whether you're on the latest version. Set it to `false` to turn it off.
* **DefaultSection**: `home` shows the hub. You can also open the screen straight onto `changelog`, `updates`, `gallery`, `music`, `keybinds`, `staff` or `settings`.
* **UISounds / UISoundVolume**: the soft clicks when hovering and clicking.
* **LinkAction**: `'copy'` copies the link and shows a "link copied" message. `'open'` opens it in the player's browser. We recommend `copy`, because players are still in the loading screen and a browser window popping up pulls them out of the game.

***

## Social buttons

```lua
Config.Socials = {
    { label = 'Instagram', icon = 'instagram', url = 'https://www.instagram.com/yourserver/' },
    { label = 'Discord',   icon = 'discord',   url = 'https://discord.gg/yourinvite' },
}
```

Icons you can use: `instagram`, `tiktok`, `youtube`, `x`, `discord`, `store`, `globe`, `link`. Delete a line to remove that button, and add a line to add one.

***

## The hub cards

The hub has three cards. The big one on the left fills itself in, and the two on the right are up to you.

**The big card** shows the banner, title, category and summary of your **first** `Config.Updates` post, and the version number and change counts of your **first** `Config.Changelog` entry. You don't have to edit the card itself. Add a new post and a new changelog entry at the top of those lists and the card updates. The only things you set here are its label, icon and buttons:

```lua
Feature = {
    label = "What's new",
    icon = 'assets/icons/memo.png',
    button = 'Read changelog',
    action = 'changelog',
    secondary = 'All news',
    secondaryAction = 'updates',
},
```

**The two side cards:**

```lua
Cards = {
    {
        label = 'Community',
        icon = 'assets/icons/discord.svg',
        badge = 1,
        title = 'Join the community',
        text = 'Events, support and people to play with.',
        button = 'Copy Discord invite',
        action = 'url:https://discord.gg/yourinvite',
        linkName = 'Discord',
        preview = 'staff',
    },
    -- second card...
},
```

* **action**: what the button does. It can be the name of a panel (`changelog`, `updates`, `gallery`, `music`, `keybinds`, `staff`, `settings`), a link written as `'url:https://...'`, or `'discord'` to use the Discord link from your socials (this one needs a Discord button in `Config.Socials`).
* **linkName**: the name shown in the "Discord link copied" message.
* **badge**: the little red number on the icon. Remove it if you don't want one.
* **preview**: `'staff'` shows a row of your staff avatars on the card, and `'gallery'` shows three gallery thumbnails that keep changing. Leave it out to show neither.
* Put `\n` in a title or text to break the line.

Only the first two cards are shown. There isn't room for a third.

***

## Characters

```lua
Config.Characters = {
    Left = 'assets/characters/left.png',
    Right = 'assets/characters/right.png',
    Seasons = {
        winter = { Left = 'assets/characters/winter-left.png', Right = 'assets/characters/winter-right.png' },
    },
}
```

Use transparent PNGs, about **900 × 1500**. They sit on the bottom edge of the screen. Set `Left` or `Right` to `false` to hide one. The `Seasons` part is optional: whatever you put there replaces the normal art while that theme is on. The example above swaps both characters for winter.

***

## Background

```lua
Config.Background = {
    Mode = 'video',
    Videos = {
        'assets/video/background.webm',
        { file = 'assets/video/background.mp4', zoom = 1.23 },
    },
    Playlist = false,
    Images = {
        'assets/backgrounds/bg-1.jpg',
        'assets/backgrounds/bg-2.jpg',
    },
    Interval = 9000,
    Parallax = true,
}
```

* **Mode**: `'video'` or `'images'`.
* **Videos**: the screen plays the first one that works and uses the rest as backups. Use WebM (VP9). The [installation page](installation.md#step-4-add-your-own-background-video-optional) explains how to convert a video.
* **zoom**: if your clip has black bars baked into it, give it a zoom like `1.23` to crop them off.
* **Playlist**: set to `true` to play every video one after another instead of looping the first one.
* **Images**: used in `'images'` mode, and as a fallback if no video plays. The first image is also shown while the video loads.
* **Interval**: how long each image stays on screen, in milliseconds.
* **Parallax**: the slight movement when the mouse moves. Players can turn it off in Settings.

***

## Music

```lua
Config.Music = {
    Enabled = true,
    Autoplay = true,
    Volume = 0.35,
    Shuffle = false,
    Tracks = {
        { title = 'Invincible', artist = 'DEAF KEV · NCS', file = 'assets/music/ncs-invincible.mp3', cover = 'assets/music/ncs-invincible.jpg' },
    },
}
```

Put your MP3s and their cover images in `web/assets/music/` and add a line for each track. `Volume` is only the starting volume. Once a player moves the volume slider or turns on shuffle, their choice is saved on their PC and used from then on.

{% hint style="warning" %}
Only use music you're allowed to use. The three included tracks are from [NoCopyrightSounds](https://ncs.io), who ask for credit wherever their music is played. The credits are already in the config comments.
{% endhint %}

Set `Enabled = false` to remove music altogether. The player in the corner and the Music panel disappear with it.

***

## Tips and rules

```lua
Config.TipInterval = 7000
Config.Tips = {
    { type = 'tip',  text = 'Press F1 to open your phone.' },
    { type = 'rule', text = 'No random deathmatch.' },
}
```

`tip` and `rule` get different labels. They change every `TipInterval` milliseconds, and players can click to skip to the next one.

***

## Changelog

```lua
Config.Changelog = {
    {
        version = '3.0.0',
        date = '2026-09-20',
        title = 'The Pulse Update',
        changes = {
            { type = 'added',   text = 'Player-owned businesses.' },
            { type = 'changed', text = 'Job payouts increased by 15%.' },
            { type = 'fixed',   text = 'Vehicles no longer disappear from garages.' },
            { type = 'removed', text = 'Old inventory system.' },
        },
    },
}
```

**Newest goes at the top.** Write dates as `YYYY-MM-DD` and they'll be shown in each player's language. A change can be `added`, `changed`, `fixed` or `removed`.

***

## News posts

```lua
Config.Updates = {
    {
        title = 'Car Meet this Saturday',
        date = '2026-09-15',
        category = 'Event',
        banner = 'assets/updates/update3.jpg',
        summary = 'Bring your best build to the LS Car Meet.',
        body = {
            'First paragraph.',
            'Second paragraph.',
        },
    },
}
```

**Newest goes at the top** here as well. The first post is shown as "Featured" and also appears on the big hub card. `summary` is the short preview text, and `body` is the full post. Each line in `body` is its own paragraph. Wide banners work best (16:9).

***

## Gallery

```lua
Config.Gallery = {
    Categories = { 'City', 'Vehicles', 'Events' },
    Items = {
        { type = 'image', src = 'assets/gallery/shot.jpg', thumb = 'assets/gallery/shot-thumb.jpg', title = 'Rooftop Meet', category = 'City' },
        { type = 'video', src = 'assets/video/clip.webm',  thumb = 'assets/gallery/clip-thumb.jpg', title = 'Trailer',      category = 'Events' },
    },
}
```

* **thumb** is a smaller copy of the picture, around 640 px wide. It keeps the grid quick to load. Videos **need** one, because a video can't be shown as a thumbnail.
* **category** has to be spelled exactly like one of your `Categories`, or the filter won't find it.

***

## Keybinds

```lua
Config.Keybinds = {
    Categories = {
        { id = 'phone', label = 'Phone', color = '#F472B6' },
    },
    Binds = {
        { key = 'F1', category = 'phone', short = 'Phone', action = 'Open phone' },
        { key = 'X',  category = 'phone', short = 'Call', action = 'Quick call', modifiers = { 'LSHIFT' } },
    },
}
```

* **key**: FiveM key names like `F1`, `E`, `LSHIFT`, `LCTRL`, `SPACE`, `NUMPAD5`. The full list is in the comment above `Config.Keybinds` in the config. Common alternatives like `LCONTROL` or `CAPITAL` work too.
* **short**: the word printed on the key itself, so keep it to one short word. **action** is the full description shown in the list and on hover.
* **modifiers**: optional keys that have to be held at the same time, like `{ 'LSHIFT' }`.
* Mouse buttons (`MOUSE_LEFT`, `MOUSE_RIGHT`, `MOUSE_MIDDLE`, `MOUSE_EXTRABTN1`, `IOM_WHEEL_UP`...) appear in the list under the keyboard instead of on it.
* Each category's `color` is used to light up its keys.

***

## Staff

```lua
Config.Staff = {
    {
        rank = 'Founder',
        color = '#FFB547',
        members = {
            { name = 'Alex Pulse', role = 'Founder & Lead Developer', discord = '@alexpulse', avatar = 'assets/staff/alex.jpg', bio = 'Built the city from the ground up.' },
        },
    },
}
```

Ranks are shown in the order you list them. Avatars should be square (JPG, PNG or WebP). Leave `avatar` empty and the person's initials are shown in the rank colour instead. `discord` and `bio` are optional.

***

## Changing the code

Everything is open, so you're not limited to what the config offers. Here's what each file does:

| File                                   | What's in it                                                                            |
| -------------------------------------- | --------------------------------------------------------------------------------------- |
| `client/main.lua`                      | Closes the loading screen when the player spawns and fades the game in                  |
| `server/main.lua`                      | Sends the config to each player when they connect, and runs the version check            |
| `locales/*.lua`                        | All interface text, one file per language                                               |
| `web/index.html`                       | The page structure                                                                      |
| `web/css/base.css`                     | Fonts, colour tokens and overall sizing (`:root` at the top)                            |
| `web/css/layout.css`                   | Where everything sits: top bar, cards, bottom bar                                       |
| `web/css/components.css`               | Buttons, cards, toggles, tooltips, the "link copied" message                            |
| `web/css/sections.css`                 | The panels (changelog, gallery, music, staff, settings...)                              |
| `web/css/keyboard.css`                 | The keyboard in the Keybinds panel                                                      |
| `web/css/seasons.css`                  | Seasonal decorations                                                                    |
| `web/js/seasons.js`                    | Each season's colours, particles, decorations and greeting icon                         |
| `web/js/progress.js`                   | How FiveM's loading events turn into the percentage, and how much of the bar each stage gets |
| `web/js/pulse.js`                      | The heartbeat line under the percentage                                                 |
| `web/js/background.js`                 | Video, slideshow and the mouse movement                                                 |
| `web/js/audio.js`                      | The music player and the visualizer                                                     |
| `web/js/ui.js`                         | Top bar, panel switching, tips, hide-interface button                                   |
| `web/js/sections/*.js`                 | One file per panel                                                                      |
| `web/js/icons.js`                      | All the icons, including the social ones                                                |
| `web/js/sfx.js`                        | The interface sounds                                                                    |
| `web/js/dev.js`                        | The browser preview                                                                     |

A few things that are easy to miss:

* **Adding your own config option?** The screen only receives the settings listed in `buildPayload` in `server/main.lua`. Add your new option there too, or the screen won't see it.
* **Adding your own season?** Copy an existing entry in `THEMES` in `web/js/seasons.js`, give it a new name, and add a `season_yourname` greeting to the locale files.
* **The fade into the game** (black for 2 seconds, then a 2.5 second fade in) is set in `client/main.lua`. Change the two numbers there to make it faster or slower.

***

{% hint style="info" %}
[Built something cool with it? Show us in the Discord.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
