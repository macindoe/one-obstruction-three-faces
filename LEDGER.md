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
**Artifacts — Merle:** *(to be linked: the pincer measurements, the canary-checked scripts.)*

---

## L2 — The p = 7 staircase instance (cross-verification)

**Claim:** the published `p = 7` staircase (`m = (4,7,9,15,23,35,1)`, `n = 94`, `K = 149`) is a size-passer on all 7 rotations with `γ = 6.7438`, failing divisibility on all 7.

**Status: `two keys` (2026-07-16).** Merle: fresh code, conventions re-derived from the published paper only — `γ = 6.7438`, size 7/7, divisibility 0/7. Macindoe: `cycles.md` 12.8.3 (original record), re-verified independently in `experiments/staircase_allp.py` (cross-check) and `experiments/p22_passer.py` (anchor).

**Artifacts — Macindoe:** as above, commit-pinned via L1's link.
**Artifacts — Merle:** *(to be linked.)*

---

## L3 — The local-global defect and its uniform distance (Merle, correspondence 2026-07-16)

**Claim:** on the `p = 7` instance, the closure equation `ω·q = R_r` is solvable over `R`, over `Z₂`, and over `Z₃` at every rotation, and over `Z` at none; the normalized distance to integrality `min(R_r mod q, q − R_r mod q)/q` is essentially uniform across rotations (range ≈ `[0.05, 0.48]`) — so no short congruence invariant kills the staircase family, and the missing mathematics is an equidistribution-rigidity statement (`R mod q` stays far from `0` along the family).

**Status: `two keys` (2026-07-17), with one structural sharpening.** Macindoe re-run: distance profile `[0.0538, 0.4784]`, rotation by rotation, matching. Sharpening: the local solvabilities are structural for the *entire* family, not a measured property of the instance — `q = 2^K − 3^n` is odd and `≡ (−1)^K (mod 3)` for every configuration — so the local-global defect is generic and the uniform-distance measurement is the substantive content.

**Artifacts — Macindoe:** `experiments/merle_pincer_check.py` (item 3).
**Artifacts — Merle:** *(to be linked.)*
