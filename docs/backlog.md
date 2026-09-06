# Backlog

Actions that have surfaced in real games, tiered but not yet bound. Populated by the
intake procedure — nothing goes here speculatively, and nothing here is a commitment.

Provisional tiers are revisable; re-tiering an entry as we learn more is expected, not a
failure.

| Action | Provisional tier | Why (mature-play reasoning) | Status | First seen |
|---|---|---|---|---|
| Go to / cycle Town Centers | B | Camera navigation, not production. Genuinely useful for checking a TC or dropping a building near one, but it is not part of the production loop and must not inherit a premium key merely for being TC-adjacent. Double-tapping `D` already centers on the TCs, which may cover most of this need. | Deferred | S2 |
| ~~Cycle idle villager~~ | S | The other half of villager economy: production is worthless if the villagers then stand still. | **Bound `S`, S5** | S2 |
| Select all Barracks | B | Mostly a prerequisite building rather than a queue you return to, but emergency spears against cav are genuinely urgent when they happen. Urgency is high, frequency is low, which is exactly the B-tier shape. Earmarked for `Ctrl+A`; that combo is cramped (pinky doing two jobs), which is acceptable for the rarest of the three. Promote to a bare tier-3 key if emergency spears turn out to be a recurring pain. | Deferred | S6 |
| Select all idle villagers | B | Bulk reassignment after a fight or a resource running dry. Real, but occasional, and usually the wrong tool — idles normally want individual assignment. Earmarked for `Ctrl+S` under the variant-pairing rule; no premium slot. | Deferred | S5 |

## Open structural questions

These are unresolved decisions that will shape large parts of the layout. Answering one
may reshuffle several bindings at once, so we hold them open rather than guessing.

- ~~**Build menus.**~~ **Resolved (S7): hand-picked, not grid.** `D`, `S` and `A` are globals
  and globals beat context, so a grid would have three dead cells in its best row. Buildings
  now get keys one at a time by placement frequency. Remaining candidates, unbound: House
  (A — placed constantly, `G` held for it), Mining Camp (B, `C` held for it), Mill (B),
  Town Center (B, but urgent when it matters), military buildings (B), Blacksmith/Market (C),
  walls and gates (C/D).
- **Control groups.** The default number row is tier 3-4 real estate carrying what is
  usually S-tier importance. Whether to relocate them, and what to, is a large decision
  that should not be made piecemeal.
- **Selection contexts.** How much key reuse DE genuinely allows across villager /
  military / building contexts. Needs in-game verification; the answer changes effective
  supply substantially.
- **Control group 3, and removing/replacing group contents.** Group 3 is C-tier by the
  player's own account (never more than 3, usually 1-2) and stays unbound; `W` is its home if
  it earns one. "Set group" (replace contents) is deferred with it, earmarked for `Ctrl+R` /
  `Ctrl+E`. Its value rose in S12: with only *add* bound, a group that gets the wrong units in
  it cannot be cleaned. **Promoted in priority by S13:** with `Shift` now carrying add-to-group,
  accidental pollution is more likely, and replace is the only cure. Bind it the first time a
  group gets polluted — or sooner if the misfire turns out to be common.
- **Give add-to-group-1 a bare key instead of a modifier.** Three sessions running, the
  friction has been the modifier rather than the base key, which suggests the native fix is to
  stop using one for the frequent case. `G` is the candidate — home-row index, one key right of
  `F`, nothing held, and it removes the stray-`Shift` hazard from the operation most likely to
  be done mid-fight. **Conflict (S15):** `G` is now held for House in the villager context, and
  a global would kill it. If this fallback is adopted, use `T` or `X` instead — the villager
  context is now the scarcer of the two. Group 2's add stays on `Shift+E`, since it is rare enough for a modifier.
  Costs one more global, dead in the villager context. **Trigger:** adopt if `Shift+R` proves
  awkward or misfires in real games. Trying `Shift` first (S14).
- **Should `D` move to a thumb button?** Since select-all-TC is global, putting it on
  `Mouse4` would reclaim `D` across every context at once while keeping the action equally
  available — and thumb-then-`F` uses opposite hands, so there is no finger contention at
  all. Held rather than done, because it is a cheap, non-destructive change we can make at
  any time, and spending a thumb reserve before knowing what needs mid-drag firing would
  break the standing reserve rule for a benefit we can still capture later. Revisit when the
  build-menu decision creates real pressure on `D`.
- ~~**Control-group relocation.**~~ **Resolved (S11):** groups 1 and 2 on `E` and `R`, off the
  number row entirely. The Session 1 tension — S-tier importance sitting on tier 3-4 real
  estate — is closed.
- ~~**`F` as a general "train the primary unit" key.**~~ **Resolved (S4): viable.** Unit
  creation is per-building scoped, so `F` can mean *train the main unit* at every producer.
  Now a standing policy reserve in `layout.md` rather than an open question.

## To verify in game

- Selecting all TCs and pressing train repeatedly should distribute villagers to the TCs
  with the shortest queues. The whole value of `D -> F F F` depends on this; if DE instead
  stacks them all on one TC, the loop needs rethinking.
- Whether `D` leaves the camera in place on a single press (expected) and centers on
  double-tap.
- That DE exposes per-type "Select all Stables" / "Select all Archery Ranges" as separate
  Game Commands globals, as assumed in Session 6.
- That `F` really does train the primary unit at a stable and an archery range, not just at
  the TC. Four loops now depend on the `F` policy holding.
- **That "add to control group" creates the group when it does not exist.** The whole
  two-operation design rests on this. If adding requires an existing group, "set group" comes
  back as a needed binding and goes on `Alt+R` / `Alt+E`.
- That DE captures `Caps` as a bindable key. If not, page 2 goes to `Tab` (also pinky column,
  slightly further from home).

### Resolved

- ~~Is the building page sticky?~~ **No** (S10). The panel resets to the base villager page
  after each placement, so the page key is pressed before every building. `Q` confirmed A+.
- ~~Do building hotkeys fire directly with a villager selected?~~ **No** (S9). Placement is
  page-gated: `[page] -> [building] -> click`.
- ~~Does the Mill farm-reseed queue need a hotkey?~~ **No** (S8). Villagers auto-reseed in DE
  while wood is available. Farm upkeep is not a hotkey problem at all.
- ~~Is select-all-TC global?~~ **Yes** (S4). Shadows `D` everywhere.
- ~~Is Create Villager TC-scoped?~~ **Yes** (S4). `F` is reusable across contexts.
