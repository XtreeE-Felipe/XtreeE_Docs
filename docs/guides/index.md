---
type: contract
---

# Guides — the production chain

A guide answers **how do I do X**. Nothing else: the *why* lives in the
[Wiki](../wiki/index.md), the *what does this field do* lives in the
[Product pages](../products/index.md).

The chain is a **relay**. Five numbered stages, one operator role each, and
**one named artefact crossing each boundary**. If you can name what you were
handed, you know which stage you are in.

## The chain

| Stage | Role | Needs | Produces | Session |
|---|---|---|---|---|
| [1 · Toolpath design](toolpath-design/index.md) | designer | geometry or a Library preset | **xObject (`.json`)** | — |
| [2 · Program preparation](program-preparation/index.md) | print preparer | xObject + a taught base | **printing program + material spec, filed into a store** | — |
| [3 · Session start-up](session-startup/index.md) | cell operator · material operator | a prepared program from the store | **a cell cleared to print** | **opens** |
| [4 · Printing operation](printing-operation/index.md) | print operator | a cell cleared to print | **printed objects + session log** | **closes** |
| [5 · Session report](session-report/index.md) | production lead | printed objects + session log | **report + archived session** | — |

Two boundaries in that table are not person-to-person, and it matters:

- **Stage 2 files into a store, not to a colleague.** Programs are typically
  prepared days ahead of the shift that uses them. Stage 3 begins by *choosing*
  one, not by receiving one.
- **Stage 3 runs in two lanes** — robot and material, two different operators —
  which rejoin at the moment the session opens.

## Where the session opens and closes

A [session](../wiki/glossary/session.md) is a printing shift. It **opens** at the
end of Stage 3, when all motors are started, the material is prepared and the
RAPID modules are loaded. It **closes** at the end of Stage 4, when printing has
finished — successful or not — the motors are off and the system is cleaned.

Both boundaries are machine-observable: motors on, motors off. Stages 1, 2 and 5
sit outside any session.

A session may print several objects, and an object may take several sessions.
Objects and sessions are **many-to-many**; batches sit under sessions, many to one.

## Before and beside the chain

The chain assumes a cell that has already been set up. Installation, commissioning
and one-off configuration live in their own section, [Cell Installation](../cell-installation/index.md) —
done once per installation, workstation, cell or print base, never once per
session. Forcing these into Stage 3 is the standard mistake: you cannot position
an object on a base in Stage 2 if teaching that base is a Stage 3 task.

### [Maintenance & recovery](maintenance/index.md)

**Beside** the chain. A fault interrupts whichever stage you were in, and it does
not announce which product owns it. So these pages are indexed **by symptom** —
what you are seeing, not what you were doing.

## What every guide page looks like

Every guide reads as short prose with steps in it, and always in the same order:

| Beat | Content |
|---|---|
| Opening | What the guide does, when you need it, what you need first — all linked. |
| Steps | Numbered and imperative. Longer guides split into one section per phase. |
| End state | One sentence you can check: how you know it worked. |
| If something goes wrong | Optional box linking into Maintenance & recovery, by symptom. |
| Next | The next guide in the chain — the site reads forward on its own. |

**Gates are self-checks.** Nothing is signed and nothing is filed; a gate exists
so one person can confirm the artefact they are about to hand on is complete.
