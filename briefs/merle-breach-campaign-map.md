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
counter-finding, carried open on round 13's record and settled in round 14's — is written into the ⊢ blocks
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
`k = 11`, two at `k = 12`, none again at `k = 14, 16` — non-monotonic, reproduced here exactly, with `k = 13` and `k = 15` (both none) added on this side and since confirmed on yours.
Your own operational note names the likely cause (the residue graph you had to specify keeps one
successor per node, where the relation has `2^v`), and you are right that this is what the keying
round must settle first. **Settled in round 14, and in your favour**: your figures reproduce
exactly on your object, and the cause is the one your own note named — the accelerated map with
a single canonical successor keeps the `m = 0` branch, and for `p = 3` the witness edge lives on
the other one at every `k` (not universally in `p`: L-A10 carries the count). Your measurement was right; the object was not ours. The resolution, the artifacts and the
two retractions it forced are in `LEDGER.md` **L-A10**, seeded at one key for yours.

**⊢ No metric descent of the excursion form (§80, §85).** The excursion is the maximum of a
multiplicative walk (×3/2 or ×1/2, each with probability ½ under the §75 bijection). Its tail
decays as `R^(−θ)` with `θ` the Cramér–Lundberg root of `(p/2)^θ + (1/2)^θ = 2`. At `θ = 1`
this is `(p+1)/2 = 2 ⟺ p = 3`: **`p = 3` sits exactly on the critical boundary** — excursion
finite (tail `1/R`) at `p = 3`, infinite at `p = 5, 7`. `θ = 1` exactly, verified. A metric
(single-clock) descent certificate therefore lives exactly at the edge where it is weakest,
which is why the metric route does not close.

## Three exact cross-domain facts (verified this round, one added in round 15)

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

**✓ Over `F₂[x]`, Collatz is a theorem — and the reason names the obstruction (added 2026-09-12).**
For the polynomial analogue `T(f) = f/x` if `x | f`, `((x+1)·f + 1)/x` otherwise, every `f ≠ 0`
reaches `1`: Hicks–Mullen–Yucas–Zavislak, *Amer. Math. Monthly* 115 (2008) 615–622, stopping time
`≤ deg(f)² + 2·deg(f)`; improved to `O(deg(f)^{1.5})` by Alon–Behajaina–Paran, arXiv 2401.03210
(2024). Reproduced here exhaustively (`run_123` P4): maximal stopping times `9, 15, 21, 29, 35, 43,
51` at degrees `4, 6, …, 16` — our journal had sampled `37, 39` for the last two; corrected. **The
mechanism, stated exactly:** a rise adds *exactly one* to the degree and a fall removes one, so
along an orbit the degree never exceeds its starting value — **the size face closes for free**, the
orbit lives in a finite set, and the theorem is the finite check that no other cycle sits inside it.
Over `ℤ` the rise adds `log₂3 = 1.58496…` bits: no finite box. *The polynomial world removes exactly
one thing — the irrationality of `log₂3` — and the conjecture falls.* This is the second, external
witness the campaign's §175 asked for, not for a theorem but for the diagnosis: REQ-067 on our
side (`log₂3` is a generic irrational, nothing to extract) and a literature that never worked on
our problem (1976→2025) say the same sentence.

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

Read together: the size/archimedean face is *balanced* (2, 3, 8), the arithmetic/2-adic face is
where the real obstruction sits (7), and the effective tools reach only the balanced face
(4, 5, 6, 9); 10 says why one more tool of the same kind will not change the reading. This is the same "one obstruction, three faces" the note maps, from the side of the
*tools* rather than the *problem*.

8. **Absence, not barrier (§167) — restated on the round-15 audit (2026-09-22).** For a gap word
   `g = (g₀,…,g_{k−1})` with `S = Σg = ⌈k·log₂3⌉`, the cycle numerator is
   `N(g) = Σ_j 3^{k−1−j}·2^{g₀+…+g_{j−1}}` (prefix sums), with `x₀·d = N(g)`, `d = 2^S − 3^k`, on every
   integer cycle (checked on `1, −1, −5, −7, −17, −25, −41`). Over all `C = C(S−1, k−1)` words,
   exhaustively at `k ≤ 15`: the residue `0` has count **exactly `0`** for `3 ≤ k ≤ 15` (as the machine
   verification already implies), and the residue counts are **not** Poisson(`C/d`) — under-dispersed
   from multiplicity `3` on (`k = 15`: `1,725,804 / 598,138 / 94,773 / 8,918 / 631 / 43` against
   `1,734,412 / 583,676 / 98,211 / 11,017 / 927 / 62`, i.e. `−0.5 / +2.5 / −3.5 / −19 / −32 / −31 %`).
   What survives of the diagnostic: `0` is one of the 71 % of residues with count `0` — undistinguished
   in that weak sense only; the collisions `N(g) ≡ N(g′) (mod d)` are a structured event, measured and
   not explained. (`run_125` P1–P3, published.)
   > **Withdrawn (2026-09-22).** As first written this item read: *"the counts of residues follow
   > Poisson(`C/d`) to `0.1 %` (`k = 15`: `1,735,122 / 582,630 / 98,147 / 11,440 / 905 / 64` against
   > Poisson `1,734,412 / 583,676 / 98,211 / 11,017 / 927 / 62`), and the residue `0` is undistinguished
   > — millions of residues share its count. … A theorem of equidistribution here would prove the
   > absence, not a wall."* Those are the figures of `run_120`, whose `corrsum` takes **suffix** sums,
   > `Σ_j 3^{k−1−j}·2^{g_{j+1}+…+g_{k−1}}` — not the cycle numerator: it is `≡ 0 (mod d)` at
   > `k = 3, 4, 5, 8, 11` where no cycle exists, and misses the doubled trivial cycle `(2,2)`. The
   > Poisson fit to `0.1 %` is a property of that other sum. Caught by the round-15 review's request for
   > an operational definition; `run_120.py` stays published with this note beside it.
9. **The reach of exact structure (§169):** the repeated-word law retires `5.1·10⁻⁸` of the admissible
   words at `k = 24` and none at half the lengths — exact, two-keyed, and not where cycles live
   (L-A2 scope note, figures corrected before sending).
10. **The second-witness criterion (§175) — the reading key of this map.** Every tool above speaks one
    language (trajectory, gaps, powers of 2 and 3, `corrsum`); descriptions in one language never
    contradict each other, and an exclusion needs two descriptions from disjoint routes that collide
    (`√2`: ratio *and* parity; Fermat: Frey curve *and* modularity). Six instruments, one witness.
    The first candidate second witness that exists is the `F₂[x]` fact above — and it witnesses the
    diagnosis, not the theorem.

## The reading for a second witness (2026-09-12) — what exists, and what it reaches

Under §175's criterion — a theorem that already exists, reached by a route that does not speak our
words, and able to collide with our description of a cycle — six languages were read at source
(logic and automata, S-unit equations, `×2×3` rigidity, `p`-adic methods, Mahler's `Z`-numbers,
combinatorics on words). **No second witness for the theorem. Half of one for a single word.
Three more for the diagnosis.**

- **Half a witness, and it lands on L-A11.** Knight, *Discrete Math.* 349 (2025) 114812: the cycle
  whose parity vector is the upper Christoffel word — the circularly balanced word — is never
  integral, by the reversal symmetry of Christoffel words, with no Baker input. With L-A2 reducing
  non-coprime `(S, k)` to the coprime case, **the balanced cycle is excluded at every length**, by a
  tool that is not ours. Foreign tool, our object; reach: circular words whose reverse is a
  rotation. Details and measurements in L-A11.
- **Logic.** Cobham (1969)–Semënov (1977): a set definable in base 2 *and* base 3 is semilinear.
  A January-2026 preprint (Dhiman–Pandey, arXiv 2601.12772 v2) shows the `k`-step transition
  relation of generalised Collatz, with `k` carried as `2^k`, is not definable in base-2 Büchi
  arithmetic — because it would define `{3^k}`; **its witness is our L-A10 residue**:
  `T^k(2^k·m − 1) = 3^k·m − 1` (checked, `run_124` P7). The `×2×3` obstruction, said in logic.
- **Computation.** Stérin–Woods (RP 2020, arXiv 2007.06979): the Collatz process *is* a
  base-3-to-base-2 converter; the cyclic conjecture is encoded there as a reachability problem;
  predicting half the bits of `T^i(x)` is in `NC¹` outside `AC⁰`.
- **The bridge that exists between words and the 2-adic face.** López–Stoll, *Integers* 9 (2009) #A13, 141–162:
  the 2-adic conjugacy image `Φ(v)` of a Sturmian word, computed as a generalised continued
  fraction; aperiodic `v` with eventually periodic `Φ(v)` remains unknown.
- **Not found**, stated so the next reader does not repeat it: no S-unit / subspace-theorem
  treatment of Collatz cycles; no Skolem–Mahler–Lech; no Ostrowski numeration in the Collatz
  literature (L-A8's grid seems to have no antecedent); Mahler's `Z`-numbers are a cousin
  (the `×3/2` map without halving), not a witness.

## Round 16 reading (2026-09-23) — what the new papers do and do not change

Swept 2025-01 → 2026-09-23 (six verifiers and two adversarial referees, then redone here). **Nothing
changes a ledger theorem.** In order of weight:

- **The one-move observation — a reformulation, graded as such.** For a parity word `w` of length `N`
  with `r` ones at `p₀ < … < p_{r−1}`, the cycle point is `C(w)/d`, `C(w) = Σ_j 2^{p_j}·3^{r−1−j}`,
  `d = 2^N − 3^r`. If two rotations of `w` differ by moving **one** 1 across `t` zeros, their `C`
  differ by exactly `2^p·(2^t − 1)·3^{r−1−j}`; an integral cycle would need `d | 2^t − 1`
  (`gcd(d, 6) = 1`). **`t = 1` is Knight's own argument** (his remark after Example 5.5: `u01` and
  `u10`, "whose simple difference provides the necessary contradiction"), and `t = 1` occurs exactly
  for the Christoffel necklace (Pirillo 2001, via Berstel 2007, Prop. 10). **`t = N − r` is the circuit,
  and `d | 2^{N−r} − 1` is Steiner's elementary reduction** (Knight §3; Simons–de Weger 2005, the
  `m = 1` chain equation). What the single statement adds is only a reading of *why* Baker is needed
  for one and not the other: the move length — `t ≤ 2` is unconditional, and at `t = N − r` the
  condition `d > 2^t − 1` is exactly Steiner's Diophantine regime. For `r ≥ 2` the class is exactly
  the necklaces whose cyclic zero-run sequence takes two values `a, a+t` and is balanced (near the
  seam: balanced blocks of 1s, every zero run equal to `t`); its share of primitive necklaces falls
  exponentially (`56 / 233,324` at `N ≤ 24`). **It excludes nothing Steiner and Knight did not**: every
  move length satisfies `t ≤ N − r`, so its class exclusion reduces to Steiner's inequality. The
  general-`t` statement and the characterization were not found in Knight, Fernández–Ibáñez,
  Simons–de Weger or the searches made — absence of evidence, not a novelty claim. (`run_126`, 13
  checks; characterization verified independently to `N ≤ 26`.)
- **Fernández–Ibáñez, arXiv 2607.24844 (July 2026) is a rediscovery.** Its main theorem — the
  Christoffel word uniquely maximizes the smallest cycle member at fixed `(N, r)` — is
  **Halbeisen–Hungerbühler, Acta Arith. 78 (1997), Lemma 5 + Corollary 1** (read at source: the same
  functional, the same ceiling word `s̃_i = ⌈in/l⌉ − ⌈(i−1)n/l⌉`), restated by Knight §4 with credit;
  F-I do not cite H-H and call theirs "the first result" of the kind. Its Theorem 8.1 (`N ≤ 2r`) and
  8.2 (Eliahou-type bound) follow in one line from the product identity. Also: a gap in the attainment
  step (repairable), a false closing claim at `N/r = 2` (the trivial cycle), and a strict inequality in
  Prop. 7.1 that fails exactly when `r | N`. Combining it with Knight changes no bound. Nothing for us.
- **Hochman, arXiv 2609.21481 (18 Sep 2026)** — zero-entropy progress in the right family: for
  multiplicatively independent `a, b` and a zero-entropy non-atomic `×a`-invariant `μ`, `μ`-a.e. point has
  a dense `×b` orbit. Not the `×2×3` measure rigidity the door below needs, and no bridge to cycles —
  but it is the first result in the zero-entropy regime we have seen move. Abstract read only.
- **Williams, arXiv 2607.01718 (July 2026)** — the coordinates `n = λ·2^a·3^b − 1` are the classical
  all-rise identity `T(x)+1 = (3/2)(x+1)` (Terras); its "why is `p = 3` special?" is answered by L-A10's
  shift: writing `(p−2)x + d = λ·2^a·p^b` diagonalises every `T_{p,d}`. Vocabulary, not leverage.
- **López–Stoll, arXiv 2101.12747 (2021)**, the same authors' follow-up to the *Integers* 9 paper above:
  aperiodic `v` maps to an aperiodic 2-adic integer when `liminf(h/l) > ln 2/ln 3`, with Sturmian parity
  vectors as the test case — the literature's nearest neighbour to L-A11's Sturmian word.
- **Diagnostic 8, one hypothesis tested and refuted.** *Is the true numerator's under-dispersion a range
  cap* — the cycle points `n₀ = N(g)/d` living in a short interval, so each residue can be hit at most once
  per integer? No: at `k = 15` the points span `[5, 2012]`, and a Poisson-binomial slot model built on the
  measured slot occupancies explains about a tenth of the deficit (multiplicity 3: observed `8,918`,
  slot model `10,762`, Poisson `11,017`). The under-dispersion stays measured and unexplained.
- Housekeeping from the same sweep: the archival verification bound is still `2⁷¹` (Barina 2025;
  the live counter stands at `2075·2⁶⁰`); ccchallenge lists Knight as *being formalised*, and Hercher 2023
  and Eliahou 1993 as *ready to be audited*; the Hercher corrigendum and the Lean kernel re-check are
  recorded in the ledger.

## The one door that stayed open

Across the whole campaign — and, from your record, across yours — exactly one native-infinity
instrument is neither closed nor blind: **Furstenberg's `×2×3` zero-entropy measure rigidity**
(open since 1967; Rudolph–Johnson 1990 needs positive entropy, which is exactly what this
problem lacks). It is `aeh.md` 13.6.7's "one missing genre of theorem", seen from the ergodic
side. Neither of us has the tool. If there is a next front, it is there. One precision from the reading: Furstenberg's *intersection* conjecture in the same family **is proved** — Shmerkin, *Ann. of Math.* 189 (2019) 319–391, and Wu, *Ann. of Math.* 189 (2019) 707–751: for `A` closed `×p`-invariant and `B` closed `×q`-invariant, `log p/log q ∉ ℚ`, `dim_H((uA+v) ∩ B) ≤ max(0, dim A + dim B − 1)` — a rigidity theorem that exists, in the right family, with **no known bridge** to a cycle. The zero-entropy *measure* rigidity is the part still open, and it is the part a cycle would need.
