# Installation

{% stepper %}
{% step %}
### Step 1 — Install Dependencies

Download and place all three resources inside your server's `resources` directory:

* [ox\_lib](https://github.com/communityox/ox_lib/releases)
* [pl\_lib](https://github.com/pulsepk/pl_lib)
* [pl\_wheelclamper\_assets](https://portal.cfx.re/)

Add the following to your `server.cfg`. **Order matters** — dependencies must start before `pl_wheelclamper`.

```cfg
ensure ox_lib
ensure pl_lib
ensure pl_wheelclamper_assets
ensure pl_wheelclamper
```

{% hint style="info" %}
Framework, notifications, target system, dispatch, and society banking are all auto-detected by pl\_lib. Configure them in `pl_lib/config/config.lua` if you need to force a specific system.
{% endhint %}
{% endstep %}

{% step %}
### Step 2 — Add Items

Open one of the following files from the `Install/` folder depending on your inventory:

| Inventory     | File to open             |
| ------------- | ------------------------ |
| ox\_inventory | `items_ox_inventory.lua` |
| QBCore        | `items_qb_inventory.lua` |

Copy its contents into your inventory item configuration:

| Inventory     | Destination file              |
| ------------- | ----------------------------- |
| QBCore        | `qb-core/shared/items.lua`    |
| ox\_inventory | `ox_inventory/data/items.lua` |
{% endstep %}

{% step %}
### Step 3 — Add Inventory Images

Open the folder:

```
Install/Img
```

Copy all images into your inventory's image directory:

| Inventory     | Destination directory       |
| ------------- | --------------------------- |
| QBCore        | `qb-inventory/html/images/` |
| ox\_inventory | `ox_inventory/web/images/`  |
{% endstep %}

{% step %}
### Step 4 — Garage Compatibility

To show the wheel clamp visual when a clamped vehicle is spawned from a garage, add one export call inside your garage resource.

> This step is only required if you use a garage script.

#### esx\_garage

**File:** `esx_garage/server/main.lua` — Line \~23\
**Event:** `esx_garage:updateOwnedVehicle`

Add inside the event handler:

```lua
exports.pl_wheelclamper:OnVehicleSpawned(source, data.vehicleProps.plate)
exports.pl_wheelclamper:OnVehicleStored(source, data.vehicleProps.plate)
```

#### Before

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

#### After

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

#### qb-garages

**File:** `qb-garages/server/main.lua` — Line \~124 & 145\
**Callback:** `qb-garages:server:spawnvehicle, qb-garages:server:canDeposit`

Add at the end of the event handler:

```lua
exports.pl_wheelclamper:OnVehicleSpawned(source, plate)
exports.pl_wheelclamper:OnVehicleStored(source, plate)
```

#### Before

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

#### After

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

#### qbx\_garage

**File:** `qbx_garage/server/spawn-vehicle.lua` **- Line 32 ,** `qbx_garage/server/main.lua` **- Line 202**

**Callback:** `qbx_garages:server:spawnVehicle, qbx_garages:server:parkVehicle`

Add before the `return` at the end of the callback:

```lua
exports.pl_wheelclamper:OnVehicleSpawned(source, playerVehicle.props.plate)
exports.pl_wheelclamper:OnVehicleStored(source, GetVehicleNumberPlateText(vehicle))
```

#### Before

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### After

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

#### JG Advanced Garages

**File:** `jg-advancedgarages->config-config-cl.lua` , `jg-advancedgarages->config-config-sv.lua`

**Event:** `jg-advancedgarages:client:InsertVehicle:config`  ,  `jg-advancedgarages:client:TakeOutVehicle:config`

**Modify both events like below**

```lua
RegisterNetEvent("jg-advancedgarages:client:InsertVehicle:config", function(vehicle, vehicleDbData, type)
  TriggerServerEvent("jg-advancedgarages:server:wheelclamper:vehicleStored", vehicleDbData.plate)
end)

RegisterNetEvent("jg-advancedgarages:client:TakeOutVehicle:config", function(vehicle, vehicleDbData, type)
  TriggerServerEvent("jg-advancedgarages:server:wheelclamper:vehicleSpawned", vehicleDbData.plate)
end)
```

**Paste the code in the file `jg-advancedgarages->config-config-sv.lua`:**

```lua
RegisterNetEvent("jg-advancedgarages:server:wheelclamper:vehicleStored", function(plate)
    exports.pl_wheelclamper:OnVehicleStored(source, plate)
end)

RegisterNetEvent("jg-advancedgarages:server:wheelclamper:vehicleSpawned", function(plate)
    exports.pl_wheelclamper:OnVehicleSpawned(source, plate)
end)
```
{% endstep %}
{% endstepper %}
