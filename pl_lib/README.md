# 📦 pl\_lib

## GitHub: [\[Click Here\]](https://github.com/pulsepk/pl_lib)

**pl\_lib** is a free, open-source compatibility library for FiveM. It acts as a single bridge between your scripts and the server's installed framework, inventory, target, notification, and other systems — so you write one API call and it works across ESX, QBCore, and Qbox automatically.

All Pulse scripts use pl\_lib as their foundation. If you are a developer, you can use the same exports in your own resources.

***

## What It Provides

| Module | What it does |
|---|---|
| **Notifications** | `Notify()` that routes to whichever notify resource is installed |
| **TextUI** | `TextUIShow/Hide` across ox\_lib, qb-core, jg-textui, and more |
| **Target System** | Unified `AddEntityTarget`, `AddBoxTarget`, `AddModelTarget` for ox\_target and qb-target |
| **Minigames** | `DoMinigame()` routing to ox\_lib, utk\_fingerprint, ps-ui, or M-drilling |
| **Progressbar** | `ProgressBar()` across ox\_lib, qb, and lation\_ui |
| **Skill Check** | `DoSkillCheck()` for ox\_lib and lation\_ui |
| **Input & Menus** | `ShowInputDialog`, `ContextMenu`, `RegisterListMenu` |
| **Inventory** | `AddItem`, `RemoveItem`, `HasItem`, `RegisterUsableItem`, `OpenStashInventory` |
| **Player Money** | `AddPlayerMoney`, `RemovePlayerMoney`, `GetPlayerAccountMoney` |
| **Society Banking** | `AddSocietyMoney`, `RemoveSocietyMoney`, `GetSocietyMoney` |
| **Dispatch** | `SendDispatch()` across ps-dispatch, aty, rcore, cd, and more |
| **Entity Utilities** | `EnsureModel`, `NetToEnt`, `TryRequestControl` |
| **Animation** | `LoadAnimDict`, `PlayAnim`, `LookAt` |
| **Fuel** | `SetVehicleFuel` across LegacyFuel, ox\_fuel, cdn-fuel, and more |
| **Keys** | `GiveVehicleKeys` across qb-vehiclekeys, wasabi\_carlock, and more |
| **Appearance** | `SetPlayerUniform`, `RevertPlayerClothing` |
| **Logger** | `Log()` to Discord webhooks, fivemanage, or fivemerr |

***

## Supported Systems

| Category | Supported |
|---|---|
| **Frameworks** | ESX, QBCore, QBox |
| **Target** | ox\_target, qb-target |
| **Inventory** | ox\_inventory, qb-inventory, qs-inventory, ps-inventory, codem-inventory, tgiann-inventory, origen\_inventory, jaksam\_inventory |
| **Notifications** | ox\_lib, esx\_notify, okokNotify, wasabi\_notify, brutal\_notify, mythic\_notify, lation\_ui |
| **TextUI** | ox\_lib, qb-core, jg-textui, esx\_textui, cd\_drawtextui, brutal\_textui, lation\_ui |
| **Minigames** | ox\_lib, utk\_fingerprint, ps-ui-circle, ps-ui-maze, ps-ui-scrambler, M-drilling |
| **Progressbar** | ox\_lib, ox\_lib\_circle, qb, lation\_ui |
| **Dispatch** | ps-dispatch, aty\_dispatch, rcore\_dispatch, cd\_dispatch, Opto\_dispatch |
| **Society/Banking** | Renewed-Banking, esx\_addonaccount, qb-management, qb-banking, okokBanking, snipe-banking, tgiann-bank |
| **Clothing** | esx\_skin, illenium-appearance, fivem-appearance, qb-clothing, tgiann-clothing, rcore\_clothing |
| **Fuel** | LegacyFuel, cdn-fuel, okokGasStation, rcore\_fuel, ox\_fuel |
| **Vehicle Keys** | qb-vehiclekeys, wasabi\_carlock, qs-vehiclekeys, vehicles\_keys |

***

{% hint style="info" %}
[Join the Discord for support and updates.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
