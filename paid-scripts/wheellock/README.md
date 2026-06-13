---
description: A paid FiveM wheel clamper script for police — supports ESX, QBCore, and Qbox via pl_lib
---

# 🔓 Wheel Clamper

{% embed url="https://youtu.be/N10_lA9NkbM" %}

## Purchase

> **Escrow Version** available on our store.\
> [Buy Here](https://pulsescripts.com/product/6805299)

> **Open Source Version** available on our store.\
> [Buy Here](https://pulsescripts.com/product/6805303)

***

A **paid FiveM police script** that lets officers place physical wheel clamps on player vehicles. Set a fine amount at the time of clamping — the vehicle owner can pay the fine to remove it, or cut the clamp themselves with the cutter item. Clamp visuals persist across garage spawns and sync to all clients in real time.

Powered by [pl\_lib](https://github.com/pulsepk/pl_lib) for automatic framework, inventory, target, notification, dispatch, and society banking detection. Works with **ESX**, **QBCore**, and **Qbox** out of the box — no manual compatibility config required.

***

## Features

### 🚗 Vehicle Clamping
Officers place a physical clamp prop on any registered player vehicle. The fine amount is set by the officer at the time of clamping and stored server-side — clients never control the fine value.

### 💰 Fine System
Vehicle owners can pay the fine directly from their bank to have the clamp removed. Officers collect the fine from their bank when they manually remove a clamp.

### ✂️ Clamp Cutter
Players can use a `wheel_clamp_cutter` item to remove a clamp from their **own vehicle** without paying the fine. Server verifies ownership before allowing this.

### 🗺️ Target & Command Support
Interactions use your installed target system (ox\_target or qb-target). Set `Config.DisableTarget = true` to switch to commands instead — configurable command names included.

### 🏦 Society / Treasury Integration
Optionally route collected fines into a shared police society account instead of the individual officer's bank. Configured via pl\_lib.

### 🚨 Dispatch Alert
Optional dispatch notification when a clamp is cut. Auto-detected from your installed dispatch resource via pl\_lib.

### 🔄 Garage Integration
Clamp visuals automatically re-apply when a clamped vehicle is spawned from a garage, and are removed when stored — without touching the database record. See the [Installation](installation.md) guide for the export calls.

### 📋 Police Clamp List
Officers can view all currently clamped vehicles via the `clampedvehicles` command — showing plate, owner, fine amount, and clamping officer.

### 🪝 Server Exports
Full export API for garage scripts and admin tools: `IsVehicleClamped`, `AddClamp`, `RemoveClamp`, `OnVehicleSpawned`, `OnVehicleStored`. See the [API](api.md) page.

### 📝 Webhook Logging
All clamp events (placed, officer removed, fine paid) are logged to a Discord webhook.

### ⚙️ Auto SQL Install
Database table is created automatically on resource start — no manual SQL import needed.

***

{% hint style="info" %}
[Join the Discord for support and updates.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
