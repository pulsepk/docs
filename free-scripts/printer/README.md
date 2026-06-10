# 🖨️ Printer

{% embed url="https://youtu.be/4yrAf1gWQps" %}

## Github Download: [\[Click Here\]](https://github.com/pulsepk/pl_printer)

A **free FiveM printer script** that lets players print custom documents in-game. Players interact with a printer prop, type their document content, and receive a `paper` item in their inventory that stores the text as metadata — readable by other players.

Supports spawning printers at fixed world locations or letting players place a portable printer anywhere they choose.

***

## Features

### 📄 Custom Document Printing
Players open a UI, type any text, and print it as a physical `paper` item. The document content is stored in the item's metadata and can be read by any player who opens it.

### 📍 Fixed & Portable Printers
- **Location mode** (`EnableLocation = true`) — spawn printer props at defined world coordinates.
- **Item mode** (`EnableLocation = false`) — players carry the printer as an item and place it anywhere.

### 💳 Pay Per Print
Deducts a configurable amount from the player's bank or cash when printing. Set the price and account type in config.

### 🔒 Item-Gated Access
Optionally require players to have a specific item before they can open the printer UI (`Config.CheckItem`).

### ⚙️ Framework & Inventory Compatible
Powered by [pl\_lib](https://github.com/pulsepk/pl_lib) — works with **ESX**, **QBCore**, and **Qbox** automatically. No manual framework config required.

### 🔔 Notification System
Auto-detected via pl\_lib. Supports ox\_lib, esx\_notify, okokNotify, wasabi\_notify, brutal\_notify, and more.

### 🌐 Multi-Language Support
Available in **English**, **Spanish**, **German**, **French**, **Italian**, **Portuguese**, and **Turkish**.

***

{% hint style="info" %}
Only [FiveManage](https://fivemanage.com) image links work for document images — Discord CDN links expire and will break. See [Common Issues](common-issues.md) for more detail.
{% endhint %}

{% hint style="info" %}
[Join the Discord for support and updates.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
