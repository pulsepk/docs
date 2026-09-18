# 🎨 UI Customization

The app's frontend is a React + Vite project (`ui/`), built and shipped as
static files rather than run live — so reskinning it means editing the
source and rebuilding, not just editing HTML in place.

***

## Project layout

```
ui/
├── src/
│   ├── App.jsx        -- main app shell/routing
│   ├── App.css
│   ├── colors.css      -- theme colors (light/dark)
│   ├── index.jsx
│   ├── index.css
│   └── components/
│       ├── Frame.jsx
│       └── Frame.css
├── public/
│   ├── icon.svg         -- app icon used by the phone's app list
│   ├── screenshot-light.png
│   └── screenshot-dark.png
├── vite.config.js
├── package.json
└── dist/                -- built output, this is what actually ships
```

`fxmanifest.lua` only ever references `ui/dist/**/*` — the `src/` folder
isn't shipped or read at runtime. **Every UI change needs a rebuild.**

***

## Colors

`src/colors.css` defines the whole light/dark palette as CSS variables:

```css
:root {
    --background-primary: #f5f5f5;
    --background-highlight: rgb(220, 220, 220);
    --text-primary: #000000;
    --text-secondary: #8e8e93;
}

[data-theme='dark'] {
    --background-primary: #000000;
    --background-highlight: rgb(20, 20, 20);
    --text-primary: #f2f2f7;
    --text-secondary: #6f6f6f;
}
```

Change these values to reskin the whole app without touching component code.
Per-restaurant accent colors come from `Config.Restaurants[i].color`
(server-side config, not this file) — that's what tints each restaurant's
card in the list.

***

## Rebuilding

```bash
cd ui
npm install
npm run build     # outputs to ui/dist — this is what fxmanifest.lua ships
```

`npm run dev` (or `npm start`) runs a local Vite dev server on port 3000 for
faster iteration — useful for layout/style work, but the final result still
needs `npm run build` before it'll show up in-game, since the resource only
ever loads `ui/dist/index.html`.

{% hint style="info" %}
`vite.config.js` sets `base: '/ui/dist'` specifically for the production
build, matching how the resource serves its NUI files. Don't change this
unless you also update the corresponding paths in `fxmanifest.lua`.
{% endhint %}

***

## App icon & screenshots

`public/icon.svg` is the icon shown in the phone's app list —
`client.lua`'s `AddCustomApp` call points at it via
`https://cfx-nui-<resource>/ui/dist/icon.svg`. Replace it with your own SVG
and rebuild. `screenshot-light.png`/`screenshot-dark.png` are reference
screenshots only, not loaded at runtime.

***

## lb-phone vs GKSPhone

The React app itself (`src/`) is shared between both builds — same
components, same styling. What differs is how each build's `client.lua`
registers the built app with its phone (`AddCustomApp` for lb-phone; the
equivalent GKSPhone call for the `-gks` build) and where each phone framework
expects the built files to live. If you're maintaining a custom skin for
both variants, build once in `ui/` and copy the resulting `dist/` folder into
both resource folders rather than maintaining two separate UI projects.
