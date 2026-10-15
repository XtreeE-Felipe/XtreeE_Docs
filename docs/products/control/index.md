---
type: product
---

# XtreeE Control

XtreeE Control is the HMI of the printing cell. It runs on **HMWin**, HMI
software published by Panasonic, and is opened on a computer with **HMWin
Client**. Installing and connecting it is covered in
[Install and connect XtreeE Control](../../cell-installation/software/install-and-connect-xtreee-control.md).

- [HMWin product page (Panasonic)](https://industry.panasonic.eu/products/automation-devices-solutions/human-machine-interfaces/hmi-programming-software/programming-software-hm-series-hmwin)

This page describes what every screen shares: the home screen, the top bar, the
status box and the motor control panel. Each page then has its own reference:

| Page | Used to | Reference |
|---|---|---|
| **CONTROL** | control the different motors — the main page | [Control screen](control-screen.md) |
| *(printing mode)* | control the motors automatically during a print, with manual adjustments | [Printing control](printing-control.md) |
| **SETTINGS** | define the equipment and its references | [Settings](settings.md) |
| **INK** | log material data | [Ink](ink.md) |
| **DATA** | monitor the system | [Data](data.md) |

## Home screen

When HMWin Client opens, it loads automatically and displays the home screen,
which gives access to the four pages **CONTROL**, **SETTINGS**, **INK** and
**DATA**.

*[Screenshot: home screen]*
<!-- IMAGE: Control_HomeScreen.png -->

## Top bar

Every page has the same top bar:

- on the left, the navigation between pages;
- in the white box, the status of the system.

*[Screenshot: top bar]*
<!-- IMAGE: Control_TopBar.png -->

### Page buttons

The buttons match the four pages of the home screen and are available at all
times.

In printing mode, an additional button replaces **CONTROL** and leads to
[Printing control](printing-control.md). The mode is loaded automatically during
the process. The button has two colours:

| Colour | Meaning |
|---|---|
| Orange | printing standby — during initialization and pause |
| Green | actual printing |

*[Screenshot: printing-mode button in the top bar]*
<!-- IMAGE: Control_Top_PrintingMode.png -->

<!-- TODO: needs source — "How to print an object ?" page referenced by the source for the full printing process -->

### Status box

The white box shows one of three statuses:

| Status | Meaning |
|---|---|
| **NO ERRORS - POWER OFF** | Motors are not powered. They need to be reset. |
| **NO ERRORS - POWER ON** | Motors are powered and ready to rotate. |
| **ERRORS** | Motors are powered but at least one of them has an error. |

<!-- TODO: needs source — "How to reset the motors ?" procedure referenced for NO ERRORS - POWER OFF -->

In case of errors, the **INFO** button gives the error code of each motor. `0`
means no error.

*[Screenshot: status box with INFO button]*
<!-- IMAGE: XtreeE_Status.png -->

*[Screenshot: motor error codes]*
<!-- IMAGE: Control_ErrorCodes.png -->

<!-- TODO: needs source — meaning of each non-zero motor error code -->

The white box also shows a message when an action does not work. **CLEAR**
deletes the message.

*[Screenshot: message in the status box]*
<!-- IMAGE: Control_JogErrorToClear.png -->

## Motor control panel

Every controlled motor has the same control panel:

| Element | What it does |
|---|---|
| Value to assign | Click inside the box to type the value with a keyboard. The box is framed in red for an idle motor, green for a rotating one. |
| **+** / **−** | Change the assigned value by increments. |
| Power button | Activates rotation, or not. |
| Pump flow update | Only on a motor driving a pump. Opens the [pump flow update](#pump-flow-update) window. |
| Usage rate | An orange bar showing how much the motor is used compared with its extremum values. |
| Converted additional values | The assigned value, expressed in another unit. |
| Torque rate | The "effort". `100%` means the rated torque is reached. |

*[Screenshot: motor control panel]*
<!-- IMAGE: Control_MotorControlPanel.png -->

The keyboard used to type a value:

*[Screenshot: on-screen keyboard]*
<!-- IMAGE: Control_OnScreenKeyboard.png -->

## Pump flow update

Recalibrates a pump when the real flow does not match the assigned flow. The
procedure is in
[Real flow doesn't match assigned flow](../../guides/maintenance/real-flow-doesnt-match-assigned-flow.md).

| Field | What it does |
|---|---|
| Date of last flow update | Erased in case of a deep reboot of the PLC (for example, a program update). |
| Flow target | The value assigned when the window was opened. Cannot be changed. |
| Flow measure | The real flow observed. This is the field you write in. |
| **YES** | Applies the update, based on the measure entered. |
| **NO** | Quits without updating; the previous flow is kept. |
| **BACK TO FACTORY** | Resets the value to the one defined in factory. |

*[Screenshot: pump flow update window]*
<!-- IMAGE: Control_FlowRateUpdateWindow.png -->

## SPRINT option: AUTO mode for pump CF

Pump CF is located inside the xFEED. It is the main pump, where the flow rate is
controlled — except on systems with the **SPRINT** option.

With the SPRINT option, a second pump, pump CD, drives the flow rate. Pump CF
then feeds the printhead and adjusts automatically to regulate the inlet
pressure. The **AUTO** mode button on its control panel does exactly that: the
pump starts, stops and changes speed automatically. Clicking **AUTO** enables or
disables control from the panel.

*[Screenshot: pump CF panel with AUTO button]*
<!-- IMAGE: Control_AUTOButton.png -->

*[Screenshot: AUTO mode on]*
<!-- IMAGE: Control_AUTOModeON.png -->

During a print, AUTO mode cannot be disabled — only during a pause. See
[Printing control](printing-control.md#initialization-pause).
