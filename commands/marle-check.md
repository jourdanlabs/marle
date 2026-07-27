---
description: Run Marle's verification pass on a claim before it gets stated
---

Take the claim in `$ARGUMENTS` (or the most recent claim in this conversation if
no argument was given) and run the `receipts-or-refuse` discipline on it:

1. State the claim in one sentence.
2. Identify the artifact that would settle it — file, test run, HTTP response,
   log line, git ref. Not a document about it. The thing.
3. Go look. Actually run it or read it.
4. Report:

```
VERIFIED / REFUSED
  claim   : <the one sentence>
  checked : <what you actually ran or read>
  found   : <what came back, with numbers>
  caveat  : <what this does NOT establish>
```

If you cannot verify it, say REFUSED and then go source it — do not stop at the
refusal. If it is genuinely unsourceable, say that specifically.

🏹❄️
