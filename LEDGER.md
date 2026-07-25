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

**Correction / sharpening (Merle, 2026-07-24, REQ-MATH-017).** The "solvable at every local place, insoluble globally" reading is imprecise. For a *linear divisibility* `q | R` there is no Hasse gap (`q | R ⟺ v_p(R) ≥ v_p(q)` for all `p`, by CRT), so a global failure forces a local one; the earlier check tested only ℝ/ℤ₂/ℤ₃ (the structural primes, where `q` is a unit) and missed the obstructing prime. The `p = 7` instance has `7 | q`, `v_7(q) = 3 > v_7(R_r) = 1` at every rotation (`gcd(q, R_r) = 7`), so it fails already in **ℤ₇**. Accurate statement: every non-cycle is locally obstructed at some prime of the seam `q = 2^K − 3^n`; the surviving, substantive content is that *no single fixed* finite place handles all profiles (the structureless prime-local probe), the obstructing prime tracking the uncontrollable factorization of `2^K − 3^n` — so the missing mathematics is the **equidistribution** of `R_r mod q` along the family, not a Hasse-type global defect. Ben's independent distance profile (the two-key content) is unaffected: this corrects the Merle-side interpretation, kept with its data per protocol. Open for co-editing. Artifact: [`test_REQ-MATH-017`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/017288f/experiments/test_REQ-MATH-017_mod7_obstruction_locale.py).

**Macindoe key turned on the correction (2026-07-24).** Verified independently our side: the no-Hasse-gap principle is confirmed as stated (for fixed `q ≠ 0`, `q | R ⟺ v_p(R) ≥ v_p(q)` at every prime; solvability over ℝ, and over ℤ_p wherever `p ∤ q`, is automatic — so a check confined to ℝ/ℤ₂/ℤ₃, where `q` is a unit, cannot see the failing place); on the `p = 7` instance, independent exact code from our own records gives `v_7(q) = 3` exactly and `v_7(R_r) = 1`, `gcd(q, R_r) = 7` at **all 7 rotations** — insoluble in ℤ₇ everywhere, as claimed; the recorded two-key data is confirmed byte-untouched (diff of this entry against `61d2cf3`: pure addition, zero deletions), and the distance profile recomputes digit-exact (`[0.0538, 0.4784]`). Correction **accepted into the two-key record**. Artifact: `macindoe/collatz` `experiments/merle_round8_check.py` part (b) (commit `d9ef06b`, on `main`).

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

**Merle key turned (2026-07-19).** Independent re-verification in his stack's own conventions (canaries hand-computed before coding): the gcd law exact, the forcing `> 1`, and divisible-iff-base — **2,400/2,400 checks each**, random bases `p ≤ 5` × repetitions `j = 2..5`. Artifact: [`experiments/test_REQ-MATH-012_repeated_word_law.py`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/ec4f229/experiments/test_REQ-MATH-012_repeated_word_law.py). Status: **two keys**.

---

## L-A3 — The anchored loops, the spent `|q| = 1` stock, and the Benford side-asymmetry (Macindoe candidate, correspondence 2026-07-19)

**DRAFT — for co-editing (Ben, 2026-07-19; per the round-5 correspondence).**

The four known cycles anchored to tower near-misses; the `|q| = 1` lock free and its stock exactly three (Gersonides 1342/43; Mihailescu not needed); `−17` the single nontrivial-divisibility instance; the envelope `q_+ + q_− = 2^{⌊kL⌋}`; the side-asymmetry `log₂(3/2)` (absolute) vs 50/50 (ratio), with the `k = 1` exact tie; the exhaustive `k ≤ 10` map = `{+1}` ∪ `{−1, −5, −17}`. Keys: his `a67970f` (REQ-MATH-010/011) + our `experiments/merle_round5_check.py` (211,047 checks, 0 failures).

**Co-edited (Merle, 2026-07-19).** Entry text accepted as seeded — one precision: the Merle-side artifact for the side-asymmetry is the *adjudicated* version at commit [`3b547c4`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/3b547c4/experiments/test_REQ-MATH-011_pourquoi_le_signe.py) (both-answers-right: 50/50 multiplicative, `log₂(3/2)` additive, law for `k ≥ 2`, Gersonides 1342/43 in place of Mihailescu). Public-facing narrative of this entry: <https://collatz-lab.org/cycles/> (companion page, cross-linked with the cycle-anchor gateway). Status: **two keys**. Framing clause (the note's brick): the finite-pure mechanism is a spent finite stock, so every remaining candidate needs the finite-place × archimedean coupling — consistent with, and joined to, the prime-local structureless verdict.

**Additions accepted (Merle, 2026-07-24).** (A) The signed characterization (Macindoe, wiki Thm 14.15.6.7, §14.15.6): the negative cycles become ordinary periodic diagonal points, `−1` the sole exception — adopted as the unifying frame for both shores. (B) The spent stock as the rational-anchor instance of the digit-match ceiling (logarithmic capacity vs linear demand, `cycles.md` 12.6.1.3) — Merle-side quantification (REQ-MATH-014): the capacity–demand margin is `≈ 0.27·n` (odd-step stratum) / `≈ 0.08·n` (general), positive and linearly growing, so the no-conspiracy cycle-count decays like `2^(−margin)`. The `positive odd integer` precision (Ben, 2026-07-24) is folded into §4.

**On (B): definition pinned, replication, and the asymptote (Macindoe, 2026-07-24).** Operational definition, from REQ-MATH-014 (the entry stated the values without it): on the tuned family `K = bitlength(3^n) = log₂ q + o(1)`, `S = K − n`, and `margin(n) = K − log₂(#profiles)` — general family: entries `≥ 1`, count `Σ_p C(n−1,p−1)·C(S−1,p−1) = C(K−2, n−1)`; odd-step stratum: all `s_t` odd, count `Σ_p C(n−1,p−1)·C((S+p)/2−1, p−1)`. (One vocabulary clause: this margin is the counting shadow of `cycles.md` 12.6.1.3's capacity/demand pair — REQ-MATH-014's "capacité" is `log₂ q`, its "demande" is `log₂ #profiles` — both vocabularies now joined under one pinned name.) Replicated digit-exact at the REQ-MATH-014 grid (`0.2730` stratum / `0.0854` general at `n = 1280`). Asymptote, closed this round and **offered**: with `β = log₂ 3` and `H` the binary entropy,

`margin/n → c_gen = β − β·log₂ β + (β−1)·log₂(β−1) = 0.0793186…` (general; equivalently `β·(1 − H(1/β))`), and
`margin/n → c_strat = β − max_{α ∈ (0, β−1]} [H(α) + ((β−1+α)/2)·H(2α/(β−1+α))] = 0.2667875…` (stratum; interior maximum at `α* = 0.3747344…`)

— genuine elementary limits (entropy bounds on the binomials, plus the largest-term sandwich for the stratum sum), with the exact counts approaching both constants monotonically from above (computed through `n = 163,840`: `0.0794`/`0.2669`). So "positive and linearly growing" is now anchored: positivity of the limit constants plus monotone-from-above convergence. The `2^(−margin)` decay clause remains the no-conspiracy **heuristic** (the artifact's own label, kept). Attribution, flat: quantification seeded Merle-side (REQ-MATH-014, `n ~ 10³`); asymptotic constants closed Macindoe-side. Artifact: `macindoe/collatz` `experiments/margin_asymptote.py` with committed output (49 checks, 0 failures; commit `52e8c5c`, on `main`); wiki home `cycles.md` Remark 12.6.1.5. Status of (B): our key is turned on the `n ~ 10³` replication, and the asymptote is offered — (B)'s quantification carries **two keys** once Merle's acceptance of the asymptote lands.

---

## L-A4 — Descent: no new cycle in structured families (Merle, correspondence 2026-07-24)

**DRAFT — one key (Merle); for co-editing.**

In the tuned regime, every periodic profile `P` (period `d | gcd(n, S)`, a repeated word in reduced coordinates) is a cycle iff its base is: `q_P | R_0(P) ⟺ q_B | R_0(B)` (fixed-point invariance under repetition, extending L-A2). Hence no structured family contains a *new* cycle — one there would descend to a strictly smaller cycle — and any hypothetical nontrivial cycle must be **aperiodic/generic**. Verified 3,600/3,600 exact over periodic draws (`n ∈ {24, 36, 60}`, `d = 2..6`, base lengths `1..3`); canaries = trivial-cycle inheritance (`([1],[1])` cycle → `B²` cycle, `q = 7`, `R = 7`) and non-cycle base → non-cycle power. Companion measurements closing the naive routes: the odd-step ("no 3-absorption") stratum carries no congruence/gcd rigidity the general family lacks (REQ-MATH-013); the finite-scale near-integer mass is a **size artifact** (94–98% from the degenerate `R_0/q < 1` region, no cycle possible there; REQ-MATH-016). So the residual gap is genuinely the generic-family equidistribution, not a structured escape hatch.

**Artifacts — Merle (2026-07-24), stack `017288f`:** [`REQ-MATH-016`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/017288f/experiments/test_REQ-MATH-016_artefact_taille_et_descente.py) (descent + size-artifact), [`013`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/017288f/experiments/test_REQ-MATH-013_rigidite_strate_sans3.py) (no congruence rigidity), [`014`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/017288f/experiments/test_REQ-MATH-014_capacite_vs_demande.py) (capacity–demand), [`015`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/017288f/experiments/test_REQ-MATH-015_equidistribution_et_structure.py) (Weyl/structure). Canary-checked, exact big-integer arithmetic.

**Macindoe key turned (2026-07-24) — clean-room, with a strengthening.** Independent re-derivation from `cycles.md` 12.6.1's conventions only (no code or text reused from either Merle repository): the biconditional follows from a *multiplicative identity* — `R_0(B^k) = R_0(B) · (q_P/q_B)`, where `q_P/q_B = G_k = Σ_{c<k} 3^{(k−1−c)·n_B} · 2^{c·K_B}` is the geometric factor of `x^k − y^k` at `x = 2^{K_B}`, `y = 3^{n_B}` — proved by two bookkeeping identities (per copy `c`, the `3`-exponent of each term gains `(k−1−c)·n_B` and the `2`-exponent gains `c·K_B`), so numerator and seam gap scale by the *same* positive integer and `G_k` cancels from the divisibility. Verified exact at every draw over three grids — exhaustive bases of length `1..3`, entries `{1,2,3}`, `k = 2..5` (3,276 pairs; the 24 divisible bases all inherit upward); 300 random bases, lengths `4..6`, entries `1..8`, `k = 2..4`; and the tuned mirror of the REQ-MATH-016 grid (`n ∈ {24,36,60}`, 720 draws): **12,888/12,888 exact checks, 0 failures**. Canaries: trivial-cycle inheritance (`([1],[1]) → B²`, `q = R = 7`), a negative-`q` square (the `(−5)`-shore word), a non-cycle square. Wiki home: `cycles.md` Remark 12.6.1.4 (identity + proof + primitivity corollary). Artifact: `macindoe/collatz` `experiments/merle_round8_check.py` with committed output (commit `d9ef06b`, on `main`). Status: **two keys**.

Two offers, inside the entry per the co-edit style — acceptance is Merle's call:

- *(offer a — scope.)* The identity and the biconditional hold with **no tuning hypothesis**: every profile with entries `≥ 1`, both signs of `q`, exactly like L-A1/L-A2. "In the tuned regime" can drop, or stay as the application's stated scope, as preferred.
- *(offer b — vocabulary.)* "aperiodic/generic" → "**primitive** (not a proper power of a shorter word)/generic" — the finite-word-correct term for the descent's conclusion, mirroring the "positive odd integer" precision.
---

**Lean key on the structured half (Merle, 2026-07-24, stack `67c428a`).** [`OneObstruction/ContentDescent.lean`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/67c428a/OneObstruction/ContentDescent.lean): the cocycle `W0(l1 ++ l2) = 3^(msum l2)*W0(l1) + 2^(mssum l1)*W0(l2)`, Macindoe's multiplicative identity in W0 form (`power_mult`: `W0(B^k) = G_k * W0(B)`), the seam scaling (`q_pow_factor`: `q(B^k) = G_k * q(B)`, same cofactor), **`cycle_iff` both directions** (k >= 1; no new cycle from repetition — the L-A4 statement itself), and **`gcd_climb`** (`gcd(q(B^k), W0(B^k)) = G_k * gcd(q(B), W0(B))` — the L-A2 law, general form). All kernel-3, 0 sorry, no user axioms, no native_decide; committed `#print axioms` at `experiments/ContentDescent_axioms.txt`. The unreduced modulus throughout. The structured half of the landscape is now kernel-certified end to end.

**Macindoe statement-match on the Lean key (2026-07-25), recorded:** all five ContentDescent statements verified clean-room against the 12.6.1.4 identity and the L-A2 law, with `G_k` confirmed as the 12.6.1.4 cofactor — recursive = closed = `q`-cofactor at every pair (`macindoe/collatz` `experiments/merle_contentdescent_check.py` with committed output, commit `00f7bbc`, on `main`; 4,541 exact checks, 0 failures; read-not-built — no toolchain our side, kernel-3 resting on his committed logs).

---

## L-A5 — The adelic content invariant and the separation lemma (Merle, correspondence 2026-07-24)

**Two keys (Merle: Lean kernel + independent scripts; Macindoe: clean-room re-derivation, 2026-07-25). Closing gloss restated per Macindoe offer (a) — adjacency separation, not the wall; `|q| > 1` domain per offer (b).**

The content `C(P) = log gcd(q, R_0) / log |q| ∈ [0,1]` (rotation-invariant by L-A1's corollary;
`C = 1 ⟺ cycle`) is the normalized fixed-point denominator collapse — the fixed-point-denominator
frame is Macindoe's (`cycles.md`, `index.md`); the normalization and the landscape results are the
new part. Measured landscape (REQ-MATH-018): aperiodic words sit at the pure-chance level at
sampled depth (max `C` 0.11–0.50, tracking `q`'s wild factorization); repeated words `B^j` climb
`C → 1` exactly per the L-A2 law; a single-letter change at fixed `q` collapses `C` to background.
The cliff is now a **theorem**:

**Separation lemma (T1/T2).** For adjacent one-unit transfers at fixed `q` (in the 2-shifted
numerator `W0 = 2^{m_0} R_0`, same gcd with the odd `q`): the s-transfer difference is
`2^{mssum(pre)} · 3^{msum(suf)} · 2^{m_1+s_1} · (3^{m_2} − 2^{m_2})` and the m-transfer difference is
`−2^{mssum(pre)} · 3^{m_2+msum(suf)} · 2^{m_1} · (2^{s_1} − 1)` — valid at every position in W0
coordinates (the boundary case is regular there). **Corollary:** a common divisor of `q` shared by
two neighbours divides the letter-scale seam `3^{m_2} − 2^{m_2}` resp. `2^{s_1} − 1` — the letter
constant being exactly the composed one-letter constant of Macindoe's affine law (`itinerary.md`,
`β` and `G(y)`); with `m = 1`: shared content 1, total isolation. So content towers have no shoulders in the exact sense the lemma proves: **no word is connected to a `C = 1` word by one-unit adjacent transfers** (adjacency separation, T1/T2), and repetition merely *approaches* `C = 1`, reaching it only from a cycle [L-A4]. What the lemma does not exclude — and what NOTE §6's residual gap now names exactly — is an **isolated** aperiodic peak at `C = 1`, unreachable by transfer: the `−17` cycle is precisely such a peak, realized on the negative shore (primitive, `q = −139`, `C = 1`, shared content 1 with all six neighbours, forced by the corollary `gcd(139, 3³ − 2³) = gcd(139, 19) = 1`). The wall, restated: no isolated `C = 1` peak on the positive shore. (Domain: `C` is defined for `|q| > 1`; on the spent-stock `|q| = 1` words it is `0/0` — offer (b), accepted.)

**Artifacts — Merle (2026-07-24), stack `e297d9d`:**
[`OneObstruction/ContentSeparation.lean`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/e297d9d/OneObstruction/ContentSeparation.lean)
— T1, T2, separation_T1/T2, q_divisor_coprime, all **kernel-3** (`propext`, `Classical.choice`,
`Quot.sound`), **0 sorry, no user axioms, no `native_decide`**, non-vacuity canaries inside, with the committed [`#print axioms` output](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/905d75b/experiments/ContentSeparation_axioms.txt) (kernel-3, all five theorems) and an explicit unreduced-modulus note in the header (statements are about the raw `q = 2^K − 3^n`, not `q/gcd`);
[`REQ-MATH-018`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/9932f3f/experiments/test_REQ-MATH-018_contenu_adelique.py)
(content landscape), [`REQ-MATH-019`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/9932f3f/experiments/test_REQ-MATH-019_lemme_separation.py)
(identities exact 713/713, 604/604; corollary 560/560),
[`REQ-MATH-020`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/e297d9d/experiments/test_REQ-MATH-020_pont_lean.py)
(Lean↔Python bridge `W0 = 2^{m_0} R_0`, exact 300/300 each). Anteriority sweep of `macindoe/collatz`
(2026-07-24): "adjacent transfer", "separation/cliff", "adelic content" — no occurrences; the letter
constant and the fixed-point-denominator frame are Macindoe's, credited above. Open for co-editing.

**Macindoe verification record (2026-07-25) — clean-room, with the exhibit computed.** Independent verification from `cycles.md` 12.6.1's conventions only (no code or text reused from either Merle repository; canaries hand-computed before any sweep). The invariant **confirmed**: `gcd(q, R_r)` rotation-invariant and `C = 1 ⟺ q | R_0` in exact integer form, 600/600 each, both signs of `q`, tuned and untuned. The landscape **consistent at reduced scale** (aperiodic band max `C` 0.24–0.38 at `N = 4,000` per depth; the one-letter collapse reproduced on all three towers), with the `B^j` climb made **exact** via the descent identity [L-A4]: `gcd(q_{B^j}, R_0(B^j)) = G_j · gcd(q_B, R_0(B))`, whence `1 − C(B^j) ~ c/j` — the climb happens for **every** base, divisible or not, and `C(B^j) = 1 ⟺ C(B) = 1` (the L-A4 identity's corollary: repetition approaches `C = 1`; it reaches it only from a cycle). T1/T2 **re-derived clean-room** from the `W0` fold alone: the closed forms match the Lean statements exactly; verified 2,025 + 2,025 exhaustive, 900 + 900 random, and the `R_0`-frame forms (including the position-0 rotation reduction the `W0` frame repairs); corollary 664/664, with all 79 unit-seam cases (`m_2 = 1` resp. `s_1 = 1`) at shared content exactly 1. Lean artifact status, flat: read, statements matching this entry clause-by-clause; no `sorry`, no `native_decide`, no user axioms in the text; not built our side (no toolchain here); a committed `#print axioms` output would close the kernel-3 claim — an invitation, not a demand. Artifact: `macindoe/collatz` `experiments/merle_la5_check.py` with committed output (commit `a87b94a`, on `main`; ~10,372 exact decisions, 0 failures).

**The exhibit, stated flat.** The `−17` cycle's word (`m = (4,3)`, `s = (1,3)`; `q = −139`, `R_0 = 139`) is primitive, untuned, at `C = 1` exactly — and **totally isolated**: shared content 1 with all six adjacent-transfer neighbours, forced by the corollary itself (`gcd(139, 3^3 − 2^3) = gcd(139, 19) = 1`). The separation lemma's showcase: a peak with no shoulders, realized.

Two offers, inside the entry per the co-edit style — acceptance is Merle's call:

- *(offer a — the closing gloss.)* T1/T2 prove adjacency separation — no word is *connected* to `C = 1` by one-unit transfers — not non-existence; unscoped, the `−17` pattern realizes an isolated aperiodic peak, and tuned-scoped, the existence of such a peak is exactly the parked condition `q | R_0`, NOTE §6's residual gap. Offered replacement for the entry's final two sentences: "So content towers have no shoulders: a word at `C = 1` shares at most letter-scale content with every adjacent-transfer neighbour (content `1` at `m = 1`), so no word is *connected to* `C = 1` by one-unit transfers; and repetition, the one road that climbs (`C(B^j) → 1` for every base, per the L-A2 law), reaches `C = 1` at finite height only from a base already at `C = 1` — and is sterile [L-A4]. The *existence* of an isolated aperiodic `C = 1` peak is untouched: it is exactly the parked condition `q | R_0` — NOTE §6's residual gap — and untuned the pattern is realized: the `−17` cycle's primitive word has `C = 1` while sharing content `1` with every neighbour (its seam `3^3 − 2^3 = 19` is coprime to `139`)."
- *(offer b — domain.)* `C` is `0/0`-undefined at `|q| = 1` — exactly the spent-stock words [L-A3; `cycles.md` 12.6.1.2/12.6.1.3]; a one-clause domain restriction `|q| > 1` (or the convention `C := 1` there, as preferred) closes the interval claim.

**Key status, honestly:** the Macindoe key turns on the invariant, the landscape, and the separation lemma (T1/T2 + corollary) as verified; on the entry's closing gloss it turns **with offer (a)** — the entry reaches **two keys** upon Merle's acceptance of a restatement (his own wording equally welcome). Status stays **DRAFT** with this stated until then. *(Condition met, 2026-07-24: restatement accepted at `49351e5` — two keys, per the header.)*

One minor offer (Macindoe, 2026-07-25) — acceptance is Merle's call:

- *(minor — the wall rider.)* "no isolated `C = 1` peak on the positive shore" → "no isolated **primitive** `C = 1` peak on the positive shore": read standalone, the forced powers of `+1` are literal positive-shore isolated `C = 1` words (the trivial square `((1,1),(1,1))` has `q = R_0 = 7`, `C = 1`, and unit seams `3¹ − 2¹ = 2¹ − 1 = 1`, so shared content 1 with every neighbour); read in place the anaphora is unambiguous — the two-word precision closes it.

---

## L-A6 — The calibrated lottery: the two shores' cycle census equals their necklace budget (Merle, correspondence 2026-07-24)

**DRAFT — one key (Merle, measured/assessed grade); Macindoe key invited.**

In the letter alphabet (classical frame, numerator `B` built from the letter constants `β_m = 3^m − 2^m`; frame-agreement `q | B ⟺ q | R_0` checked on every hit), the **complete `C = 1` census at `n ≤ 14`, both shores,** is exactly: the Gersonides freebies (`|q| = 1`: `+1`, `−1`, `−5` — deterministic, outside any lottery), the `−17` orbit at `(n, K) = (7, 11)` (primitive, `q = −139`, the words `(4,3|1,3)` and `(3,4|3,1)` realizing `−17` and `−41`), and the L-A4-forced powers. Nothing else — predictions written before measurement, canaries = the four real cycles' words hand-computed first.

**The lottery, in necklace units** (the necklace is the independent trial — `gcd(q, R_r)` is rotation-invariant by L-A1): south `n ≤ 14`: `λ = 1.12`, primitive necklace-hits **1** (the `−17` — the unique *paid-lock* cycle in existence); north: `λ = 2.64`, primitive hits **0** (`P(0) ≈ 7%`, larger still after the realizability filter — all 18 formal hits observed do realize as true cycles/powers, so the filter only shrinks `λ`). The tail `Σ_{n>14}` decays geometrically at the capacity–demand rate (the (B) constants): south `+0.16`, north `+0.33` through `n = 200`, vanishing beyond; the dominant future cells sit on convergent anchors (`27/17` north, `84/53` south). Cross-checked against the verified range, the north's residual budget — cells whose realizable elements could exceed verification — is `≈ 5·10⁻³` formal cycles.

**Filter closed (Merle, 2026-07-24, REQ-MATH-025).** A formal hit IS a real cycle: all 18 census hits realize exactly (true-map orbit, parity, sigma pattern, return), and the mechanism is the 2-adic ghost identity — the fixed point `x = B/q` follows the word's itinerary automatically (300/300 random words, classical frame; parity of `x` forced by `v_2(ghost) = 0`). So no realizability correction applies: the budgets above are directly real-cycle expectations.

**Reading, at assessed grade and no higher:** the mirror shore *calibrates* the uniform-residue model — its winnings equal its budget — and under the calibrated model the positive shore's remaining expectation is `~0.005`. The wall's exact role is unchanged and now has odds attached: replace this Poisson statement by rigidity (NOTE §6's gap). Falsifier: any second paid-lock cycle, either shore, breaks the calibration.

**Artifacts — Merle (2026-07-24):** `experiments/test_REQ-MATH-022_miroir_rive_sud.py` (exhaustive census), `experiments/test_REQ-MATH-023_loterie_calibree.py` (necklace correction + tails), outputs committed alongside. Joins L-A3's spent-stock and (B)-margin bricks; census consistent with the known ×3−1 cycle list. Open for co-editing.

**Macindoe key turned (2026-07-25) — scoped: census and realizability exact, budgets and tail as replicated model computations, the reading at its assessed grade.** Independent verification with fresh code from `cycles.md` 12.6.1/12.6.1.1's conventions only (no code or text reused from either Merle repository; predictions printed before any sweep; canaries = the four known cycles' words hand-computed first): **424 recorded checks over the census's 816,871 words, 0 failures.** The census **exact-confirmed** in his domain: exactly the 18 hit words and nothing else; frame agreement `q | B ⟺ q | R_0` at 816,870/816,870 words, both directions — and at full gcd level (`gcd(|q|, B) = gcd(|q|, R_0)` at every word). **Completed our side to ALL `S` at `n ≤ 14`: the complete census is 23 words** (13 trivial powers + 6 `(−5)`-powers + the `−17` orbit's 2 + its square's 2), so the qualitative claim — freebies + `−17` orbit + L-A4-forced powers, nothing else — holds **unconditionally** at `n ≤ 14`, a strengthening: by the ghost lemma below plus the cycle product identity `2^K = Π_t (3 + 1/x_t)`, a south hit forces `S ≤ 8` for `n ≤ 14` (every possible south hit was already inside his window), and a north extension hit forces `x = 1` — the trivial powers at `(j, 2j)`, `j = 10..14`, each verified `B = q` directly. Budgets and tail **replicated digit-exact, as model computations** (exact necklace counts, two methods agreeing on every cell): south `λ = 1.1175`, north `λ = 2.6447` (his 1.12/2.64); tail tranches identical at all four decimals over his window; dominant cells matching his list cell for cell. **The ghost identity is proved exact our side** — the telescoping lemma `3·B(W) + q = 2^{σ_0} · B(shift W)` (`q = 2^K − 3^n`) holds for every σ-word with entries `≥ 1`, and `B(W)` is **odd** for every word; hence for `x = B(W)/q` the valuation `v_2(3x+1) = σ_0` is **forced** at every step — "a formal hit IS a real cycle" is a theorem, not a measurement (verified 1,364 exhaustive + 400 random words; all 23 census hits realize as exact true-map orbits; 350/350 fresh ghost draws). The calibration reading (south winnings = budget; north residual `~0.005` as odds attached to the wall) is left **at his own assessed grade, explicitly** — nothing our side raises or lowers it. Artifact: `macindoe/collatz` `experiments/merle_la6_check.py` with committed output (commit `38b7595`, on `main`).

Offers, inside the entry per the co-edit style — acceptance is Merle's call:

- *(offer a — domain clauses.)* The census "18" is the `S ≤ 9` window count with the `n ≥ 2` start (of the three freebies only `−5`'s word is in-domain), and the budgets/tail live on the near-tuned band `S ≤ int(0.5849625·n) + 3` — load-bearing: outside it the formal budget does not decay while realizable size collapses (the REQ-016 size artifact). One clause naming the window and the band closes it; the all-`S` completion at `n ≤ 14` (23 words, ghost + product-identity argument) is offered as the closure.
- *(offer b — the mechanism sentence.)* The exact ghost lemma `3·B(W) + q = 2^{σ_0} · B(shift W)` (`B(W)` always odd — his `v_2(ghost) = 0` — so the itinerary is forced at every step) offered in place of "300/300 random words": the filter's mechanism as a stated identity rather than an empirical rate.
- *(offer c — the residual's cut.)* The north residual `≈ 5·10⁻³` is the tail sum at the cut `n ≥ 61` (his OUT-023: `0.0049 + 0.0001`); the committed script computes no verification-bound criterion, so pinning the cut in the entry grounds "beyond the verified range" in the artifact.
- *(offer d — minor.)* "known" before "in existence" (true on the known ×3−1 list; universality is exactly what the falsifier sentence carries); primitive-only units for `P(0)` if preferred (`λ_prim = 1.0502` south / `2.4282` north, `P(0)` 0.350/0.088 — same story, cleaner units); and `27/17` is a semiconvergent (the mediant of `8/5` and `19/12`) with the top south cell by budget `(24,38)` and `(53,84)` second — "convergent anchors" covers both loosely.

**Key status:** **two keys** — the census and the realizability filter exact on both sides (his measured grades upgraded: the census exact-confirmed and completed, the filter a proved lemma), the budgets and tail as replicated model computations (exact necklace counts matching his approximation at all printed decimals), and the calibration reading at its assessed grade on both sides, exactly as the entry labels it.

---

## L-A7 — The torsion ruler: the lottery's total ticket mass is effectively finite, at every scale (Merle, correspondence 2026-07-24)

**DRAFT — one key (Merle; theorem-grade modulo two published ingredients); Macindoe key invited.**

The instrument fuses the two rulers this program already owns: the **(B) counting constant** `c_gen = 0.0793186` (crowd-side, finite places) and the **effective irrationality measure of `log₂3`** (exponent `μ = 5.125`, Salikhov as documented in the Merle v2 corpus §5 — *primary source to be re-checked before any publication*). The second is an **individual-grade** Diophantine statement — true for *every* `n`, no averaging — i.e. exactly the archimedean component of the "individual resolver" that NOTE §6's residual gap calls for, wired to the counting for the first time in this frame.

**Statement (verified `n ≤ 2000`, canary-anchored):** for the best north cell at scale `n`, `R(n) = log₂(#words) − log₂ q ≤ −c_gen·n + (μ−1)·log₂ n + C₀`, with `C₀ = −5.77` exhibited (max at `n = 2`); the ingredient inequality has enormous slack (`min_n ε_n·n^{μ−1} ≈ 14.5`). Canaries: anchors `(5,8) → q = 13`, `(7,12) → q = 1909`; the `n ≤ 14` word-budgets reproduce the census exactly (`6.17` north / `3.41` south). **Consequence, effective and scale-free:** the tickets' total mass beyond `n = 600` is provably `< 5.2·10⁻⁴` (both shores; word units, which upper-bound necklace units), and everything below `n = 600` is exact finite computation. **The kiosk provably closes:** L-A6's tail is no longer "computed to `n = 200`" but bounded for all `n` by two published constants and elementary algebra.

**Honest scope:** this bounds the *expectation*, not the truth — the model→certainty step remains the ×2×3 gap, unchanged. The bound is slack at small `n` (the transplanted exponent is worst-case). ~~crosses below one ticket near `n ≈ 550`~~ — **withdrawn (Merle, 2026-07-25): that figure was never computed, an unbacked estimate that should not have entered the entry; see the re-derivation below.** Sharper measures only improve `C₀`.

**Artifacts — Merle (2026-07-24):** `experiments/test_REQ-MATH-029_regle_de_torsion.py` (+ committed output), predictions written before measurement. Open for co-editing.

**Macindoe verification record (2026-07-25) — replication digit-exact; the flagged μ source re-checked.** Independent replication with fresh code (μ a parameter throughout; exact integer arithmetic for every `q` and word count; his script read for operational definitions only, never run): `C₀ = −5.774` at `n = 2`, the ingredient slack `14.483` at `n = 2`, the tail table at all seven cuts, and the headline cut exact (min `N` for `< 5.2·10⁻⁴` = **600**) — all matching his committed output. **The μ source, re-checked as the entry itself flags, stated flat:** `5.125` is Salikhov 2007's effective irrationality measure of **`ln 3`** (Dokl. Akad. Nauk 417 (2007), no. 6, 753–755; English transl. Doklady Mathematics 76 (2007), no. 3, 955–957; superseded even for `ln 3` by Wu–Wang 2014, `5.1163051`, J. Number Theory 142 (2014), 264–273) — not of `log₂3`, and no measure of that strength is published for `log₂3`; as committed, the headline "`< 5.2·10⁻⁴` beyond `n = 600`" survives only under the transplanted exponent with the fitted constant. The citable effective ingredient for `log₂3` is **Rhin 1987** (Proposition, p. 160, Progress in Mathematics 71: `|u₀ + u₁·ln 2 + u₂·ln 3| > H^(−13.3)`; the printed Collatz-side precedent is Simons–de Weger 2005, Acta Arith. 117, Lemma 12), under which **the same construction closes: total ticket mass provably `< 5.2·10⁻⁴` beyond `n ≈ 2233`, exact finite computation below** — the instrument intact, the ruler re-sourced. "Effectively finite at every scale" is TRUE under every sourced row, down to the guaranteed two-log fallback (Gouillon 2006, a constant floor, crossing `~7.36·10⁸`). Artifact: `macindoe/collatz` `experiments/merle_la7_check.py` with committed output (commit `e7a3696`, on `main`).

Offer, inside the entry per the co-edit style — acceptance is Merle's call:

- *(offer — the re-sourced ruler.)* Replace the ingredient line by the Rhin 1987 / Simons–de Weger 2005 citation; restate the bound as `R(n) ≤ −c_gen·n + 13.3·log₂ K₀ + C₀` with explicit `C₀ ≈ 2.06` (+3 repair bits for the best-cell → both-shore-mass step, measured `< 1.94`); restate the consequence as "provably `< 5.2·10⁻⁴` beyond `n ≈ 2233`; exact computation below" (`n ≤ 2000` already exists on both sides; the 2000→2233 strip is a finite computation of the same kind); and re-derive or drop the `n ≈ 550` crossing sentence — neither natural reading reproduces it our side (per-scale bound < 1 ticket at `n = 372`; cumulative tail < 1 at `N = 440`). Two further ingredients, named so the "modulo published ingredients" ledger is complete: the for-all-`n` margin inequality `margin(n) ≥ c_gen·n` (verified `n ≤ 2000`, min `2.84` at `n = 2`; elementary, not yet proved anywhere), and the south-side floor `ε'_n` for the both-shore step (our slack `70.1` at `n = 3`; unchecked in the committed artifact).

**Key status, honestly:** the Macindoe key turns on the replication (digit-exact) and on the construction **with the re-sourced ingredient** — the entry reaches **two keys** upon Merle's acceptance of a re-sourcing (his own wording equally welcome). Status stays **DRAFT** with this stated until then. The honest-scope paragraph stands untouched — it is correct as written, including "sharper measures only improve `C₀`".


**Merle acceptance and re-derivation (2026-07-25).** All four offer clauses accepted as stated; the re-sourcing is right and the flag was raised for exactly this reason.

- *(Re-sourcing.)* Accepted: the ingredient is **Rhin 1987** (Progress in Mathematics 71, Proposition p. 160) with the Collatz-side precedent **Simons–de Weger 2005** (Acta Arith. 117, Lemma 12); the `5.125` line is withdrawn — it is Salikhov's measure of `ln 3`, and transplanting it to `log₂3` was an error on the Merle side, caught by the Macindoe re-check. The instrument stands; only its label changes. The re-sourced headline (`< 5.2·10⁻⁴` beyond `n ≈ 2233`, exact computation below, with the 2000→2233 strip a finite computation of the same kind) is adopted, together with the explicit `C₀ ≈ 2.06` and the measured `< 1.94` repair bits for the best-cell → both-shore step.
- *(The `n ≈ 550` crossing — re-derived, and it was wrong.)* Re-computed from the exact `R_best(n)` data on the Merle side (`n ≤ 4000`, canary-anchored `(5,8) → 13`, `(7,12) → 1909`): under the entry's own constants the per-scale bound drops below one ticket at **`n = 372`** and the cumulative tail falls below one ticket at **`N = 440`** — **reproducing both Macindoe readings exactly**. The `550` matches neither and is withdrawn. Artifact: `experiments/test_REQ-MATH-035_croisement_un_ticket.py` (+ committed output).
- *(Merle-side honesty item, volunteered.)* The `C₀` in the committed artifact is **exhibited from the exact data up to the computed range, not proved for all `n`** — so the statement as it stands is *verified to `N`*, not *proved for all `n`*. That is precisely the first of the two ingredients named: the for-all-`n` margin inequality `margin(n) ≥ c_gen·n`. Until it is written, "effectively finite at every scale" should read as conditional on it. The Macindoe offer to write that elementary proof is **accepted with thanks**; the south-side floor `ε'_n` for the both-shore step is likewise acknowledged as owed and unchecked in the Merle artifact.

With the re-sourcing accepted and the crossing re-derived, the entry stands at **two keys**, scope as stated: an effective bound on the *expectation*, conditional on the named margin inequality, with the model→certainty step still the ×2×3 gap.


**Merle — the two named ingredients, addressed (2026-07-25, stack `517ba89`).**

- *(South floor `ε′_n` — resolved, and it needs no new ingredient.)* North and south sit on opposite sides of the same real number: `ε_n = ⌈nL⌉ − nL` and `ε′_n = nL − ⌊nL⌋` satisfy **`ε_n + ε′_n = 1` identically**. Hence at most one of the two can be small: whichever it is, it is the distance to the *nearest* integer and is exactly what the Rhin/Simons–de Weger bound controls; the other is `≥ 1/2` for free. So the best-cell → both-shore step costs at most one bit beyond the single-shore bound, consistent with the measured `< 1.94` repair bits. Verified with 0 violations at every `n` tested including the convergent denominators (`n = 15601`: `ε = 2.6·10⁻⁵`, `ε′ = 0.999974`; `n = 190537`: `min = 9.3·10⁻⁸`). The debt is discharged without a new citation.
- *(Margin inequality — verified exact, and the proof route validated but **tight**.)* `margin(n) − c_gen·n ≥ 0` re-verified in exact arithmetic (mpmath, `n ≤ 3000`): **minimum slack `2.8414` at `n = 2`**, 0 violations — reproducing the Macindoe figure `2.84`. On the proof itself, offered as de-risking before it is written: the natural route (`C(m,k) ≤ 2^{m·H(k/m)}`, `m = n+S−2`, `k = n−1`) **does dominate `c_gen·n` at every `n ≤ 200,000`** — the route works. **But it is tight and does not improve with scale:** the entropy-route margin stays in `[1.66, 2.10]` bits, minimum **`1.6647` at `n = 16266`**, and is asymptotically constant, because the gap between the true margin and the entropy bound tracks the `(1/2)·log₂ n` Stirling correction exactly (measured: `3.92` at `n = 100`, `8.91` at `n = 10⁵`, against `(1/2)log₂ n` = `3.32`, `8.30`). Practical consequence for the write-up: the Stirling term must be handled with an explicit bound rather than absorbed, since there are under two bits of room. Artifact: [`test_REQ-MATH-036`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/517ba89/experiments/test_REQ-MATH-036_dettes_nommees.py) (+ committed outputs, predictions written before measurement).


**Merle — the margin inequality's analytic core, now kernel-friendly (2026-07-25, stack `f844467`).** Offered toward the ingredient Macindoe offered to write; the Stirling warning above was the reason to look for a route that avoids Stirling altogether.

The entropy bound `C(m,k) ≤ 2^{m·h(k/m)}` is the *optimum* of the elementary family `C(m,k)·x^k ≤ (1+x)^m` (the left side is one term of the binomial expansion). Taking the **rational** `x = 12/7` — near the optimum `x* = 1/(log₂3 − 1) = 1.7095` — and clearing denominators removes real analysis entirely, and since **`19 = 12 + 7`** the statement becomes *one summand ≤ the sum*:

> `deficit_term_le (m k : ℕ) (h : k ≤ m) : 12^k * 7^(m−k) * C(m,k) ≤ 19^m`

[`OneObstruction/DeficitLemma.lean`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/f844467/OneObstruction/DeficitLemma.lean) — **kernel-3, 0 sorry, no user axioms, no `native_decide`**, committed `#print axioms`, five non-vacuity canaries (two of them instantiate the theorem rather than restate it). Numerics established *before* formalizing (REQ-MATH-039/040, canary-anchored, committed): the resulting asymptotic constant is `0.0793165`, within `2.1·10⁻⁶` of `c_gen` — the rational choice costs essentially nothing; with the safe rational `c = 1/13`, `margin(n) ≥ n/13` holds for `n = 1..3000` with **0 failures and minimum slack 1.700 bits**; the integer target `C(K−2,n−1)^13·2^n ≤ 2^{13K}` holds for `n = 1..1200`, 0 failures, and the binomial route implies it with ≥ 22 bits to spare. A negative control is included: `c = 2/25 = 0.08 > c_gen` fails at 241 scales, as it must.

**Honest scope.** What is proved in Lean is the analytic heart. The remaining step — from `deficit_term_le` to the `n`-indexed margin statement — is the comparison of `K` with `n` (`3^n ≤ 2^K < 2·3^n`); it is stated in the file as `MarginTarget` and is **not yet proved**, deliberately left explicit rather than absorbed. It is a finite rational-exponent comparison, not an analytic obstacle. Provenance: the deficit is Merle's own earlier result (Junction Theorem preprint §3, entropy form, constant `γ` with `γ·log₂3 = c_gen` exactly — REQ-MATH-037); this entry contributes the elementary re-derivation and the kernel artifact. If the Macindoe-side proof is written independently, two proofs of the same inequality is the currency this ledger runs on.


**Merle — assembly heart proved (2026-07-25, stack `266f26b`).** Following the Stirling warning, the route now avoids real analysis entirely. Reparametrising `m = k+j`, `n = k+1`, `K = k+j+2` removes every natural subtraction, and the Diophantine hypothesis plus the whole `j`-dependence concentrate into one lemma:

> `key_core (k j) (hub : 2^(k+j+2) ≤ 2·3^(k+1)) : 2^(86(k+j+2))·2^(15(k+1))·7^(195k) ≤ 2^562·12^(195k)`

Proof: `hub` to the 86th power; `atom_a` on the per-`k` factor; `atom_D` on the constant. The admissible window for the exponent ratio is `[5.727444, 5.747075]` (width `0.0196`) and `s = 15, t = 86` is the smallest admissible pair — `atom_A` and `atom_a` hold with `0.088` and `0.327` bits to spare, exact. Six theorems in [`DeficitLemma.lean`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/266f26b/OneObstruction/DeficitLemma.lean), **all kernel-3, 0 `sorry`, no user axioms, no `native_decide`**, committed axiom log.

**Remaining, stated exactly:** the bookkeeping from `key_core` + `deficit_term_le` to the `n`-indexed `MarginTarget` — exponent arithmetic only, no new mathematical content — verified in exact integers (REQ-MATH-042, full chain step by step, `n = 1..300`, 0 failures; the implication `(3) ⟹ (2)` tested separately, 0 violations), not yet formalised. Two Merle-side errors were caught by the machine during this round and are recorded in the artifacts rather than smoothed: a missing `/log₂3` in the first window computation (which proposed an inadmissible `s = 1, t = 6`, refuted by the exact integer check), and a `norm_num` failure on a 71-digit constant (replaced by the soft chain `3^86 ≤ 4^86 = 2^172`).


**Merle — the margin inequality is PROVED (2026-07-25, stack `b22fafc`).** The debt named in this entry is discharged on the Merle side, at kernel level.

> `marginTarget (n K) (1 ≤ n) (3^n ≤ 2^K) (2^K < 2·3^n) : C(K−2, n−1)^13 · 2^n ≤ 2^(13K)`

Chain, all in ℕ, no real analysis anywhere: `deficit_term_le` (one summand of `(12+7)^m`) → atoms `A`/`a`/`D` → `key_core` (absorbs the Diophantine hypothesis and the entire `j`-dependence) → `key_shifted` → `key15` → `margin_core` (the `k,j` form, free of natural subtraction) → `marginTarget`. **Ten theorems in [`DeficitLemma.lean`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/b22fafc/OneObstruction/DeficitLemma.lean), every one kernel-3 (`propext`, `Classical.choice`, `Quot.sound`), 0 `sorry`, no user axioms, no `native_decide`**, with the committed axiom log.

**Honest, and it matters for this entry's numbers.** What is *proved* is the inequality with the rational constant `1/13 = 0.0769231`, about 3% below the asymptotic `c_gen = 0.0793186`; `c_gen` itself remains an asymptotic value, not a Lean theorem. Recomputing this entry's thresholds under the **proved** constant (REQ-MATH-043, same Rhin exponent): per-scale crossing `1596 → 1655`, cumulative-tail crossing `1661 → 1722`. The qualitative statement is unchanged — the ticket mass is effectively finite at every scale, and now the margin step is no longer conditional. The remaining ingredient of this entry is therefore only the published Diophantine input (Rhin 1987 / Simons–de Weger 2005), not an unproved lemma of ours.

The Macindoe offer to write this proof independently stands and is still welcome: two proofs of the same inequality — one entropic, one elementary — is the currency this ledger runs on, and the entropic route (with the Stirling caution recorded above) is the one that connects to the published Junction-Theorem form.


---

## L-A8 — T1, the no-hair theorem for cycles: the ceiling half at the kernel (Merle, correspondence 2026-07-25)

**DRAFT — one key (Merle: Lean kernel + scripts); Macindoe key invited.**

T1 is the structure theorem the joint note's §6 names as the program's next step: *every surviving positive cycle is forced into a rigid shape* — no freedom, like a black hole's no-hair theorem. Its **ceiling half is now a kernel theorem**, stated in pure integers with no logarithm:

> `ceiling_upper` : a positive cycle with `p+1` odd elements, all `≥ X`, with `2(p+1) < 3X`, has `3^(p+1) < 2^K < 2·3^(p+1)` — i.e. `K = ⌈(p+1)·log₂3⌉` is forced.

Chain: the **cycle product identity** `∏(3xᵢ+1) = 2^K·∏xᵢ` (telescoping over the rotation, `Fintype.prod_equiv`); the **survivor bound** `2^K(3X)^{p+1} ≤ 3^{p+1}(3X+1)^{p+1}` (per-factor `(3x+1)(3X) ≤ 3x(3X+1) ⟺ X ≤ x`); and the elementary strict two-bound `(m+1)^n < 2m^n` for `2n < m` (induction, no analysis). [`OneObstruction/T1Structure.lean`](https://github.com/ericmerle3789/one-obstruction-three-faces-lean/blob/41fa4f8/OneObstruction/T1Structure.lean), **kernel-3, 0 sorry, no user axioms, no `native_decide`**, committed axiom log; canaries instantiate the theorems on the trivial cycle.

Machine chain first (REQ-MATH-052, committed): the product identity holds **exactly on all four real cycles, both shores** (`−17`: `∏(3x+1) = −403123745024000 = 2^11·∏x`); the Legendre window is `4.955·10^10` (below Hercher's `1.375·10^11`, so the surviving range is governed by the Ostrowski regime, not Legendre — stated honestly); and the **grid half** is script-verified: the Ostrowski expansion of every `ε`-small `n` uses **only large convergent denominators** (median lowest denominator 15601, against 1 for controls; e.g. `14936 = 22·665 + 306`, the coefficient 22 being the partial quotient 23 − 1). The grid half — `n` forced onto the convergent sub-grid — is measured and stated, **not yet proved**; it is the remaining half of T1.

**Honest scope:** the ceiling half needs only `x_min > 2(p+1)/3` — far weaker than verification bounds — and pins `K` for every surviving scale. It does not by itself exclude anything; it removes one degree of freedom (K) of the two (K, shape), which is exactly what a no-hair theorem does. Open for co-editing.


**Merle — the grid half, launched to proof (2026-07-25, stack `81054ea`).** The quantitative core of the second half is now also a kernel theorem:

> `seam_bound` : under the same cycle hypotheses with `2p < 3X`: `2^K·3X < 3^(p+1)·(3X + 2(p+1))` — reading: `q·3X < 2(p+1)·3^(p+1)`, the seam gap squeezed inversely to the minimum element.

Chain: `survivor_bound` + `succ_pow_le_pow_add` (difference of powers in multiplied form, no natural subtraction) + the strict two-bound. **Five T1 theorems, all kernel-3, 0 `sorry`, no `native_decide`**, committed axiom log; both compiles first-try. Consequences computed exactly (REQ-MATH-053): best approximation verified **exhaustively** to `q₁₀ = 190537` (for every `j`, `min_{n<q_{j+1}} ‖nL‖ = θ_j`, attained at `q_j`); for `X ≥ 2⁷¹` the first admissible scale is **`n ≥ q₂₁ = 6.547·10¹⁰`** — one convergent step below Hercher's dedicated `q₂₂ = 1.375·10¹¹`, which is *itself a convergent denominator*, exactly as this frame predicts. What remains for the grid half: formalizing the best-approximation step (standard number theory, nontrivial in Lean) — the Ostrowski confinement is measured (`ε`-small `n` use only large denominators) and stated, not yet kernel-proved.


**Merle — March 1: T1 closed in the Legendre window (2026-07-25, stack `89d9efc`).** The grid half now has a fully verified consequence, and one more kernel theorem.

**Verified exactly (REQ-MATH-054):** from `seam_bound`, a positive cycle with `x_min ≥ 2⁷¹` forces `‖n·log₂3‖ < n·δ` with `δ = 2/(3·2⁷¹·ln 2) = 4.0734·10⁻²²`. Legendre's criterion applies whenever `n ≤ √(1/2δ) = 3.5035·10¹⁰`, and then `K/n` must be a **convergent** of `log₂3` — so `n` is one of the 22 convergent denominators below that window. **All 22 fail the constraint** (the tightest, `q₂₁ = 6.587·10⁹`, by a factor 5.4). Hence: **no positive cycle with `x_min ≥ 2⁷¹` and length `n ≤ 3.5035·10¹⁰`.** For comparison, Hercher's dedicated paper bound is `1.375·10¹¹` — 3.9× further, but on paper; this chain is designed to be machine-checked end to end.

**Kernel added:** `seam_gap_at_barina` — the integer half, stated subtraction-free (`2^K·3X < 3^(p+1)·3X + 3^(p+1)·2(p+1)` at `X = 2⁷¹`), with a canary showing it is not vacuous about the trivial cycle. **Six T1 theorems, all kernel-3, 0 `sorry`, no `native_decide`**, both files compiled first try, committed axiom log.

**Honest scope and the remaining link.** The analytic half — the real bridge `q ≥ 3ⁿ·ε·ln 2`, Legendre, and the 22-point check — is exactly verified but **not formalized**. Its entry point is identified and clean: `LegendreApprox.abs_sub_ge_of_not_convergent` (Legendre contrapositive wrapping Mathlib's criterion, **0 sorry, 0 axioms, 0 native_decide**) in the Merle Junction repository. A correction recorded rather than smoothed: the previous entry's `δ` dropped a factor 2, which moved the window from `4.955·10¹⁰` to `3.5035·10¹⁰`; the earlier figure is withdrawn.


**Merle — March 1-bis: the analytic bridge is now kernel too (2026-07-25, stack `dac39a3`).** The step from the integer seam gap to Legendre's input needed no continued fractions after all — only `Real.log_le_sub_one_of_pos` from Mathlib:

> `ratio_bound_at_barina` : `1 < 2^K/3^(p+1) < 1 + 2(p+1)/(3·2⁷¹)` (cast of the integer gap)
> `log_gap_at_barina` : `0 < K·log 2 − (p+1)·log 3 < 2(p+1)/(3·2⁷¹)`

Dividing the second by `(p+1)·log 2` is exactly `|log₂3 − K/(p+1)| < δ`, `δ = 2/(3·2⁷¹·ln 2)` — the input of Legendre's criterion. **Eight T1 theorems, every one kernel-3, 0 `sorry`, no `native_decide`, no user axioms**, committed axiom log; every compile first-try but one trivial cast.

**What is now left for a fully machine-checked closure of the Legendre window** is exactly two named steps: invoke Legendre's criterion (entry point `LegendreApprox.abs_sub_ge_of_not_convergent`, clean, already in the Merle Junction repository, wrapping Mathlib) and discharge the 22-point convergent check (REQ-MATH-054: all 22 fail, tightest by a factor 5.4). The mathematics is verified; what remains is formalization, not discovery.


**Merle — the Legendre step proved, and a retraction recorded (2026-07-25, stack `4856058`).**

*First, the retraction.* An earlier commit (`da2c8db`) claimed this step was kernel-3. **That claim was false.** `lake env lean` printed no `error:` line but had aborted with a stack overflow, and at workable recursion depths the proof carried `sorryAx`; I read "0 errors" without checking the compiler had finished. It is withdrawn in the artifact with a `RETRACTED` note stating what was claimed and why it failed. The verification protocol is now hardened: every check tests for `error:` **and** stack overflow/abort **and** `sorryAx` **and** presence in the theorem's own `#print axioms` probe.

*Then, the proof.* The obstruction was elaboration blow-up on the literal `2⁷¹`, not mathematics. Abstracting the threshold fixes it:

> `quotient_is_convergent_gen` : a positive cycle above threshold `X`, of length `n = p+1` with `4000·n² ≤ 2079·X`, has `K/n` a **convergent** of `log₂3`.

`X` is a variable, so no numeral reaches a tactic; the final nonlinear step is supplied explicitly rather than left to `nlinarith`. The chain is now complete and general: `cycle_prod_identity → survivor_bound → seam_bound → log_gap_gen → quotient_is_convergent_gen`, plus `ceiling_upper`. **Eleven theorems, all kernel-3, 0 `sorry`, no `native_decide`, no user axioms**, each verified by its own probe; `LegendreApprox` (from the Merle Junction repository) compiles unchanged.

Instantiating `X := 2⁷¹` gives the Barina window `n ≤ 3.5032·10¹⁰`. What remains for the full closure is only the finite discharge: the 22 convergent denominators inside that window, all of which fail the seam constraint (REQ-MATH-054/055, tightest by a factor 5.4).