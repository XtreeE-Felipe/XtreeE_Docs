---
type: guide
stage: toolpath-design
role: designer
frequency: per-version
---

<!-- PLACEHOLDER CONTENT - verify against product -->

# Export an xObject with traceable metadata

*designer*{ .badge .role } *per version*{ .badge .freq }

The export is the end of your work and the start of the print preparer's. What
leaves Grasshopper here is the only thing they will ever see, so everything they
need has to be inside it.

## Before you start

- A toolpath you have already [inspected](inspect-a-toolpath-before-export.md) —
  no self-intersections, no unreachable segments.
- The [`xEncoder`](../../products/grasshopper-plugin.md) component wired and
  producing an xObject on its output.
- A naming convention agreed with whoever prepares programs. If there isn't one,
  agree it now; this is the field they search on.

!!! info "XtreeE v4+ only"
    Variable flow rate and variable admixture proportion are written into the
    xObject as per-point values. On pre-v4 hardware they are ignored at print
    time and the whole path runs at the program's constant flow, so exporting
    variable values against a v3 cell will silently print something other than
    what you simulated.

## You'll produce

An **xObject (`.json`)**, version-stamped, ready to file for Stage 2.

## Steps

1. Connect your encoded toolpath to the `xExporter` component.
2. Set **Name** to the piece identifier, not the Rhino file name. This is what
   appears in [XtreeE Slice](../../products/slice.md)'s import list.
3. Set **Version** explicitly. Increment it on every export — never overwrite a
   previous file, and never re-export the same number with different geometry.
4. Fill the metadata inputs: author, source geometry reference, date, and the
   target print base identifier if you already know it.
5. Check the reported point count and total path length against what
   [`xViewer`](../../products/grasshopper-plugin.md) showed you. A mismatch means
   you exported a different branch than the one you inspected.
6. Toggle **Export** and choose the destination folder.
7. Open the file once and confirm the header block carries the name, version and
   author you set. See [Read back what an xObject contains](read-back-what-an-xobject-contains.md).

!!! warning "An xObject is a transmission format, not an editable file"
    It encapsulates a **finished** toolpath. No guide in this set tells anyone to
    edit one, and no downstream tool offers to. If something is wrong, you revise
    the toolpath here, in the tool that produced it, and
    [export a new version](revise-a-toolpath-and-export-a-new-version.md).
    Reading an xObject back is inspection — never a way in.

    This is what makes the hand-off safe: the print preparer can be certain the
    file they hold corresponds to a design someone signed off on, because there
    is no path by which it could have been changed in transit.

## Done when

A version-stamped `.json` exists in the agreed location, opens without error,
and its header block reports the name, version and author you intended.

## If it goes wrong

- Export produces a file but Slice won't import it →
  [Real flow doesn't match assigned flow](../maintenance/real-flow-doesnt-match-assigned-flow.md)
  is *not* your problem; check the version and point count first, then re-export.
- The geometry in the file isn't the geometry you inspected → you have more than
  one live branch in the definition. Go back to
  [Inspect a toolpath before export](inspect-a-toolpath-before-export.md).

## Next

[Revise a toolpath and export a new version](revise-a-toolpath-and-export-a-new-version.md)

**Related:** [The xObject](../../wiki/the-xobject.md) explains why the format is
closed · [Grasshopper plugin](../../products/grasshopper-plugin.md) enumerates
every component input.
