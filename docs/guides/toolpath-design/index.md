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

1. [Choose your design route — Library or Grasshopper](choose-your-design-route-library-or-grasshopper.md) — *per object*
1. [Configure a piece in XtreeE Library](configure-a-piece-in-xtreee-library.md) — *per object*
1. [Slice a surface in Grasshopper](slice-a-surface-in-grasshopper.md) — *per object*
1. [Encode a toolpath into an xObject](encode-a-toolpath-into-an-xobject.md) — *per object*
1. [Inspect a toolpath before export](inspect-a-toolpath-before-export.md) — *per version*
1. [Export an xObject with traceable metadata](export-an-xobject-with-traceable-metadata.md) — *per version*
1. [Revise a toolpath and export a new version](revise-a-toolpath-and-export-a-new-version.md) — *as needed*
1. [Read back what an xObject contains](read-back-what-an-xobject-contains.md) — *as needed*
1. [Hand-off check — is this toolpath printable?](hand-off-check-is-this-toolpath-printable.md) — *per object* · **gate**


## Then

[Stage 2 · Program preparation](../program-preparation/index.md)
