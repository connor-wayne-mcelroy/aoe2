# Live Layout

The ledger of **deliberate** bindings. Anything not listed here is still on the DE default
and is fair game to replace.

## Bound

| Slot | Grade | Scope | Action | Tier | Bound on |
|---|---|---|---|---|---|
| `F` | 1 | Contextual (TC) | Train villager | S | Session 2 |
| `D` | 1 | **Global** | Select all Town Centers | S | Session 2 |

`D` is the layout's first and so far only **global** binding. It is therefore unavailable
in every other context — a villager-selected `D` will select the Town Centers, not place a
building. That is intended for the macro sweep but it is the expensive kind of binding; see
the scope cost model in `docs/key-real-estate.md`.

`F` is contextual and stays free for reuse elsewhere, including the possible
"train the primary unit at any producer" pattern.

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
