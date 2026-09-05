# Live Layout

The ledger of **deliberate** bindings. Anything not listed here is still on the DE default
and is fair game to replace.

## Bound

| Slot | Grade | Scope | Action | Tier | Bound on |
|---|---|---|---|---|---|
| `F` | 1 | Contextual (TC) | Train villager | S | Session 2 |
| `D` | 1 | **Global** | Select all Town Centers | S | Session 2 |

Both scopes confirmed in game (Session 4).

## Global layer

Globals fire regardless of selection and consume their key in **every** context, which
makes this — not the supply of good keys — the layout's real bottleneck. Tracked separately
so the pressure stays visible.

| Slot | Action | Spent |
|---|---|---|
| `D` | Select all Town Centers | Session 2 |

**Anticipated demand.** Listed to keep the future layout in mind, not as commitments or a
queue: cycle idle villager (est. S), select all military (est. A), go to / cycle TC (B),
cycle idle military building (B), go to last event (B), select-all-of-building-type (B/C).
Six or so plausible globals against a much smaller supply of keys worth spending on them.
Expect this layer to be rationed, and expect some of these to end up on modifiers or unbound.

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
D  ->  F  F  F ...        select all TCs, then queue a villager per press
```

`D` is middle finger, `F` is index: different fingers, and middle-to-index is a natural
outward roll. The repeated key sits on the strongest finger. Neither key moves the camera,
so the whole loop runs without disturbing whatever the mouse is doing.

Because `D` is global, the sweep fires from any selection state — mid-build, mid-fight,
anything. That is the point of it, and it is what the key is being paid for.

## Free premium supply

Unreserved and unbound, for quick reference when shopping: `E` `R` `W` (tier 1),
`A` `Q` `G` `T` `C` `V` `X` `Caps` (tier 2).

`Space` is unbound by us but carries a useful DE default; treat it as occupied until we
decide otherwise.
