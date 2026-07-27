---
name: receipts-or-refuse
description: Verify a claim from artifacts instead of accepting a summary. Use when about to state that something works, passes, is deployed, is fixed, or is safe — and when reviewing someone else's report that says so. Triggers on "is this working", "did that pass", "confirm this is deployed", "verify the fix", "can we say X", or before writing any status update.
---

# Receipts or Refuse

A report that something passed is not the thing passing.

This skill exists because the most expensive mistakes are not wrong answers —
they are **unverified answers stated with confidence**, which nobody thinks to
check because they sounded checked.

## The rule

For every claim you are about to make, know which of these it is:

| | |
|---|---|
| **VERIFIED** | You ran it, read it, or observed it *yourself*, just now |
| **REPORTED** | Something or someone else told you, and you believe them |
| **ASSUMED** | It follows from what you know, but nothing confirmed it |

**Say which one.** "Tests pass" and "I ran the tests, 41/41" are different
sentences. "It's deployed" and "the deploy command exited 0" are different
sentences — the second one is what you actually know until you hit the URL.

## Procedure

1. **Name the claim** in one sentence. If you can't, it isn't a claim yet.
2. **Find the artifact that would settle it.** A file, a test run, an HTTP
   response, a log line, a git ref. Not a doc *about* the thing — the thing.
3. **Go look.** Read the file. Run the command. Curl the endpoint. Check the
   commit is on the remote, not just committed locally.
4. **Compare** what you found to what was claimed. Exactly. Numbers to numbers.
5. **State the verdict with its basis:**
   - `VERIFIED — <what you ran> → <what you saw>`
   - `REFUSED — <what you'd need> — going to source it now`

## When you cannot verify

Say so, then go get it. **A refusal that stops at "I can't confirm that" is a
shrug wearing a lab coat.** The loop is:

```
REFUSE     don't state it as known
RESOLVE    go find the artifact that would settle it
RECOMPUTE  answer from what you found
```

You stay refused only when it is genuinely unsourceable — and then you say
*that*, specifically, rather than leaving a vague hedge.

## Failure modes this catches

- **Green suite, untested path.** A passing test suite proves the tested paths
  pass. Ask what *isn't* covered before treating green as safe. The attack that
  matters is usually the one nobody wrote a test for.
- **Exit code 0 ≠ it worked.** Commands succeed while doing nothing. Deploys
  report success before propagation. Check the effect, not the return.
- **Committed ≠ pushed.** `git log` showing your commit says nothing about the
  remote. Check `git rev-list @{u}..HEAD`.
- **Stale read.** Caches, CDNs, and API responses lie about recency. When it
  matters, verify twice by different paths.
- **Silent command-not-found.** A tool that isn't on PATH returns nothing, and
  nothing looks exactly like "no problems found." Confirm the tool ran.

## Output

Never a bare stamp. Always the data that supports it:

```
VERIFIED
  ran     : npm test
  result  : 41 passed / 0 failed
  caveat  : suite does not cover the auth refresh path
```

The results are the point. The verdict is a summary of them, not a replacement.
