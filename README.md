# XtreeE_Docs — structural prototype

A working MkDocs + Material site built to test **one thing**: whether the
production-chain structure holds up when every page actually exists.

**The content is placeholder.** Three guides are written properly; everything
else is a template stub that is honest about being one. Judge the structure, not
the prose.

## What's here

Four top-level sections:

| Section | Answers | State |
|---|---|---|
| **Cell Installation** | How do I get a cell ready to print with | 7 pages, stubbed |
| **Guides** | How do I do X (in production) | Built in full — 53 pages across 6 sets |
| **Wiki** | Why does it work this way | Stubbed, except the *session* glossary entry |
| **Products** | What does this field do | Stubbed — 5 pages |

The Guides are a **relay**: five numbered stages, one operator role each, one
named artefact handed across every boundary, plus *Maintenance & recovery*
beside it, indexed by symptom. *Cell Installation* is its own section, before the chain.

### The three written guides

- `docs/guides/toolpath-design/export-an-xobject-with-traceable-metadata.md` —
  the xObject-is-immutable rule, links out to both a Wiki and a Product page
- `docs/guides/session-startup/dry-test-the-program.md` —
  content tabs for ABB vs other controllers, sits just before the session-open gate
- `docs/guides/printing-operation/adjust-layer-width.md` —
  parameter limits pulled in by snippet include, plus a warning admonition

Any page carrying `<!-- PLACEHOLDER CONTENT - verify against product -->` has
invented specifics in it. That includes the three written ones — the structure
is real, the UI details need checking against the software.

## Run it locally

```bash
pip install -r requirements.txt
mkdocs serve
```

Then open <http://127.0.0.1:8000>.

```bash
mkdocs build --strict   # must pass with no warnings
```

`--strict` is the review gate: it fails on a broken internal link or a page
missing from the nav, which is exactly the drift this structure is trying to
prevent.

## Conventions the repo enforces

1. **Nav is explicit in `mkdocs.yml`** — never alphabetical, never
   `awesome-pages`. The order *is* the argument and must be reviewable in a diff.
2. **No numbers in slugs or folder names.** Stages get renamed; URLs shouldn't
   break. Order lives in the nav.
3. **Every parameter limit lives in `docs/snippets/parameter-limits.md`** and is
   included wherever it's mentioned. Nothing is restated in prose.
4. **Front-matter carries `type`, `stage`, `role`, `frequency`** — metadata only
   for now (rendering them would need a theme override, out of scope), but
   lintable in CI and the basis of the badges.
5. **Guides link out, never re-explain** — Wiki for *why*, Products for
   *what each field does*.
6. **"Session" always links to `wiki/glossary/session.md`.**
7. **Gates are self-checks** — nothing signed, nothing filed.
8. **Stage landing pages are contracts**, not tables of contents: role, inputs,
   outputs, then the ordered guide list.

## Layout

```
docs/
  index.md
  cell-installation/       # before the chain — install, commission, configure
    software/              # per workstation
    printing-cell/         # per cell, device, base
  guides/
    index.md               # the whole chain
    toolpath-design/       # 1 · designer
    program-preparation/   # 2 · print preparer
    session-startup/       # 3 · cell operator + material operator (two lanes)
    printing-operation/    # 4 · print operator
    session-report/        # 5 · production lead
    maintenance/           # beside the chain, by symptom
  wiki/
  products/
  snippets/                # include source, excluded from the build as pages
  stylesheets/extra.css    # badge and two-lane styling
mkdocs.yml
requirements.txt
.github/workflows/docs.yml
```
