---
type: guide
stage: printing-operation
role: print-operator
frequency: as needed
---

# Adjust global performance

*print operator*{ .badge .role } *as needed*{ .badge .freq }

During a print, the **Performance** sub-page of
[Printing control](../../products/control/printing-control.md#performance)
accelerates or decelerates the whole process without changing the material or
the extruded layer.

!!! warning "Every motor follows"
    A change in the performance factor changes every motor. The
    [usage rate](../../products/control/printing-control.md#usage-rate) shows how
    far the global performance can change — keep an eye on it.

1. Open the **Performance** sub-page.
2. Change the performance factor.

    <!-- TODO: needs source — how the performance factor is entered, and its range -->

3. Watch the usage rates on the left.

The change is applied once the live values of the motors have moved on the usage
rate, and every one stays inside its extremum values.

!!! tip "If something goes wrong"
    **ERRORS** in the status box → [A motor reports an error code](../maintenance/a-motor-reports-an-error-code.md)

**Next:** [Pause and resume a print](pause-and-resume-a-print.md)
