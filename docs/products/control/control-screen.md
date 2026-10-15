---
type: product
---

# Control screen

The **CONTROL** page is the main page of [XtreeE Control](index.md). Each motor
is controlled independently, with the shared
[motor control panel](index.md#motor-control-panel). Three sub-pages set how the
motors are controlled — by speed, by flow or by proportion — and a
**Maintenance** window jogs the motors.

During a print, this page is replaced by [Printing control](printing-control.md).

## Speed control

Each motor is controlled by its output speed, before reduction. This mode does
not depend on any flow, which makes it useful when monitoring motor health.

*[Screenshot: Control — speed sub-page]*
<!-- IMAGE: Controlspeed.png -->

## Flow control

Each motor is controlled by its effective value:

- a flow rate for a pump;
- a rotation speed for the HM mixer — the speed of the mixer, after reduction.

The motor speed is shown on the left of the control panel.

*[Screenshot: Control — flow sub-page]*
<!-- IMAGE: Controlflows.png -->

## Proportion control

The same as flow control, except that admixture pumps are controlled in
proportion to concrete: the AD pumps accelerate when the concrete flow rate is
increased.

*[Screenshot: Control — proportion sub-page]*
<!-- IMAGE: Controlproportions.png -->

## Maintenance

A service operation, for when a motor needs to be jogged by 1/6 of a rotation.
All motors must be stopped before the window is opened.

- the maintenance button opens the window;
- one control rotates the motor clockwise;
- one control rotates the motor counter-clockwise.

Motors can be run normally again once the window is closed.

*[Screenshot: Maintenance window]*
<!-- IMAGE: image 7.png -->

<!-- TODO: needs source — when a 1/6-rotation jog is needed -->
