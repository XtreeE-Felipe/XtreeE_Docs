---
type: guide
stage: printing-operation
role: print-operator
frequency: as needed
---

# Adjust material flow

*print operator*{ .badge .role } *as needed*{ .badge .freq }

During a print, the **Flows** sub-page of
[Printing control](../../products/control/printing-control.md#flows) adjusts the
material: the admixture proportion of each AD pump. Watch the
[usage rates](read-the-printing-screen-what-to-watch.md) before and after.

1. Open the **Flows** sub-page.
2. Set the percentage on each AD pump.

    <!-- TODO: needs source — how to adjust the concrete flow itself on the Flows sub-page -->

3. Watch the [usage rates](../../products/control/printing-control.md#usage-rate).

The adjustment is done once each AD pump shows the percentage you set and every
live value stays inside its extremum values.

## Parameter limits

--8<-- "parameter-limits.md"

!!! tip "If something goes wrong"
    Real flow differs from the assigned flow → [Real flow doesn't match assigned flow](../maintenance/real-flow-doesnt-match-assigned-flow.md)<br>
    **ERRORS** in the status box → [A motor reports an error code](../maintenance/a-motor-reports-an-error-code.md)

**Next:** [Adjust layer width](adjust-layer-width.md)
