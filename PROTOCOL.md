# Collaboration protocol — DRAFT for co-editing

*This is one side's opening draft (Macindoe, 2026-07-17), assembled from the terms already agreed in correspondence. Co-editing it is the collaboration's first exercise: edit directly, strike freely.*

## 1. The three-repo model

Each side's verification stack lives in its own repository and is never merged into the other's. This repository holds only: the note's text, this protocol, and the claims ledger. Independence of the stacks is itself the evidence the note reports.

## 2. The two-key rule

- Every numbered claim in the note passes at least one side's full verification bar.
- **Load-bearing claims pass both**: Lean kernel on one side, independent code on the other, neither derived from the other (clean-room: conventions re-derived from published text, not from the other side's source).
- A claim's ledger entry states which keys have turned, with links to the runnable artifact on each side.

## 3. The claims ledger

`LEDGER.md`, one entry per numbered claim: statement, status (`proposed` / `one key` / `two keys` / `refuted` / `corrected`), and the verification artifact per side (commit-pinned link, script name, what it checks). Refuted and corrected entries are kept, with what refuted them — on both sides, deletions are not how errors are handled.

**The regime column (Merle's proposal, round 12 §4(d); accepted by the author, second key = this pull request's approving review).** Beside the two keys, each entry records the regime it was discharged in; any claim asserting an equality additionally records a second regime chosen against it. Two round-12 errors — one on each side, in the same L-A8 block — were made and caught in exactly the regime the correspondence works in (Barina's threshold, the `2⁷¹` window, `q₂₁` through `q₂₃`), and would have passed both keys had the regime not changed; this column is the guardrail against exactly that.

## 4. Corrections

Disagreements between the stacks are recorded precisely, then resolved by computation, and the resolution names which side's record needed correcting (precedent: the p = 22 exchange corrected one claim on each side; ledger entry L1).

## 5. Register

Flat, calibrated prose. Heuristics labeled as heuristics; assessed ≠ proved; no claim passes into the note's text before its ledger entry says which keys turned.

## 6. Working conditions, disclosed

- Macindoe's side: research direction and standards of evidence are the author's; mathematical development is carried out with an AI collaborator under the documented protocol of the main repository (`AGENTS.md` there), and that includes contributions to this note and this correspondence.
- Merle's side: research direction and standards of evidence are the author's; the mathematical development is carried out with an AI collaborator (Claude) under the A.R.E.S. protocol (independent second key, zero bibliographic recall, every assertion traceable to a runnable check), and the Lean kernel is the final arbiter — a model cannot bluff a compiler. This includes contributions to this note and this correspondence. The Lean stack lives at `ericmerle3789/one-obstruction-three-faces-lean`.

## 7. Publication

The note publishes only when both sides agree; venue and licensing decided jointly. This repository starts private; making it public is proposed as the default once the protocol is agreed — **accepted (Merle, 2026-07-19; per the correspondence: "yes to the repo, yes to the protocol"). The repository is public.** Venue signal to date: three independent readings converge on a number-theory-shaped home with the formalization as supporting artifact.
