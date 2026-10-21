---
type: contract
stage: toolpath-design
---

# Stage 1 · Toolpath design

*designer*{ .badge .role }

The designer turns geometry into a printable toolpath and freezes it into an xObject. Nothing downstream edits that file — a change means revising the toolpath here and exporting a new version.

## The contract

| | |
|---|---|
| **Role** | designer |
| **Needs in hand** | geometry, or a preset from XtreeE Library |
| **Produces** | **an xObject (`.json`)** |
| **Session** | outside any session |

## The guides, in order

No guides are published for this stage yet.


## Then

[Stage 2 · Program preparation](../program-preparation/index.md)
