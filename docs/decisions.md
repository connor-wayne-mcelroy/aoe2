# Decisions Log

Newest first. Records changes *and* declines. A session with no binding still gets an entry.

---

## Session 2 — Villager production loop

**Reported need:** Constant villager production identified as the top priority, with a
"select all Town Centers" path that will be used heavily.

**Tier decision:** S, for both halves of the loop.

This is the rare case where prior knowledge substitutes for a reported in-game cost.
Uninterrupted villager production is the single highest-value macro habit in AoE2, and
every second of idle TC time compounds for the rest of the match. There is no plausible
future in which this is less than S-tier, so waiting for a game to prove it would be
ceremony rather than rigor.

**Outcome:** Unlock reserves — `F` and `D` both spent.

**Bindings changed:**

| Slot | Action |
|---|---|
| `F` | Train villager (TC context) |
| `D` | Select all Town Centers |

**Reasoning:**

- *Why the reserves at all.* `F` and `D` were held for "the most frequent keyboard action"
  and "the second most frequent, ideally chaining with it." That description was written
  before we knew what would claim them, and this loop matches it exactly. Holding them for
  something hypothetically better would be hoarding, not discipline.
- *Why this split.* Train fires more often than select — with multiple TCs you select once
  and queue several times — so the repeated key takes the stronger finger. `F` is index,
  `D` is middle.
- *Sequence rule.* Different fingers, so the pair does not collide. Middle-to-index is an
  outward roll, the more comfortable direction, and the repeats then sit still on one finger.
- *Why not the thumb buttons.* Their unique property is firing mid-drag or mid-aim. Neither
  of these actions needs the cursor to be anywhere, so spending a thumb button here would
  buy nothing and waste the one advantage those slots have. They stay reserved.
- *Camera.* Neither key disturbs the view on a single press, so the loop can run while the
  mouse is busy elsewhere. This is most of why the loop is cheap to execute.

**Declined:**

- *Go to / cycle Town Centers* was **not** given a premium key. It is camera navigation,
  tiered B, and the temptation to cluster it near `D` purely because both involve Town
  Centers is exactly the associative reasoning this project is meant to avoid. Backlogged.
- *Cycle idle villager* was tiered S but **not bound**. It is the obvious next reserve
  spend, and binding it now — before it has been felt in a game — would be predicting the
  layout rather than growing it. Backlogged, and the `S` reserve is shaped for it.

**Reserve replenished:** `S` designated as the held tier-1 key, and a standing rule added
that both thumb buttons plus at least one tier-1 key stay unbound permanently. `S` is a
ring-finger key, chosen deliberately: index and middle are now committed to the macro
sweep, so the next action that chains with it wants a different finger.

**Open questions carried forward:** build menus, control-group relocation, DE selection-context
reuse, and a new one — whether `F` can mean "train the primary unit" at every producer, not
just the TC.

---

## Session 1 — Foundation

**Bindings changed:** none.

Deliberately zero. No game data yet, and the first binding made without a rubric is the one
most likely to squat on a slot something better will want.

**Decisions:**

- **Posture fixed.** Left hand extended reach, two mouse side buttons available. This
  defines the home region and therefore the whole real-estate grading.
- **Real-estate map written before any action was tiered.** Grading slots first, in
  isolation from content, is what prevents rationalizing a good key for a mediocre action.
- **Four slots reserved** (`Mouse4`, `Mouse5`, `F`, `D`). The two thumb buttons are reserved
  specifically because they can fire mid-drag, a property no keyboard key has; spending them
  on something that doesn't need that property would waste their only unique advantage.
- **`Shift` ruled out as a hotkey modifier.** It is load-bearing for queueing and additive
  selection; combos on it risk silently changing what a click does.
- **Build menus deferred.** Grid vs. hand-picked is a large structural choice that should be
  driven by observed build-order habits, not decided cold.
- **Control groups flagged, not touched.** The number row is tier 3-4 real estate holding
  what is likely S-tier importance. Real tension, but relocating them is a big coordinated
  move, not a one-off binding.

**Open questions carried forward:** build menus, control-group relocation, how far DE
selection contexts allow key reuse.

---

## Entry template

```
## Session N — <date / what prompted it>

**Reported need:** <what happened in the game, and what it cost>

**Tier decision:** <S/A/B/C/D> — <mature-play reasoning>

**Outcome:** bind at tier / defer / displace / unlock reserve / no binding ever

**Bindings changed:** <slot → action, or none>

**Reasoning:** <why this slot, what chains it sits in, what it blocks>

**Declined:** <what we chose not to do, and why>
```
