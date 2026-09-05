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

**Context reuse.** DE scopes many hotkeys to a selection context (villager selected,
military selected, building selected), so the same physical key can legitimately serve
different actions in different contexts. This expands supply considerably — but only
where the contexts genuinely cannot overlap. Verify in game before relying on it.

**Modifier hygiene.** Prefer `Ctrl` and `Alt` as hotkey modifiers. Leave `Shift` alone.

## Reserved slots

Deliberately held empty so future high-priority actions have somewhere to land. Nothing
gets one of these by default — a slot leaves this list only by an explicit decision logged
in `docs/decisions.md`.

| Slot | Held for |
|---|---|
| `Mouse4` | An S-tier action that must fire mid-drag or mid-aim |
| `Mouse5` | An S-tier action that must fire mid-drag or mid-aim |
| `F` | The single most frequent keyboard-triggered action |
| `D` | The second most frequent, ideally one that chains with `F` |

`Space` is not reserved but is not cheap either; it currently carries a useful default.
