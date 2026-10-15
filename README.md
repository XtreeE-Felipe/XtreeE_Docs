# XtreeE_Docs

An MkDocs + Material site for robotic concrete 3D printing, organised as a
production chain.

**Content is source-only.** Every fact traces to a source in `_sources/`
(local-only, see `CLAUDE.md`). Pages are added as sources arrive; nothing is
published as a placeholder. Gaps inside a page are marked
`<!-- TODO: needs source — … -->`.

## What's here

Four top-level sections:

| Section | Answers | State |
|---|---|---|
| **Cell Installation** | How do I get a cell ready to print with | 2 guides |
| **Guides** | How do I do X (in production) | 11 guides; stages 1, 2 and 5 have none yet |
| **Wiki** | Why does it work this way | the *session* glossary entry |
| **Products** | What does this field do | XtreeE Control, 6 pages |

The Guides are a **relay**: five numbered stages, one operator role each, one
named artefact handed across every boundary, plus *Maintenance & recovery*
beside it, indexed by symptom. *Cell Installation* is its own section, before the chain.

Every landing page is kept, so the navigation structure stays fixed while pages
are filled in. Screenshots are marked with text placeholders until the images
are copied into `docs/assets/`.

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
    control/               # XtreeE Control, one page per screen
  assets/                  # logo and product screenshots
  snippets/                # include source, excluded from the build as pages
  stylesheets/extra.css    # badge and two-lane styling
mkdocs.yml
requirements.txt
.github/workflows/docs.yml
```
