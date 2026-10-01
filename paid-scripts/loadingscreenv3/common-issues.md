# Common Issues

Most problems come down to a missing dependency, a video format FiveM can't play, or a setting the player saved on their own PC. Check here before opening a ticket.

***

<details>

<summary>The resource won't start / "Could not find dependency pl_lib"</summary>

The loading screen needs `pl_lib`. If it's missing or starts later, the loading screen won't start.

Make sure it's in your resources folder, then check the order in `server.cfg`:

```cfg
ensure pl_lib
ensure pl_loadingscreenv3
```

If `pl_lib` itself won't start, check its own requirements in the [pl\_lib install guide](../../pl_lib/pl_lib/installation.md).

</details>

<details>

<summary>The background is black or the video doesn't play</summary>

Nine times out of ten it's the video format. FiveM's built-in browser usually **can't play H.264 `.mp4` files**, even ones that play fine in Chrome. Convert the video to **WebM (VP9)**:

```bash
ffmpeg -i clip.mp4 -an -c:v libvpx-vp9 -b:v 0 -crf 36 -row-mt 1 background.webm
```

If that doesn't fix it, check these:

* The path in `Config.Background.Videos` starts from the `web/` folder, so `'assets/video/background.webm'` and not `'web/assets/video/...'`.
* The file name matches exactly, including upper and lower case. Linux servers care about this.
* The file isn't huge. Aim for under 30 MB.
* It's a local file. YouTube, Streamable and other online links won't work.

To see what's going on, open the [browser preview](installation.md#optional-preview-it-in-your-browser), press F12 and look at the console. A video that can't be played logs `background video skipped (missing or unsupported)` along with the file name.

Even when every video fails, the screen switches to your `Images` slideshow, so if you see the slideshow instead of your video, this is why.

</details>

<details>

<summary>The loading screen never goes away</summary>

The loading screen closes when the player spawns. Most character selection scripts (Qbox, QBCore and ESX multicharacter, for example) also close it themselves when the character menu opens, so normally you don't have to do anything.

If yours stays stuck:

1. Look in the server console and in F8 for errors from other resources. A script that crashes while the game is loading can stop the player from ever spawning.
2. If you use a custom spawn or character script, make sure it calls this when it takes over the screen:

   ```lua
   ShutdownLoadingScreenNui()
   ```

</details>

<details>

<summary>I changed the config but nothing changed in game</summary>

The config is sent to each player when they connect, so you need to **restart `pl_loadingscreenv3` and reconnect** to see the change.

Some things are saved on each player's own PC, and those win over the config once the player has changed them:

* **Language**: once a player picks a language in Settings, `Config.Locale` won't change it for them.
* **Music volume and shuffle**: `Config.Music.Volume` is only the starting volume.
* **Seasonal effects and background motion**: if a player turned these off, they stay off.

If you're testing in the browser preview and want a clean start, clear the site data for `localhost` in your browser.

</details>

<details>

<summary>There's no music</summary>

* If you see **"Click anywhere to enable sound"**, the game blocked autoplay. One click anywhere starts the music. This is normal and depends on the player's settings.
* Check that `Config.Music.Enabled = true` and that the paths in `Tracks` point to real MP3 files in `web/assets/music/`.
* The player may have turned their volume all the way down at some point, and that's remembered. They can turn it back up in Settings or in the Music panel.

</details>

<details>

<summary>Clicking a link doesn't open my browser</summary>

That's on purpose. By default links are **copied to the clipboard** and a "link copied" message pops up, so players aren't pulled out of the game while it's still loading. To open links in the browser instead:

```lua
Config.LinkAction = 'open'
```

</details>

<details>

<summary>Players see the normal GTA loading screen for a while before mine appears</summary>

Players have to download the whole resource before the loading screen can show, and the default files add up to roughly 56 MB, most of it the demo video and music. To make that faster:

* Delete `web/assets/video/background.mp4` (and its line in `Config.Background.Videos`) once your WebM works. That alone saves about 22 MB.
* Compress your own video and keep it under 30 MB.
* Delete demo images, music and gallery shots you aren't using.

This only happens the first time. After that, FiveM keeps the files cached until you change them.

</details>

<details>

<summary>Console says "Version check failed ... no entry in manifest"</summary>

You renamed the folder. The version checker looks the script up by its name, so change the folder back to `pl_loadingscreenv3`.

</details>

<details>

<summary>Console says "Version check failed ... server unreachable"</summary>

Your server couldn't reach GitHub to check for updates. Some hosts block outgoing requests. It doesn't affect the loading screen at all. If the message bothers you, turn the check off:

```lua
Config.CheckVersion = false
```

</details>

<details>

<summary>Console says Locale "xx" not found, falling back to "en"</summary>

`Config.Locale` is set to a language that doesn't have a file in `locales/`. Check the spelling (`en`, `de`, `fr`, `es`, `ar`), or add the file if it's a language you're adding yourself. The [Customisation](customisation.md#language) page shows how.

</details>

<details>

<summary>A keybind doesn't light up on the keyboard</summary>

* Check the key name against the list in the comment above `Config.Keybinds` in `config.lua`. Use `LCTRL`, not `Control`.
* Make sure its `category` matches the `id` of one of your categories.
* Mouse buttons (`MOUSE_LEFT`, `IOM_WHEEL_UP`...) don't have a key on the keyboard, so they're shown in the list underneath it instead.

</details>

<details>

<summary>The gallery card on the hub always shows the same three pictures</summary>

The thumbnails only change when there are more than three images in `Config.Gallery.Items` (videos don't count). Add a few more and they'll start changing.

</details>

***

{% hint style="info" %}
[Still stuck? Open a ticket in the Discord.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
