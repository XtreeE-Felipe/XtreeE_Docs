---
type: product
---

# Printing control

In printing mode, the motors of [XtreeE Control](index.md) are controlled
automatically, but manual adjustments are still possible. This page replaces
**CONTROL** in the top bar — see [Page buttons](index.md#page-buttons).

Three sub-pages hold the adjustments:

| Sub-page | Adjusts |
|---|---|
| [Flows](#flows) | the material |
| [Width](#width) | the layer geometry |
| [Performance](#performance) | the global printing speed, without changing the material or the extruded layer |

Every sub-page also lets you:

- pause — **GO TO MAINTENANCE**, see [Initialization / Pause](#initialization-pause);
- turn each motor on or off;
- see the [usage rate](#usage-rate) of each motor;
- read the [program data](#program-data).

The HM motor control panel is available on every sub-page, as it is
independent.

On systems with the SPRINT option, AUTO mode cannot be disabled during printing —
only during a pause. See [SPRINT option](index.md#sprint-option-auto-mode-for-pump-cf).

*[Screenshot: printing control]*
<!-- IMAGE: image 8.png -->

## Usage rate

Shows how much the global performance could change. Each motor is a horizontal
bar:

| Mark | Shows |
|---|---|
| Grey rectangle | the extremum values of the motor |
| Triangle | the live value |
| Line | the nominal value |
| Extra rectangle around the nominal value | only for a variable-flow program: the extremum values of the current program |

*[Screenshot: usage rate bars]*
<!-- IMAGE: image 9.png -->

## Program data

- Name of the object
- Current layer / total number of layers
- Current layer width
- Current layer height
- Live robot speed
- Time left
- Volume left to be printed
- Progress

*[Screenshot: program data]*
<!-- IMAGE: image 10.png -->

## Flows

Admixture proportion is controlled by a percentage on each AD pump.

*[Screenshot: printing control — flows sub-page]*
<!-- IMAGE: printflows.png -->

## Width

Layer width is a direct result of the ratio between material flow rate and robot
speed. This sub-page takes:

| Field | What it does |
|---|---|
| Width correction | The correction, in mm. Can be negative. |
| Machine selection | Whether the robot or the pump absorbs the change. |

The admixture proportion is fixed here, so a change in concrete flow induces a
change in the activated AD pumps. Watch the [usage rates](#usage-rate) on
the left.

*[Screenshot: printing control — width sub-page]*
<!-- IMAGE: image 11.png -->

## Performance

Accelerates or decelerates the global process without changing the material or
the extruded layer: a change in the performance factor changes every motor.
Watch the [usage rates](#usage-rate) on the left.

*[Screenshot: printing control — performance sub-page]*
<!-- IMAGE: printfperf.png -->

## Initialization / Pause

This page appears in the initialization phase, to prepare for the print, and
when a program is paused.

Each motor is controlled one by one, as on the [Control screen](control-screen.md).
The difference is that a program is loaded, with its pointer at the start
(initialization) or somewhere in the middle (pause). Each component shows a
target: the next values applied in automatic printing mode.

On systems with the SPRINT option, AUTO mode is activated automatically if it was
not, but it can still be disabled here.

The buttons to the next step are at the bottom right of the screen:

| Phase | Buttons |
|---|---|
| Initialization | **START** |
| Pause | **CONTINUE**, **QUIT** |

*[Screenshot: initialization page]*
<!-- IMAGE: Printing_Calibration.png -->

*[Screenshot: pause page]*
<!-- IMAGE: Printing_Maintenance.png -->
