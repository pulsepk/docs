# 🧰 Installation

{% hint style="info" %}
Pick the resource folder that matches your server's phone: `pl_restaurantapp-lb`
for [lb-phone](https://lbscripts.com/package/phone), `pl_restaurantapp-gks`
for [GKSPhone](https://www.gkshop.org/). Both are the same app — same config,
same logic, same callbacks — only the phone-integration calls underneath
differ. Everything below applies to either one; steps that differ are marked.
{% endhint %}

***

## Dependency matrix

| Resource | Required? | Why |
|---|---|---|
| [`ox_lib`](https://github.com/overextended/ox_lib) | **Required** | `lib.callback` — every NUI action round-trips through it |
| [`oxmysql`](https://github.com/overextended/oxmysql) | **Required** | Writes completed delivery orders into the restaurant's own order-history table |
| [`pl_lib`](../pl_lib/pl_lib/README.md) | **Required** | Framework bridge (job lookups, notifications) |
| [`lb-phone`](https://lbscripts.com/package/phone) | Required for the **lb** build | The phone app is registered inside it |
| [GKSPhone](https://www.gkshop.org/) | Required for the **gks** build | Same role, GKSPhone's own custom-app system |
| Every resource listed in `Config.Restaurants` | **Required** | Must already be installed and running — RestaurantApp doesn't sell food on its own, it's a storefront in front of these |

***

## Step 1 — Download & place

Drop **one** of the two folders into `resources` — not both:

- Using lb-phone → `pl_restaurantapp-lb`
- Using GKSPhone → `pl_restaurantapp-gks`

***

## Step 2 — server.cfg

{% tabs %}
{% tab title="lb-phone" %}
```cfg
ensure ox_lib
ensure oxmysql
ensure pl_lib
ensure lb-phone

# every restaurant this app will sell for must already be running, e.g.
ensure pl_burgershot
ensure pl_uwucafe

ensure pl_restaurantapp-lb
```
{% endtab %}

{% tab title="GKSPhone" %}
```cfg
ensure ox_lib
ensure oxmysql
ensure pl_lib
# ensure whatever your GKSPhone resource is actually called — check
# pl_restaurantapp-gks/fxmanifest.lua's dependencies {} for the exact name

# every restaurant this app will sell for must already be running, e.g.
ensure pl_burgershot
ensure pl_uwucafe

ensure pl_restaurantapp-gks
```
{% endtab %}
{% endtabs %}

The phone resource (lb-phone/GKSPhone) and every restaurant in
`Config.Restaurants` must start **before** RestaurantApp does.

***

## Step 3 — Configure

`config.lua` is shared between both builds — the same file, same options,
regardless of which phone you're running. This is the real, shipped config:

```lua
Config = {}

-- "lb-phone" → native phone push notification
-- "pl_uwucafe" → in-game HUD notification via pl_lib instead
Config.NewDeliveryNotify = "lb-phone"

Config.EnableSocietyMoney = true  -- If true, delivery payments go to the restaurant's society account

Config.Restaurants = {
    {
        id            = "uwucafe",
        name          = "UwU Cafe",
        description   = "Bubble tea, ramen & Asian-inspired treats",
        icon          = "🐱",
        color         = "#ff85a2",
        resource      = "pl_uwucafe",
        adapter       = "kiosk",
        jobName       = "uwu",
        dbTable       = "pl_uwucafe",
    },
    {
        id            = "burgershot",
        name          = "BurgerShot",
        description   = "Classic American burgers, fries & drinks",
        icon          = "🍔",
        color         = "#E8451F",
        resource      = "pl_burgershot",
        adapter       = "kiosk",
        jobName       = "burgershot",
        dbTable       = "pl_burgershot",
    },
}
```

### Registering a restaurant

Add an entry to `Config.Restaurants` for each script you want customers to
order from:

| Field | Meaning |
|---|---|
| `id` | Unique key for this restaurant within the app |
| `name` / `description` / `icon` / `color` | Shown in the restaurant list UI |
| `resource` | The exact resource name of the restaurant script |
| `adapter` | Which adapter to use — `"kiosk"` today, see [Integration Guide](integration-guide.md) |
| `jobName` | The job that can see/accept this restaurant's deliveries |
| `dbTable` | **Must exactly match** that restaurant's own `Config.DBTable` — completed deliveries are written into `<dbTable>_orders`, a table the restaurant script itself creates |

{% hint style="warning" %}
`dbTable` isn't RestaurantApp's own table name — it's the target restaurant's.
Get it wrong (or start RestaurantApp before that restaurant has created its
own order table) and delivery orders will place fine but silently fail to log
to history.
{% endhint %}

***

## Common pitfalls

<details>
<summary>A restaurant doesn't show up in the app, or its menu is empty</summary>

Its resource isn't started, isn't started yet when a player opens the app, or
its `adapter` type doesn't match how that script actually exposes its menu.
For the `"kiosk"` adapter, the target resource needs
`<resource>:getKioskData` and `<resource>:placeKioskOrder` callbacks
registered — see [Integration Guide](integration-guide.md).
</details>

<details>
<summary>Deliveries work but never show up in order history</summary>

`dbTable` for that restaurant in `Config.Restaurants` doesn't exactly match
its `Config.DBTable`, or that restaurant hasn't created its `_orders` table
yet (start it at least once first).
</details>

<details>
<summary>The app doesn't appear on the phone at all</summary>

**lb-phone:** confirm `lb-phone` is fully started before RestaurantApp — the
app registers itself via `AddCustomApp` on start and again whenever lb-phone
restarts, but if lb-phone was never running when RestaurantApp tried, nothing
gets a chance to register.
**GKSPhone:** check `pl_restaurantapp-gks`'s own startup logs/fxmanifest for
its actual custom-app registration call and confirm the GKSPhone resource
name in your `server.cfg` matches what that build expects.
</details>

<details>
<summary>Notifications aren't showing up</summary>

Check `Config.NewDeliveryNotify` — `"lb-phone"` routes through the phone's own
push notifications, `"pl_uwucafe"` routes through `pl_lib`'s in-game HUD
notify instead. Make sure whichever one you picked is actually working on
your server.
</details>
