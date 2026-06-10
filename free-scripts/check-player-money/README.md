# 💲 Check Player Money

{% embed url="https://youtu.be/9lldlXt-wK0" %}

## Github Download: [\[Click Here\]](https://github.com/pulsepk/pl-checkplayermoney)

A **free FiveM admin tool** that lets staff check player wealth across the entire server. Run one command to open a menu with three query modes — filter by bank balance, view cash and crypto, or list the top N richest players.

Requires an ACE permission to use, keeping it staff-only.

***

## Features

### 🏦 Three Query Modes

* **Check Bank** — find all players with a bank balance above a specified amount
* **Check Cash & Crypto** — view bank, cash, and crypto balances for filtered players
* **Top Players** — list the wealthiest N players on the server, sorted by bank balance

### 🔒 ACE Permission Gated

The command is protected by a FiveM ACE permission (`checkplayermoney`). Only players or groups granted this ace can open the menu — everyone else is denied and logged.

### ⚙️ Framework Compatible

Works with **ESX**, **QBCore**, and **Qbox** automatically via [pl\_lib](https://github.com/pulsepk/pl_lib). Reads directly from your server's database — no manual framework config required.

### 🔔 Notification System

Auto-detected via pl\_lib. Supports ox\_lib, esx\_notify, okokNotify, wasabi\_notify, and more.

### 🗄️ Direct Database Queries

Queries your server's `users` (ESX) or `players` (QB/Qbox) table directly via oxmysql for accurate, real-time results.

***

{% hint style="info" %}
[Join the Discord for support and updates.](https://discord.gg/c6gXmtEf3H)
{% endhint %}
