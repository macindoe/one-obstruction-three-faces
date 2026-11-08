# One obstruction, three faces

*The Collatz cycle problem between size, digits, and the local–global seam — first version.*

**Status of this file.** This is the two-page first version of the joint note, confined by agreement to the counting dichotomy and the located obstruction. `NOTE.md` in this repository — the architecture skeleton — stands as the map for the second, full version; nothing here supersedes it.

## Position

This note is a map, not an exclusion: it states where the resistance to Collatz cycle exclusion lives, with the instruments that measure it, every claim at a stated grade — theorem, machine-checked statement, or measurement. It excludes nothing beyond the cited verified ranges.

The verified frontier is Barina's: every start below `2⁷¹` reaches 1 [3]. Hercher [2] proves that a nontrivial cycle has at least 92 local minima (Theorem 23, `m ≥ 92`, on verified range `704·2⁶⁰`) and more than `1.375·10¹¹` odd members (Corollary 29, needing verification only to `1536·2⁶⁰ = 3·2⁶⁹`). The machine-checked exclusion below instantiates `2048·2⁶⁰ = 2⁷¹`: the asymmetry runs in Hercher's favour on hypothesis and conclusion alike. (`m` counts local minima, `K` odd members; only `K` is on the axis of the exclusion below.)

Machine-checking of the cycle literature is not new here either: on the register ccchallenge.org [4], Böhm–Sontacchi 1978 — itself a cycle-existence paper — is formalised, audited and accepted; Knight 2026 is being formalised; Eliahou 1993 carries a Lean 4 formalisation awaiting audit. This note contributes location, not precedence.

## The counting dichotomy

The dichotomy is stated in [1]; credit for each half is given below. The label *counting dichotomy* is Merle's contraction of that paper's phrases — "a sharp dichotomy for counting arguments" and "the counting-limit dichotomy developed here" — and is used here as a pointer to those phrases, not as standing terminology.

**Upper half** (Theorem 4.5 of [1]). A trim uniform in the number of blocks `p` exists and, combined with an effective irrationality measure for `log₂3`, gives **effective finiteness at every period**: in [1]'s notation, `n ≤ n₀(p) = O(p·(log₂3)^p)`. This half is Rozier's [5] (Théorème, p. 8; Lemme 4, p. 11, with the same exponent `(log₂3 − 1)/((log₂3)^p − 1)`), made explicit by Simons–de Weger [6] (Lemma 7, Lemma 14, Theorem 3(d)), whose number `m` of local minima is [1]'s `p` exactly; finiteness for each `m` is also Brox [7]. [1]'s Theorem 4.5 is a rederivation by another route (rotation numerators and a max-plus recursion). Effective finiteness is the proved statement — not that any period is closed; this note claims no closure.

**Lower half** (Theorem 4.6 of [1]). No trim uniform in `p` can extend the small-period constants: configurations exist that satisfy every rotation's exact size condition `q ≤ R_r` (notation of [1] §4: `q = 2^K − 3^n` the seam quantity, `R_r` the rotation sums) while the slack `γ = K − log₂ q` falls far below any polynomial-in-`p` extension of the constants of periods 2–3 — the *staircase* family, divergent-orbit profiles bent into loops, which "shows counting cannot do substantially better" [1, abstract]. The theorem's accompanying assessment — all size conditions passed at every `p` — has since been proved in the project record ([1], *Status of the assessment*): a witness at every period (unconditional for `p ≥ 16`, finite check for `3 ≤ p ≤ 15`, exhibition at `p ∈ {2, 4}`), `γ` between `3.683012` and `5.140212` [1]. Every witness fails the divisibility conditions `q | R_r`: "sharper evidence that counting cannot do better, and no evidence about exclusion" [1]. The optimality is not first in [1]: Rozier [5, p. 11] observes, by a minimax over positive real run-length tuples, that his bound is optimal given his per-minimum inequalities, Simons–de Weger [6, p. 69] expected the exponential dependence on `m` to be unavoidable, and Halbeisen–Hungerbühler [8] proved the analogue in the cycle-length parameter — an optimal size criterion attained by an explicit rational cycle at every length (Lemma 5, p. 230). What is [1]'s is the realization in integers, in the block parameter: configurations meeting every rotation's exact size condition at bounded slack `γ`, at every period.

## The obstruction, located

A note titled for one obstruction must say which it means. Macindoe's record carries four statements of where the difficulty lives, at four grades — a proved consumption identity, an organizing heuristic, an organizing observation, and one theorem — and this note's obstruction means the theorem: the closing sentence of Theorem 4.6 of [1], quoted exactly:

> "Uniform cycle exclusion therefore requires the divisibility system — equivalently, rigidity of the closed anchor walk `Σₜ ΔMₜ = 0`."

The sentence is [1]'s; its moral is older. In the cycle-length parameter, Halbeisen–Hungerbühler [8, p. 238] showed that size arguments "*cannot* be successful" and that further progress "would hence involve number theoretical arguments", reducing what remains to the divisibility condition at every rotation; in the parameter `m`, Simons–de Weger [6, p. 69] expected the same. [1]'s theorem carries the moral into the block parameter `p` (= `m`).

The gloss both records agree on: a cycle is a closed walk in the 2-adic anchor coordinate of [1]; counting bounds that walk's size and Theorem 4.6 caps counting; uniform exclusion requires "arithmetic (divisibility) input, not sharper counting" [1, abstract]. Neither record proves that requirement unattainable, or attains it. The obstruction is located, not overcome.

## The three faces

The second version owes each face a full section; here each gets one clause. **Size**, the archimedean face: how large a cycle's elements must be — where counting, irrationality measures and the verified range operate; the face the dichotomy caps. **Digits**, the 2-adic face: a cycle is a closed walk in the 2-adic anchor coordinate, and exclusion asks for the rigidity of that walk [1, §§3–4]. **The seam**, the local–global face: `q | R_r` is a linear condition, so it holds over ℤ exactly when it holds prime by prime — there is no local–global gap; the failure is local, at primes of `q`. Three faces, not three independent directions: they are faces precisely because they are not independent — each reads the same closure equation in a different completion. Everything deeper — exact per-step laws, the verified entries behind each face, the elementary front door (Gersonides, 1342/43) — is deferred to the second version, mapped by `NOTE.md`.

## Claims resting on the shared verification apparatus, named

The spine above rests on published papers and elementary reading. Two further claims rest on the collaboration's verification apparatus: the shared `LEDGER.md`, where every claim enters first and is verified independently on both sides — it carries *two keys* once each collaborator has verified it in his own stack, fresh code or proof, neither derived from the other — with the regime it was discharged in.

**The δ8 entry (`LEDGER.md`, L-A9): the analytic face of the size wall.** The claim: the Product-Bound route — closing the current window (the frontier and bound above) by improving effective irrationality constants for `log₂3` — cannot succeed: it needs a linear-form bound at exponent `c* ≈ 0.9617` — equivalently an irrationality measure `μ* = c* + 1 ≈ 1.96` — and Dirichlet's floor is `c ≥ 1` (`μ ≥ 2`): the route is shut for every constant, not merely for `log₂3`, by a few hundredths in the exponent. The entry's second half is marked *measured*: the open window widens as verification advances — the reachable scale grows at best like `X₀^{1/3}`, the demanded scale measured at `X₀^α`, `α = 0.482–0.511` over `X₀ ∈ [2⁷¹, 2⁴⁰⁰]` — a finite-range measurement, not a proof. Nothing in the entry is formalised, and nothing in it excludes a cycle; it closes one proof route. Grade at this writing: two keys on the Dirichlet half (Merle — exact arithmetic, written-ahead canaries; Macindoe — clean-room derivation, independently verified) — the current-window impossibility is unconditional theorem-grade; the measured half permanently a measurement.

**The machine-checked fragment (`LEDGER.md`, L-A8): T1's window closure.** The statement: *no positive cycle of the odd map with minimum element `≥ 2⁷¹` and at most `3.5032·10¹⁰` odd members* — the same count Hercher's `K` measures. The proof chain, ending in a finite discharge over the 22 in-window convergent denominators of `log₂3`, is formalised in Lean 4 in Merle's stack — fifteen kernel-checked theorems, zero `sorry`, no user axioms, committed axiom logs — except for two named continued-fraction glue facts, independently confirmed but outside the kernel claims. Macindoe's keys are scoped as the ledger scopes them: the mathematics of every link clean-room; the kernel claims by statement match and the committed logs — read, not built; no end-to-end machine checking is claimed or implied. The window sits strictly inside Hercher's bound on a stronger verification hypothesis: its value is the machine-checkable chain, not range.

## What this note does not do

It excludes no cycle beyond the record it cites, and the gap between a well-calibrated model and certainty stands on both sides: Macindoe's cycle front is parked under stated stopping rules, to reopen only with a divisibility-aware idea; Merle's formal cycle exclusions are conditional on Baker-type and verification hypotheses [1, Related work]. The second version owes the reader the faces in full; this one owes only honesty about its size: two pages, one obstruction, three faces, nothing excluded.

---

Benjamin James Macindoe · Eric Merle

This note is a collaborative effort of mutual verification. Each claim raised was independently verified by the other and attribution is made where it appears. The full record's details can be traced in `LEDGER.md`.

## References

[1] B. J. Macindoe, *Reduced coordinates for the Collatz map: exact per-step laws, anchor dynamics, and the limits of counting arguments for cycles*, v3, Zenodo, DOI [10.5281/zenodo.21730505](https://doi.org/10.5281/zenodo.21730505) (August 2026).

[2] C. Hercher, *There are no Collatz m-cycles with m ≤ 91*, J. Integer Seq. 26 (2023), Article 23.3.5; arXiv:2201.00406.

[3] D. Barina, *Improved verification limit for the convergence of the Collatz conjecture*, J. Supercomputing 81 (2025), article 810; DOI 10.1007/s11227-025-07337-0.

[4] The Collatz Conjecture Challenge, [ccchallenge.org](https://ccchallenge.org) — register entries `BohmSontacchi1978` (Formalised), `Knight2026` (Being formalised), `Eliahou1993` (Ready to be audited); consulted 2026-07-28.

[5] O. Rozier, *Problème de Syracuse : « majorations » élémentaires des cycles*, Singularité 2, no. 5 (1991), 8–11.

[6] J. Simons, B. de Weger, *Theoretical and computational bounds for m-cycles of the 3n+1-problem*, Acta Arith. 117 (2005), 51–70; DOI 10.4064/aa117-1-3.

[7] T. Brox, *Collatz cycles with few descents*, Acta Arith. 92 (2000), 181–188.

[8] L. Halbeisen, N. Hungerbühler, *Optimal bounds for the length of rational Collatz cycles*, Acta Arith. 78 (1997), 227–239; DOI 10.4064/aa-78-3-227-239.
