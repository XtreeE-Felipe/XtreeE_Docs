---
type: guide
stage: printing-operation
role: print-operator
frequency: as-needed
---

<!-- PLACEHOLDER CONTENT - verify against product -->

# Adjust layer width

*print operator*{ .badge .role } *as needed*{ .badge .freq }

Mid-print correction when the deposited bead is measurably wider or narrower
than the program assumed — usually because the material is behaving differently
from the batch the recipe was sized against.

## Before you start

- A print running, with the [session](../../wiki/glossary/session.md) open.
- A measurement, not an impression: caliper the last completed layer in at least
  three places. Adjusting on how it looks from the gantry is how a print drifts.
- The program's assigned width to hand, from the printing screen in
  [XtreeE Control](../../products/control.md).

## You'll produce

A bead whose measured width matches the assigned width, with flow and pump load
still inside their limits.

!!! warning "Width does not move alone"
    Layer width is delivered by material flow at a given travel speed. Raising
    width raises the flow the pump must sustain, and on a variable-proportion
    head it raises admixture pump load with it. Push width up far enough and you
    hit the flow ceiling before you hit the width ceiling — at which point the
    system honours flow and quietly under-delivers width.

    Change width in small steps and re-measure. If you need more than about
    20 % correction, the batch is wrong, not the setting:
    [Real flow doesn't match assigned flow](../maintenance/real-flow-doesnt-match-assigned-flow.md).

## Steps

1. On the printing screen, note the currently assigned **layer width** and
   **flow rate**.
2. Measure the last completed layer in three places and take the mean.
3. Enter the corrected width in the width field. Values are constrained to the
   table below — the field will refuse anything outside it.
4. Confirm. The change takes effect at the start of the next segment, not
   immediately.
5. Let one full layer deposit, then re-measure. Repeat at most twice.
6. If flow has risen to its ceiling, stop adjusting width and
   [adjust material flow](adjust-material-flow.md) or revisit the batch.
7. Note the change and the reason in the session log — Stage 5 will ask why the
   printed object does not match the program.

## Parameter limits

These values are defined once, in one file, and included wherever they are
mentioned. Never restate them in prose.

--8<-- "parameter-limits.md"

Field-by-field definitions live in
[XtreeE Control](../../products/control.md); the physics of why width, flow and
speed are one setting in three costumes lives in
[Toolpath anatomy](../../wiki/toolpath-anatomy.md).

## Done when

Measured bead width is within tolerance of assigned width across three
consecutive layers, and flow rate has settled below its ceiling.

## If it goes wrong

- Width won't hold after two corrections →
  [Real flow doesn't match assigned flow](../maintenance/real-flow-doesnt-match-assigned-flow.md)
- The bead is the right width but landing off-path →
  [The head prints off-target](../maintenance/the-head-prints-off-target.md)
- You need to reach the nozzle to clear it →
  [Need to reach the head](../maintenance/need-to-reach-the-head.md)

## Next

[Adjust global performance](adjust-global-performance.md)
