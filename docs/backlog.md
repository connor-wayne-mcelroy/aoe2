# Backlog

Actions that have surfaced in real games, tiered but not yet bound. Populated by the
intake procedure — nothing goes here speculatively, and nothing here is a commitment.

Provisional tiers are revisable; re-tiering an entry as we learn more is expected, not a
failure.

| Action | Provisional tier | Why (mature-play reasoning) | Status | First seen |
|---|---|---|---|---|
| Go to / cycle Town Centers | B | Camera navigation, not production. Genuinely useful for checking a TC or dropping a building near one, but it is not part of the production loop and must not inherit a premium key merely for being TC-adjacent. Double-tapping `D` already centers on the TCs, which may cover most of this need. | Deferred | S2 |
| Cycle idle villager | S (est.) | The other half of villager economy: production is worthless if the villagers then stand still. Expected to be the next reserve spend, but not bound until it is felt in a real game. | Deferred | S2 |

## Open structural questions

These are unresolved decisions that will shape large parts of the layout. Answering one
may reshuffle several bindings at once, so we hold them open rather than guessing.

- **Build menus.** Positional grid vs. hand-picked per building. Deferred; currently on DE
  defaults. Resolving this determines how much left-hand supply the villager context needs.
- **Control groups.** The default number row is tier 3-4 real estate carrying what is
  usually S-tier importance. Whether to relocate them, and what to, is a large decision
  that should not be made piecemeal.
- **Selection contexts.** How much key reuse DE genuinely allows across villager /
  military / building contexts. Needs in-game verification; the answer changes effective
  supply substantially.
- **Should `D` move to a thumb button?** Since select-all-TC is global, putting it on
  `Mouse4` would reclaim `D` across every context at once while keeping the action equally
  available — and thumb-then-`F` uses opposite hands, so there is no finger contention at
  all. Held rather than done, because it is a cheap, non-destructive change we can make at
  any time, and spending a thumb reserve before knowing what needs mid-drag firing would
  break the standing reserve rule for a benefit we can still capture later. Revisit when the
  build-menu decision creates real pressure on `D`.
- **`F` as a general "train the primary unit" key.** If unit-creation hotkeys are scoped
  per building, `F` could mean *train villager* at a TC and *train the main unit* at a
  barracks / archery range / stable. That would be an unusually clean pattern — one finger,
  one meaning, every producer. Attractive enough to be worth deliberately not spending `F`
  elsewhere until it is tested.

## To verify in game

- Selecting all TCs and pressing train repeatedly should distribute villagers to the TCs
  with the shortest queues. The whole value of `D -> F F F` depends on this; if DE instead
  stacks them all on one TC, the loop needs rethinking.
- Whether `D` leaves the camera in place on a single press (expected) and centers on
  double-tap.
- **Scope test (do this first).** Select a villager, press `D`. If the Town Centers get
  selected, "Select all Town Centers" is confirmed global and shadows `D` in every context.
  Then try binding `D` inside Buildings 1 and see whether the editor warns about a conflict.
- Whether "Create Villager" really is scoped to the Town Center rather than global. If it
  turns out to be global too, `F` is far more expensive than currently priced and the
  "train the primary unit everywhere" idea is dead.
