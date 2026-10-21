---
type: guide
stage: printing-operation
role: print-operator
frequency: as needed
---

# Adjust layer width

*print operator*{ .badge .role } *as needed*{ .badge .freq }

Layer width is a direct result of the ratio between material flow rate and robot
speed. During a print, the **Width** sub-page of
[Printing control](../../products/control/printing-control.md#width) corrects it,
and lets you choose which machine absorbs the change. Start from the current
layer width in the
[program data](../../products/control/printing-control.md#program-data).

<!-- TODO: needs source — how to decide the width correction needed -->

!!! warning "A width change moves the admixture pumps too"
    The admixture proportion is fixed on this sub-page. If the pump absorbs the
    change, the concrete flow changes — and the activated AD pumps change with
    it. Keep an eye on the
    [usage rates](../../products/control/printing-control.md#usage-rate).

1. Open the **Width** sub-page.
2. Enter the width correction, in mm. It can be negative.
3. Select the machine that absorbs the change: the robot or the pump.
4. Watch the usage rates on the left.

The correction is applied once the **Width** sub-page shows your correction and
selected machine, and every live value stays inside its extremum values.

## Parameter limits

--8<-- "parameter-limits.md"

!!! tip "If something goes wrong"
    Real flow differs from the assigned flow → [Real flow doesn't match assigned flow](../maintenance/real-flow-doesnt-match-assigned-flow.md)<br>
    **ERRORS** in the status box → [A motor reports an error code](../maintenance/a-motor-reports-an-error-code.md)

**Next:** [Adjust global performance](adjust-global-performance.md)
