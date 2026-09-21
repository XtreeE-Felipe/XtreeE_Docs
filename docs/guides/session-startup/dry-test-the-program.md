---
type: guide
stage: session-startup
role: cell-operator
frequency: per-session
---

<!-- PLACEHOLDER CONTENT - verify against product -->

# Dry-test the program

*cell operator*{ .badge .role } *per session*{ .badge .freq }

The last thing that happens before the cell is cleared to print. The robot runs
the whole path with the pump off, at reduced speed, so that collisions and
unreachable poses surface now rather than into a live batch.

## Before you start

- The program [loaded on the pendant](load-the-program-on-the-flexpendant.md)
  and [tool calibration checked](check-tool-calibration.md).
- [Motors reset](reset-the-motors.md) and the cell clear of people and tooling.
- The print base in place and empty. A dry test over a base that still has
  yesterday's object on it tells you nothing.
- Pump **off** and material line disconnected or purged.

## You'll produce

A program confirmed reachable end to end — the last input the
[session-open gate](session-open-motors-on-material-ready-files-loaded.md) needs.

## Steps

1. Confirm the pump is off and the head carries no material.
2. Select the program's main module and move the program pointer to `main`.
3. Set speed override to **25 %**.

=== "ABB"

    4. Put the controller in **Manual** mode with the key switch, and hold the
       three-position enabling device.
    5. On the FlexPendant, press and hold **Start**. Step through the first
       layer and watch the wrist orientation at the path's tightest corners.
    6. Switch to **Auto**, confirm the mode change on the pendant, then run the
       full path at 25 %.
    7. Watch the pendant for `50056 Joint collision` and
       `50024 Corner path failure`. Either one stops the test — see
       [Axes lost their reference](../maintenance/axes-lost-their-reference.md).

=== "Other"

    4. Put the controller into its manual/teach mode and run the first layer
       under the enabling device, watching wrist orientation at the tightest
       corners.
    5. Return to automatic mode and run the full path at 25 %.
    6. Watch the controller log for reach, singularity and collision faults.
       Names differ by brand; anything that halts motion halts the test.

8. Restore speed override to 100 % only after the path has completed once.
9. Record the dry-test result in the session log as you
   [open the session](session-open-motors-on-material-ready-files-loaded.md).

!!! warning "A dry test is not a rehearsal of the print"
    It proves the robot can *reach* every point. It proves nothing about flow,
    layer adhesion or early-age stability, because no material moved. Do not
    treat a clean dry test as permission to skip the
    [pre-print check](../printing-operation/pre-print-check.md).

## Done when

The full path has run once, end to end, at reduced speed, with no fault on the
controller and no operator intervention — and the head never came closer to the
base or the enclosure than you were comfortable with.

## If it goes wrong

- Motion halts at the same point every pass →
  [Axes lost their reference](../maintenance/axes-lost-their-reference.md)
- The path runs but the head is visibly off the base →
  [The head prints off-target](../maintenance/the-head-prints-off-target.md)
- Motors drop out during the run →
  [Motors won't power on](../maintenance/motors-wont-power-on.md)

A dry test that fails on geometry rather than on the cell is a Stage 2 problem.
Send the program back to the preparer; do not fix a toolpath at the pendant.

## Next

[Session open — motors on, material ready, files loaded](session-open-motors-on-material-ready-files-loaded.md)
