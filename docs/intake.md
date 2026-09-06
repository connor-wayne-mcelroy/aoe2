# Intake Procedure

Run this when a game surfaces a need. The point is to make the *tier* decision before the
*key* decision, so that noticing an action never entitles it to a good slot.

## Step 1 — Describe the need, not the key

Record what actually happened: what you wanted to do, what you did instead, and what it
cost. "I wanted X on a key" is not an intake; "I lost 20 seconds of villager production
because I couldn't get back to the TC" is.

## Step 2 — Tier it for the mature layout

Answer these before looking at any keyboard:

1. **Frequency at maturity.** How often will an experienced version of you do this per
   game? Per minute in the phase where it matters?
2. **Time pressure.** Does being half a second slow cost anything, or is it merely tedious?
3. **Substitutability.** Can the mouse do it acceptably? Many actions are fine on the mouse
   and deserve no key at all.
4. **Growth.** Will this get more or less important as skill increases? Some early-player
   pains disappear; some late-player needs are invisible today.
5. **Context.** Is it scoped to a selection context, meaning it can share a physical key?

Then assign S / A / B / C / D. Write the reasoning down — a tier without a reason is an
impulse wearing a costume.

### If the need splits into sub-actions

Run each sub-action through Step 2 **independently**. A derived half inherits nothing from the
parent request — not its tier, and not the assumption that it is a hotkey problem at all.
Question 3 (substitutability) applies to every half separately: the game may already solve one
of them. This is exactly the check that was skipped in Session 7.

## Step 3 — Decide whether it gets a binding *now*

Tiering is not binding. Valid outcomes, in rough order of frequency:

- **Defer.** Correct answer most of the time, especially for anything below B, and for
  anything whose tier we can't yet estimate honestly. Goes on the backlog.
- **Bind at tier.** Take the best *available* slot whose grade matches the tier — not the
  best free slot overall.
- **Bind and displace.** If the new action outranks something already holding a good slot,
  move the incumbent down. Demotions are normal and expected.
- **Unlock a reserve.** Only for a genuine S-tier with a demonstrated cost. Requires an
  explicit note in the decisions log saying why the reserve was spent.
- **No binding, ever.** Some actions are correctly left on the mouse or on defaults.

## Step 4 — Check the neighborhood

Before committing:

- What chains does this key appear in? Apply the sequence rule (no shared finger in a
  frequent pair).
- Is it pressed while the mouse is busy? Apply the simultaneity rule.
- Does the choice block a plausible future S/A-tier action from its natural home?
- Are we still holding enough reserves?

## Step 5 — Log it

Every change gets an entry in `docs/decisions.md`, including changes we *declined* to make.
The declines are the more valuable record: they are what stops the layout drifting into
first-come-first-served.

## Budget

One or two bindings per session, typically. Zero is a perfectly good session.
