---
type: contract
stage: session-startup
---

# Stage 3 · Session start-up

*cell operator*{ .badge .role } *material operator*{ .badge .role }

This stage runs in **two lanes with two operators**: a robot lane and a material lane. They run in parallel and rejoin at the gate, which is the moment the session opens.

## The contract

| | |
|---|---|
| **Role** | cell operator · material operator |
| **Needs in hand** | a prepared program, waiting in the store |
| **Produces** | **a cell cleared to print** — and the session opens |
| **Session** | **the session opens at the end of this stage** |

## The two lanes

<div class="lanes" markdown>

<div markdown>

### Robot lane

*cell operator*{ .badge .role } *per session*{ .badge .freq }

1. [Verify the Settings table against the cell](verify-the-settings-table-against-the-cell.md) — *per session*

</div>

<div markdown>

### Material lane

*material operator*{ .badge .role } *per batch*{ .badge .freq }

1. [Log the batch and spreading diameter](log-the-batch-and-spreading-diameter.md) — *per batch*

</div>

</div>

The two lanes run **in parallel** and rejoin at the gate below. Neither lane opens the session on its own.

## The gate

No gate guide is published yet.

Passing it is the moment the [session](../../wiki/glossary/session.md) opens: motors on, material ready, files loaded.


## Then

[Stage 4 · Printing operation](../printing-operation/index.md)
