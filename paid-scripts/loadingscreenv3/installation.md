# Installation

This takes about five minutes. Most of your time will go into filling in the config with your own server's stuff, and that part's covered on the [Customisation](customisation.md) page.

***

### Dependencies

Make sure this is installed and running.

[<kbd>pl\_lib</kbd>](https://github.com/pulsepk/pl_lib) (see the [pl\_lib install guide](../../pl_lib/pl_lib/installation.md) if you don't have it yet)

You don't need anything for your framework. The loading screen never talks to it, so Qbox, QBCore, ESX and standalone servers all work the same way.

***

### Step 1: Put it in your resources folder

Download `pl_loadingscreenv3` from your purchase, unzip it and drop the folder into your `resources` directory.

{% hint style="warning" %}
**Keep the folder name as `pl_loadingscreenv3`.** The version checker looks the script up by that name. Rename it and you'll get a "no entry in manifest" message in your console.
{% endhint %}

Using another loading screen right now, like our V1 or V2? Remove it or take it out of your `server.cfg`. Only one loading screen can run at a time.

***

### Step 2: Add it to server.cfg

```cfg
ensure pl_lib
ensure pl_loadingscreenv3
```

It doesn't matter where it sits next to your framework. What matters is that `pl_lib` starts before it. If `pl_lib` is missing, the loading screen won't start at all.

***

### Step 3: Put your server's details in

Open `config.lua`. Every option has a comment above it explaining what it does. If you only have a few minutes, change these first:

1. **`Config.Branding`**: your server name, tagline, logo and colours.
2. **`Config.Socials`**: your Instagram, TikTok, YouTube and so on.
3. **`Config.Home`**: swap our Discord invite in the Community card for yours (`action = 'url:https://discord.gg/...'`).
4. **`Config.Keybinds`** and **`Config.Staff`**: your real keybinds and your team.
5. **`Config.Changelog`** and **`Config.Updates`**: delete our example posts and write your own.

The [Customisation](customisation.md) page goes through every block and shows exactly which file to edit for each change.

***

### Step 4: Add your own background video (optional)

A demo clip is included, so you can leave this step for later. When you're ready to use your own:

Convert it to **WebM (VP9)** first. FiveM's built-in browser usually can't play H.264 `.mp4` files, so an mp4 that plays fine in Chrome can show nothing in game. If you have [ffmpeg](https://ffmpeg.org/download.html), this does it in one go and strips the audio, since the music player takes care of sound:

```bash
ffmpeg -i clip.mp4 -an -c:v libvpx-vp9 -b:v 0 -crf 36 -row-mt 1 background.webm
```

No ffmpeg? Any online converter works as long as you pick **WebM** as the format and **VP9** as the codec.

Put the file in `web/assets/video/` and point the config at it:

```lua
Config.Background = {
    Mode = 'video',
    Videos = {
        'assets/video/background.webm',
    },
    -- ...
}
```

{% hint style="info" %}
**Keep it small. Under 30 MB is a good target.** Players download the whole resource before the loading screen appears, so a big video means they stare at the default GTA screen for longer first.

The demo comes with an mp4 copy of the video as a fallback. Once your own WebM works, delete `web/assets/video/background.mp4` and remove its line from `Videos`. That cuts about 22 MB from the download.
{% endhint %}

If a video can't play for any reason, the screen skips to the next one in the list. If none of them play, it switches to the image slideshow from `Config.Background.Images`. You'll get a slideshow at worst, never a black screen.

***

### Step 5: Restart and test

Restart the resource (or the whole server) and reconnect:

```
ensure pl_loadingscreenv3
```

You should see something like this in the server console:

```
[pl_loadingscreenv3] Up to date (1.0.0).
```

{% hint style="warning" %}
**Config changes need a restart and a reconnect.** The server sends the config to each player when they connect, so to see a change, restart `pl_loadingscreenv3` and join again. You can also test without joining the server at all, see below.
{% endhint %}

***

### Optional: Preview it in your browser

This one saves a lot of time. You don't have to rejoin the server after every tiny change. You can open the loading screen in Chrome, edit `config.lua`, and just refresh the page.

1. Open a terminal **inside the `pl_loadingscreenv3` folder** and start a small local web server. If you have Python:

   ```bash
   python -m http.server 8080
   ```

   Or with Node:

   ```bash
   npx http-server -p 8080 -c-1
   ```
2. Open [http://localhost:8080/web/index.html](http://localhost:8080/web/index.html) in Chrome.
3. Edit `config.lua` or any locale file, save, and refresh the page.

You can add these to the end of the URL to check things quickly:

| Add to the URL       | What it does                                          |
| -------------------- | ----------------------------------------------------- |
| `?season=winter`     | Try a seasonal theme without changing the config      |
| `?locale=ar`         | Open in a specific language                           |
| `?section=keybinds`  | Open straight onto a panel                            |
| `?progress=off`      | Stop the fake progress bar from moving                |

Combine them with `&`, for example `?season=halloween&section=gallery`.

{% hint style="info" %}
Double-clicking `index.html` won't show your config. The browser blocks it from reading `config.lua` when it's opened as a plain file, so it has to go through a local server like the ones above. In the preview the progress bar fakes a load and the player is called "Dev Player". In game it uses the real loading progress and the player's real name.
{% endhint %}

***

{% hint style="success" %}
That's it. Your loading screen will show up the next time someone connects.
{% endhint %}

{% hint style="info" %}
[Join the Discord if anything's not working.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
