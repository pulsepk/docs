# Config File

<details>

<summary>Config File</summary>

```lua
Config = {}

Config.Debug = {
    Prints = false, --Prints debug messages in console
}

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

Config.RewardPoints = {
    gifts = 3,     -- points per collection
    delivery = 2,    -- points per delivery
}


Config.Event = {
    TargetDate = "2026-01-01T00:00:00",  -- ISO8601 format
    Timezone = "Europe/London",          -- Choose from options below
}

-- Supported Timezone Options (examples)
-- "UTC"
-- "Europe/London"
-- "America/New_York"
-- "Asia/Kolkata"
-- "Australia/Sydney"
-- "Asia/Tokyo" ]]

Config.Interaction = 'target' -- 'target' or 'textui'
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
    BlipName = "Christmas Deliveries",
    Coords = vector3(708.1627, -978.7142, 24.1257),
    Options = {
        Sprite = 89,
        Color = 1,
        Scale = 0.7,
        Display = 4
    },
    Ped = {
        coords=vector3(708.1627, -978.7142, 24.1257),
        heading=185.0453,
        model='s_m_m_trucker_01'
    },
    VehicleSpawn = {
        coords=vector3(708.9480, -982.0478, 24.1093), 
        heading=268.7512,
        model='burrito'
    }
}

Config.GiftMarker = {
    enabled = true,                -- turn gift marker on or off
    type = 21,                      -- marker type
    width = 0.3,
    height = 0.3,
    distance = 15.0,               -- draw distance
    color = { r = 255, g = 255, b = 255, a = 120 }, -- white marker
    bounceSpeed = 4,
    bounceHeight = 0.10
}

Config.DeliveryHelpMarker = {
    type = 21, -- Marker type
    width = 0.3, -- Marker width
    height = 0.3, -- Marker height
    color = { r = 255, g = 255, b = 255, a = 120 }, -- Marker color
    distance = 15, -- Distance to show the marker
    Interact = 1, -- Distance to interact with the marker
    bounceSpeed = 5,
    bounceHeight = 0.10
}

Config.Control = {
    Key = 38, --E key
}

Config.Emotes = {
    ["gift"] = {
        Dict = "hold_flowers@dad",
        Anim = "hold_flowers_clip",
        Label = "Gift",
        AnimationOptions = {
            Prop = 'christmas_present_01',
            PropBone = 60309,
            PropPlacement = {
                0.0180,
                0.0390,
                0.1160,
              0.0,
             -0.0,
              0.0
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

Config.GiftModel = 'christmas_present_01'

Config.DeliveryReward = 100

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

--Credits https://gist.github.com/Randolio/b18b2519a6ec4ec34d5309251c34827f
Config.DeliveryLoc = {
    Smallest = {
        Payout = 150, --Change the Payout Accordingly
        DeliveryCount = 3, -- Number of deliveries to complete in this route
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
        {label = 'Jamestown St 4', coords = vec3(256.58, -2023.60, 19.27)},
        {label = 'Jamestown St 5', coords = vec3(251.26, -2030.09, 18.71)},
        {label = 'Jamestown St 6', coords = vec3(368.45, -1896.04, 25.18)},
        {label = 'Jamestown St 7', coords = vec3(385.05, -1881.49, 26.03)},
        {label = 'Jamestown St 8', coords = vec3(399.44, -1864.83, 26.72)},
        {label = 'Jamestown St 9', coords = vec3(412.64, -1855.93, 27.32)},
        {label = 'Jamestown St 10', coords = vec3(427.48, -1841.97, 28.46)},
        {label = 'Macdonald St 1', coords = vec3(440.14, -1829.93, 28.36)},
        {label = 'Jamestown St 11', coords = vec3(495.28, -1823.25, 28.87)},
        {label = 'Jamestown St 12', coords = vec3(500.31, -1812.88, 28.89)},
        {label = 'Jamestown St 13', coords = vec3(511.92, -1790.83, 28.93)},
        {label = 'Jamestown St 14', coords = vec3(513.97, -1780.94, 28.91)},
        {label = 'Jamestown St 15', coords = vec3(500.52, -1697.14, 29.79)},
        {label = 'Jamestown St 16', coords = vec3(490.09, -1714.22, 29.71)},
        {label = 'Jamestown St 17', coords = vec3(479.75, -1736.23, 29.15)},
        {label = 'Jamestown St 18', coords = vec3(474.48, -1757.79, 29.09)},
        {label = 'Jamestown St 19', coords = vec3(472.52, -1775.21, 29.07)},
    },
    Medium = {
        Payout = 250, --Change the Payout Accordingly
        DeliveryCount = 4, -- Number of deliveries to complete in this route
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
        {label = 'Picture Perfect Drive 6', coords = vec3(-678.96, 511.65, 113.53)},
        {label = 'Picture Perfect Drive 7', coords = vec3(-667.12, 472.01, 114.14)},
        {label = 'Picture Perfect Drive 8', coords = vec3(-641.07, 520.52, 109.88)},
        {label = 'Picture Perfect Drive 9', coords = vec3(-622.84, 489.16, 108.40)},
        {label = 'Picture Perfect Drive 10', coords = vec3(-580.49, 492.12, 108.90)},
        {label = 'Picture Perfect Drive 11', coords = vec3(-595.24, 530.28, 107.41)},
        {label = 'Milton Rd 10', coords = vec3(-536.98, 477.58, 102.75)},
        {label = 'Milton Rd 11', coords = vec3(-561.20, 403.05, 101.81)},
        {label = 'Milton Rd 12', coords = vec3(-595.62, 393.21, 101.43)},
        {label = 'Milton Rd 13', coords = vec3(-615.48, 398.26, 101.63)},
        {label = 'Cox Way 1', coords = vec3(-516.60, 433.48, 97.36)},
        {label = 'Cox Way 2', coords = vec3(-500.00, 398.40, 98.27)},
        {label = 'Didion Dr 10', coords = vec3(-477.39, 354.29, 104.15)},
        {label = 'Didion Dr 11', coords = vec3(-444.28, 343.18, 105.09)},
        {label = 'Didion Dr 12', coords = vec3(-409.39, 341.74, 108.43)},
        {label = 'Didion Dr 13', coords = vec3(-371.83, 343.40, 109.94)},
        {label = 'Didion Dr 14', coords = vec3(-328.08, 369.68, 110.01)},
        {label = 'Didion Dr 15', coords = vec3(-297.92, 380.36, 112.10)},
        {label = 'Didion Dr 16', coords = vec3(-240.08, 381.64, 111.94)},
        {label = 'Didion Dr 17', coords = vec3(-166.40, 424.43, 111.81)},
        {label = 'Didion Dr 18', coords = vec3(-214.09, 399.88, 111.30)},
        {label = 'Cox Way 3', coords = vec3(-305.19, 431.66, 110.31)},
        {label = 'Cox Way 4', coords = vec3(-355.81, 422.36, 110.50)},
        {label = 'Cox Way 5', coords = vec3(-400.95, 427.46, 111.86)},
        {label = 'Cox Way 6', coords = vec3(-450.89, 395.62, 104.78)},
    },
    Longest = {
        Payout = 400, --Change the Payout Accordingly
        DeliveryCount = 5, -- Number of deliveries to complete in this route
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
        {label = 'Paleto Blvd 7', coords = vec3(-280.75, 6351.04, 32.60)},
        {label = 'Paleto Blvd 8', coords = vec3(-302.08, 6326.99, 32.89)},
        {label = 'Procopio Dr 17', coords = vec3(-332.35, 6302.38, 33.09)},
        {label = 'Procopio Dr 18', coords = vec3(-359.55, 6334.68, 29.85)},        
    }
}

-- Gift item names (use these as inventory item names in your item DB)
Config.Gifts = {
    'pl_christmas_gift_red',
    'pl_christmas_gift_green',
    'pl_christmas_gift_gold'
}

Config.GiveRewardMoney = "money" -- "bank", "money"

-- Each reward entry: { type = 'item'|'money'|'weapon', name = 'item_name'|'money' amount|'weapon name', count = number, chance = percent }

Config.Rewards = {
    pl_christmas_gift_red = {
        { type = 'item', name = 'pl_candy_cane', count = 2, chance = 50 },
        { type = 'item', name = 'pl_hot_chocolate', count = 1, chance = 30 },
        { type = 'money', amount = 100, chance = 20 }
    },

    pl_christmas_gift_green = {
        { type = 'item', name = 'pl_christmas_cookie', count = 3, chance = 40 },
        { type = 'item', name = 'pl_gingerbread', count = 1, chance = 30 },
        { type = 'money', amount = 200, chance = 30 }
    },

    pl_christmas_gift_gold = {
        { type = 'item', name = 'pl_location_clue', count = 1, chance = 20 },
        { type = 'money', amount = 500, chance = 50 }
    }
}

-- Each entry: itemName = { duration = seconds, notify = 'message shown', playAnim = true/false }
Config.Consumables = {
    pl_candy_cane = { duration = 5, notify = 'You ate a candy cane! Sweet and cozy.', playAnim = true },
    pl_hot_chocolate = { duration = 6, notify = 'You drank hot chocolate. Feeling warm.', playAnim = false },
    pl_christmas_cookie = { duration = 4, notify = 'Cookie consumed. Yum!', playAnim = true },
    pl_gingerbread = { duration = 4, notify = 'Gingerbread eaten.', playAnim = true },
    pl_location_clue = {}
}

Config.RemoveGiftOnUse = true -- remove 1 gift from inventory when used

Config.GiftCoords = {
    [1] =vec3(1512.501,-1956.709,70.787),
    [2] =vec3(1568.66,-1878.38,90.83), 
    [3] =vec3(1507.56,-1923.63,70.43), 
    [4] =vec3(1540.26,-2027.26,87.4), 
    [5] =vec3(1595.23,-2105.89,90.53), 
    [6] =vec3(1608.62,-2258.58,106.35), 
    [7] =vec3(1614.7,-2340.75,90.94), 
    [8] =vec3(1589.24,-2394.22,90.41), 
    [9] =vec3(1558.82,-2486.48,72.69), 
    [10] =vec3(1470.99,-2464.91,65.96), 
    [11] =vec3(1444.93,-2470.18,62.99), 
    [12] =vec3(1396.13,-2530.6,49.99), 
    [13] =vec3(1350.99,-2526.58,47.59), 
    [14] =vec3(1378.22,-2454.94,53.86), 
    [15] =vec3(1364.45,-2338.1,60.53), 
    [16] =vec3(1294.55,-2303.09,50.79), 
    [17] =vec3(1288.61,-2335.61,50.62), 
    [18] =vec3(1229.28,-2470.48,42.34), 
    [19] =vec3(1166.44,-2499.95,34.56), 
    [20] =vec3(1277.45,-1031.6,40.01), 
    [21] =vec3(1243.33,-1033.53,40.03), 
    [22] =vec3(1307.83,-1087.94,40.11), 
    [23] =vec3(1470.12,-1013.19,52.27), 
    [24] =vec3(1511.26,-982.12,60.64), 
    [25] =vec3(1660.47,-738.86,106.59), 
    [26] =vec3(1415.46,-540.58,74.87), 
    [27] =vec3(1423.91,-582.81,73.81), 
    [28] =vec3(1386.72,-642.59,73.32), 
    [29] =vec3(1052.23,-149.63,68.84), 
    [30] =vec3(992.72,-278.44,66.14), 
    [31] =vec3(934.84,-292.09,65.15), 
    [32] =vec3(900.24,-306.14,64.18), 
    [33] =vec3(896.59,-281.49,64.75), 
    [34] =vec3(827.81,-281.02,65.72), 
    [35] =vec3(821.09,-295.21,65.7), 
    [36] =vec3(791.32,-310.66,58.76), 
    [37] =vec3(746.84,-287.06,58.4), 
    [38] =vec3(690.09,-298.45,58.0), 
    [39] =vec3(727.78,-192.25,67.93), 
    [40] =vec3(696.45,-269.62,57.42), 
    [41] =vec3(611.69,-111.89,73.54), 
    [42] =vec3(559.03,-118.24,63.7), 
    [43] =vec3(554.34,-239.03,53.01),
    [44] =vec3(532.75,321.07,128.04), 
    [45] =vec3(494.05,352.75,135.89), 
    [46] =vec3(448.75,413.1,139.23), 
    [47] =vec3(431.07,556.81,168.06),
    [48] =vec3(343.59,505.96,151.97), 
    [49] =vec3(333.91,580.37,155.49), 
    [50] =vec3(181.44,653.55,203.63), 
    [51] =vec3(63.97,622.03,195.86),
    [52] =vec3(-15.14,601.89,195.32),
    [53] =vec3(-113.58,610.1,206.67), 
    [54] =vec3(-222.17,610.51,189.78), 
    [55] =vec3(-261.55,601.78,183.44),
    [56] =vec3(-417.93,675.87,158.48),
    [57] =vec3(-485.63,652.98,143.11),
    [58] =vec3(-545.53,657.77,142.48), 
    [59] =vec3(-633.03,800.94,194.79), 
    [60] =vec3(-625.05,797.76,193.38), 
    [61] =vec3(-561.21,786.06,189.15), 
    [62] =vec3(-322.7,645.81,173.49),
    [63] =vec3(1201.32,-578.14,68.14),
    [64]=vec3(1203.7, -560.26, 68.4),
    [65]=vec3(1205.21, -602.8, 66.74),
    [66]=vec3(1206.98, -622.4, 65.15),
    [67]=vec3(1219.68, -669.55, 62.07), 
    [68]= vec3(1218.76, -688.9, 59.8), 
    [69]= vec3(1233.85, -713.83, 59.65),
    [70]=vec3(1228.78, -727.61, 59.65), 
    [71]= vec3(995.45, -727.47, 56.46), 
    [72]= vec3(981.3, -715.43, 56.82),
    [73]= vec3(969.95, -699.92, 57.48), 
    [74]= vec3(961.59, -671.43, 57.09), 
    [75]= vec3(944.84, -652.11, 57.02), 
    [76]= vec3(931.27, -641.19, 56.86), 
    [77]= vec3(904.2, -616.94, 57.45), 
    [78]= vec3(886.55, -606.72, 57.22), 
    [79]= vec3(860.67, -582.83, 57.16), 
    [80]= vec3(844.03, -563.59, 56.83),
    [81]= vec3(850.61, -531.35, 56.93), 
    [82] = vec3(864.05, -508.6, 56.33), 
    [83]= vec3(879.62, -497.59, 56.88),
    [84]= vec3(905.59, -491.92, 58.02),
    [85]= vec3(920.9, -478.67, 60.08),
    [86]=vec3(1357.1830, -1692.5898, 60.5184),
    [87]=vec3(1337.3766, -1689.6417, 60.5184),
    [88]=vec3(1313.9886, -1699.1558, 57.8379),
    [89]=vec3(1287.6123, -1711.4440, 55.4775),
    [90]=vec3(1273.3206, -1721.3975, 54.6556),
    [91]=vec3(1250.7943, -1734.7618, 52.0369),
    [92]=vec3(1256.9185, -1760.8087, 49.2599),
    [93]=vec3(1295.9955, -1739.3925, 54.2818),
    [94]=vec3(1315.5609, -1732.2948, 54.7001),
    [95]=vec3(1366.7404, -1720.9974, 65.6343),
    [96]=vec3(1296.6027, -1619.2955, 54.2253),
    [97]=vec3(1276.4948, -1630.0796, 54.5417),
    [98]=vec3(1254.03, -1640.55, 50.89),
    [99]=vec3(1220.33, -1658.8, 47.63),
    [100]=vec3(1202.72, -1672.2, 41.36)
}  
```

</details>
