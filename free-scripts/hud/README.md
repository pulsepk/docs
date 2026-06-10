# 🎮 HUD V1

{% embed url="https://youtu.be/GVH74UGXYXM" %}

***

## Download

This script is available in two versions:

| | **Escrow** | **Open Source** |
|---|---|---|
| **Price** | Free | Paid |
| **Lua files** | Unlocked | Unlocked |
| **Web/UI files** | Locked (escrow) | Complete `src/` files included |
| **Edit UI/React/TS** | ❌ | ✅ |
| **Download** | [**📥 Get Escrow (Free)**](https://pulsescripts.com/product/hudv1) | [**📥 Get Open Source**](https://pulsescripts.com/product/hudv1opensource) |

{% hint style="warning" %}
**Escrow vs Open Source — what's the difference?**

Both versions are fully functional. The **Escrow version is free** — all Lua files are unlocked and editable, but the compiled web UI files are locked. The **Open Source version is paid** and includes the **complete `src/` web files** (React + TypeScript + Tailwind CSS), so you can fully customise the look and feel of every HUD element at the code level.
{% endhint %}

***

## Features

### 📊 Player Status HUD
Circular stat indicators for **health**, **hunger**, **thirst**, **stamina**, **armor** (hidden at 0), and **oxygen** (only shown when underwater). Auto-detected from your framework via pl\_lib — works with ESX, QBCore, and Qbox with no manual config.

### 👤 Player Info Panel
Top-right panel showing **player ID**, **cash**, **bank balance**, and **job name with grade** — updated in real time as framework events fire.

### 🚗 Vehicle Dashboard
Full vehicle HUD when driving: **speedometer** (mph or kmh), **RPM gauge**, **fuel level** (turns red below 20%), **engine status**, **seatbelt status**, and **lights indicator** (OFF / LOW / HIGH).

### 🗺️ Minimap Control
Choose between **square** or **circle** minimap. Optionally show the minimap only while in a vehicle, or always keep it visible.

### 🔒 Seatbelt Mechanic
Toggle seatbelt with a configurable key (default **B**). Seatbelt prevents ragdolling on collision and blocks exiting the vehicle while buckled.

### 💡 Lights Toggle
Cycle vehicle lights (OFF → LOW → HIGH) with a configurable key (default **H**).

### 🎙️ Voice Proximity Indicator
Mic icon shows when talking and reflects your current voice proximity range.

### ⚙️ Framework & Inventory Compatible
Works with **ESX**, **QBCore**, and **Qbox** automatically via [pl\_lib](https://github.com/pulsepk/pl_lib). No manual framework config needed.

***

{% hint style="info" %}
[Join the Discord for support and updates.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
