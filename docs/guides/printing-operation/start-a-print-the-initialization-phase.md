---
type: guide
stage: printing-operation
role: print-operator
frequency: per object
---

# Start a print — the initialization phase

*print operator*{ .badge .role } *per object*{ .badge .freq }

Before automatic printing begins, XtreeE Control shows the
[Initialization](../../products/control/printing-control.md#initialization-pause)
page: the program is loaded with its pointer at the start, and you prepare each
motor for the print. You need an open [session](../../wiki/glossary/session.md)
and XtreeE Control in printing mode — the printing button in the top bar is
orange.

<!-- TODO: needs source — how to load a program and enter printing mode ("How to print an object ?" in XtreeE Control source) -->

1. Read the target of each component: the next values applied in automatic
   printing mode.
2. Control each motor one by one, as on the
   [Control screen](../../products/control/control-screen.md).

    <!-- TODO: needs source — what to prepare on each motor before START -->

3. On a system with the SPRINT option, AUTO mode for pump CF switches on
   automatically if it was off. You can still switch it off here.
4. Click **START**, at the bottom right of the screen.

The print has started once the printing button in the top bar turns green.

!!! tip "If something goes wrong"
    **NO ERRORS - POWER OFF** in the status box → [Motors won't power on](../maintenance/motors-wont-power-on.md)<br>
    **ERRORS** in the status box → [A motor reports an error code](../maintenance/a-motor-reports-an-error-code.md)

**Next:** [Read the printing screen — what to watch](read-the-printing-screen-what-to-watch.md)
