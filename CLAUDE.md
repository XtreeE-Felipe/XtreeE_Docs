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
    MkDocs never reads it. Never copy source files into `docs/` or commit them.
- **Conflicts:** when Notion and `_sources/` disagree, Notion wins. Mention the
  conflict in the report.
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
- **Removing the PLACEHOLDER marker:** only when every specific on the page has
  been replaced or confirmed from an approved source. A page with any open TODO
  keeps the marker.
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

```markdown
---
type: guide
stage: <stage>
role: <role>
frequency: <frequency>
---

# <Imperative title>

*<role in words>*{ .badge .role } *<frequency>*{ .badge .freq }

<One short paragraph: what this does and why it matters here.>

## Before you start
## You'll produce
## Steps
## Done when
## If it goes wrong
## Next
```

- **Before you start:** required artefacts, access and cell state — linked, never restated.
- **You'll produce:** the named output in one line (the hand-off).
- **Steps:** numbered, imperative. Controller-specific steps go in content tabs (`=== "ABB"`).
- **Done when:** a verifiable end state. If it can't be written, the page belongs in the Wiki or Products.
- **If it goes wrong:** links into Maintenance & recovery, by symptom.
- **Next:** link to the following page in the nav.

Use admonitions (`!!! warning`, `!!! note`) sparingly, for consequences the
reader must not miss.

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
