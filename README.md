<p align="center"><img src="assets/banner.svg" alt="Panta Rhei: five thinking modules, one flow from reframe to decision" width="100%"></p>

# Panta Rhei

A thinking-skills pack for Claude, Claude Code and Hermes: reframe, brainstorm, solve, challenge and decide, run end to end.

<p align="center">
  <a href="#install"><img alt="Install" src="https://img.shields.io/badge/install-1%20command-14161A"></a>
  <img alt="Library" src="https://img.shields.io/badge/library-100%20models-14161A">
  <img alt="Works with" src="https://img.shields.io/badge/works%20with-Claude%20·%20Claude%20Code%20·%20Hermes-5B6270">
  <img alt="License" src="https://img.shields.io/badge/license-MIT%20%2B%20CC%20BY%204.0-5B6270">
</p>

## What it does

Real problems rarely need one method: they need the right problem, then options, then a cause or a test, then a call. Panta Rhei routes a request to the right module, or runs several in order, handing each stage's output to the next. Installed alone it still works, with a compact fallback for any module that is missing.

<p align="center"><img src="assets/demo.gif" alt="A full Panta Rhei session: the board lights each stage in turn, from a reframed problem to a decision with kill criteria" width="85%"></p>

## Try it

Say any of these after installing:

> Take me from problem to decision on whether to restructure my team
> Which thinking tool should I use for this?
> What are the incentives here? Use that mental model on my situation.

## How it works: The Board

The board shows the five stages with the current one lit and the route chosen for your request. Each stage is owned by a sibling skill; the hub only chooses the order and carries the output across.

<p align="center"><img src="assets/hero-interaction.svg" alt="The Board: a worked example" width="90%"></p>

```
PANTA RHEI   ( REFRAME )──( BRAINSTORM )──( SOLVE )──( CHALLENGE )──( DECIDE )
                   ●                                                      
Route: REFRAME → BRAINSTORM → CHALLENGE → DECIDE   ·   SOLVE skipped (no diagnosis needed)
```

1. **Show the board:** the five stages and the route.
2. **Pick the route:** only the stages the request needs.
3. **Run the stages:** each module in turn, or its built-in fallback.
4. **Single-model mode:** ask for one of the 100 shared models by what it does.

## Install

**Claude Code**
```
/plugin marketplace add fairyanna85/pantarhei
/plugin install pantarhei-flow@pantarhei
```
This marketplace lists all six skills; install any of them by name.

**Hermes Agent**
```
hermes skills install https://github.com/fairyanna85/pantarhei
```

**Claude apps (web, desktop, mobile)**
1. Download [`pantarhei-flow.zip`](https://github.com/fairyanna85/pantarhei/releases/latest/download/pantarhei-flow.zip).
2. Go to **Customize > Skills**, click **+**, then **+ Create skill**, then **Upload a skill**, and choose the ZIP.
3. Turn the skill on. Code execution and file creation must be enabled (Settings > Capabilities).

**Any Agent Skills client** (Codex, Cursor and others): copy `skills/pantarhei-flow/` into your
client's skills folder.

## What's inside

| Module | Contents | Signature |
|---|---|---|
| Panta Rhei Reframe | 26 lenses | Lens rotation into a one-line problem statement |
| Panta Rhei Brainstorm | 31 methods | Card deck, bursts of ideas, shortlist |
| Panta Rhei Solve | 27 methods | Issue tree, ranked hypotheses, cheapest test |
| Panta Rhei Challenge | 13 methods | Steelman, attacks, survival score |
| Panta Rhei Decide | 31 methods | Council of advisors and a Chair |
| Shared library | 100 models | Mental models used across all five, plus 16 plays |

## How honest is it?

Every method carries an evidence class (`formal`, `empirical`, `heuristic`, `analogical`) and its
origin, and the skill caps its claims by them. Practitioner methods are labelled as such.
The hub inherits each module's evidence classes and adds none of its own claims.

## The Panta Rhei pack (optional)

Each module works on its own. The pack installs all five plus Panta Rhei, the hub that runs them
end to end.

| | Module | For |
|---|---|---|
| 🔵 | [Panta Rhei Reframe](https://github.com/fairyanna85/pantarhei-reframe) | Working out what the real problem is |
| 🟣 | [Panta Rhei Brainstorm](https://github.com/fairyanna85/pantarhei-brainstorm) | Brainstorming and idea generation |
| 🟢 | [Panta Rhei Solve](https://github.com/fairyanna85/pantarhei-solve) | Structuring and diagnosing problems |
| 🔴 | [Panta Rhei Challenge](https://github.com/fairyanna85/pantarhei-challenge) | Red-teaming ideas and claims |
| 🟡 | [Panta Rhei Decide](https://github.com/fairyanna85/pantarhei-decide) | Making the call |
| ⚫ | [Panta Rhei](https://github.com/fairyanna85/pantarhei) | The pack: all five, end to end |

## Credits and license

Methods are credited to their originators in `catalog.json` and on every card; all descriptions are
our own wording. Code: MIT. Method text: CC BY 4.0. Propose a method: see [CONTRIBUTING.md](CONTRIBUTING.md).
