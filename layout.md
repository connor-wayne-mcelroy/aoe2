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

**Anticipated demand.** Listed to keep the future layout in mind, not as commitments or a
queue: select all military units (est. A), go to / cycle TC (B), cycle idle military
building (B), go to last event (B), select all idle villagers (B), select all Barracks (B).
Against a much smaller supply of keys worth spending on them. Expect this layer to be
rationed, and expect some of these to end up on modifiers or unbound.

Two of the layout's three bindings are already globals. That is the correct shape for an
economy-first layout — the eco loops must fire from any selection state — but it means the
global layer is being consumed fast, and the next candidate needs a harder look than these
two did.

**Build-menu pressure.** `D`, `S` and `A` are all globals, so all three are dead in the
villager-selected context. Three of the eight best left-hand keys are now unavailable to any
future build menu, and the run `A` `S` `D` is contiguous. This is the pressure that was named
in Session 3 as the trigger for reconsidering whether a global should move to a thumb button.
It has not been acted on yet, but it is close.

**Hazard.** Because `D` is global, firing the sweep while a building footprint is on the
cursor cancels the placement. The sweep is safe mid-walk, mid-fight, mid-anything *except*
mid-placement.

`F` is contextual and stays free for reuse elsewhere — see the producer-key policy below.

## Policy reserves

Not bindings, and not slots held empty; commitments about how a key may be *spent*.

| Slot | Policy |
|---|---|
| `F` | In any **producer** context (barracks, archery range, stable, dock, siege workshop), `F` is not to be spent on anything but "train the primary unit." Confirmed viable now that Create Villager is TC-scoped. One finger, one meaning, every producer. **Now load-bearing:** two loops depend on it. |
| `Alt+A` / `Ctrl+A` | Reserved for the remaining military production types under variant pairing. `Alt+A` spent on Archery Ranges (S6); `Ctrl+A` held for Barracks. |

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
villagers       D      ->  F  F  F ...      select all TCs, queue a villager per press
military        A      ->  F  F  F ...      select all Stables, queue a unit per press
                Alt+A  ->  F  F  F ...      same, Archery Ranges
idle cleanup    S      -> click,  S -> click   grab next idle villager, assign it, repeat
```

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
