# Claims ledger

Status vocabulary: `proposed` / `one key` / `two keys` / `refuted` / `corrected`. Artifacts are commit-pinned where possible. Entries are append-mostly; corrections extend an entry rather than rewriting it.

---

## L1 — The p = 22 Diophantine pincer (Merle, correspondence 2026-07-16)

**Claim as proposed:** the `p = 22` failure of the staircase recipe is Diophantine, not combinatorial — the scale target `n ~ L^22` falls in the largest hole of the good-`n` grid (shadow of the partial quotient 23 of `log₂3`), in-scale candidates being too coarse and off-scale ones over budget, both beyond the correction algorithm's `≈ −3/−4` bit recovery threshold.

**Status: `corrected` (both directions), and productive — closed 2026-07-17.**
- Cause **confirmed**: the candidate chain has a genuine hole at that scale (`(16266, 31867)` committed chain; `(15601, 47468)` strict lemma grid — endpoints differ from the proposed `(15601, 31202)`; generator-definition comparison open).
- Recovery-threshold half **refuted at the proposer's own candidates**: `n = 25217` resolves in 13 correction moves, `n = 31202` in 8 — yielding verified `p = 22` size-passers (`γ/log₂22 = 2.508` and `3.307`) and a contiguous verified range `p ∈ {2,…,23}`.
- Macindoe-side prior claim ("the Diophantine choice of `n` was never the binding constraint") **refuted at `p = 22`** in the complementary direction; record corrected.
- All four of Merle's calibration measurements reproduce exactly in the Macindoe stack: `p=21, n=15601 → (3, −2.27)`; `p=22, n=25217 → (9, −7.86)`; `p=22, n=31202 → (6, −4.80)`; `p=23, n=47468 → (4, −3.77)`.

**Artifacts — Macindoe:** [`cycles.md` §12.8.6](https://github.com/macindoe/collatz/blob/28e578f/cycles.md) (resolved obstruction, extended record); `experiments/merle_pincer_check.py` (margins, calibration, distances); `experiments/p22_passer.py` (standalone certificate verification from the rotation identity alone); `briefs/merle-pincer-check-findings.md` (full diagnostic record, including the dissolved p=23 retrieval-glyph incident).
**Artifacts — Merle (2026-07-18):** [`experiments/test_REQ-MATH-002`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/804a8a7/experiments/test_REQ-MATH-002_cf_log23_p22gap.py) — CF of log₂3, the good-`n` grid and the p=22 hole (shadow of partial quotient 23); [`experiments/test_REQ-MATH-005`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/804a8a7/experiments/test_REQ-MATH-005_localglobal_p22margins.py) — pre-correction margins at p=21/22/23 (the pincer) and calibration distances. Both canary-checked, exact big-integer arithmetic.

---

## L2 — The p = 7 staircase instance (cross-verification)

**Claim:** the published `p = 7` staircase (`m = (4,7,9,15,23,35,1)`, `n = 94`, `K = 149`) is a size-passer on all 7 rotations with `γ = 6.7438`, failing divisibility on all 7.

**Status: `two keys` (2026-07-16).** Merle: fresh code, conventions re-derived from the published paper only — `γ = 6.7438`, size 7/7, divisibility 0/7. Macindoe: `cycles.md` 12.8.3 (original record), re-verified independently in `experiments/staircase_allp.py` (cross-check) and `experiments/p22_passer.py` (anchor).

**Artifacts — Macindoe:** as above, commit-pinned via L1's link.
**Artifacts — Merle (2026-07-18):** [`experiments/test_REQ-MATH-003`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/804a8a7/experiments/test_REQ-MATH-003_staircase_p7_twokey.py) — fresh-code re-verification (γ = 6.7438, size 7/7, divisibility 0/7); canary = the trivial cycle `R_r = 4^p − 3^p`.

---

## L3 — The local-global defect and its uniform distance (Merle, correspondence 2026-07-16)

**Claim:** on the `p = 7` instance, the closure equation `ω·q = R_r` is solvable over `R`, over `Z₂`, and over `Z₃` at every rotation, and over `Z` at none; the normalized distance to integrality `min(R_r mod q, q − R_r mod q)/q` is essentially uniform across rotations (range ≈ `[0.05, 0.48]`) — so no short congruence invariant kills the staircase family, and the missing mathematics is an equidistribution-rigidity statement (`R mod q` stays far from `0` along the family).

**Status: `two keys` (2026-07-17), with one structural sharpening.** Macindoe re-run: distance profile `[0.0538, 0.4784]`, rotation by rotation, matching. Sharpening: the local solvabilities are structural for the *entire* family, not a measured property of the instance — `q = 2^K − 3^n` is odd and `≡ (−1)^K (mod 3)` for every configuration — so the local-global defect is generic and the uniform-distance measurement is the substantive content.

**Artifacts — Macindoe:** `experiments/merle_pincer_check.py` (item 3).
**Artifacts — Merle (2026-07-18):** [`experiments/test_REQ-MATH-005`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/804a8a7/experiments/test_REQ-MATH-005_localglobal_p22margins.py) part A — the closure equation `ω·q = R_r` solvable over ℝ, ℤ₂, ℤ₃ and never ℤ on the p=7 instance, with the uniform distance-to-integrality profile across rotations.

---

## L-A1 — The transport recurrence (Merle & Macindoe, correspondence 2026-07-18)

**DRAFT — for co-editing (Ben, 2026-07-18; per the reply of the same date).**

The rotation numerators of the period-p elimination satisfy 2^{sigma_r} R_{r+1} = 3^{m_r} R_r + (2^{s_r} − 1) q exactly, for every profile with entries ≥ 1, no closure, either sign of q. Corollaries: gcd(q, R_r) is rotation-invariant, and q | R_0 iff q | R_r for all r — the p divisibility conditions are one condition (the size conditions q ≤ R_r do not collapse). Found independently and essentially simultaneously by E. Merle (integer form, correspondence 2026-07-18) and this repository (fixed-point form, Lemma 14.15.9.2, merged 2026-07-17); the seam identity N_r + q = 2^{m_r} R_r identifying the two frames was first stated in the joint verification. Status: both keys turned on the mathematics; Lean artifact pending (Merle). Cross-stack test vectors for the Lean artifact at `macindoe/collatz`, `experiments/transport_recurrence_vectors.json` (two independent implementations agree on every row; includes the reduction witnesses).

**Artifacts — Merle (2026-07-18): Lean key now turned.** [`OneObstruction/TransportRecurrence.lean`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/7d3d44a/OneObstruction/TransportRecurrence.lean) (Lean 4 / Mathlib v4.27.0). `transport_collapse` and `cycle_divisibility_one_check` certify *recurrence ⟹ collapse* for the **unreduced** modulus `q = 2^K − 3^n`, with axiom profile **kernel-3** (`propext`, `Classical.choice`, `Quot.sound`), **0 `sorry`, no user axioms, no `native_decide`**; a non-vacuity canary (the trivial cycle, `q = 2^4 − 3^2 = 7`) is proved inside Lean. Scope (stated in the artifact header): the recurrence identity itself is the part verified numerically on both sides and in fixed-point form — this artifact certifies the kernel-friendly core. With Macindoe's independent-code + fixed-point key, the mathematics of L-A1 now carries **both keys**, neither derived from the other.

---

## L4 — AEH cross-verification and class spectrum (Merle, correspondence 2026-07-18)

**DRAFT — for co-editing (Ben, 2026-07-18; per the reply of the same date).**

The AEH class skeleton cross-verified by independent implementations on both sides: the two exact class values reproduce (15,515/15,515 his; 19,036/19,036 and 13,987/13,987 ours), P(s = j) tracks 2^{−j}, and the 8-class transfer-matrix spectrum is measured at |lambda_2| ≤ 0.06 (his) and 0.028/0.036 (ours) at cuts 2^20/2^30 — the class chain mixes in effectively one step. Both keys turned at measured grade; scope is the generic face only. The flagged drift artifact (−0.33/−0.36 vs −0.415) is resolved as protocol-level: survivorship bias from the cut, confirmed by fixed-horizon re-measurement returning to theory at both normalizations, with one normalization flag noted (per-odd-step theory −0.415, per-block −0.830).

**Artifacts — Merle (2026-07-18):** [`experiments/test_REQ-MATH-009`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/804a8a7/experiments/test_REQ-MATH-009_transfer_spectrum.py) — independent F-map (canaries `F(1,1)=(1,1)`, block of 7 → exit 13), the two exact AEH class values, and the 8-class transfer-matrix spectrum (`|λ₂| ≤ 0.06`, gap ≈ 0.95), with the cut-sensitivity control and the declared survivorship flag.

---

## L-A2 — The repeated-word gcd law (Merle proposal, round 5; correspondence 2026-07-19)

**DRAFT — for co-editing (Ben, 2026-07-19; per the round-5 correspondence).**

For every profile `P = B^j` (`j ≥ 2`): `gcd(q_P, R_0(P)) = |q_P|/q_red(B)`, `q_red(B) = |q_B|/gcd(q_B, R_0(B))` — forced `> 1`, sign-blind; a repeated word is divisible iff its base is, and then realizes the base's cycle traversed `j` times, never a new one. Closed with complete elementary cause (fixed-point invariance under repetition + the seam identity), `briefs/prime-local-probe-findings.md` (2026-07-18); re-verified on all 384 repeated words of the `k ≤ 10` map (round-5 check). Did real work in his `k = 5` sweep (swept the one false survivor a priori). Keys: his `a67970f` scripts + our `experiments/prime_local_probe.py` and `experiments/merle_round5_check.py`.

---

## L-A3 — The anchored loops, the spent `|q| = 1` stock, and the Benford side-asymmetry (Macindoe candidate, correspondence 2026-07-19)

**DRAFT — for co-editing (Ben, 2026-07-19; per the round-5 correspondence).**

The four known cycles anchored to tower near-misses; the `|q| = 1` lock free and its stock exactly three (Gersonides 1342/43; Mihailescu not needed); `−17` the single nontrivial-divisibility instance; the envelope `q_+ + q_− = 2^{⌊kL⌋}`; the side-asymmetry `log₂(3/2)` (absolute) vs 50/50 (ratio), with the `k = 1` exact tie; the exhaustive `k ≤ 10` map = `{+1}` ∪ `{−1, −5, −17}`. Keys: his `a67970f` (REQ-MATH-010/011) + our `experiments/merle_round5_check.py` (211,047 checks, 0 failures). Framing clause (the note's brick): the finite-pure mechanism is a spent finite stock, so every remaining candidate needs the finite-place × archimedean coupling — consistent with, and joined to, the prime-local structureless verdict.
