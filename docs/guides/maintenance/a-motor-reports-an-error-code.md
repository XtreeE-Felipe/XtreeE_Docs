---
type: guide
stage: maintenance
role: cell-operator
frequency: on symptom
---

# A motor reports an error code

*cell operator*{ .badge .role } *on symptom*{ .badge .freq }

When the [status box](../../products/control/index.md#status-box) of XtreeE
Control reads **ERRORS**, the motors are powered but at least one has an error.
Find which motor, and its code.

1. In the status box, click **INFO**. It lists the error code of each motor.
2. Find the motors whose code is not `0` — `0` means no error.
3. Resolve the error.

    <!-- TODO: needs source — meaning of each motor error code and how to clear it -->

The error is cleared once every motor shows `0` under **INFO** and the status box
reads **NO ERRORS - POWER ON**.

!!! tip "If something goes wrong"
    **NO ERRORS - POWER OFF** in the status box → [Motors won't power on](motors-wont-power-on.md)

**Next:** [Maintenance & recovery](index.md)
