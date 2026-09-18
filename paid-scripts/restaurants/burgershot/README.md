# 🍔 BurgerShot

{% embed url="https://youtu.be/ePB-4ZlnF1k" %}

[**Purchase Escrow**](https://pulsescripts.com/product/burgershot) · [**Purchase OpenSource**](https://pulsescripts.com/category/opensource)

{% hint style="info" %}
**v3.0.0 is a full rebuild.** New NUI, a self-migrating database, and a phone
delivery app. If you're coming from v2, read [What's New in v3](whats-new-v3.md)
before you touch your live server.
{% endhint %}

BurgerShot turns the classic fast-food job into an actual restaurant
simulation. Cooks work real stations — grill, fryer, drink machine, assembly
counter — each with its own timing, burn risk, and skill check. Cashiers run
a live order queue that customers can see updating on a TV board in the
kitchen. Owners get a full management suite: society funds, staff, shift
history, and order history, all from one menu. And when you're ready to take
orders off-site, the companion `pl_restaurantapp` puts BurgerShot straight
into your players' phones as a real delivery job.

It's built to drop into an existing server with minimal fuss — pick a
supported map, run it, and the script figures out your framework, inventory,
and target system through `pl_lib`.

### Map Supported by This Script

| Map Pack | Price | Link |
|---|---|---|
| **Gabz** | Paid | [fivem.gabzv.com](https://fivem.gabzv.com/) |
| **Molo Modding** | Paid | [molo-modding.com](https://www.molo-modding.com/package/5375088) |
| **G\&N Studio** | Paid | [fivem.gn.studio](https://fivem.gn.studio/) |
| **Smallo** | Free | [gta5-mods.com](https://www.gta5-mods.com/maps/gtaiv-burgershot-interior-sp-and-fivem) |
| **Uniqx** | Free | [gta5-mods.com](https://www.gta5-mods.com/maps/mlo-burgershot-2023-add-on-sp-fivem) |
| **King Maps** | Paid | [kingmaps.net](https://kingmaps.net/products/6167902) |
| **TStudio** | Paid | [turbosaif.tebex.io](https://turbosaif.tebex.io/package/5956096) |
| **Giant** | Free | [forum.cfx.re](https://forum.cfx.re/t/mlo-free-burger-shot/5401933) |

Own more than one? Set `Config.location = 'auto'` and the script will detect
whichever map is actually running on your server — see
[Installation](installation.md).

### Prop Supported

**pl\_restaurant\_props** ships alongside the script and provides every
custom model it needs — patties, fries, the fry basket, the burger bun, the
kiosk. v3 no longer relies on the external DJ Collections prop pack the way
v2 did. It's a separate resource though, so it has to be installed
deliberately — see [Installation](installation.md#1-pl_restaurant_props-required).

***

## What's Inside

### Front of house

Customers order at the kiosk through a proper NUI menu, not a text prompt,
and pay by bank or at the counter. Every order moves through a live
Pending → Cooking → Ready → Completed queue that your whole crew sees at
once — and so do customers, on a TV order board mounted in the kitchen.
Staff can also raise a custom bill on the spot for anything that isn't on the
menu, take a tip, and hand out a printed, itemized receipt when the order's
done. Want to go further? The companion `pl_restaurantapp` sells BurgerShot
food through lb-phone or gksphone, delivery job included.

### The kitchen

Every station behaves like the real thing. The grill and fryer run
independent cook and burn timers per slot, synced live across every employee
working them. The assembly counter enforces build order — patty before bun,
bun before cheese — and nudges staff toward whatever ingredient they're
missing. Drinks get filled at the machine as a proper multi-step craft, ice
comes from actual water bottles, and cooking itself runs through a real
skill-check minigame rather than a progress bar. Let the kitchen get messy
long enough and it needs cleaning before anyone can cook again; add an
optional hand-wash requirement on top if you want it stricter still. Eating
and drinking the food is handled entirely by the script, animations and
hunger/thirst included — nothing extra to wire up on the inventory side.

### Running the business

Managers get one menu for the whole operation: open or close the shop,
move money in and out of the society account, hire, promote, demote, or fire
staff, and review — or wipe — order and shift history. Employees clock in
and out, and their worked hours and items cooked are tracked automatically.
The fridge doubles as bulk stock ordering with a real delivery ETA, on top of
manual put/take access for staff. Round it out with a job uniform, seated
tables and counter trays for dine-in customers, and a trash can for
whatever gets burnt.

### Under the hood

The database installs and migrates itself — there's no manual SQL to run on
a fresh install or an upgrade. Menu items live in one declarative recipe
file, so adding a new burger is a copy-paste, not a code change. Framework,
inventory, and target support (ESX, QBCore, Qbox / ox\_inventory,
qb-inventory, ESX items / ox\_target, qb-target) all come through `pl_lib`,
and location support spans eight map packs with automatic detection.

***

See the [Feature Guide](feature-guide.md) for how each system actually works,
[Installation](installation.md) to get set up, and
[Exports & Events](exports-and-events.md) if you're building an integration.
