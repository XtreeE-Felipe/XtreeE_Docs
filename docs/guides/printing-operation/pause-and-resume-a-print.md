---
type: guide
stage: printing-operation
role: print-operator
frequency: as needed
---

# Pause and resume a print

*print operator*{ .badge .role } *as needed*{ .badge .freq }

A pause stops automatic printing without losing your place: the program stays
loaded with its pointer where the print stopped, and you can control each motor
one by one before carrying on. See the
[Pause](../../products/control/printing-control.md#initialization-pause) page
reference.

## Pause

On any Printing control sub-page, click **GO TO MAINTENANCE**. The printing
button in the top bar turns orange.

<!-- TODO: needs source — confirm GO TO MAINTENANCE is the pause control, and what the pause does to the robot -->

## While paused

Control each motor as needed. Each component shows its target — the values
applied as soon as automatic printing resumes.

On a system with the SPRINT option, AUTO mode for pump CF switches on
automatically if it was off. You can switch it off here, which is not possible
while printing.

## Resume or quit

At the bottom right of the screen, click **CONTINUE** to resume. The printing
button turns green again.

Click **QUIT** to leave the program instead.

<!-- TODO: needs source — what QUIT does to the program and the print -->

!!! tip "If something goes wrong"
    **ERRORS** in the status box → [A motor reports an error code](../maintenance/a-motor-reports-an-error-code.md)<br>
    **NO ERRORS - POWER OFF** → [Motors won't power on](../maintenance/motors-wont-power-on.md)

**Next:** [Stage 5 · Session report](../session-report/index.md)
