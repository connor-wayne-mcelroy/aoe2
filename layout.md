# Live Layout

The ledger of **deliberate** bindings. Anything not listed here is still on the DE default
and is fair game to replace.

## Bound

| Slot | Grade | Scope | Action | Tier | Bound on |
|---|---|---|---|---|---|
| `F` | 1 | Contextual (TC) | Train villager | S | Session 2 |
| `D` | 1 | **Global** | Select all Town Centers | S | Session 2 |
| `S` | 1 | **Global** | Select next idle villager | S | Session 5 |

Both scopes confirmed in game (Session 4).

## Global layer

Globals fire regardless of selection and consume their key in **every** context, which
makes this — not the supply of good keys — the layout's real bottleneck. Tracked separately
so the pressure stays visible.

| Slot | Action | Spent |
|---|---|---|
| `D` | Select all Town Centers | Session 2 |
| `S` | Select next idle villager | Session 5 |

**Anticipated demand.** Listed to keep the future layout in mind, not as commitments or a
queue: select all military (est. A), go to / cycle TC (B), cycle idle military building (B),
go to last event (B), select all idle villagers (B), select-all-of-building-type (B/C).
Against a much smaller supply of keys worth spending on them. Expect this layer to be
rationed, and expect some of these to end up on modifiers or unbound.

Two of the layout's three bindings are already globals. That is the correct shape for an
economy-first layout — the eco loops must fire from any selection state — but it means the
global layer is being consumed fast, and the next candidate needs a harder look than these
two did.

**Hazard.** Because `D` is global, firing the sweep while a building footprint is on the
cursor cancels the placement. The sweep is safe mid-walk, mid-fight, mid-anything *except*
mid-placement.

`F` is contextual and stays free for reuse elsewhere — see the producer-key policy below.

## Policy reserves

Not bindings, and not slots held empty; commitments about how a key may be *spent*.

| Slot | Policy |
|---|---|
| `F` | In any **producer** context (barracks, archery range, stable, dock, siege workshop), `F` is not to be spent on anything but "train the primary unit." Confirmed viable now that Create Villager is TC-scoped. One finger, one meaning, every producer. |

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
production      D  ->  F  F  F ...          select all TCs, queue a villager per press
idle cleanup    S  -> click,  S  -> click   grab next idle villager, assign it, repeat
```

Fingers: `D` middle, `F` index, `S` ring. All three distinct, so no pair in the sweep
collides, and `F` -> `S` (index to ring) crosses the hand cleanly on the transition between
loops.

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
