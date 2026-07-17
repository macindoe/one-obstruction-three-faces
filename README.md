# One obstruction, three faces

A joint technical-comparison note between two independent Collatz research programs:

- **Eric Merle** — conditional cycle exclusion, formalized in Lean 4 (Zenodo DOI [10.5281/zenodo.19790406](https://doi.org/10.5281/zenodo.19790406)); verification culture: the kernel, plus the A.R.E.S. protocol (independent second key, zero bibliographic recall, everything traceable to a runnable check).
- **Ben Macindoe** — the reduced-coordinates program (Zenodo DOIs [10.5281/zenodo.21273548](https://doi.org/10.5281/zenodo.21273548), [10.5281/zenodo.21303918](https://doi.org/10.5281/zenodo.21303918); full research record at [github.com/macindoe/collatz](https://github.com/macindoe/collatz)); verification culture: independent re-implementation before any claim is called proved, failures recorded rather than deleted, AI-assisted under a documented protocol.

**Scope of the note** (working title above is Merle's coinage, adopted): the δ8 impossibility and the staircase sharpness as one obstruction; what the anchor walk offers the conditional theorem; and the local-global specification of the missing mathematics — size as the archimedean shadow, the anchor walk as the 2-adic body, the integrality defect as the incompatibility between the places.

**Structure of the collaboration** (three-repo model): the two verification stacks are deliberately **not merged** — their independence is the evidence. This repository holds only the note's text and the claims ledger; every numbered claim maps to verification artifacts in each side's own repository. See `PROTOCOL.md` (draft, under co-editing) and `LEDGER.md`.

**Status**: protocol draft awaiting co-editing (the collaboration's first exercise); note not started.
