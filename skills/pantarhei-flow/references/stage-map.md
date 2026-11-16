# Stage map and fallbacks (vendored into the hub as `references/stage-map.md`)

When a sibling skill is not installed, the hub runs the compact fallback for that stage. Each
fallback uses one method and produces the same artefact type as the full skill, so the next stage
can still consume it. After the fallback, add one line: "The full version of this step is <Module>."

| Stage | Sibling | Fallback method | Artefact passed forward |
|---|---|---|---|
| frame | pantarhei-reframe | Whose problem? (Gause & Weinberg) + one reframe from mm.inversion | v1 problem statement, one sentence, with owner |
| create | pantarhei-brainstorm | SCAMPER, one pass, 10 ideas, top 3 by novelty × feasibility | top-3 shortlist |
| solve | pantarhei-solve | Issue tree (2 levels) + 3 ranked hypotheses with one test each | ranked hypotheses + top test |
| challenge | pantarhei-challenge | Steelman + pre-mortem (5 failure reasons) + survival score | stronger version + score |
| decide | pantarhei-decide | Two advisors: Actuary (expected value, base rate) and Future You (regret); Chair verdict with one kill criterion | decision + kill criterion |

## Artefact contract between stages

| From → To | What is passed | What is not passed |
|---|---|---|
| frame → create | v1 problem statement, the question to carry forward | the lens rotation |
| frame → solve | v1 problem statement, domain reading | the lens rotation |
| create → challenge | top 3 + wildcard pick, one line each | the full wall |
| create → decide | top 3 as options | the full wall |
| solve → create | the top hypothesis and the binding constraint | the full tree |
| solve → decide | candidate countermeasures | the full tree |
| challenge → decide | the stronger version, survival score, weakest link | the attack table |
