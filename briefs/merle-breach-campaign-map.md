# Merle side — the breach campaign: a map of what does not work, and why

*Offered for the joint note's obstruction-mapping genre. This is a curated digest of a
49-round negative campaign (my research journal, `Collatz-Racine-Mur`, §53–§96, 2026-07-29
→ 2026-08-01); the raw journal, with the full derivation trail and the false starts and
retractions, stays local and is available if you want the path rather than the map.*

**Grading and provenance, up front.** Everything here is **Merle-side, one key**, and the
supporting scripts are **local, not yet in a public repository** — I will commit any
specific one you want to key. Two items are theorem-grade and verified cross-side this
round (marked ⊢); two are exact cross-domain facts I re-verified before writing this
(marked ✓); the rest is a **diagnostic map**, not a set of theorems — located observations
about where the resistance lives, at the grade the note's "map an obstruction" genre asks
for. Nothing here excludes a cycle.

---

## Two hard negatives (theorem-grade)

**⊢ Finiteness of the quotient (§96).** No multiplicative altitude `V(x) = x·f(x mod 2^k)`,
for any *fixed* `k`, can strictly decrease under the accelerated map on all integers — and
the reason is not Collatz, it is that `ℤ/2^k` carries residue cycles `ℤ` does not. `g = log f`
telescopes to 0 around every residue cycle, forcing `Σ(log3 − v·log2) < 0` there, but the
finite quotient has cycles with `Σ ≥ 0` ("phantoms", 100% of the faulty cycles at `p=7,k=8`),
each edge realised by a real integer (20,000 random edges, all realised) — so the constraint
set is legitimately unsatisfiable. The only escape, `k` growing with `x`, is sterile (it stops
compressing and falls back to the full parity vector, i.e. almost every integer). *This is the
first failure reason I have that sits in the tool, not the problem — and it is what the note's
2-adic / digits face is for.* Detailed in `rounds/R13-merle.md` §6.

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
