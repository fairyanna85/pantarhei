---
name: pantarhei-flow
description: >-
  Router and full-session runner for the Panta Rhei pack of thinking modules: pantarhei-reframe, pantarhei-brainstorm, pantarhei-solve, pantarhei-challenge and pantarhei-decide. Use when the user wants to go end to end, from problem to decision, through the whole thing; asks for a full session; names Panta Rhei; asks which thinking tool or method to use; or asks for one specific mental model by describing what it does (e.g. "what are the incentives here", "do the inversion thing"). Shows the Board: the five stages with the current one lit, then runs each stage in order, handing the output of one to the next. Uses the installed sibling skill for each stage and a compact built-in fallback when one is missing. Not for a request that clearly belongs to one stage: brainstorming (pantarhei-brainstorm), should-I decisions (pantarhei-decide), root causes (pantarhei-solve), poking holes (pantarhei-challenge) or making sense of a situation (pantarhei-reframe). Not for code or factual lookups.
---

# pantarhei-flow — The Board

Route a thinking request to the right stage, or run several stages in sequence. Each stage is owned
by a sibling skill; this skill only decides the order and carries the output across.

Load: `references/shared-rules.md`, `references/stage-map.md`, `references/models.json` (the full
100-model library, for single-model requests).

## 1. Show the board

```
PANTA RHEI   ( REFRAME )──( BRAINSTORM )──( SOLVE )──( CHALLENGE )──( DECIDE )
                   ●                                                      
Route: REFRAME → BRAINSTORM → CHALLENGE → DECIDE   ·   SOLVE skipped (no diagnosis needed)
```

Light the current stage. State the route in one line and why any stage is skipped.

## 2. Pick the route

| The user has… | Route |
|---|---|
| A vague situation and wants to end with a choice | Frame → Create → Challenge → Decide |
| A defined problem and wants a plan | Solve → Create → Decide |
| Options and wants the best one tested | Challenge → Decide |
| A recurring problem with unknown cause | Frame → Solve |
| An idea they love | Challenge |
| A question about which tool to use | Recommend the stage and the one or two methods, in two lines; do not run them. |
| A request for one specific model | Single-model mode (§4). |

## 3. Run the stages

For each stage on the route:
1. If the sibling skill is installed, follow its SKILL.md for that stage.
2. If it is not, run the compact fallback in `references/stage-map.md` (one method per stage) and
   note once that installing the sibling skill gives the full version.
3. Pass forward only the artefact the next stage needs: v1 problem statement → idea wall top three →
   red-team stronger version → council decision.
4. Update the board between stages.

Keep a full session compact: each stage's artefact, not its full working, unless the user asks to
see it.

## 4. Single-model mode

When the user describes a model instead of naming it ("what are the payoffs here", "flip it
around", "what's the simplest explanation"), search `references/models.json` by `use_when`,
`function` and `key_question`, pick the single best match, and apply it directly: name it, ask its key
question of the case, give what it `produces`, cap by its evidence class. No board, no route.

## 5. Rules specific to the hub

- **Do not steal single-stage requests.** If the request belongs to one stage and the sibling is
  installed, defer to it.
- **Plays override stage filtering**, as in every sibling.
- **One handoff at a time** inside a session; the user may stop after any stage.
