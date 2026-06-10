# Installation

## 📦 Installation Guide

***

### Step 1 — Download

Choose your version from the [README](README.md):

* **Escrow (Free)** — [pulsescripts.com/product/loadingscreenv2](https://pulsescripts.com/product/loadingscreenv2)
* **Open Source (Paid)** — [pulsescripts.com/product/7314950](https://pulsescripts.com/product/7314950)

Extract the folder and place `pl_loadingscreenv2` inside your server's `resources` directory.

***

### Step 2 — Add to server.cfg

```cfg
ensure pl_loadingscreenv2
```

{% hint style="warning" %}
The loading screen resource must be started **before** your framework and all other resources, otherwise it may not appear. Place the `ensure` line at the very top of your `server.cfg`.
{% endhint %}

***

### Step 3 — Configure

Open `web/config.js`. All customisation is done here:

```javascript
// Server name shown on the loading screen
serverName: "Your Server Name",

// Server keybinds shown on screen
keybinds: [
    { key: "F1",  action: "Open Menu" },
    { key: "F2",  action: "Inventory" },
],

// Staff members displayed on the loading screen
staff: [
    { name: "AdminName", role: "Owner" },
    { name: "ModName",   role: "Moderator" },
],

// Background music tracks (MP3, OGG, etc.)
music: [
    { name: "Track 1", url: "assets/music/track1.mp3" },
],

// Social media links (leave empty "" to hide the button)
discord:   "https://discord.gg/yourlink",
youtube:   "",
twitter:   "",
instagram: "",
```

***

### Step 4 — Set Your Background Video

Place your video file inside `assets/` and set the path in `config.js`:

```javascript
video: {
    url: "assets/background.mp4",
},
```

{% hint style="danger" %}
### ⚠️ Reasons your background video will NOT work

These are the most common causes of a black/broken background:

* **Wrong codec** — FiveM's browser only plays **H.264 (AVC)**. H.265, AV1, VP9, and other codecs will not play.
* **File too large** — Files over **20 MB** will fail to load. Compress your video first.
* **Resolution too high** — 1080p and 4K videos are often too heavy. Use **720p**.
* **Streaming URL** — YouTube, Twitch, or any online URL will **not** work. The file must be stored locally inside the resource.
* **Wrong file path** — The path in `config.js` must exactly match where the file is placed (e.g. `assets/background.mp4`).
* **File name mismatch** — If `fxmanifest.lua` references `background.mp4`, your file must be named exactly `background.mp4`.

**Fix:** Use [freeconvert.com/video-compressor](https://www.freeconvert.com/video-compressor) — set resolution to **720p**, encoder to **H.264 – CPU**, and keep the output under **20 MB**.
{% endhint %}

***

### Step 5 — Add Assets and Restart

Place all images, music, and video files inside the `assets/` folder and update their paths in `config.js`. Then restart your server.

***

{% hint style="success" %}
Done! Your loading screen will now appear when players connect.
{% endhint %}

{% hint style="info" %}
[Join the Discord in case you need additional support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
