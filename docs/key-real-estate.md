# Key Real Estate Map

Grades **slots**, not actions. A slot's grade never changes because something got bound
to it — this map is the fixed price list we shop against.

Assumptions: right hand on mouse, left hand anchored over the `QWER`/`ASDF` region with
the thumb near `Space`, extended reach (one column past the tight home region).

## Grading

### P — Premium
Zero hand travel, and pressable *while the mouse is moving or dragging*.

| Slot | Notes |
|---|---|
| `Mouse4`, `Mouse5` | Thumb side buttons. Unique property: usable mid-drag and mid-aim, with no finger reassignment at all. The most valuable slots in the entire setup. |
| `Space` | Thumb. Independent of every finger, so it never fights another key for a digit. Huge target, impossible to miss. |

### 1 — Prime
Home anchor, strong fingers, no reach.

`F` `D` `E` `R` `W` `S`

### 2 — Very good
Home anchor on weaker fingers, or a one-key reach that keeps the anchor.

`A` `Q` `G` `T` `C` `V` `X` `Caps`

`Caps` is pinky-adjacent and physically excellent; verify DE actually captures it before
committing anything important to it.

### 3 — Decent
A deliberate small stretch; the anchor survives but momentarily loosens.

`Z` `B` `Tab` `1` `2` `3` `4`

### 4 — Reachable
Edge of extended reach, or number row past the comfortable span.

`5` `6` `Y` `H` `N`

### 5 — Modifier combos
`Ctrl+<any tier 1-2 key>`, `Alt+<any tier 1-2 key>`.

Cheap in supply, expensive in time: two-key presses, and the pinky leaves its anchor.
Correct home for C-tier actions. **Avoid `Shift+` combos** — `Shift` is load-bearing for
queueing and additive selection, and a mis-timed `Shift+key` can silently change what a
click does.

### 6 — Far
Everything right of the `T/G/B` column beyond extended reach, F-keys, numpad, `7`-`0`.
Fine for D-tier. Requires abandoning the anchor.

## Structural rules

**Sequence rule.** Two keys pressed in quick succession should not share a finger. A
frequent chain like *select producer → train unit* is slower on `D` then `E` (both index-ish)
than on `D` then `W`. Evaluate every new binding against the chains it will appear in, not
in isolation.

**Simultaneity rule.** Anything held or pressed *while* the cursor is being placed
(attack-move, patrol, stance changes mid-fight) belongs on a thumb slot or a strong finger
that is not also mid-chain. This is what makes `Mouse4`/`Mouse5` and `Space` special.

**Context reuse.** Where scope is contextual, the same physical key can legitimately serve
different actions under different selections. This expands supply considerably — but only
where the contexts genuinely cannot overlap, and never against a global.

**Modifier hygiene.** Prefer `Ctrl` and `Alt` as hotkey modifiers. Leave `Shift` alone.

## Scope: the second price dimension

A slot's grade says how good the key *feels*. Scope says how much of the layout it
*consumes*. These are independent, and ignoring scope is how a layout quietly runs out of
room.

DE hotkeys fall into two kinds:

**Global** (the Game Commands group — select-all-X, go-to-X, camera and control commands).
Fires no matter what is selected. A global binding consumes that key in **every context,
permanently**. There is no villager-context `D` if `D` is a global.

**Contextual** (building command sets, unit commands, build menus). Only exists while the
matching thing is selected. A contextual binding consumes that key **in one context only**,
so the same physical key can serve different actions in contexts that cannot overlap.

### The cost model

> A global binding is roughly as expensive as *n* contextual bindings, where *n* is the
> number of contexts you care about.

Consequences that should drive every future decision:

1. **Keep the global layer small.** Globals are the scarcest resource in the layout, not
   the good keys. Only actions that must fire from anywhere, mid-anything, justify one.
2. **A global action is what earns a premium key.** Being always-available is exactly the
   property that pairs with a slot that is always under a finger.
3. **Contextual actions should be routed around the global layer**, not the other way
   round. Build menus and per-building train keys get whatever the globals left behind.
4. **Globals are the natural candidates for the thumb buttons**, because moving a global
   off the keyboard reclaims that key across every context at once. This is a much stronger
   reason to spend a thumb slot than the mid-drag property alone.

### Verified

Both tested in game (Session 4) and confirmed:

- **"Select all Town Centers" is global.** With a villager selected, `D` rips the selection
  to the Town Centers. It shadows `D` in every context.
- **"Create Villager" is Town-Center-scoped.** `F` is free for reuse in other contexts.

The scope model is no longer a hypothesis. Price accordingly.

## Reserved slots

Deliberately held empty so future high-priority actions have somewhere to land. Nothing
gets one of these by default — a slot leaves this list only by an explicit decision logged
in `docs/decisions.md`.

**Standing reserve rule.** At all times, hold **both thumb buttons and at least one tier-1
key** unbound. Reserves are not a starting allowance to be drawn down; when one is spent,
another tier-1 key is designated in its place. This is what keeps late-discovered S-tier
actions from being stuck with tier-3 slots.

| Slot | Held for |
|---|---|
| `Mouse4` | An S-tier action that must fire mid-drag or mid-aim |
| `Mouse5` | An S-tier action that must fire mid-drag or mid-aim |
| `S` | The next S-tier action, per the standing reserve rule |

`S` replaced `F`/`D` when those were spent on the villager production loop in Session 2.
It is the strongest remaining tier-1 key, and it is a **ring**-finger key, which matters:
the existing macro sweep already occupies index (`F`) and middle (`D`), so a ring-finger
slot is the one that chains cleanly with it. `W` is the same finger and the natural
fallback if `S` proves awkward.

`Space` is not reserved but is not cheap either; it currently carries a useful default.
