# 🛠️ How-To Guides

Short, direct answers to things customers actually ask for. Unlike
[Common Issues](common-issues.md) (things that are broken) or
[Customization](customization.md) (how the systems work under the hood), this
page is a growing list of "I want X" → exactly what to change. Each entry is
self-contained — jump straight to the one you need.

<details>
<summary>How do I add a new burger/fries/drink to the menu?</summary>

Edit `shared/recipe.lua` and add an entry to the right category (`Burgers`,
`Fries`, or `Drinks`) with a `label`, `price`, `reward`, and `required`
ingredients list. Then register the new item name in your inventory
(`Installfolder/items-*`) and, if it needs new raw ingredients, add those to
`Config.Shop.Storage` so staff can buy stock for it. See
[Customization → Adding or changing a menu item](customization.md#adding-or-changing-a-menu-item).

</details>

<details>
<summary>How do I move the shop to a different map pack?</summary>

Set `Config.location` in `shared/config.lua` to one of `gabz`, `molo`, `gn`,
`smalo`, `uniqx`, `king`, `tstudio`, `giant` — or `'auto'` to have it detect
whichever map resource is currently running (fill in `Config.LocationResources`
first). See [Installation → Step 5](installation.md#step-5-configure).

</details>

<details>
<summary>How do I disable the cooking skill-check mini-game?</summary>

Set `Config.SkillCheck.Enable = false`. Cooking steps will still run their
timer/progress bar, they just won't require the mini-game.

</details>

<details>
<summary>How do I turn off tipping, or change how tips are split?</summary>

`Config.Tip.Enable = false` turns tipping off entirely. To change the split,
set `Config.Tip.Distribution` to `'employee'`, `'society'`, or `'split'`
(with `Config.Tip.SocietyPercent` controlling the split ratio).

</details>

<details>
<summary>How do I require employees to clock in before they can work?</summary>

Set `Config.RequireDuty = true`. Combine with `Config.RequireHandWash = true`
if you also want a hand-washing step before cooking.

</details>

<details>
<summary>How do I change how often the kitchen needs cleaning?</summary>

`Config.Kitchen.DirtyAfterCooks` controls how many items can be cooked before
the kitchen gets dirty; `Config.Kitchen.CleanDuration` controls how long
cleaning each mess prop takes. Set `Config.Kitchen.Enable = false` to turn the
whole system off.

</details>

<details>
<summary>How do I move or hide the order display TV board?</summary>

Its position comes from `Location.DisplayBoard` in `shared/location.lua` (per
map pack) — edit the coordinates there. To remove it entirely, comment out
`'client/modules/display.lua'` in `fxmanifest.lua`'s `client_scripts`.

</details>

<details>
<summary>How do I change how much ice a water bottle produces, or how long it takes?</summary>

`Config.IceMachine.IceGiven` sets the yield per bottle;
`Config.IceMachine.WaitTime` sets the production time in seconds.

</details>

<details>
<summary>How do I change the maximum a custom bill/invoice can charge?</summary>

`Config.MaxBillAmount` caps the total. `Config.Commission` sets the
percentage the business takes from custom bills.

</details>

<details>
<summary>How do I change the interaction style (target vs press-E vs 3D text)?</summary>

`Config.Interaction` sets the default (`'target'`, `'textui'`, or `'text3d'`)
for the whole script — individual zones in `shared/location.lua` can override
it per spot if you want a mix. `'text3d'` requires the optional `ctn-text3d` resource.

</details>
