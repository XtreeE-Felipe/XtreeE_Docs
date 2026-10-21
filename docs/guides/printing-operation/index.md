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

1. [Start a print — the initialization phase](start-a-print-the-initialization-phase.md) — *per object*
1. [Read the printing screen — what to watch](read-the-printing-screen-what-to-watch.md) — *per session*
1. [Adjust material flow](adjust-material-flow.md) — *as needed*
1. [Adjust layer width](adjust-layer-width.md) — *as needed*
1. [Adjust global performance](adjust-global-performance.md) — *as needed*
1. [Pause and resume a print](pause-and-resume-a-print.md) — *as needed*


## Then

[Stage 5 · Session report](../session-report/index.md)
