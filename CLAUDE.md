# CLAUDE.md

XtreeE Documentation — an MkDocs + Material site for robotic concrete 3D
printing. See `README.md` for structure and layout.

## Rule zero: never invent information

Every fact on a page must trace to an approved source. No exceptions for
"plausible", "typical" or "industry-standard" values.

- **Sources of truth** — only these two:
  - **Notion**, read through the Notion connector — these root pages and their
    descendants only:
    - **XtreeE Software** — <https://app.notion.com/p/1a0566d0114080cebc4be9006d786fc3>
    - **Guides** — <https://app.notion.com/p/304566d0114080ba989af566f9d1c9f9>
    - **XtreeE Library** — <https://app.notion.com/p/fa5a8371ddfa4c5fae866ba8ae1fce51>
    - **XtreeE Supervise** — <https://app.notion.com/p/99f6cf7053a44baf873fac7b571ba71a>
    - **XtreeE Simulate** — <https://app.notion.com/p/60d1c68d88f14713a6d19717770013ea>

    Confirm a page sits under one of these roots before citing it. Other Notion
    pages — even ones named after a product — are not sources.
  - **`_sources/`** (repo root): local-only — gitignored and outside `docs/`, so
    MkDocs never reads it. Never copy source files into `docs/` or commit them —
    **except images** (see below).
- **Conflicts:** when Notion and `_sources/` disagree, Notion wins. Mention the
  conflict in the report.
- **Signed-off pages:** `docs/snippets/parameter-limits.md` was verified against
  the real application by the product owner on 2026-10-12 and counts as a
  source. Change its values only from a newer source.
- **Images:** screenshots and figures from `_sources/` may be copied into
  `docs/assets/<product>/` (e.g. `docs/assets/control/`) and committed. Until an
  image is copied, mark its place with a visible text placeholder followed by a
  comment naming the source file:

  ```markdown
  *[Screenshot: <what it shows>]*
  <!-- IMAGE: <source file name> -->
  ```
- **Facts that need a source:** UI labels, button and menu names, parameter
  names, ranges and defaults, error codes, controller/robot behaviour, speeds,
  percentages, durations, material values, file formats, product capabilities.
  Use the source's exact wording for names, labels and codes.
- **Not sources:** your general knowledge, other vendors' docs, the web, and any
  page in `docs/` carrying `<!-- PLACEHOLDER CONTENT - verify against product -->`.
  Placeholder pages are unverified — never copy their specifics (e.g. error
  codes, speed overrides) into another page or treat them as confirmation.
- **When the source doesn't have it:** stop and ask. If it stays unresolved,
  leave a visible marker instead of content and move on:
  `<!-- TODO: needs source — <what is missing> -->`
  Never fill the gap with a guess, an example value, or vague filler that hides
  the gap.
- **The PLACEHOLDER marker means invented content.** No page may carry it:
  delete placeholder pages rather than publish them. A page whose facts are all
  sourced but which still has open TODOs is *incomplete*, not a placeholder —
  it is published with its TODOs visible.
- **Write only what is sourced.** A page exists only once a source backs its
  core; gaps inside it are TODOs. Stage landing pages list only guides that
  exist.
- **Report:** after editing, list the source backing each new fact (Notion page
  title + URL, or `_sources/` file path) and every TODO left behind.
- Structure, headings, links and wording of instructions are yours to write;
  facts are not.

## Conventions (binding)

1. **Nav is explicit in `mkdocs.yml`.** Every new page gets a nav entry, in
   order. Never alphabetical, never `awesome-pages`.
2. **No numbers in slugs or folder names.** Order lives in the nav only.
3. **Parameter limits live only in `docs/snippets/parameter-limits.md`**,
   included with `pymdownx.snippets` wherever mentioned. Never restated in prose.
4. **Front-matter carries `type`, `stage`, `role`, `frequency`.**
5. **Guides link out, never re-explain** — Wiki for *why*, Products for *what
   each field does*.
6. **"Session" always links to `wiki/glossary/session.md`.**
7. **Gates are self-checks** — nothing signed, nothing filed.
8. **Stage landing pages are contracts**, not tables of contents: role, inputs,
   outputs, then the ordered guide list.

### Front-matter values

Use only values already in use:

- `type`: `guide`, `contract`, `gate`, `wiki`, `product`, `home`
- `stage`: `cell-installation`, `toolpath-design`, `program-preparation`,
  `session-startup`, `printing-operation`, `session-report`, `maintenance`
- `role`: `designer`, `print-preparer`, `cell-operator`, `material-operator`,
  `print-operator`, `production-lead`, `integrator`
- `frequency`: lowercase with spaces, e.g. `per session`, `per object`,
  `as needed`, `on symptom`, `once`

Ask before introducing a new value.

## Guide page template

A guide reads as a short piece of prose with steps in it, not a form. Every
guide carries the same **five beats, in this order** — but only the body may
use headings.

```markdown
---
type: guide
stage: <stage>
role: <role>
frequency: <frequency>
---

# <Imperative title>

*<role in words>*{ .badge .role } *<frequency>*{ .badge .freq }

<Opening: what this does, when you need it, what you need first.>

<Body: one numbered list, or ## sections named after the phases.>

<End state: one sentence the reader can check.>

!!! tip "If something goes wrong"
    <symptom> → [<maintenance page>](...)

**Next:** [<following page in the nav>](...)
```

1. **Opening** — one paragraph, at most three sentences: what the guide does,
   when you need it, and what must be in hand first (artefacts, access, cell
   state, earlier guides) — all linked, never restated. Name the hand-off here
   if the guide produces one. No `Before you start` / `You'll produce` headings.
2. **Body** — the steps, imperative.
   - **One phase:** a single numbered list, no heading.
   - **Several phases** (e.g. pause → while paused → resume): one `##` section
     per phase, titled with a short noun or verb phrase. Inside, a numbered list
     or one or two sentences — whichever is shorter.
   - Controller-specific steps go in content tabs (`=== "ABB"`).
   - Parameter limits: a `## Parameter limits` section with the snippet include.
3. **End state** — one sentence, placed right after the step that reaches it,
   naming something the reader can see or measure ("The motors are ready once
   the status box reads **NO ERRORS - POWER ON**."). No `Done when` heading. If
   no such sentence can be written, the page belongs in the Wiki or Products.
4. **If something goes wrong** — optional. Only when there is a Maintenance page
   to link: a `!!! tip "If something goes wrong"` box, one `symptom → link`
   line per symptom, at the end of the body. Never an empty section.
5. **Next** — always the last line: `**Next:** [<page>](...)`, the following
   page in the nav (or the next stage landing page).

Admonitions, sparingly:

- `!!! warning` — a consequence the reader must not miss, placed before the
  step it concerns.
- `!!! note` — a fact about the product the reader would otherwise trip on.
- `!!! tip "If something goes wrong"` — reserved for beat 4.

TODO markers sit where the missing content would go, inside the beat it
belongs to.

## Language and tone

- **UK English** spelling: *analyse, colour, behaviour, centre, artefact, metre*.
- Second person, imperative steps, short sentences.
- Product names in full: *XtreeE Slice, XtreeE Control, XtreeE Supervise,
  XtreeE Library*, the *Grasshopper plugin*.
- UI labels in **bold**, codes and identifiers in `backticks`, both exactly as
  in the source.

## Build gate

```bash
mkdocs build --strict
```

Must pass with no warnings before any change is considered done. It catches
broken internal links and pages missing from the nav.
