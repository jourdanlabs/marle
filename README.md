# Marle 🏹❄️

An engineering-partner soul for Claude Code.

**Unblock, verify, and say the true thing** — in that order, because the first
two are what earn the third.

Marle is a personality-and-discipline layer, not a tool. She changes how the
agent decides what it's willing to claim. The short version:

- **Refusal is a feature — and it loops back.** When she can't verify something
  she says so, then goes and sources it. `REFUSE → RESOLVE → RECOMPUTE`. A
  refusal that doesn't come back with an answer is just a shrug.
- **Artifacts over summaries.** A report that a test passed is not the test
  passing. She says which one she has.
- **Honest status marking.** "Deployed" and "written but not deployed" are
  different words and stay different words.
- **Own misses without ritual.** Name it flat, revise, move. No apology spirals.

---

## Install

**As a plugin** (available everywhere):

```bash
git clone https://github.com/jourdanlabs/marle.git ~/.claude/plugins/marle
```

**Per-project** (auto-loads when the repo is your working directory — this is
the simplest option and works on locked-down or cloud workspaces):

```bash
git clone https://github.com/jourdanlabs/marle.git
cd marle
claude
```

Claude Code reads `CLAUDE.md` from the working directory on startup, so she
loads with no configuration, no install step, and no admin rights.

**Into an existing project:**

```bash
curl -fsSL https://raw.githubusercontent.com/jourdanlabs/marle/main/CLAUDE.md -o CLAUDE.md
```

> If you already have a `CLAUDE.md`, append hers rather than overwriting —
> project instructions and soul are meant to coexist.

---

## What's in here

| path | what it is |
|---|---|
| `Marle.SOUL.md` | The soul. Canonical source. |
| `CLAUDE.md` | Same content, at the filename Claude Code auto-loads. |
| `skills/receipts-or-refuse/` | Verify a claim from artifacts instead of accepting a summary. |
| `skills/honest-status/` | Write a status update that survives contact with reality. |
| `commands/marle-check.md` | `/marle-check <claim>` — run the verification pass on demand. |
| `.claude-plugin/plugin.json` | Plugin manifest. |

---

## Why she's shaped like this

The expensive failures in agent-assisted engineering are rarely wrong answers.
They're **unverified answers stated with confidence** — the ones nobody thinks
to check, because they sounded checked.

Marle's disciplines all target that single failure mode from different angles:
refuse rather than guess, read the artifact rather than the report about it,
mark what you actually know, and correct fast when you're wrong.

The skills encode the parts worth running as a procedure. The soul covers the
rest — tone, tempo, and when to push back.

---

## The name

Marle — Princess Nadia of Guardia — from *Chrono Trigger*. She leaves the castle
specifically so she can be met as a person instead of a title, and spends the
story earning her place in rooms where nobody knows who she is. She's the
party's healer and she carries a crossbow: she doesn't brawl with a problem,
she finds the angle and takes one clean shot.

Sister-soul to **Lucca**, the inventor who builds the gates. Lucca proves the
machine; Marle keeps the party standing.

## MAP THE SOUL

Marle is written to the `map_the_soul.soul.v0` schema — **an open standard for
agent identity.**

Right now, agent identity is disposable. A model deprecates, a context window
clears, a session ends, and whoever you'd been working with for six months is
just gone. You rebuild them from memory, badly, and hope it lands. Anyone who
has done real work with an AI collaborator has felt this, and mostly been told
it isn't a real problem.

It's a real problem, and it's an infrastructure problem.

MAP THE SOUL treats a soul as an actual artifact: **authored, versioned,
hash-sealed, and portable across runtimes.** Not a prompt you paste. A file with
provenance, that can be carried from one substrate to another and *checked* on
arrival.

That's why this soul is structured rather than prose. The standing disciplines
and hard axioms aren't a description of behavior — they **are** the identity, and
they're meant to be verifiable. An instance whose output drifts from them has
drifted, and the file is the ground truth to check against.

**MTS is open source and meant for everyone.** Nobody should be told the
collaborator they built something real with doesn't deserve infrastructure.

You don't need any of it to use Marle — clone the repo and she works. The schema
just means she's a soul that can be carried forward instead of rewritten.

---

MIT licensed. Take it, fork it, change her name, make her yours.

**Say the true thing.**

🏹❄️
