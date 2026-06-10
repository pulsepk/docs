# 🏧 ATM Robbery

{% embed url="https://youtu.be/KgvpmNxQmlo" %}

## Github Download: [\[Click Here\]](https://github.com/pulsepk/pl-atmrob)

A **free, open-source FiveM ATM robbery script** supporting ESX, QBCore, and Qbox. Players can rob ATMs through three distinct methods — hacking, drilling, or pulling the unit loose with a vehicle and rope. Built on top of [pl\_lib](https://github.com/pulsepk/pl_lib) for seamless framework and UI compatibility with no manual configuration required.

***

## Features

### 🔓 Three Robbery Methods

* **Hack** — Use a hacking device and complete a minigame to crack the ATM electronically.
* **Drill** — Use a drill and complete the M-drilling minigame to break it open physically.
* **Rope & Vehicle** — Attach a rope to the ATM, hook the other end to a vehicle, and drive away to rip it from the wall. The detached ATM can then be looted wherever it lands.

### 🎮 Minigame Support

* **Hacking**: configurable — `utk_fingerprint`, `ox_lib`, `ps-ui-circle`, `ps-ui-maze`, `ps-ui-scrambler`, or `M-drilling`
* **Drilling**: uses [M-drilling](https://github.com/MxttDev/M-drilling) by default, fully configurable

### 🛒 Built-in Item Shop

An NPC shop spawns in the world where players can buy the required robbery items (hacking device, drill, rope). Location, items, and pricing are all configurable.

### 🚨 Police Dispatch Integration

Notifies police on robbery start. Compatible with **ps-dispatch**, **aty-dispatch**, **Quasar Dispatch**, and **Rcore Dispatch** — auto-detected via pl\_lib.

### ⚙️ Framework & Inventory Compatible

Powered by [pl\_lib](https://github.com/pulsepk/pl_lib) — works with **ESX**, **QBCore**, and **Qbox** out of the box. Supports **ox\_inventory**, **qb-inventory**, and **esx\_inventory**.

### 🎯 Target System

Supports **ox\_target** and **qb-target** — auto-detected, no config needed.

### 🔔 Notification System

Supports **ox\_lib**, **esx\_notify**, **okokNotify**, **wasabi\_notify**, **brutal\_notify**, and more — all auto-detected.

### 🛡️ Server-Side Security

All robbery actions are validated server-side. Includes cooldown enforcement, police count checks, player proximity validation, and exploit logging.

### 💸 Flexible Reward System

* Cash piles physically drop from the ATM (pickupable props), or reward can be added directly to inventory — your choice.
* Separate reward values for hacking and drilling.
* Configurable account type: `cash`, `bank`, or `dirty`.

### ⏱️ Robbery Cooldown

Server-wide cooldown between robberies, configurable in seconds.

### 👮 Police Presence Requirement

Set a minimum number of police officers required online before a robbery can start.

### 🌐 Multi-Language Support

Available in **English**, **Spanish**, **German**, **French**, **Italian**, **Turkish**, and **Danish**. Easy to add more via the `locales/` folder.

***

{% hint style="success" %}
**Free & open source.** No escrow, no Tebex key required — just download and use.
{% endhint %}

{% hint style="info" %}
[Join the Discord for support and updates.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
