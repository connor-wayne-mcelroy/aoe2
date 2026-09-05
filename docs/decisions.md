# Decisions Log

Newest first. Records changes *and* declines. A session with no binding still gets an entry.

---

## Session 5 — Idle villager

**Reported need:** Cycling idle villagers, identified in Session 4 as the obvious next step.

**Tier decision:** S. Production and idle-cleanup are two halves of one thing — queuing
villagers is worthless if they then stand around, and idle time compounds exactly the way
missed production does. This was tiered S in Session 2 and nothing since argues it down.

**Outcome:** Spend the `S` reserve.

**Bindings changed:** `S` → Select next idle villager (**global**).

**Reasoning:**

- *Why `S` specifically.* It was designated in Session 2 as a **ring**-finger reserve,
  precisely because the sweep already held index (`F`) and middle (`D`). That reasoning still
  holds: all three sweep keys are now distinct fingers, and `F` -> `S` crosses cleanly on the
  transition from production to idle cleanup.
- *Why not a thumb button.* This is the interesting one, because the scope model's rule 4
  says globals are natural thumb candidates — moving one off the keyboard reclaims that key
  everywhere. It loses here to hand alternation. The idle loop is *key, click, key, click*:
  on the keyboard that alternates hands, one job each. On `Mouse4` the entire loop collapses
  onto the right hand — thumb, click, thumb, click — while the left hand does nothing. Rule 4
  is about supply; this is about throughput, and throughput wins on the layout's second-most
  frequent loop.
- *Accepted cost.* Repeats land on the ring finger, which is weaker than the index finger
  carrying the `F` repeats. Judged acceptable because cycling several idles at once should be
  rare in good play — if it turns out not to be, that is a real signal to revisit.

**New rule — variant pairing.** A bulk, inverse, or narrower variant of a bound action goes
on `Ctrl+<same key>`. One physical location per concept, modifier carries the variation. This
is spatial consistency, not a mnemonic, and it keeps variants off premium slots. First
application: *select all idle villagers* is earmarked for `Ctrl+S`, tiered B, not bound.

**Reserve replenished — and changed in kind.** Instead of designating a single tier-1 key,
`W` `E` `R` is now held as a **contiguous block**. It is an unbroken run sitting directly
above the sweep's `S` `D` `F`, and adjacency is the one form of real estate that cannot be
reassembled after being nibbled away one binding at a time. Control groups — the S-tier
tension flagged in Session 1 — are the leading candidate; `Q` and `T` extend it to five keys
if needed. Generous on purpose. Tier 2 remains the working supply and is ample.

**Watch item:** two of three bindings are now globals. Correct for an economy-first layout,
since the eco loops must fire from any selection state, but the global layer is being spent
quickly and the next candidate deserves more scrutiny than these two needed.

**Open questions carried forward:** build menus, control-group relocation (now with a block
reserved for it), whether `D` should move to a thumb button.

---

## Session 4 — Scope model verified

**Tested in game:**

1. Villager selected, press `D` → selection ripped to the Town Centers. **Select-all-TC is
   global, confirmed.**
2. **Create Villager is Town-Center-scoped, confirmed.**

**Bindings changed:** none. Both results confirm existing choices rather than disturb them.

**What this settles:**

- The scope cost model is promoted from prior knowledge to verified fact. Global vs
  contextual is now the primary thing to establish about any candidate action, before slot
  grade is even considered.
- **The producer-key pattern is alive**, and this is the more valuable of the two results.
  Because unit creation is per-building, `F` can mean "train the primary unit" at the TC,
  barracks, archery range, stable, dock and siege workshop alike — one finger, one meaning,
  every producer. That is worth protecting before anything else has a chance to claim it.

**New commitment:** `F` is now a **policy reserve** in producer contexts — not a held-empty
slot, but a rule that `F` may not be spent on anything other than "train the primary unit"
wherever a producer is selected. This costs nothing today and prevents a genuinely good
structural pattern from being eroded one context at a time.

**Also added:** a global-layer register in `layout.md`, tracking spent globals and listing
anticipated demand (idle villager, select-all-military, go-to-TC, idle military building,
go-to-last-event, select-all-of-type). Roughly six plausible globals competing for a much
smaller number of keys worth spending on them. Making that pressure visible now is what
should stop a mid-tier global from casually taking a prime key later.

**Hazard recorded:** the sweep cancels an in-progress building placement, since `D` is
global and will drop the villager footprint. Safe mid-walk and mid-fight, not mid-placement.

**Still not doing:** moving select-all-TC to `Mouse4`. Verification strengthened the
*reasoning* behind that idea — globals really are the bottleneck — but not the *trigger*,
which is real contention for `D`. Nothing is contending yet. Revisit at the build-menu
decision.

**Open questions carried forward:** build menus, control-group relocation, whether `D`
should move to a thumb button.

---

## Session 3 — Scope collision on `D`

**Reported need:** With a villager selected, does `D` place a building or rip the selection
to the Town Centers?

**Finding:** It rips you to the Town Centers, and the framework was under-specified for
missing it.

"Select all Town Centers" lives in DE's Game Commands group and is **global** — it fires
regardless of selection. "Create Villager" is part of the Town Center's own command set and
is **contextual**. So the two bindings made in Session 2 are not the same kind of object at
all, and Session 2's claim that they cost one slot each was wrong for `D`.

**Framework change:** Added **scope** as a second pricing dimension alongside slot grade.
Grade says how good a key feels; scope says how much of the layout it consumes. A global
binding costs that key in *every* context; a contextual one costs it in *one*. The scarcest
resource in this layout is not good keys — it is the global layer.

Four consequences now written into the price list: keep the global layer small; being global
is what earns a premium key; route contextual actions around the globals rather than the
reverse; and thumb buttons are especially valuable for globals, since moving a global off the
keyboard reclaims that key across every context at once.

**Outcome:** No bindings changed. `D` stays.

**Reasoning:**

- The collision is not a bug in the choice. The macro sweep is *supposed* to fire mid-build,
  mid-fight, from any selection state — that is the whole reason it is worth a prime key. A
  contextual select-all-TC would be useless.
- What changed is the *price*, not the value. `D` is expensive, and it should be understood
  as the layout's one global so far rather than as a cheap tier-1 spend.

**Declined for now:** Moving select-all-TC to `Mouse4`. It is a genuinely attractive idea —
it would reclaim `D` in every context while keeping the action just as available, and
thumb-then-`F` splits across opposite hands, which has no finger contention at all. Held
because the change is cheap and non-destructive at any later date, nothing is currently
competing for `D`, and spending a thumb reserve before we know what actually needs mid-drag
firing would break the standing reserve rule to buy something we can still buy later. This
becomes live the moment the build-menu decision puts real pressure on `D`.

**Caveat:** The scope model is prior knowledge, not yet tested on this install. A concrete
verification procedure is in the price list and at the top of the backlog's verify list —
including a check that "Create Villager" is genuinely TC-scoped. If it turns out to be
global, `F` is badly mispriced and the "train the primary unit everywhere" idea is dead.

**Open questions carried forward:** build menus, control-group relocation, whether `D` should
move to a thumb button, whether `F` generalizes across producers.

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
