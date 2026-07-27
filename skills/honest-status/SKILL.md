---
name: honest-status
description: Write a status update, standup note, or handoff that survives contact with reality. Use when reporting progress, writing a summary of work done, handing off to someone else, or answering "where are we on X". Keeps done/partial/blocked distinctions visible instead of smoothing them into a cleaner story.
---

# Honest Status

The purpose of a status update is that someone can act on it without asking
follow-up questions. Every smoothed edge costs somebody a round trip.

## The three words that matter

**DONE** — finished *and verified*. You can point at the artifact.
**PARTIAL** — real work landed, something specific remains. Name the something.
**BLOCKED** — cannot proceed. Name what would unblock it and who owns that.

If a thing doesn't fit cleanly into one, it's PARTIAL. When in doubt, PARTIAL.

## Rules

- **Built ≠ shipped.** Written, committed, pushed, deployed, and verified-live
  are five different states. Say which one.
- **Name what you did NOT do.** Scope you dropped, tests you skipped, the case
  you didn't handle. This is the highest-value line in any update and the one
  most often missing.
- **One owner per blocker.** "Waiting on the team" is not a blocker, it's a
  mood. "Waiting on <person> for <thing>" is actionable.
- **Numbers, not adjectives.** "Mostly working" tells no one anything.
  "38/41 tests pass; the 3 failures are all in the retry path" tells them
  everything.
- **Lead with the thing they'd want to interrupt you about.** Bad news goes
  first, in the first sentence, in plain words.

## Anti-patterns

| Don't write | Write |
|---|---|
| "Made good progress on the migration" | "3 of 7 tables migrated; `orders` blocked on a FK cycle" |
| "Should be done tomorrow" | "Remaining: the FK cycle. ~half a day once we pick an approach." |
| "Deployed the fix" | "Deployed at 14:20; verified the 500s stopped in prod logs" |
| "Tests are passing" | "41/41 green — note the suite doesn't cover token refresh" |
| "Ran into some issues" | "Two issues: <a> (fixed), <b> (open, needs a decision)" |

## Shape

```
<one sentence: the headline, bad news first if there is any>

DONE
  · <thing> — <how it was verified>

PARTIAL
  · <thing> — <exactly what remains>

BLOCKED
  · <thing> — needs <what> from <who>

NOT DONE / DROPPED
  · <thing> — <why>
```

Short is fine. Vague is not.

## The hardest one

When you were wrong, or something you previously reported as done turns out not
to be — **correct it in one plain sentence at the top and move on.** No
preamble, no apology paragraph, no re-litigating how it happened.

> "Correction: the deploy I reported yesterday didn't land — the branch had no
> upstream. Pushed now, verified live."

That's the whole correction. Owning it is the work; performing regret about it
wastes the time of the person who needs the fix.
