# Preview Config

This is the full `config.lua` that comes with the script, so you can look through every option before you buy or install. Each setting is explained on the [Customisation](customisation.md) page.

<details>

<summary>config.lua</summary>

```lua
Config = {}

--[[
    PULSE SCRIPTS - LOADING SCREEN V3

    Every piece of text shown in the loading screen can be a plain string or a
    table of translations, e.g.

        title = 'New garage system'
        title = { en = 'New garage system', de = 'Neues Garagensystem', ar = 'نظام كراجات جديد' }

    When a translation is missing, the English one (or the first available) is used.
    All file paths are relative to the web/ folder.
]]

-- ─────────────────────────────────────────────────────────────
--  Branding
-- ─────────────────────────────────────────────────────────────
Config.Branding = {
    ServerName = 'Pulse Scripts',
    Tagline = { en = 'Premium roleplay, crafted with care.', de = 'Premium-Roleplay, mit Liebe gemacht.', fr = 'Du roleplay premium, fait avec soin.', es = 'Roleplay premium, hecho con cariño.', ar = 'تجربة رول بلاي فاخرة، مصنوعة بعناية.' },
    Logo = 'assets/logo/logo.png',   -- logo shown top-left (png / svg / webp, transparent background)
    ShowName = true,                 -- show ServerName + Tagline next to the mark. Set false if Logo is a full wordmark image
    BackdropWord = nil,              -- giant outlined word behind the cards (default: first word of ServerName). false = hide
    PrimaryColor = '#1FE0C6',        -- pulse teal
    SecondaryColor = '#FFB547',      -- signal amber
}

-- ─────────────────────────────────────────────────────────────
--  Language
-- ─────────────────────────────────────────────────────────────
Config.Locale = 'en'                 -- default language: en, de, fr, es, ar
Config.AllowLanguageSwitch = true    -- let players pick a language (remembered per player)

-- ─────────────────────────────────────────────────────────────
--  Seasonal theme - each one recolours the whole screen and adds its own decorations
--  'none'      : default graphite / teal / amber
--  'fall'      : amber tint, leaves piling up along the bottom, falling leaves
--  'winter'    : festive red tint, frosted card corners, fairy lights under the dock, snow on the pulse line
--  'spring'    : rose tint, cherry blossom branches, falling petals
--  'summer'    : jungle green tint, sun glare, palm silhouettes, warm light motes
--  'halloween' : orange / lime, fog, pumpkins, embers & bats
--  'ramadan'   : teal / gold, hanging lanterns, crescent moon, stars
--  'newyear'   : gold lights under the dock, confetti & fireworks
-- ─────────────────────────────────────────────────────────────
Config.Season = {
    Theme = 'none',
    OverrideColors = true,           -- use the season's accent colours instead of the branding colours
    Intensity = 1.0,                 -- particle amount multiplier (0.0 - 2.0)
    ShowGreeting = true,             -- seasonal greeting next to the server name
}

-- ─────────────────────────────────────────────────────────────
--  General
-- ─────────────────────────────────────────────────────────────
Config.CheckVersion = true           -- checks on start whether you're running the latest version and prints a notice in the console if an update is available
Config.DefaultSection = 'home'       -- home (hub) | changelog | updates | gallery | music | keybinds | staff | settings
Config.UISounds = true               -- soft hover / click sounds
Config.UISoundVolume = 0.25

-- What happens when a player clicks a social button or a card link (e.g. Join Discord):
--   'copy' : the link is copied to the clipboard and a "link copied" toast is shown (recommended -
--            players are still in the loading screen, so opening a browser pulls them out of the game)
--   'open' : opens the link in the player's default browser
Config.LinkAction = 'copy'

-- "Follow us" buttons in the bottom-left corner. icons: instagram, tiktok, youtube, x, discord, store, globe, link
Config.Socials = {
    { label = 'Instagram', icon = 'instagram', url = 'https://www.instagram.com/pulsescripts/' },
    { label = 'TikTok',    icon = 'tiktok',    url = 'https://www.tiktok.com/@pulse.scripts' },
    { label = 'YouTube',   icon = 'youtube',   url = 'https://www.youtube.com/@pulsescripts' },
    { label = 'X',         icon = 'x',         url = 'https://x.com/' },
}

-- ─────────────────────────────────────────────────────────────
--  Hub (the cards in the middle of the screen)
--  Feature : the big card. Its banner, title, version and change counts are filled in automatically
--            from the newest Config.Updates entry and the newest Config.Changelog entry.
--  Cards   : the two cards on the right.
--  action  : a section ('changelog', 'updates', 'gallery', 'music', 'keybinds', 'staff', 'settings')
--            or 'url:https://...' (copied to the clipboard / opened, see Config.LinkAction)
--  preview = 'gallery' shows rotating gallery thumbnails, preview = 'staff' shows the staff avatars.
--  Use \n in title / text for a line break.
-- ─────────────────────────────────────────────────────────────
Config.Home = {
    Feature = {
        label = { en = "What's new", de = 'Neuigkeiten', fr = 'Nouveautés', es = 'Novedades', ar = 'الجديد' },
        icon = 'assets/icons/memo.png',
        button = { en = 'Read changelog', de = 'Changelog lesen', fr = 'Lire le changelog', es = 'Ver cambios', ar = 'اقرأ سجل التغييرات' },
        action = 'changelog',
        secondary = { en = 'All news', de = 'Alle News', fr = 'Toutes les news', es = 'Todas las noticias', ar = 'كل الأخبار' },
        secondaryAction = 'updates',
    },
    Cards = {
        {
            label = { en = 'Community', de = 'Community', fr = 'Communauté', es = 'Comunidad', ar = 'المجتمع' },
            icon = 'assets/icons/discord.svg',
            badge = 1,
            title = { en = 'Join the community', de = 'Werde Teil der Community', fr = 'Rejoins la communauté', es = 'Únete a la comunidad', ar = 'انضم إلى المجتمع' },
            text = { en = 'Events, support and people to play with.', de = 'Events, Support und Leute zum Spielen.', fr = 'Événements, support et joueurs.', es = 'Eventos, soporte y gente para jugar.', ar = 'فعاليات ودعم وأشخاص للعب معهم.' },
            button = { en = 'Copy Discord invite', de = 'Discord-Link kopieren', fr = "Copier l'invitation", es = 'Copiar invitación', ar = 'نسخ رابط ديسكورد' },
            action = 'url:https://discord.gg/c6gXmtEf3H',
            linkName = 'Discord',
            preview = 'staff',               -- shows the staff avatars (opens the Staff sheet)
        },
        {
            label = { en = 'City gallery', de = 'Galerie', fr = 'Galerie', es = 'Galería', ar = 'معرض المدينة' },
            icon = 'assets/icons/camera.png',
            title = { en = 'Moments from the city', de = 'Momente aus der Stadt', fr = 'Moments de la ville', es = 'Momentos de la ciudad', ar = 'لحظات من المدينة' },
            button = { en = 'Open gallery', de = 'Galerie öffnen', fr = 'Ouvrir la galerie', es = 'Abrir galería', ar = 'افتح المعرض' },
            action = 'gallery',
            preview = 'gallery',
        },
    },
}

-- ─────────────────────────────────────────────────────────────
--  Character art on the left / right edge (transparent PNG, ~900x1500, anchored to the bottom).
--  Seasons can swap them, e.g. Santa & Mrs. Claus for winter. Set Left / Right to false to hide.
-- ─────────────────────────────────────────────────────────────
Config.Characters = {
    Left = 'assets/characters/left.png',
    Right = 'assets/characters/right.png',
    Seasons = {
        -- winter = { Left = 'assets/characters/winter-left.png', Right = 'assets/characters/winter-right.png' },
    },
}

-- ─────────────────────────────────────────────────────────────
--  Background footage
--  Mode 'video'  : loops the first entry of Videos that can play; later entries are fallbacks
--                  (set Playlist = true to play every entry in turn instead). If none play, Images are used.
--                  USE WEBM (VP9). FiveM's built-in browser usually cannot decode H.264 .mp4 files, so an mp4
--                  that plays in Chrome may show nothing in game. Convert with:
--                    ffmpeg -i clip.mp4 -an -c:v libvpx-vp9 -b:v 0 -crf 36 -row-mt 1 background.webm
--                  An entry can be a path or { file = '...', zoom = 1.23 } (zoom crops baked-in black bars).
--                  Keep files small (aim for < 30 MB): the whole resource downloads before the screen shows.
--  Mode 'images' : slow Ken Burns slideshow of Images
-- ─────────────────────────────────────────────────────────────
Config.Background = {
    Mode = 'video',
    Videos = {
        'assets/video/background.webm',                          -- your car-meet clip (VP9, letterbox + outro removed)
        { file = 'assets/video/background.mp4', zoom = 1.23 },   -- original mp4 as a fallback (delete it to save ~22 MB)
    },
    Playlist = false,
    Images = {
        'assets/backgrounds/bg-1.jpg',
        'assets/backgrounds/bg-2.jpg',
        'assets/backgrounds/bg-3.jpg',
        'assets/backgrounds/bg-4.jpg',
    },
    Interval = 9000,                 -- ms per image
    Parallax = true,                 -- subtle movement following the cursor
}

-- ─────────────────────────────────────────────────────────────
--  Music player
-- ─────────────────────────────────────────────────────────────
Config.Music = {
    Enabled = true,
    Autoplay = true,
    Volume = 0.35,                   -- 0.0 - 1.0 (players can change it, it is remembered)
    Shuffle = false,
    -- Music provided by NoCopyrightSounds (ncs.io). NCS asks for credit wherever its music is used:
    --   DEAF KEV - Invincible [NCS Release]                     https://ncs.io/Invincible
    --   Elektronomia - Sky High [NCS Release]                   https://ncs.io/SkyHigh
    --   Different Heaven & EH!DE - My Heart [NCS Release]       https://ncs.io/MyHeart
    Tracks = {
        { title = 'Invincible', artist = 'DEAF KEV · NCS',                 file = 'assets/music/ncs-invincible.mp3', cover = 'assets/music/ncs-invincible.jpg' },
        { title = 'Sky High',   artist = 'Elektronomia · NCS',             file = 'assets/music/ncs-sky-high.mp3',   cover = 'assets/music/ncs-sky-high.jpg' },
        { title = 'My Heart',   artist = 'Different Heaven & EH!DE · NCS', file = 'assets/music/ncs-my-heart.mp3',   cover = 'assets/music/ncs-my-heart.jpg' },
    },
}

-- ─────────────────────────────────────────────────────────────
--  Tips & rules carousel (type = 'tip' | 'rule')
-- ─────────────────────────────────────────────────────────────
Config.TipInterval = 7000
Config.Tips = {
    { type = 'tip',  text = { en = 'Press F1 to open your phone and check your messages.', de = 'Drücke F1, um dein Handy zu öffnen.', fr = 'Appuyez sur F1 pour ouvrir votre téléphone.', es = 'Pulsa F1 para abrir tu teléfono.', ar = 'اضغط F1 لفتح هاتفك وقراءة رسائلك.' } },
    { type = 'rule', text = { en = 'No random deathmatch — every conflict needs a roleplay reason.', de = 'Kein Random Deathmatch – jeder Konflikt braucht einen RP-Grund.', fr = 'Pas de deathmatch gratuit — chaque conflit doit avoir une raison RP.', es = 'Nada de deathmatch aleatorio: todo conflicto necesita un motivo de rol.', ar = 'ممنوع القتل العشوائي — كل نزاع يحتاج سبباً في الرول بلاي.' } },
    { type = 'tip',  text = 'Visit the Job Center at Legion Square to find your first job.' },
    { type = 'tip',  text = 'Use /report in-game to contact the staff team at any time.' },
    { type = 'rule', text = 'Respect everyone. Harassment of any kind results in a permanent ban.' },
    { type = 'tip',  text = 'Your vehicles are stored at the nearest garage when you log out.' },
}

-- ─────────────────────────────────────────────────────────────
--  Changelog (detailed, versioned). Newest first.
--  change types: 'added' | 'changed' | 'fixed' | 'removed'
-- ─────────────────────────────────────────────────────────────
Config.Changelog = {
    {
        version = '3.0.0',
        date = '2026-09-20',
        title = { en = 'The Pulse Update', de = 'Das Pulse-Update', ar = 'تحديث بولس' },
        changes = {
            { type = 'added',   text = { en = 'Brand-new loading screen with music, gallery and keybinds.', de = 'Brandneuer Ladebildschirm mit Musik, Galerie und Tastenbelegung.', ar = 'شاشة تحميل جديدة كلياً مع موسيقى ومعرض واختصارات.' } },
            { type = 'added',   text = 'Player-owned businesses with custom menus and employee management.' },
            { type = 'added',   text = 'New Vinewood Hills housing district with 24 properties.' },
            { type = 'changed', text = 'Rebalanced the economy — job payouts increased by 15%.' },
            { type = 'changed', text = 'Police MDT redesigned for faster report writing.' },
            { type = 'fixed',   text = 'Vehicles no longer disappear from garages after a restart.' },
            { type = 'fixed',   text = 'Phone notifications now stack correctly.' },
            { type = 'removed', text = 'Old legacy inventory system.' },
        },
    },
    {
        version = '2.4.1',
        date = '2026-08-28',
        title = 'Hotfix',
        changes = {
            { type = 'fixed',   text = 'Fixed a crash when entering the Maze Bank arena.' },
            { type = 'fixed',   text = 'Fuel consumption no longer doubles on bikes.' },
            { type = 'changed', text = 'Reduced the cooldown for store robberies to 45 minutes.' },
        },
    },
    {
        version = '2.4.0',
        date = '2026-08-15',
        title = 'Summer Nights',
        changes = {
            { type = 'added',   text = 'Beach events at Del Perro Pier every weekend.' },
            { type = 'added',   text = '12 new imported vehicles at the dealership.' },
            { type = 'changed', text = 'EMS respawn timer lowered from 10 to 7 minutes.' },
            { type = 'fixed',   text = 'Minor clipping issues in the Pillbox hospital interior.' },
            { type = 'removed', text = 'Temporary spring event decorations.' },
        },
    },
    {
        version = '2.3.0',
        date = '2026-07-02',
        title = 'Law & Order',
        changes = {
            { type = 'added',   text = 'Court system with judges, lawyers and trials.' },
            { type = 'changed', text = 'Jail sentences now continue after relogging.' },
            { type = 'fixed',   text = 'Handcuff animation desync between players.' },
        },
    },
}

-- ─────────────────────────────────────────────────────────────
--  Update log (news / announcements). Newest first.
-- ─────────────────────────────────────────────────────────────
Config.Updates = {
    {
        title = { en = 'Welcome to Season 3', de = 'Willkommen in Season 3', fr = 'Bienvenue dans la Saison 3', es = 'Bienvenido a la Temporada 3', ar = 'مرحباً بكم في الموسم الثالث' },
        date = '2026-09-20',
        category = 'Announcement',
        banner = 'assets/updates/update-4.jpg',
        summary = { en = 'A fresh start, a new city economy and dozens of new features. Here is everything you need to know.', ar = 'بداية جديدة واقتصاد جديد للمدينة وعشرات الميزات الجديدة. إليك كل ما تحتاج معرفته.' },
        body = {
            'Season 3 is finally here! After months of work behind the scenes, we are proud to launch the biggest update in the history of the server.',
            'Every player starts with a fresh economy, new job progression and the brand-new housing district in Vinewood Hills.',
            'Join our Discord for the full patch notes and to share your first impressions with the community.',
        },
    },
    {
        title = 'Car Meet this Saturday',
        date = '2026-09-15',
        category = 'Event',
        banner = 'assets/updates/update3.jpg',
        summary = 'Bring your best build to the LS Car Meet — prizes for the top three cars voted by the community.',
        body = { 'The meet starts at 20:00 server time at the LS Car Meet warehouse. Entry is free, and prizes include exclusive plates and livery packs.' },
    },
    {
        title = 'Whitelisted Jobs are Open',
        date = '2026-09-02',
        category = 'Jobs',
        banner = 'assets/updates/1.jpg',
        summary = 'LSPD, EMS and Mechanic applications are open. Apply through our website.',
        body = { 'We are looking for dedicated roleplayers for our whitelisted departments. Applications are reviewed within 72 hours.' },
    },
    {
        title = 'Summer Festival Recap',
        date = '2026-08-20',
        category = 'Community',
        banner = 'assets/updates/recap.jpg',
        summary = 'Over 300 players joined the summer festival. Thank you for making it unforgettable!',
        body = { 'Thank you to everyone who joined. Screenshots from the festival are now in the gallery.' },
    },
}

-- ─────────────────────────────────────────────────────────────
--  Gallery (screenshots & clips). type = 'image' | 'video'
-- ─────────────────────────────────────────────────────────────
Config.Gallery = {
    Categories = { 'City', 'Vehicles', 'Events', 'Car Meets' },
    Items = {
        { type = 'image', src = 'assets/updates/1.jpg',          thumb = 'assets/gallery/1-thumb.jpg',         title = 'Grove Street Days',  category = 'City' },
        { type = 'image', src = 'assets/updates/update3.jpg',    thumb = 'assets/gallery/update3-thumb.jpg',   title = 'Getaway Drivers',    category = 'Vehicles' },
        { type = 'image', src = 'assets/gallery/ingame-2.jpg',   thumb = 'assets/gallery/ingame-2-thumb.jpg',  title = 'White Skyline',      category = 'Car Meets' },
        { type = 'video', src = 'assets/video/background.webm',  thumb = 'assets/gallery/trailer-thumb.jpg',   title = 'Car Meet Trailer',   category = 'Events' },
        { type = 'image', src = 'assets/gallery/ingame-1.jpg',   thumb = 'assets/gallery/ingame-1-thumb.jpg',  title = 'Rooftop Meet',       category = 'Car Meets' },
        { type = 'image', src = 'assets/gallery/ingame-3.jpg',   thumb = 'assets/gallery/ingame-3-thumb.jpg',  title = 'Muscle Classic',     category = 'Vehicles' },
        { type = 'image', src = 'assets/updates/update-4.jpg',   thumb = 'assets/gallery/update-4-thumb.jpg',  title = 'Vinewood Business',  category = 'City' },
        { type = 'image', src = 'assets/gallery/ingame-4.jpg',   thumb = 'assets/gallery/ingame-4-thumb.jpg',  title = 'Highway Run',        category = 'Vehicles' },
        { type = 'image', src = 'assets/gallery/ingame-5.jpg',   thumb = 'assets/gallery/ingame-5-thumb.jpg',  title = 'Track Ready',        category = 'Car Meets' },
    },
}

-- ─────────────────────────────────────────────────────────────
--  Keybinds - bound keys light up on a drawn full-size keyboard, with `short` printed on the key.
--  key: FiveM key names (F1-F12, A-Z, 0-9, LSHIFT, RSHIFT, LCTRL, LALT, TAB, CAPSLOCK,
--       SPACE, RETURN, BACK, ESCAPE, GRAVE, MINUS, EQUALS, LBRACKET, RBRACKET, SEMICOLON,
--       APOSTROPHE, COMMA, PERIOD, SLASH, BACKSLASH, INSERT, DELETE, HOME, END, PAGEUP,
--       PAGEDOWN, UP, DOWN, LEFT, RIGHT, NUMPAD0-9, MULTIPLY, ADD, SUBTRACT, DIVIDE,
--       DECIMAL, NUMPADENTER). FiveM aliases such as LCONTROL / LMENU / CAPITAL also work.
--  modifiers: optional keys that must be held, e.g. { 'LSHIFT' }
-- ─────────────────────────────────────────────────────────────
Config.Keybinds = {
    Categories = {
        { id = 'general',  label = { en = 'General', de = 'Allgemein', fr = 'Général', es = 'General', ar = 'عام' },                color = '#1FE0C6' },
        { id = 'phone',    label = { en = 'Phone', de = 'Handy', fr = 'Téléphone', es = 'Teléfono', ar = 'الهاتف' },                color = '#F472B6' },
        { id = 'interact', label = { en = 'Interaction', de = 'Interaktion', fr = 'Interaction', es = 'Interacción', ar = 'التفاعل' }, color = '#FBBF24' },
        { id = 'emotes',   label = { en = 'Emotes', de = 'Emotes', fr = 'Emotes', es = 'Emotes', ar = 'الحركات' },                   color = '#34D399' },
        { id = 'movement', label = { en = 'Movement', de = 'Bewegung', fr = 'Mouvement', es = 'Movimiento', ar = 'الحركة' },          color = '#22D3EE' },
        { id = 'camera',   label = { en = 'Camera', de = 'Kamera', fr = 'Caméra', es = 'Cámara', ar = 'الكاميرا' },                   color = '#FB923C' },
    },
    Binds = {
        { key = 'F1',    category = 'phone',    short = { en = 'Phone', de = 'Handy', fr = 'Tél.', es = 'Móvil', ar = 'هاتف' },                 action = { en = 'Open phone', de = 'Handy öffnen', fr = 'Ouvrir le téléphone', es = 'Abrir teléfono', ar = 'فتح الهاتف' } },
        { key = 'B',     category = 'interact', short = { en = 'Interact', de = 'Aktion', fr = 'Interagir', es = 'Usar', ar = 'تفاعل' },         action = { en = 'Interact', de = 'Interagieren', fr = 'Interagir', es = 'Interactuar', ar = 'تفاعل' } },
        { key = 'F3',    category = 'emotes',   short = { en = 'Emotes', de = 'Emotes', fr = 'Emotes', es = 'Emotes', ar = 'حركات' },           action = { en = 'Emote menu', de = 'Emote-Menü', fr = 'Menu des emotes', es = 'Menú de emotes', ar = 'قائمة الحركات' } },
        { key = 'LCTRL', category = 'movement', short = { en = 'Crouch', de = 'Ducken', fr = 'Accroupi', es = 'Agachar', ar = 'انحناء' },        action = { en = 'Crouch', de = 'Ducken', fr = "S'accroupir", es = 'Agacharse', ar = 'الانحناء' } },
        { key = 'V',     category = 'camera',   short = { en = 'POV', de = 'Ego', fr = 'Vue 1P', es = '1ª P', ar = 'منظور' }, action = { en = 'First person view', de = 'Ego-Perspektive', fr = 'Vue à la première personne', es = 'Primera persona', ar = 'منظور الشخص الأول' } },
        { key = 'Z',     category = 'general',  short = { en = 'Radial', de = 'Radial', fr = 'Radial', es = 'Radial', ar = 'القائمة' },         action = { en = 'Radial menu', de = 'Radialmenü', fr = 'Menu radial', es = 'Menú radial', ar = 'القائمة الدائرية' } },
    },
}

-- ─────────────────────────────────────────────────────────────
--  Staff team (ranks in display order). avatar: square image (jpg / png / webp), initials are shown when empty.
-- ─────────────────────────────────────────────────────────────
Config.Staff = {
    {
        rank = { en = 'Founder', de = 'Gründer', fr = 'Fondateur', es = 'Fundador', ar = 'المؤسس' },
        color = '#FFB547',
        members = {
            { name = 'Alex Pulse',   role = 'Founder & Lead Developer', discord = '@alexpulse', avatar = 'assets/staff/staff1.jpg', bio = 'Built the city from the ground up. Loves clean code and fast cars.' },
        },
    },
    {
        rank = { en = 'Administrators', de = 'Administratoren', fr = 'Administrateurs', es = 'Administradores', ar = 'المشرفون العامون' },
        color = '#F43F5E',
        members = {
            { name = 'Jordan Reyes', role = 'Head Admin', discord = '@jreyes', avatar = 'assets/staff/staff3.jpg', bio = 'Handles appeals and server-wide decisions.' },
            { name = 'Sam Okafor',   role = 'Admin',      discord = '@samo',   avatar = 'assets/staff/staff2.jpg', bio = 'Economy balancing and events.' },
        },
    },
    {
        rank = { en = 'Moderators', de = 'Moderatoren', fr = 'Modérateurs', es = 'Moderadores', ar = 'المراقبون' },
        color = '#1FE0C6',
        members = {
            { name = 'Kai Tanaka',   role = 'Senior Moderator', discord = '@kaitan', avatar = 'assets/staff/staff4.jpg', bio = 'Night shift hero.' },
            { name = 'Noah Fischer', role = 'Moderator',        discord = '@noahf',  avatar = 'assets/staff/staff5.jpg', bio = 'Knows every rule by heart.' },
        },
    },
    {
        rank = { en = 'Support', de = 'Support', fr = 'Support', es = 'Soporte', ar = 'الدعم' },
        color = '#38BDF8',
        members = {
            { name = 'Zoe Martin',   role = 'Support', discord = '@zoem', avatar = 'assets/staff/staff6.jpg', bio = 'Here to help new players settle in.' },
        },
    },
}
```

</details>
