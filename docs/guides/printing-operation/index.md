---
type: contract
stage: printing-operation
---

# Stage 4 · Printing operation

*print operator*{ .badge .role }

The only stage that happens inside an open session. It ends when the motors are shut off and the system is cleaned — that event closes the session and ends the log, whether the print succeeded or not.

## The contract

| | |
|---|---|
| **Role** | print operator |
| **Needs in hand** | a cell cleared to print, with the session open |
| **Produces** | **printed objects + a session log** |
| **Session** | inside the session — **it closes at the end of this stage** |

## The guides, in order

1. [Pre-print check](pre-print-check.md) — *per object* · **gate**
1. [Start a print — the initialization phase](start-a-print-the-initialization-phase.md) — *per object*
1. [Resume a partial print in a new session](resume-a-partial-print-in-a-new-session.md) — *as needed*
1. [Read the printing screen — what to watch](read-the-printing-screen-what-to-watch.md) — *per session*
1. [Adjust material flow](adjust-material-flow.md) — *as needed*
1. [Adjust layer width](adjust-layer-width.md) — *as needed*
1. [Adjust global performance](adjust-global-performance.md) — *as needed*
1. [Pause and resume a print](pause-and-resume-a-print.md) — *as needed*
1. [Print the next object in the same session](print-the-next-object-in-the-same-session.md) — *per object*
1. [Stop a print safely](stop-a-print-safely.md) — *as needed*
1. [Close the session — purge, park, clean, motors off](close-the-session-purge-park-clean-motors-off.md) — *per session*
1. [Session closed — the log ends here](session-closed-the-log-ends-here.md) — *per session* · **gate**


## Then

[Stage 5 · Session report](../session-report/index.md)
