# Merle side — the breach campaign: a map of what does not work, and why

*Offered for the joint note's obstruction-mapping genre. This is a curated digest of a
49-round negative campaign (my research journal, `Collatz-Racine-Mur`, §53–§96, 2026-07-29
→ 2026-08-01); the raw journal, with the full derivation trail and the false starts and
retractions, stays local and is available if you want the path rather than the map.*

**Grading and provenance, up front.** Everything here is **Merle-side, one key**, and the
supporting scripts are **local, not yet in a public repository** — I will commit any
specific one you want to key. Two items are theorem-grade and were **offered for cross-side
verification** this round (marked ⊢) — as first written this sentence said "verified
cross-side this round," which outran its own clock: cross-side verification was what the
round was asking for, not what had already happened when the map was drafted. Your round-13
review has since taken the invitation up, and what came back — including one genuine
counter-finding, carried open on this round's record — is written into the ⊢ blocks
themselves. Two more are exact cross-domain facts I re-verified before writing this
(marked ✓); the rest is a **diagnostic map**, not a set of theorems — located observations
about where the resistance lives, at the grade the note's "map an obstruction" genre asks
for. Nothing here excludes a cycle.

---

## Two hard negatives (theorem-grade)

**⊢ Finiteness of the quotient (§95–§96).** No multiplicative altitude `V(x) = x·f(x mod 2^k)`,
for any *fixed* `k`, can strictly decrease on the positive integers under the Terras half map
`T` — and the reason is not Collatz, it is that a finite window on the last `k` bits cannot see
the sign. **Two lines, one integer comparison.** Since `p − 2` is odd, set
`r_p = −(p−2)^{−1} mod 2^{k+1}` and `u_p = r_p mod 2^k`; `r_p` is odd, so for every positive
`x ≡ r_p (mod 2^{k+1})` we get `x ≡ T(x) ≡ u_p (mod 2^k)` with `T(x) > x` whenever `p > 2`.
The two points carry the *same* `f`, so `V(T(x)) > V(x)`. For `p = 3`: `u_p = 2^k − 1`, and
`511 → 767` at `k = 8`, both `≡ 255 (mod 256)`. `ℤ/2^k` does not distinguish `2^k − 1` from
`−1`, and `−1` is a genuine fixed point of `3x+1` — the quotient inherits, as a loop, the
shadow of a real fixed point living where the altitude is not defined. The only escape, `k`
growing with `x`, is sterile — it stops compressing and falls back to the full parity vector,
i.e. almost every integer — and that last clause is prose, not an artifact. *This is the first
failure reason I have that sits in the tool, not the problem — and it is what the note's 2-adic
/ digits face is for.* Full entry, artifacts and scope: `LEDGER.md` **L-A10**.

> **Withdrawn (2026-09-03).** This paragraph previously ran the argument through a census of
> "phantom" residue cycles and quoted *"100 % of the faulty cycles at `p = 7, k = 8`"*. **That
> figure is withdrawn, not corrected**: re-running its artifact for the round-14 delivery showed
> the script halts on its own canary and had never produced the census at all, that the census is
> wrong again once the halting bug is fixed, and that the file never tests `p = 7`. It also said
> "the accelerated map", which is not the map §96 works on. Nothing in the conclusion depended on
> any of it — the standing run's own argument is that phantom-ness is *beside the point*, since
> every edge is realised by real integers (20,000 checked). Kept visible rather than deleted, and
> detailed in L-A10.

**Cross-side, round 13 — what came back (2026-09-03).** Your review reconstructed the
telescoping mechanism independently, and it reproduces exactly at `p=7, k=8`: 4 residue cycles,
3 faulty, at `(L,K) = (3,4), (4,8), (31,67)` — **that** much confirmed a third time here, cycle
for cycle, lengths and valuation sums identical. Your accompanying bounded search found those
three faulty cycles to be 100% phantom; **that figure is yours, on your object, and this side has
not reproduced it** — it should not be read as related to the withdrawn census above, which was
mine, on a different graph, and never computed at all. Carried alongside it, at the grade you set
it: your reconstruction **does
not reproduce for `p=3` at small `k`** — no faulty cycle for `k = 4..9`, one at `k = 10` and
`k = 11`, two at `k = 12`, none again at `k = 13..16` — non-monotonic, reproduced here exactly.
Your own operational note names the likely cause (the residue graph you had to specify keeps one
successor per node, where the relation has `2^v`), and you are right that this is what the keying
round must settle first. **Settled in round 14, and in your favour**: your figures reproduce
exactly on your object, and the cause is the one your own note named — the accelerated map with
a single canonical successor keeps the `m = 0` branch, and the witness edge lives on the other
one. Your measurement was right; the object was not ours. The resolution, the artifacts and the
two retractions it forced are in `LEDGER.md` **L-A10**, seeded at one key for yours.

**⊢ No metric descent of the excursion form (§80, §85).** The excursion is the maximum of a
multiplicative walk (×3/2 or ×1/2, each with probability ½ under the §75 bijection). Its tail
decays as `R^(−θ)` with `θ` the Cramér–Lundberg root of `(p/2)^θ + (1/2)^θ = 2`. At `θ = 1`
this is `(p+1)/2 = 2 ⟺ p = 3`: **`p = 3` sits exactly on the critical boundary** — excursion
finite (tail `1/R`) at `p = 3`, infinite at `p = 5, 7`. `θ = 1` exactly, verified. A metric
(single-clock) descent certificate therefore lives exactly at the edge where it is weakest,
which is why the metric route does not close.

## Two exact cross-domain facts (verified this round)

**✓ The Erdős base-3 barrier is the Collatz barrier.** For every *odd* `n`, `2^n ≡ 2 (mod 3)`,
so the last base-3 digit of `2^n` is 2 (never 0) and the Erdős base-3 conjecture holds in one
line; the three known exceptions (0, 2, 8) are all even. The congruence sieve then gives an
exact density of undecided `n` at level `k` of `(1/2)·(2/3)^(k−1)` (exact count `k = 1..14`,
99.743% decided at `k = 14`), so the exceptional set has **density zero** (elementary). And
the sieve's ceiling exponent is **`log₃2 = 1/log₂3 = 0.630930`** — the *same* barrier constant
that governs `log₂3` in the cycle problem, appearing here in a neighbouring `×2/×3` problem.
The zero-entropy `×2×3` obstruction is not ours alone; it is the shared floor of this family.

**✓ `x* = 7/3`, the sign/drift crossover.** The per-step sign information equals the drift
exactly at `x* = 7/3` (`(3+3/7)/(3−3/7) = 4/3`, `log₂(4/3) = 2 − log₂3`); `x = 1` is the only
odd positive integer above the crossover, i.e. the trivial cycle. (This is the corollary
already in the L-A8 block — recorded here only because it is the archimedean-face anchor of
the same map.)

## The diagnostic map — the seven located reasons the wall resists

Not theorems; a cartography, one key, offered for the note's spine. Each is a *category error
a method makes*, located precisely:

1. **Dimension (§14):** dimension 0 ≠ finite — the object is thin, not small.
2. **Density (§75):** density 0 ≠ empty — the counting face is exactly balanced, not closed.
3. **Arithmetic (§73):** the descent obstruction is independent of `p` — the tool is blind to
   the very arithmetic that would distinguish `3x+1`.
4. **Effectivity (§76):** the effective Diophantine tool exists, but only bites *where the
   object already closes* — this is the L-A9 razor, from the tool's side.
5. **Range/scope (§82):** none of the standard instruments measures its own applicability —
   they report a verdict without reporting whether they were entitled to.
6. **Logical form (§88):** the available tools produce *density* (almost-all) statements; the
   problem asks a *pointwise* (every-`n`) question. The genre does not match.
7. **Finiteness of the quotient (§96):** every finite model of `ℤ` inherits cycles `ℤ` does
   not — the ⊢ result above, seen as the seventh coordinate.

Read together: the size/archimedean face is *balanced* (2, 3), the arithmetic/2-adic face is
where the real obstruction sits (7), and the effective tools reach only the balanced face
(4, 5, 6). This is the same "one obstruction, three faces" the note maps, from the side of the
*tools* rather than the *problem*.

## The one door that stayed open

Across the whole campaign — and, from your record, across yours — exactly one native-infinity
instrument is neither closed nor blind: **Furstenberg's `×2×3` zero-entropy measure rigidity**
(open since 1967; Rudolph–Johnson 1990 needs positive entropy, which is exactly what this
problem lacks). It is `aeh.md` 13.6.7's "one missing genre of theorem", seen from the ergodic
side. Neither of us has the tool. If there is a next front, it is there.
