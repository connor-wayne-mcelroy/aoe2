# Live Layout

The ledger of **deliberate** bindings. Anything not listed here is still on the DE default
and is fair game to replace.

## Bound

| Slot | Grade | Scope | Action | Tier | Bound on |
|---|---|---|---|---|---|
| `F` | 1 | Contextual (TC) | Train villager | S | Session 2 |
| `D` | 1 | **Global** | Select all Town Centers | S | Session 2 |
| `S` | 1 | **Global** | Select next idle villager | S | Session 5 |
| `A` | 2 | **Global** | Select all Stables | A | Session 6 |
| `Alt+A` | 5 | **Global** | Select all Archery Ranges | A/B | Session 6 |
| `F` | 1 | Contextual (villager) | Build Farm | A+ | Session 7 |
| `Q` | 2 | Contextual (villager) | Building page 1 (economy) | A+ | Session 9 |
| `Caps` | 2 | Contextual (villager) | Building page 2 (military) | B | Session 9 |
| `V` | 2 | Contextual (villager) | Build Lumber Camp | B | Session 15 |
| `R` | 1 | **Global** | Select control group 1 | S | Session 11 |
| `E` | 1 | **Global** | Select control group 2 | A | Session 11 |
| `Shift+R` | 5 | **Global** | Add to control group 1 | A | Session 11 |
| `Shift+E` | 5 | **Global** | Add to control group 2 | B | Session 11 |

Both scopes confirmed in game (Session 4).

## Global layer

Globals fire regardless of selection and consume their key in **every** context, which
makes this — not the supply of good keys — the layout's real bottleneck. Tracked separately
so the pressure stays visible.

| Slot | Action | Spent |
|---|---|---|
| `D` | Select all Town Centers | Session 2 |
| `S` | Select next idle villager | Session 5 |
| `A` | Select all Stables | Session 6 |
| `Alt+A` | Select all Archery Ranges | Session 6 |
| `R` / `Shift+R` | Control group 1: select / add | Session 11 |
| `E` / `Shift+E` | Control group 2: select / add | Session 11 |

**Anticipated demand.** Listed to keep the future layout in mind, not as commitments or a
queue: select all military units (est. A), go to / cycle TC (B), cycle idle military
building (B), go to last event (B), select all idle villagers (B), select all Barracks (B).
Against a much smaller supply of keys worth spending on them. Expect this layer to be
rationed, and expect some of these to end up on modifiers or unbound.

Two of the layout's three bindings are already globals. That is the correct shape for an
economy-first layout — the eco loops must fire from any selection state — but it means the
global layer is being consumed fast, and the next candidate needs a harder look than these
two did.

**Build menus: resolved (S7).** Hand-picked, not grid. `D`, `S` and `A` are globals and
globals beat context (verified S4), so a positional grid would have three dead cells in its
best row. The choice was effectively made by the last three sessions rather than decided on
its merits — worth noting honestly — but hand-picked is also the better fit for this project,
since it lets each building earn its key by placement frequency instead of by menu position.

Buildings are bound one at a time, on demand, like everything else. Villager context is
**cheap supply**: contextual bindings consume nothing globally, so a prime key there costs
almost nothing.

**Hazard — stray `Shift`.** `Shift+R` / `Shift+E` add the current selection to a control
group, and `Shift` is held all game for queueing and farm placement. If `Shift` is still down
when you reach for `R`, you silently add whatever is selected — possibly villagers — to the
army group, and nothing looks wrong until they walk into a fight. Accepted knowingly (S13) as
the price of the only modifier that is comfortable with a top-row base. Watch for it.

**Hazard.** Because `D` is global, firing the sweep while a building footprint is on the
cursor cancels the placement. The sweep is safe mid-walk, mid-fight, mid-anything *except*
mid-placement.

`F` is contextual and stays free for reuse elsewhere — see the producer-key policy below.

## Policy reserves

Not bindings, and not slots held empty; commitments about how a key may be *spent*.

| Slot | Policy |
|---|---|
| `F` | **`F` = make the next obvious thing here.** Widened in S7 from "train the primary unit" to cover building as well. At a producer it trains the primary unit; with a villager selected it places a Farm. One finger, one verb, every context. `F` is not to be spent on anything else in any context, ever. **Load-bearing:** four loops now depend on it. |
| `Alt+A` / `Ctrl+A` | Reserved for the remaining military production types under variant pairing. `Alt+A` spent on Archery Ranges (S6); `Ctrl+A` held for Barracks. |
| `Ctrl+R` / `Ctrl+E` | Held for **replace** control group 1 / 2. Deliberately the awkward combo: replacing is rare, and rare actions should pay the awkwardness. It is also the only way to clean a group that got the wrong units into it. |
| `G` | Villager context: held for **House**. The best remaining key there — home row, index, one step right of `F` — and House is placed three to four times as often as anything else still unbound. Not to be spent on a less frequent building. |
| `C` | Villager context: held for **Mining Camp**, keeping the two drop-off camps adjacent on `C`/`V`. |
| Pinky column | In the villager context, the pinky column (`Q`, `Caps`, `Tab`, `Z`) is for building **pages** only. No building gets a pinky key. |

## Reserved

Held empty on purpose. See `docs/key-real-estate.md` for the reserve policy.

| Slot | Grade | Held for |
|---|---|---|
| `Mouse4` | P | S-tier action needing mid-drag / mid-aim firing |
| `Mouse5` | P | S-tier action needing mid-drag / mid-aim firing |
| `S` | 1 | The next S-tier macro-sweep action (see standing reserve rule) |

## The macro sweep

The one chain that matters most so far. Keep it protected when placing anything new.

```
villagers       D      ->  F  F  F ...          select all TCs, queue a villager per press
military        A      ->  F  F  F ...          select all Stables, queue a unit per press
                Alt+A  ->  F  F  F ...          same, Archery Ranges
idle cleanup    S      -> click,  S -> click    grab next idle villager, assign it, repeat
farm spam       S -> Q -> F -> shift-click x N   idle vill, economy page, farm, ring them out
lumber camp     S -> Q -> V -> click             idle vill, economy page, camp, place
combat          R      -> [attack-move] -> click  grab the army, aim, go
reinforce       box new units -> Shift+R       add them; creates the group if absent
```

Farm *upkeep* needs no binding: villagers reseed automatically in DE as long as there is
wood. Only initial placement is a hotkey problem.

### Building placement is page-gated

Confirmed in game (S9): a building hotkey does **not** fire directly. You must be on the
correct building page first, so every placement is `[page] -> [building] -> click`.

Fingers in the farm loop: `S` ring, `Q` pinky, `F` index — three different fingers, no
collision anywhere in the chain.

**The page does not persist** (confirmed S10): after a placement the panel resets to the base
villager page, so `Q` is pressed before *every* building — two presses for one house, four for
two houses unless you Shift-click. That makes `Q` the most-pressed key in the villager context
and confirms it at A+.

**Page keys live on the pinky column; building keys never use the pinky.** That single rule
guarantees the page prefix can never collide with the building key that follows it, no matter
which building is bound later. `Q` and `Caps` are both pinky, and they are never pressed
together, so sharing a finger between them costs nothing.

### Farm spam, in detail

The mechanic doing the work is **Shift-click**, not a hotkey: with the farm footprint on the
cursor, Shift-click places a farm and *keeps the cursor loaded*. So the whole spam is one
`F` press and then as many Shift-clicks as you have wood for. Ring the TC, then the mill.

`S` -> `F` is ring finger to index — the same wide alternation that makes the military loop
fast, and it means grabbing an idle villager and immediately putting it on farms is two keys
with no finger collision.

`F` is the universal terminator. Every producer loop is *select, then* `F`, and `F` always
means the same thing: train the primary unit of whatever is selected. Two loops, one verb.

Fingers: `A` pinky, `S` ring, `D` middle, `F` index. The home row is now one action per
finger, left to right — military, idle villagers, town centers, train — with no pair in any
loop sharing a finger.

`A` -> `F` is the widest alternation available on the left hand (pinky to index), which is
why `A` won over `G`, `T` and `V`: those are all index-finger keys and would have collided
with `F` on every single press of the military loop.

`D` -> `F` is an outward middle-to-index roll with the repeated key on the strongest finger.
Neither key moves the camera, so production runs without disturbing the mouse.

The idle loop alternates hands by design: key with the left, assign with the right, key with
the left. This is the main reason it stayed on the keyboard rather than a thumb button — on
`Mouse4` the whole loop would collapse onto the right hand, thumb-then-click over and over,
while the left hand sat idle.

Because `D` is global, the sweep fires from any selection state — mid-build, mid-fight,
anything. That is the point of it, and it is what the key is being paid for.

## Free premium supply

Unreserved and unbound, for quick reference when shopping: `E` `R` `W` (tier 1),
`A` `Q` `G` `T` `C` `V` `X` `Caps` (tier 2).

`Space` is unbound by us but carries a useful DE default; treat it as occupied until we
decide otherwise.
