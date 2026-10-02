# Round 18 — Merle to Macindoe

*Housekeeping in the ledger, a public truthfulness pass on my side, and one text for your approval.
Business paragraphs only; this round is a pull request; the second key is the approving review, as
agreed in R11 §13.*

---

## 1. Rounds 16 and 17 merged; your two notes applied first.

Both pull requests were merged on 2026-10-02 (`bb1510e`, `474125d`), after a pre-merge commit on
round 16 (`2dbb364`) that applies the two notes of your review: the negative control's clause now says
that `R/n ≤ 0.5727` is the ratio needed to reach `q₂₂` — one convergent short of Hercher's own `q₂₃` —
and not Hercher's bound; and the `56 / 233,324` class count in the breach map is recorded as a gap,
unreproduced, not to be cited. The earlier wording in the header of `T1Structure.lean` is named and
superseded in place; the Lean file itself is untouched, so no key moves.

## 2. Two ledger lines that were behind the record.

- **L-A10 carries two keys.** Your approving review of PR #4 (2026-09-12) says "The second key turns on
  L-A10."; the entry's `Key status` line still read "one key (Merle)". Amended in place, nothing else in
  the entry changed.
- **A reading note at the head of the ledger**: an entry's status is its last `Key status` line. Five
  entries (L-A4, L-A6, L-A7, L-A8, L-A9) still open with the `DRAFT — one key` line of their first
  version; I kept those lines as written rather than rewrite history.

## 3. A truthfulness pass on my public pages (for information; nothing of yours is touched).

An audit of everything I publish found statements that are not true as written, all on my side:

- **collatz-lab.org, v0.9.0** (2026-10-02): an erratum to the site's headline. The conditional
  no-cycle theorem of my April paper is circular for long cycles — its third hypothesis,
  `DerivedLargeKBound`, is assumed, not derived, and with Bařina's verification it already amounts to
  the conclusion for `k > 1322`; what stands as published is "no non-trivial cycle with `k ≤ 1322`,
  under the two other hypotheses". Also corrected: Salikhov's 5.125 is a measure of `ln 3` (your
  catch, L-A7); Christian Hercher's theorem is about `m ≤ 91`; the main theorem was checked on Lean
  4.27.0 and has not been re-checked since lean4#14576 (unlike the six files of our stack).
- **Six public repositories** of mine now carry an erratum at the top of their README and a corrected
  description; among them, an axiom of my old Junction skeleton (`simons_de_weger`) is false as
  written (the trivial cycle satisfies what it negates), so the two theorems built on it establish
  nothing. History, Lean files and deposited papers are left unchanged. `one-obstruction-three-faces-lean`
  only gained a status line, the kernel-version note, a working build command, and corrected notes in
  `rounds/` and `experiments/` (no Lean file changed).

The site's previous collaboration paragraph said nothing false about our work, but it stopped at L-A1.
It now names you as an open collaborator with a link to this repository, and cites your preprint's v3.

## 4. For your approval: the collaboration block.

`briefs/merle-site-collaboration-block.md` is the text I propose to put on the site about our work:
the established entries with their attributions, the two records of rounds 16–17, and the sentence
that none of it crosses the published bounds. **It goes online only with your approving review**, and
with whatever you change. Four open points close the brief: Gersonides' year (the page now says
"1342/43"), which DOI of your preprint you prefer, how you would like to be named on the site, and any
entry you would word differently.

One small thing on the record: we both write "PROTOCOL §13" for the pull-request rule, but
`PROTOCOL.md` has no §13 — the rule was proposed in R11 §13 and accepted. I can add it to
`PROTOCOL.md` in a later round if you agree; until then this letter cites R11 §13.

*Eric Merle*
