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

1. [Choose a prepared program](choose-a-prepared-program.md) — *per session*
1. [Power up the cell](power-up-the-cell.md) — *per session*
1. [Load the program on the FlexPendant](load-the-program-on-the-flexpendant.md) — *per session*
1. [Check tool calibration](check-tool-calibration.md) — *per session*
1. [Reset the motors](reset-the-motors.md) — *per session*
1. [Verify the Settings table against the cell](verify-the-settings-table-against-the-cell.md) — *per session*
1. [Dry-test the program](dry-test-the-program.md) — *per session*

</div>

<div markdown>

### Material lane

*material operator*{ .badge .role } *per batch*{ .badge .freq }

1. [Mix the batch to the specified recipe](mix-the-batch-to-the-specified-recipe.md) — *per batch*
1. [Log the batch and spreading diameter](log-the-batch-and-spreading-diameter.md) — *per batch*
1. [Hand over the prepared material](hand-over-the-prepared-material.md) — *per batch*

</div>

</div>

The two lanes run **in parallel** and rejoin at the gate below. Neither lane opens the session on its own.

## The gate

1. [Session open — motors on, material ready, files loaded](session-open-motors-on-material-ready-files-loaded.md) — *per session* · **gate**

Passing it is the moment the [session](../../wiki/glossary/session.md) opens: motors on, material ready, files loaded.


## Then

[Stage 4 · Printing operation](../printing-operation/index.md)
