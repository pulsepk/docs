# Config File

<details>

<summary>Config File</summary>

```lua
Config = {}

Config.CheckVersion = true
Config.AutoInstallSQL = true

Config.Framework = 'autodetect' -- 'autodetect' or "esx" ,"qb", "qbox"

Config.Locale = 'en' -- 'en', 'fr', 'de', 'es', 'it', 'pt', 'tr' -- Language

Config.FrameworkResources = {
    esx = {
        resource = 'es_extended',
        export = 'getSharedObject'
    },
    qb = {
        resource = 'qb-core',
        export = 'GetCoreObject'
    }
}

Config.HalloweenPoints = {
    pumpkin = 3,     -- points per pumpkin collected
    delivery = 2,    -- points per delivery
    trickOrTreat = 1 -- points per trick-or-treat
}


Config.HalloweenEvent = {
    TargetDate = "2025-10-31T23:59:59",  -- ISO8601 format
    Timezone = "Europe/London",          -- Choose from options below
}

-- Supported Timezone Options (examples)
-- "UTC"
-- "Europe/London"
-- "America/New_York"
-- "Asia/Kolkata"
-- "Australia/Sydney"
-- "Asia/Tokyo" ]]


Config.TextUI = "ox_lib" -- "3dtext" or "ox_lib"
Config.Notify = 'autodetect' --'autodetect' or 'ox_lib', 'esx_notify', 'okokNotify','lation_ui', 'wasabi_notify', 'brutal_notify', 'mythic_notify'
Config.Target = 'autodetect' --'autodetect' --'autodetect' or 'ox_target', 'qb-target'
Config.Progressbar = 'ox_lib' -- 'qb', 'ox_lib', 'ox_lib_circle', 'lation_ui'
Config.Menu = 'ox_lib' -- 'ox_lib', 'lation_ui'

Config.CheckCanCarryItem = true

Config.Prize = {
    { rank = 1, title = "First Place Prize", description = "$5000 + Legendary Item", icon = "trophyIcon", glowColor = "rgba(255, 215, 0, 0.8)", bgGradient = "from-yellow-900/40 to-orange-900/40" },
    { rank = 2, title = "Second Place Prize", description = "$3000 + Rare Cosmetic", icon = "secondplaceIcon", glowColor = "rgba(192, 192, 192, 0.6)", bgGradient = "from-gray-800/40 to-gray-700/40" },
    { rank = 3, title = "Third Place Prize", description = "$1500 + Unique Item", icon = "thirdplaceIcon", glowColor = "rgba(205, 127, 50, 0.6)", bgGradient = "from-amber-900/40 to-amber-800/40" },
}

Config.Delivery = {
    Enable = true, --if False Whole Delivery feature will be disable
    BlipName = "Halloween Deliveries",
    Coords = vector3(1142.0092, -465.3374, 66.8397),
    Options = {
        Sprite = 96,
        Color = 47,
        Scale = 0.7,
        Display = 4
    },
    Ped = {
        coords=vector3(1142.0092,-465.3374,66.8397),
        heading=253.52,
        model='s_m_m_trucker_01'
    },
    VehicleSpawn = {
        coords=vector3(1145.6339,-471.3034,65.9118), 
        heading=260.0458,
        model='burrito'
    }
}

Config.TrickoTreat = {
    Enable = true,
    pedModel = "a_m_y_hipster_01",
    zombieModel = "u_m_y_zombie_01",
    BlipName = "Trick or Treat House",
    Options = {
        Sprite = 40,
        Color = 47,
        Scale = 0.5,
        Display = 4
    },
}

Config.ZombieSpawnChance = 10 --10%

Config.Control = {
    Key = 38, --E key
}

Config.Emotes = {
    ["pump"] = {
        Dict = "missfbi4prepp1",
        Anim = "idle",
        Label = "Pumpkin",
        AnimationOptions = {
            Prop = "prop_veg_crop_03_pump",
            PropBone = 28422, 
            PropPlacement = {
                0.0200,  -- X offset
                0.0600,  -- Y offset
                -0.1200, -- Z offset
                0.0,     -- X rotation
                0.0,     -- Y rotation
                0.0      -- Z rotation
            },
            Flag = 49,
        }
    }
}

Config.Logging = {
    LogEnable = true, -- It will send logs.
    --'discord' for discord webhook. Edit the Log.lua file to add the webook
    --'fivemanage'
    --'fivemerr'
    LogType = 'discord'
}

Config.Fuel = { --Edit in the clientopen.lua
    enabled = true,
} 

Config.PumpkinModel = 'prop_veg_crop_03_pump'

Config.PumpkinReward = 1000

Config.DeliveryReward = 100

Config.TrickoTreatLoc = {
    {label = 'Mirror Park Blvd 1', coords = vec3(1228.86, -725.41, 60.80)},
    {label = 'Mirror Park Blvd 2', coords = vec3(1222.79, -697.04, 60.80)},
    {label = 'Mirror Park Blvd 3', coords = vec3(1221.39, -668.83, 63.49)},
    {label = 'Mirror Park Blvd 4', coords = vec3(1206.88, -620.22, 66.44)},
    {label = 'Mirror Park Blvd 5', coords = vec3(1203.69, -598.96, 68.06)},
    {label = 'Mirror Park Blvd 6', coords = vec3(1200.84, -575.72, 69.14)},
    {label = 'Mirror Park Blvd 7', coords = vec3(1204.48, -557.80, 69.62)},
    {label = 'Nikola Pl 1', coords = vec3(1302.80, -528.49, 71.46)},
    {label = 'Nikola Pl 2', coords = vec3(1328.17, -535.87, 72.44)},
    {label = 'Nikola Pl 3', coords = vec3(1347.80, -547.87, 73.89)},
    {label = 'Nikola Pl 4', coords = vec3(1372.98, -555.50, 74.69)},
    {label = 'Nikola Pl 5', coords = vec3(1388.53, -569.69, 74.50)},
    {label = 'Nikola Pl 6', coords = vec3(1386.18, -593.38, 74.49)},
    {label = 'Nikola Pl 7', coords = vec3(1367.30, -606.03, 74.71)},
    {label = 'Nikola Pl 8', coords = vec3(1341.83, -597.71, 74.70)},
    {label = 'Nikola Pl 9', coords = vec3(1323.54, -582.69, 73.25)},
    {label = 'Nikola Pl 10', coords = vec3(1301.33, -573.53, 71.73)},
     {label = 'Wild Oats Dr 1', coords = vec3(223.48, 514.19, 140.77)},
    {label = 'Wild Oats Dr 2', coords = vec3(149.16, 474.69, 142.51)},
    {label = 'Wild Oats Dr 3', coords = vec3(107.17, 467.23, 147.37)},
    {label = 'Wild Oats Dr 4', coords = vec3(57.98, 450.17, 147.03)},
    {label = 'Wild Oats Dr 5', coords = vec3(-7.57, 468.17, 145.87)},
    {label = 'Wild Oats Dr 6', coords = vec3(-66.52, 490.63, 144.69)},
    {label = 'Wild Oats Dr 7', coords = vec3(-109.90, 502.31, 143.48)},
    {label = 'Wild Oats Dr 8', coords = vec3(-175.49, 502.46, 137.42)},
    {label = 'Wild Oats Dr 9', coords = vec3(-230.23, 487.93, 128.77)},
    {label = 'Didion Dr 1', coords = vec3(-312.14, 474.67, 111.82)},
    {label = 'Whispymound Dr 1', coords = vec3(8.63, 540.41, 176.03)},
    {label = 'Whispymound Dr 2', coords = vec3(45.97, 555.89, 180.08)},
    {label = 'Whispymound Dr 3', coords = vec3(84.99, 561.71, 182.77)},
    {label = 'Whispymound Dr 4', coords = vec3(119.37, 564.46, 183.96)},
    {label = 'Whispymound Dr 5', coords = vec3(150.84, 555.85, 183.74)},
    {label = 'Whispymound Dr 6', coords = vec3(216.34, 620.42, 187.76)},
    {label = 'Whispymound Dr 7', coords = vec3(232.14, 672.09, 189.98)},
    {label = 'Procopio Promenade 10', coords = vec3(-709.87, 5768.67, 17.51)},
    {label = 'Procopio Promenade 9', coords = vec3(-706.02, 5766.78, 17.51)},
    {label = 'Procopio Promenade 8', coords = vec3(-701.78, 5764.89, 17.51)},
    {label = 'Procopio Promenade 7', coords = vec3(-698.20, 5763.21, 17.51)},
    {label = 'Procopio Promenade 6', coords = vec3(-694.07, 5761.30, 17.51)},
    {label = 'Procopio Promenade 5', coords = vec3(-690.18, 5759.49, 17.51)},
    {label = 'Procopio Promenade 4', coords = vec3(-687.39, 5759.04, 17.51)},
    {label = 'Procopio Promenade 3', coords = vec3(-685.93, 5763.11, 17.51)},
    {label = 'Procopio Promenade 2', coords = vec3(-683.91, 5766.50, 17.51)},
    {label = 'Procopio Promenade 1', coords = vec3(-681.93, 5770.75, 17.51)},
    {label = 'Procopio Promenade 11', coords = vec3(-480.81, 6266.25, 13.63)},
    {label = 'Procopio Promenade 12', coords = vec3(-453.57, 6337.12, 12.90)},
    {label = 'Paleto Blvd 1', coords = vec3(-374.56, 6190.98, 31.73)},
    {label = 'Paleto Blvd 2', coords = vec3(-356.99, 6207.47, 31.85)},
    {label = 'Paleto Blvd 3', coords = vec3(-347.29, 6225.23, 31.88)},
    {label = 'Paleto Blvd 4', coords = vec3(-15.18, 6557.69, 33.24)},
    {label = 'Paleto Blvd 5', coords = vec3(11.60, 6578.39, 33.07)},
    {label = 'Paleto Blvd 6', coords = vec3(31.61, 6596.41, 32.82)},
    {label = 'Procopio Dr 1', coords = vec3(56.47, 6646.05, 32.28)},
    {label = 'Procopio Dr 2', coords = vec3(35.63, 6663.06, 32.19)},
    {label = 'Procopio Dr 3', coords = vec3(-9.57, 6654.11, 31.69)},
    {label = 'Procopio Dr 4', coords = vec3(1.40, 6612.76, 32.08)},
    {label = 'Procopio Dr 5', coords = vec3(-41.42, 6637.02, 31.09)},
    {label = 'Procopio Dr 6', coords = vec3(-26.83, 6597.55, 31.86)},
    {label = 'Procopio Dr 7', coords = vec3(-44.70, 6582.37, 32.18)},
    {label = 'Procopio Dr 8', coords = vec3(-130.58, 6551.60, 29.52)},
    {label = 'Procopio Dr 9', coords = vec3(-105.61, 6528.55, 30.17)},
    {label = 'Procopio Dr 10', coords = vec3(-214.89, 6444.24, 31.31)},
    {label = 'Procopio Dr 11', coords = vec3(-189.29, 6409.56, 32.30)},
    {label = 'Procopio Dr 12', coords = vec3(-214.01, 6396.43, 33.09)},
    {label = 'Procopio Dr 13', coords = vec3(-237.55, 6422.75, 31.17)},
    {label = 'Procopio Dr 14', coords = vec3(-227.87, 6378.04, 31.76)},
    {label = 'Procopio Dr 15', coords = vec3(-272.19, 6400.67, 31.50)},
    {label = 'Procopio Dr 16', coords = vec3(-248.09, 6370.40, 31.85)},
    {label = 'Invention Ct 1', coords = vec3(-1068.83, -1162.28, 2.16)},
    {label = 'Invention Ct 2', coords = vec3(-1063.78, -1159.97, 2.55)},
    {label = 'Invention Ct 3', coords = vec3(-1046.19, -1159.91, 2.16)},
    {label = 'Invention Ct 4', coords = vec3(-1034.75, -1147.16, 2.16)},
    {label = 'Invention Ct 5', coords = vec3(-1024.84, -1139.31, 2.75)},
    {label = 'Invention Ct 6', coords = vec3(-1040.20, -1136.01, 2.16)},
    {label = 'Invention Ct 7', coords = vec3(-1074.07, -1152.56, 2.16)},
    {label = 'Invention Ct 8', coords = vec3(-977.73, -1108.06, 2.15)},
    {label = 'Invention Ct 9', coords = vec3(-992.15, -1103.73, 2.15)},
    {label = 'Invention Ct 10', coords = vec3(-970.17, -1093.00, 2.15)},
    {label = 'Invention Ct 11', coords = vec3(-959.70, -1109.71, 2.15)},
    {label = 'Invention Ct 12', coords = vec3(-948.51, -1107.55, 2.17)},
    {label = 'Invention Ct 13', coords = vec3(-952.61, -1077.65, 2.67)},
    {label = 'Invention Ct 14', coords = vec3(-938.65, -1087.90, 2.15)},
    {label = 'Invention Ct 15', coords = vec3(-942.98, -1075.61, 2.74)},
    {label = 'Imagination Ct 1', coords = vec3(-989.29, -989.61, 2.05)},
    {label = 'Imagination Ct 2', coords = vec3(-986.55, -981.58, 2.15)},
    {label = 'Imagination Ct 3', coords = vec3(-1007.17, -989.55, 2.15)},
    {label = 'Imagination Ct 4', coords = vec3(-1008.43, -1015.21, 2.15)},
    {label = 'Imagination Ct 5', coords = vec3(-1023.35, -998.03, 2.15)},
    {label = 'Imagination Ct 6', coords = vec3(-1022.20, -1022.96, 2.15)},
    {label = 'Imagination Ct 7', coords = vec3(-1041.84, -1025.52, 2.57)},
    {label = 'Imagination Ct 8', coords = vec3(-1081.02, -1036.23, 2.15)},
    {label = 'Imagination Ct 9', coords = vec3(-1108.23, -1041.75, 2.15)},
    {label = 'Imagination Ct 10', coords = vec3(-1104.20, -1059.51, 2.41)},
}

Config.Animation = {
    Take = {
        Dict = 'mp_common',
        Anim = 'givetake1_a'
    },
    Harvest = {
        Dict = 'amb@world_human_gardener_plant@female@base',
        Anim = 'base_female'
    }
}

Config.Reward = {
    {item='candycorn',amount=2,chance=50},
    {item='pumpkin_lollipop',amount=2,chance=50},
    {item='ghost_lollipo',amount=2,chance=50},
    {item='halloween_toffee',amount=2,chance=50},
    {item='pumpkin_cookies',amount=2,chance=50},
}
--Credits https://gist.github.com/Randolio/b18b2519a6ec4ec34d5309251c34827f
Config.DeliveryLoc = {
    Smallest = {
        Payout = 150, --Change the Payout Accordingly
        {label = 'Grove St 1', coords = vec3(76.20, -1948.22, 21.17)},
        {label = 'Grove St 2', coords = vec3(85.96, -1959.71, 21.12)},
        {label = 'Grove St 3', coords = vec3(114.31, -1961.08, 21.33)},
        {label = 'Grove St 4', coords = vec3(126.88, -1929.94, 21.38)},
        {label = 'Grove St 5', coords = vec3(118.42, -1920.99, 21.32)},
        {label = 'Forum Dr 1', coords = vec3(-158.09, -1680.06, 33.83)},
        {label = 'Forum Dr 2', coords = vec3(-148.28, -1687.74, 32.87)},
        {label = 'Forum Dr 3', coords = vec3(-146.83, -1688.47, 33.07)},
        {label = 'Forum Dr 4', coords = vec3(-142.43, -1692.28, 32.87)},
        {label = 'Forum Dr 5', coords = vec3(-141.66, -1693.75, 33.07)},
    },
    Medium = {
        Payout = 250, --Change the Payout Accordingly
        {label = 'Whispymound Dr 1', coords = vec3(8.63, 540.41, 176.03)},
        {label = 'Whispymound Dr 2', coords = vec3(45.97, 555.89, 180.08)},
        {label = 'Whispymound Dr 3', coords = vec3(84.99, 561.71, 182.77)},
        {label = 'Whispymound Dr 4', coords = vec3(119.37, 564.46, 183.96)},
        {label = 'Whispymound Dr 5', coords = vec3(150.84, 555.85, 183.74)},
        {label = 'Whispymound Dr 6', coords = vec3(216.34, 620.42, 187.76)},
        {label = 'Whispymound Dr 7', coords = vec3(232.14, 672.09, 189.98)},
        {label = 'Picture Perfect Drive 1', coords = vec3(-824.80, 422.28, 92.12)},
        {label = 'Picture Perfect Drive 2', coords = vec3(-762.17, 431.19, 100.19)},
        {label = 'Picture Perfect Drive 3', coords = vec3(-784.62, 459.36, 100.38)},
        {label = 'Picture Perfect Drive 4', coords = vec3(-717.99, 449.03, 106.91)},
        {label = 'Picture Perfect Drive 5', coords = vec3(-721.24, 490.01, 109.04)},
    },
    Longest = {
        Payout = 400, --Change the Payout Accordingly
        {label = 'Paleto Blvd 1', coords = vec3(-374.56, 6190.98, 31.73)},
        {label = 'Paleto Blvd 2', coords = vec3(-356.99, 6207.47, 31.85)},
        {label = 'Paleto Blvd 3', coords = vec3(-347.29, 6225.23, 31.88)},
        {label = 'Paleto Blvd 4', coords = vec3(-15.18, 6557.69, 33.24)},
        {label = 'Paleto Blvd 5', coords = vec3(11.60, 6578.39, 33.07)},
        {label = 'Paleto Blvd 6', coords = vec3(31.61, 6596.41, 32.82)},
        {label = 'Paleto Blvd 7', coords = vec3(-280.75, 6351.04, 32.60)},
        {label = 'Paleto Blvd 8', coords = vec3(-302.08, 6326.99, 32.89)},
        {label = 'Paleto Blvd 9', coords = vec3(-157.29, 6409.41, 31.92)},
        {label = 'Paleto Blvd 10', coords = vec3(-150.56, 6416.88, 31.92)},
    }
}

Config.PumpkinCoords = {
    [1] =vec3(1512.501,-1956.709,70.787),[2] =vec3(1568.66,-1878.38,90.83), [3] =vec3(1507.56,-1923.63,70.43), [4] =vec3(1540.26,-2027.26,87.4), [5] =vec3(1595.23,-2105.89,90.53), [6] =vec3(1608.62,-2258.58,106.35), [7] =vec3(1614.7,-2340.75,90.94), [8] =vec3(1589.24,-2394.22,90.41), [9] =vec3(1558.82,-2486.48,72.69), [10] =vec3(1470.99,-2464.91,65.96), [11] =vec3(1444.93,-2470.18,62.99), [12] =vec3(1396.13,-2530.6,49.99), [13] =vec3(1350.99,-2526.58,47.59), [14] =vec3(1378.22,-2454.94,53.86), [15] =vec3(1364.45,-2338.1,60.53), [16] =vec3(1294.55,-2303.09,50.79), [17] =vec3(1288.61,-2335.61,50.62), [18] =vec3(1229.28,-2470.48,42.34), [19] =vec3(1166.44,-2499.95,34.56), [20] =vec3(1277.45,-1031.6,40.01), [21] =vec3(1243.33,-1033.53,40.03), [22] =vec3(1307.83,-1087.94,40.11), [23] =vec3(1470.12,-1013.19,52.27), [24] =vec3(1511.26,-982.12,60.64), [25] =vec3(1660.47,-738.86,106.59), [26] =vec3(1415.46,-540.58,74.87), [27] =vec3(1423.91,-582.81,73.81), [28] =vec3(1386.72,-642.59,73.32), [29] =vec3(1052.23,-149.63,68.84), [30] =vec3(992.72,-278.44,66.14), [31] =vec3(934.84,-292.09,65.15), [32] =vec3(900.24,-306.14,64.18), [33] =vec3(896.59,-281.49,64.75), [34] =vec3(827.81,-281.02,65.72), [35] =vec3(821.09,-295.21,65.7), [36] =vec3(791.32,-310.66,58.76), [37] =vec3(746.84,-287.06,58.4), [38] =vec3(690.09,-298.45,58.0), [39] =vec3(727.78,-192.25,67.93), [40] =vec3(696.45,-269.62,57.42), [41] =vec3(611.69,-111.89,73.54), [42] =vec3(559.03,-118.24,63.7), [43] =vec3(554.34,-239.03,53.01), [44] =vec3(532.75,321.07,128.04), [45] =vec3(494.05,352.75,135.89), [46] =vec3(448.75,413.1,139.23), [47] =vec3(431.07,556.81,168.06), [48] =vec3(343.59,505.96,151.97), [49] =vec3(333.91,580.37,155.49), [50] =vec3(181.44,653.55,203.63), [51] =vec3(63.97,622.03,195.86), [52] =vec3(-15.14,601.89,195.32), [53] =vec3(-113.58,610.1,206.67), [54] =vec3(-222.17,610.51,189.78), [55] =vec3(-261.55,601.78,183.44), [56] =vec3(-417.93,675.87,158.48), [57] =vec3(-485.63,652.98,143.11), [58] =vec3(-545.53,657.77,142.48), [59] =vec3(-633.03,800.94,194.79), [60] =vec3(-625.05,797.76,193.38), [61] =vec3(-561.21,786.06,189.15), [62] =vec3(-322.7,645.81,173.49),[63] =vec3(1201.32,-578.14,68.14), [64]=vec3(1203.7, -560.26, 68.4),[65]=vec3(1205.21, -602.8, 66.74),[66]=vec3(1206.98, -622.4, 65.15),[67]=vec3(1219.68, -669.55, 62.07), [68]= vec3(1218.76, -688.9, 59.8), [69]= vec3(1233.85, -713.83, 59.65), [70]=vec3(1228.78, -727.61, 59.65), [71]= vec3(995.45, -727.47, 56.46), [72]= vec3(981.3, -715.43, 56.82), [73]= vec3(969.95, -699.92, 57.48), [74]= vec3(961.59, -671.43, 57.09), [75]= vec3(944.84, -652.11, 57.02), [76]= vec3(931.27, -641.19, 56.86), [77]= vec3(904.2, -616.94, 57.45), [78]= vec3(886.55, -606.72, 57.22), [79]= vec3(860.67, -582.83, 57.16), [80]= vec3(844.03, -563.59, 56.83), [81]= vec3(850.61, -531.35, 56.93), [82] = vec3(864.05, -508.6, 56.33), [83]= vec3(879.62, -497.59, 56.88), [84]= vec3(905.59, -491.92, 58.02),[85]= vec3(920.9, -478.67, 60.08)
}

```

</details>
