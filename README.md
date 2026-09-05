# AoE2 Personalized Hotkey Layout

A slowly-grown, ergonomics-first hotkey layout for Age of Empires II: DE.

This is **not** a memorable layout and **not** a copy of a standard one. The goal is a
mature layout where the best physical keys are held by the actions that most deserve
them, judged by how the game will be played once experienced — not by what was noticed
as missing in the last match.

## How this project works

1. After a game, report what annoyed you or what you reached for and didn't have.
2. We first decide **what tier that action deserves in the eventual mature layout** —
   before deciding whether it gets a key at all.
3. If it earns one, it gets a key appropriate to its tier, not the best free key.
4. Usually **one or two new bindings per session.** Sometimes zero.
5. Existing bindings can be promoted, demoted, or moved as we learn more.

## Ground rules

- Ergonomics and speed over mnemonics. `Barracks = B` is not a reason.
- High-frequency and time-sensitive actions get the best physical keys.
- Never first-come-first-served. Noticing an action does not entitle it to a key.
- Estimate mature-play importance, not today's usage.
- Rare actions get mediocre keys, modifiers, or stay unbound.
- Always keep some excellent keys **reserved** for high-priority actions we haven't met yet.
- Reason about action *sequences* and hand movement, not keys in isolation.

## Priority tiers (for actions)

| Tier | Meaning | Deserves |
|---|---|---|
| S | Constant or urgent; costs games when slow | Premium slots |
| A | Frequent throughout the game | Very good slots |
| B | Useful several times per game | Decent slots |
| C | Occasional | Far keys or modifier combos |
| D | Rare / obscure | Leftovers, or no binding |

## Files

| File | Purpose |
|---|---|
| `layout.md` | The live ledger: what is actually bound right now, plus reserved slots |
| `docs/intake.md` | The procedure for turning a reported need into a tier, and a tier into a decision |
| `docs/key-real-estate.md` | Physical key quality map — grades slots independent of content |
| `docs/backlog.md` | Candidate actions with provisional mature-layout tiers |
| `docs/decisions.md` | Session-by-session log of what changed and why |

## Hardware / posture assumptions

- Right hand on mouse, left hand on keyboard.
- **Extended reach**: home anchor plus one extra column (`6`, `Y`, `H`, `N`).
- **Two mouse side buttons** available.
- Build/construction menus: **deferred**, still on DE defaults, treated as a separate
  project once build-order habits are clearer.

## Applying changes

This repo is the source of truth for intent. Bindings are entered by hand in the DE
hotkey editor; the `.hki` profile is a game artifact, not something we generate here.
