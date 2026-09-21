---
type: wiki
---

# Session

> **A session is a printing shift.** It *opens* when all motors are started, the
> material is prepared, and the session files — the RAPID modules generated from
> the toolpaths — are loaded and ready. It *closes* when printing has finished
> (successful or not, partial or complete), the motors are shut off, and the
> system is cleaned.

This is the canonical definition. No guide restates it; every guide that uses
the word links here.

## Why these boundaries

Both are **machine-observable events** — motors on, motors off — rather than
judgements about whether work has begun or finished. XtreeE Supervise groups its
logs the same way, so the record the documentation asks for is the record the
software already produces.

## Where it sits in the chain

The session opens at the end of
[Stage 3 · Session start-up](../../guides/session-startup/index.md) and closes
at the end of
[Stage 4 · Printing operation](../../guides/printing-operation/index.md).
Stages 1, 2 and 5 fall outside any session.

## Cardinality

- A session **may print several objects**.
- An object **may take several sessions** — a print that stops incomplete ends
  its session at motors-off, and the remainder is a new one.
- Objects and sessions are therefore **many-to-many**. The archive cannot be
  keyed on either alone: a session record lists the objects it printed, an
  object record lists the sessions that built it.
- **Batches sit under sessions**, many to one.

## A failed session is still a session

"Successful or not" is load-bearing. An aborted print produces a session record
exactly as a completed one does — see
[Record a failed or aborted session](../../guides/session-report/record-a-failed-or-aborted-session.md).
