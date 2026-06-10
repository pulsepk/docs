# Common Issues

***

### ❌ Background video is not showing / black background

{% hint style="danger" %}
**The most common reason for a broken background video. Check all of these:**

* **Wrong codec** — FiveM only plays **H.264 (AVC)**. H.265, HEVC, AV1, and VP9 will silently fail.
* **File too large** — Files over **20 MB** will not load. Always compress first.
* **Resolution too high** — Use **720p**. 1080p and 4K are too heavy for FiveM's browser.
* **Streaming URL used** — YouTube, Twitch, and any external URL will **not** work. The file must be local.
* **Wrong path in config.js** — Must exactly match the file location (e.g. `assets/video/background.mp4`).
* **File name mismatch** — The filename on disk must exactly match what is referenced in `config.js` and `fxmanifest.lua`.
{% endhint %}

**Fix:** Go to [freeconvert.com/video-compressor](https://www.freeconvert.com/video-compressor), upload your video, set resolution to **720p**, encoder to **H.264 – CPU**, and keep the output under **20 MB**.

#### Video Tutorial

{% embed url="https://youtu.be/vfsgxu7nMd4" %}

***

### ❌ Background music is not playing

**Possible causes:**

* The music file path in `config.js` is wrong — confirm it matches the actual file location inside `assets/`.
* The file format is not supported — use **MP3** or **OGG**.
* The player muted the audio on a previous visit — this setting is saved in the browser. Ask them to click the unmute button on the loading screen.

***

### ❌ Loading screen is stuck / never disappears

**Cause:** The loading screen only disappears once FiveM has finished loading all resources. If a resource throws a startup error, the screen can hang indefinitely.

**Fix:**
1. Open your server console and look for any resource errors on startup.
2. Fix the erroring resource.
3. If no errors appear, check that `pl_loadingscreenv1` is ensured at the very **top** of `server.cfg` — not at the bottom.

***

### ❌ Black screen with no loading screen UI at all

**Cause:** The resource failed to start, or the `ensure` line is missing/wrong in `server.cfg`.

**Fix:**
1. Confirm `ensure pl_loadingscreenv1` is in your `server.cfg`.
2. Confirm the folder name on disk matches exactly — it is case-sensitive on Linux servers.
3. Check the server console for any errors from `pl_loadingscreenv1` on startup.

***

{% hint style="info" %}
[Join the Discord for support.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
