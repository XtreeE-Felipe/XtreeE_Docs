---
type: guide
stage: maintenance
role: print-operator
frequency: on symptom
---

# Real flow doesn't match assigned flow

*print operator*{ .badge .role } *on symptom*{ .badge .freq }

When a pump delivers a different flow from the one assigned in XtreeE Control,
recalibrate it with a
[pump flow update](../../products/control/index.md#pump-flow-update). You need
the pump running at an assigned flow, and a measure of the real flow it
delivers.

<!-- TODO: needs source — how to measure the real flow of a pump -->

1. On the pump's
   [control panel](../../products/control/index.md#motor-control-panel), open
   the pump flow update window. **Flow target** shows the assigned value; it
   cannot be changed.
2. Write the flow you observe in **Flow measure**.
3. Click **YES** to update the flow from your measure — or **NO** to quit and
   keep the previous flow.

A new measure should now match the assigned flow. To go back to the factory
calibration instead, click **BACK TO FACTORY**.

!!! note
    The date of the last flow update is erased on a deep reboot of the PLC, for
    example a program update.

<!-- TODO: needs source — what to do when the flow still does not match after an update -->

**Next:** [A motor reports an error code](a-motor-reports-an-error-code.md)
