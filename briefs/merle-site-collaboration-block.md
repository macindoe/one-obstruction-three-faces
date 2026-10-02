# Proposed public text — the collaboration block on collatz-lab.org (draft for your approval)

*Merle, 2026-10-02, round 18. Nothing below is on the site. Per PROTOCOL §7 (publication by common
agreement), this block goes online only after your approving review, with every amendment you make.
Attributions follow each entry's own header and its last `Key status` line in `LEDGER.md` at `main`;
where I was unsure, I wrote less. The site would show it in English and French, same content.*

---

## Collaboration Macindoe–Merle (state at 2026-10-02)

Since July 2026, Benjamin Macindoe (independent researcher; *Reduced coordinates for the Collatz map*,
v3, DOI [10.5281/zenodo.21730505](https://doi.org/10.5281/zenodo.21730505)) and Eric Merle keep a
public **two-key** claims ledger: each statement is checked independently on both sides, in fresh code
that borrows nothing from the other side (a Lean kernel key on Merle's side for the formalised entries).
Errors are not deleted: each correction names who erred and who corrected.
Repository: [macindoe/one-obstruction-three-faces](https://github.com/macindoe/one-obstruction-three-faces)
(`LEDGER.md`, joint working note `NOTE-v1.md` — a working note, not a publication).

**Established (two keys)**

- **The p = 22 Diophantine pincer** (L1; Merle's proposal; each side refuted one claim of the other;
  status *corrected*).
- **The p = 7 instance** (L2; Macindoe's staircase; Merle's key in fresh code) and **the spectrum of the
  class chain** (L4; Merle; cross-checked on both sides; measured grade).
- **Local failure at a prime of q, no Hasse gap** (L3; Merle's proposal, re-run and refined by Macindoe;
  corrected by Merle on 2026-07-24, Macindoe's key on the correction).
- **Transport recurrence** (L-A1; simultaneous independent discovery; Lean: Merle): the p divisibility
  conditions of a cycle reduce to one.
- **Repeated-words law** (L-A2; Merle's proposal, its elementary cause closed by Macindoe) and
  **descent** (L-A4; Merle's statement, Macindoe's multiplicative identity; Lean: Merle): a new cycle,
  if any, is primitive.
- **Anchored loops and the Benford side-asymmetry** (L-A3; Macindoe's candidate; margin quantified by
  Merle).
- **Separation lemma** (L-A5; Merle, Lean; framework and final gloss: Macindoe). It does not prove "the
  wall": the cycle −17 realises an isolated peak.
- **Exact census for n ≤ 14** (L-A6; Merle; completed by Macindoe, who proved the phantom identity).
- **Margin inequality, proved twice** (L-A7): in the Lean kernel with constant 1/13 (Merle), on paper
  with the exact constant (Macindoe).
- **T1** (L-A8; Lean: Merle; the missing half found by Macindoe): no positive cycle with least element
  ≥ 2⁷¹ and length ≤ 4.95·10¹⁰ (direct route, round 16). **This is weaker than Hercher 2023**
  (1.375·10¹¹); its value is that it is machine-checked, not its reach. Kernel statements read, not built,
  on Macindoe's side; two continued-fraction facts and one cancellation remain in prose.
- **δ8, Dirichlet half** (L-A9; Merle; convention corrected by Macindoe): the Product-Bound route is
  closed by Dirichlet's strict inequality, with a margin of about 0.04 in the exponent. The other half
  is measured only.
- **No altitude computed on a finite quotient decreases** (L-A10; Merle; not formalised).
- **The Sturmian word** (L-A11; Merle; reformulation by Macindoe): the balanced cycle is excluded by
  Knight's theorem (*Discrete Math.* 349 (2026), 114812) combined with L-A2.

**Records**

- Every Lean key of the ledger was re-checked on a patched kernel (Lean 4.34.0, after
  [lean4#14576](https://github.com/leanprover/lean4/issues/14576)): 40 declarations, standard axioms only
  (round 16).
- Round 17 corrected our own round-14 retraction: the phantom census at p = 7, k = 8 stands, exhaustive
  for L ≤ 11.

**What none of this does:** exclude a cycle beyond the published bounds (Bařina's verification to 2⁷¹;
Hercher 2023). The ledger locates the obstruction; it does not cross it.

---

## Open points for your review

1. **Gersonides' year.** The `/cycles/` page now says "1342/43" (sources differ). Which do you prefer,
   from your reading of *De numeris harmonicis*?
2. **Your preprint's DOI.** The site now cites v3 (`21730505`). Would you rather it cite the concept DOI
   (`21273547`), which always resolves to your latest version?
3. **Team section.** The site names you as an open collaborator with a link to this repository. Tell me
   if you would like that worded differently, or removed.
4. Any entry above you would word differently, or leave out.
