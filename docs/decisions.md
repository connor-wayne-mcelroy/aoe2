# Decisions Log

Newest first. Records changes *and* declines. A session with no binding still gets an entry.

---

## Session 8 — Correction: farm reseeding needs no binding

**Correction:** Villagers reseed farms automatically in DE while wood is available. The
Session 7 Mill binding solved a problem the game does not have.

**Bindings changed:** removed `F` (Mill context) → Add farm to reseed queue.

`F` in the villager context is untouched. Farm *placement* was always the real request; the
upkeep half was invented.

**What this cost:** nothing in the layout — the Mill binding was contextual, so removing it
frees a context nothing else wanted, and no other binding referenced it. The `F` policy is
unchanged in substance: "make the next obvious thing here" still covers train-at-producer and
build-farm-with-villager, four loops in total.

**Where the error came from, since it is worth not repeating:** Session 7 correctly split the
request into placement and upkeep, then assumed upkeep needed a *hotkey* answer rather than
checking whether it needed an answer at all. The intake procedure already guards against this
— Step 2 question 3 is "can this be done acceptably without a key?" — and it was applied to
placement but not to upkeep. Splitting an action into halves means tiering **both** halves,
not just carrying the parent tier across.

**Process note added:** when a request splits into sub-actions, each sub-action goes through
intake independently. A derived half inherits nothing from the parent — not its tier, and not
the assumption that it is a hotkey problem.

---

## Session 7 — Farms, and the build-menu decision

**Reported need:** An efficient way to spam farms.

**Tier decision:** A+ for placement, A for upkeep. Farms are the most-placed building in the
game by a wide margin and the backbone of food from Feudal onward. Short of S only because
placement is bursty — you ring out several at once and then leave it alone — rather than
continuous the way villager production is.

**The request split into two actions,** which is the main insight of this session:

1. *Placing* farms — villager, build cursor, place.
2. *Keeping them seeded* — expiring farms that need replanting.

These are different problems with different homes, and solving only the first would have left
the more annoying half untouched.

**Outcome:** Bind both. Also resolves the build-menu question.

**Bindings changed:**

| Slot | Context | Action |
|---|---|---|
| `F` | Villager selected | Build Farm |
| `F` | Mill selected | Add farm to reseed queue |

**Build menus — resolved: hand-picked, not grid.**

Deferred since Session 1, and it turns out the last three sessions decided it. A positional
grid needs `QWER` / `ASDF` / `ZXCV`, but `D`, `S` and `A` are globals, and Session 4 verified
that globals beat context. A grid would have three dead cells in its best row.

Worth being honest that this was foreclosed by accumulated constraint rather than chosen on
its merits. It is still the right answer for this project — hand-picked lets each building
earn its key by how often it is actually placed, which is the whole premise here — but if
grid had been the goal, those three globals should have been questioned earlier.

**Reasoning for `F`:**

- *Villager context is free supply.* Contextual bindings consume nothing globally, so putting
  the best key on the most frequent villager action costs almost nothing. This is now written
  into the price list as consequence 5: within a context, give the best remaining key to the
  most frequent action without hesitation.
- *The chain.* `S -> F -> shift-click x N`: grab an idle villager, load the farm cursor, ring
  out as many as there is wood for. Ring finger to index, the same wide alternation that makes
  the military loop fast.
- *The actual spam mechanism is Shift-click, not a hotkey.* Shift-click places a farm and keeps
  the cursor loaded. One `F` press covers an entire ring of farms. No amount of hotkey design
  improves on that, and it would have been a mistake to bind around it.

**The `F` policy widened.** From "train the primary unit at a producer" to **"make the next
obvious thing here"**: trains a unit at a producer, places a Farm with a villager, queues a
reseed at a Mill. One finger, one verb, four loops. This is the strongest structural pattern
in the layout and `F` is now formally off-limits for anything else in any context.

*Farm queueing was deliberately placed at the Mill rather than the Town Center*, even though
`D` already selects all TCs. The TC context has `F` taken by Train Villager, so queueing there
would have needed a second key and broken the one-verb rule. Using the Mill keeps `F`
unambiguous everywhere.

**Weakest assumption in the layout so far:** that the Mill farm-reseed queue exists and is
bindable in your build. Flagged at the top of the verify list. If it is not there, the upkeep
half falls back to villager-context `F` and manual replanting — the spam half is unaffected.

**Open questions carried forward:** control-group relocation, whether `D` should move to a
thumb button. House is the obvious next building candidate (A-tier, placed constantly).

---

## Session 6 — Military production selection

**Reported need:** A way to select all barracks / archery ranges / stables.

**Tier decision:** A for the main line, B for the rest.

Selecting military production to queue units happens many times per game and is
time-sensitive — an idle production building is army that does not exist. It falls short of
S because military production is bursty (queue several, walk away) and does not exist at all
in the early game, unlike villager production which runs from minute zero.

The important refinement: **this is not one action, it is three, and they are not equally
important.** Which building matters is decided by the game's main line, so binding all three
at equal cost would leave two good keys idle in most games. Main line is Stables.

**Outcome:** Bind at tier, with the variants under variant pairing.

**Bindings changed:**

| Slot | Action | Scope |
|---|---|---|
| `A` | Select all Stables | Global |
| `Alt+A` | Select all Archery Ranges | Global |

**Reasoning:**

- *The producer policy did most of the work.* Because `F` already means "train the primary
  unit at the selected producer," this action is only the front half of a chain that exists:
  `A -> F F F` is structurally identical to `D -> F F F`. One verb, two loops. That is the
  Session 4 policy reserve paying off exactly as intended.
- *The sequence rule eliminated three otherwise-good keys.* `G`, `T` and `V` are all decent
  tier-2 slots, and all three are **index**-finger keys. Since `F` is index and follows this
  key on every single press of the loop, each would have collided on every use. Ruled out on
  ergonomics alone, with no reference to what they might have "meant."
- *Why `A`.* Home row, pinky, no reach, and pinky-to-index is the widest and fastest
  alternation the left hand has. It also completes the home row as one action per finger:
  `A` `S` `D` `F` = military, idle villagers, town centers, train.
- *Why `Alt` and not `Ctrl` for the variant.* See the new rule below.

**New rule — modifier choice follows the base key's finger.** `Ctrl` is a left-**pinky** key,
so `Ctrl` plus a pinky base (`A` `Q` `Z` `Tab` `Caps`) asks one finger to do two jobs and
forces a cramped pinky/ring contortion. `Alt` is a left-**thumb** key and conflicts with
nothing on the left hand. Rule: pinky base keys take `Alt`; everything else defaults to
`Ctrl`. A combo is only as good as the hand shape it produces, and "it is just a modifier"
is not a reason to skip checking that.

**Declined:** Barracks, tiered B and left unbound. High urgency (emergency spears) but low
frequency, and this is the third binding in a session budgeted for one or two. Earmarked for
`Ctrl+A` — deliberately the cramped combo, since it carries the rarest of the three. Promote
to a bare tier-3 key if emergency spears become a recurring pain.

**Also rejected:** an aggregate "select all military production buildings" spanning types,
had one existed. It is actively incompatible with the producer policy — a mixed selection of
stables and ranges makes `F` ambiguous. Per-type selection is not a limitation here, it is
what makes the chain work.

**Watch item — the build-menu squeeze is now real.** `D`, `S` and `A` are all globals, so all
three are dead in the villager context, and they form a contiguous run across the home row.
Three of the eight best left-hand keys are now unavailable to any future build menu. Session 3
named exactly this as the trigger for moving a global to a thumb button; the trigger has not
fired yet only because the build-menu decision itself is still open. Expect that to be the
next structural move rather than another binding.

**Open questions carried forward:** build menus (now urgent), control-group relocation,
whether `D` should move to a thumb button (now likely).

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
