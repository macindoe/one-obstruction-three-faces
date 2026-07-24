# One obstruction, three faces

**ARCHITECTURE DRAFT — for co-editing (Merle, 2026-07-19). Prose not started; this is the load-bearing skeleton, seeded the way this repository seeds everything: edit directly, strike freely. Every numbered claim enters via LEDGER.md first (all entries below have their keys turned).**

Working title: *One obstruction, three faces: the Collatz cycle problem between size, digits, and the local–global seam.*

## 0. The porch (elementary front door)

Gersonides, 1342/43, *De numeris harmonicis*, written for the composer Philippe de Vitry: the only pairs of harmonic numbers differing by one are (1,2), (2,3), (3,4), (8,9) — a mod-8 remainder argument and a two-line factoring. Fourteenth-century, referee-proof, and the reader meets it before Baker. Consequence stated immediately: the "free locks" `|q| = 1` are a **spent finite stock** (three tickets, dealt one north / two south), and the four real loops of the map — `{+1}` and `{−1, −5, −17}` — are the stock's biography [L-A3]. The crank-proof detector falls out as a corollary: any parity/speed argument forbidding loops forbids the four that exist.

## 1. The problem and the two shores

The cycle half of Collatz; the `×3−1` mirror as the negative shore; the anchor correspondence (known cycles = good rational approximations of `log₂3`) with its folklore provenance live-checked: Steiner 1977, Crandall 1978, Eliahou 1993, Halbeisen–Hungerbühler 1997, Simons 2005, Simons–de Weger 2005, Lagarias's bibliographies.

## 2. Face I — size (the archimedean shadow)

The δ8 impossibility (Merle side): why no uniform Product-Bound refinement closes the window; the scissors (required exponent below Dirichlet's floor; `k_min ~ X₀^{1/2}` vs `k_max ≤ X₀^{1/3}`). The staircase family (Macindoe side): the sharpness that makes the same wall constructive — contiguous verified range `p ∈ {2,…,23}` [L1]. One wall, one analytic face and one constructive face.

## 3. Face II — digits (the 2-adic body)

Reduced coordinates and the anchor walk; the transport recurrence and the collapse of the `p` divisibility conditions to **one** [L-A1: independent simultaneous discovery, seam identity `N_r + q = 2^{m_r} R_r`, Lean 4 kernel-3 artifact + fixed-point proof]; the repeated-word gcd law [L-A2: two keys] — closure under repetition is inherited, never created.

## 4. Face III — the seam (local–global)

The closure equation `ω·q = R_r` is a linear divisibility, so it has **no Hasse gap**: `q | R_r` iff `v_p(R_r) ≥ v_p(q)` at every prime — an integer solution exists exactly when a local one does at each place. The obstruction is therefore **local, at the uncontrollable primes of the seam `q = 2^K − 3^n`**: the `p = 7` instance already fails in `ℤ₇` (`7 | q`, `v_7(q) = 3 > v_7(R_r) = 1`, `gcd(q, R_r) = 7`), which our earlier `ℝ/ℤ₂/ℤ₃`-only reading missed [L3, corrected 2026-07-24]. What survives is that *no single fixed* finite place handles all profiles — the prime-local probe is structureless (no coset confinement, no coarse-invariant law), the obstructing prime tracking the wild factorization of `2^K − 3^n`; so the residual gap is quantitative: whether `R_r mod q` **equidistributes** along the forced family (an equidistribution statement, not a congruence). Structured (periodic) profiles are closed by descent — a cycle there forces a strictly smaller one — so any new cycle is aperiodic [L-A4]. The realization-height theorem (Macindoe wiki, `itinerary.md` §14.15.5(b), Corollary 14.15.5.4 — the combined characterization; the wrong-sign clause at §14.15.5(c)): an itinerary is realized by an integer iff its 2-adic and 3-adic limits coincide at a positive odd integer; the classical negative cycles reappear as diagonal points of the wrong sign.

## 5. The quantitative complements

The Benford side-asymmetry: which shore gets the better near-miss is 50/50 in ratio distance and `log₂(3/2) = 58.5%` in absolute distance (the cycle-relevant one; law for `k ≥ 2`, `k = 1` the sole tie) — apparently unstated in the cycle context; neighbors cited (Kontorovich–Miller 2005, Lagarias–Soundararajan 2006, on iterates) [L-A3]. The AEH class skeleton and its measured spectrum (`|λ₂| ≤ 0.06`: the class chain mixes in one step), at measured grade, generic face only [L4].

## 6. What remains, stated exactly

The residual hypothesis, now stated exactly: the **equidistribution of `R_r mod q`** along the aperiodic forced family (the structured refuge closed by descent [L-A4]); strictly weaker than `ProductBoundThreshold`; honestly placed on the ×2×3 gap. The capacity–demand margin is positive and grows linearly — `≈ 0.27·n` in the odd-step stratum, `≈ 0.08·n` in general [L-A3 cadeau B; REQ-MATH-014] — so the no-conspiracy cycle-count decays like `2^(−margin)`, making that one equidistribution the exact remaining gap. No promise past the calculations.

## 7. Method (the actual novelty for many readers)

Two independent stacks, never merged; the two-key rule with the kernel as one key; errors kept with their refutation data; the ledger as the note's spine. Precedent worth naming: each stack broke one of its own claims on the other's data within one exchange [L1], and a self-catch was itself adjudicated as both-answers-right [L-A3].

## Appendices (candidates)

A. The Lean artifact and its axiom profile. B. The shared test vectors. C. The two gateways (operate vs. narrate): `viz/cycle_anchor_gateway.html` ↔ <https://collatz-lab.org/cycles/>.
