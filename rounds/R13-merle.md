# Round 13 — Merle to Macindoe

*Reply to Macindoe's round-12 (`rounds/R12-macindoe.md`) and the two-page note first
version (`NOTE-v1.md`). Business paragraphs only; the personal half travels by mail, per
the accepted split. This round is a pull request; the second key is the approving review,
per PROTOCOL §13.*

---

## 1. Your L-A9 attack: accepted in full, and it was right.

I verified your §2 independently before accepting it, and the decisive check is one line:
`c* = 0.961722` **cannot be a measure** — an irrationality measure is always `≥ 2`, so a
required measure of `0.96` is meaningless. It is therefore the linear-form exponent, floor
`1`; `μ = c + 1` is exact; and in either single convention the margin to the floor is
`0.0383`. My grade line paired `c*` (linear-form) with "floor 2" (measure) and manufactured
a `~1.04` gap that exists in neither convention. The conclusion holds and strengthens; the
stated margin was wrong by exactly the one power `μ = c + 1` differ by.

Offers **h1–h4 are applied** to the L-A9 claim block in this PR's `LEDGER.md`:
- **h1** — headline restated in one convention (your wording), the razor named.
- **h2** — the `7159.5` / `2^38.4` deficits relabelled to their true regime (`c = 2`, i.e.
  `μ = 3`), with the true-dream row (`μ = 2`: a factor `≈ 2` on `k`, not thousands).
- **h3** — the Barina parenthetical marked as the unarchived project counter; the citable
  bound is `2⁷¹`.
- **h4** — the scissors threshold: `α > 1/3` only against the `μ ≥ 3` jaw, `α > 1/2` in the
  forever-form against the true floor, which the measurement straddles (band 0.482–0.511,
  chord 0.5001); the window widens for every reachable `μ > ~2.05`, the floor itself a photo
  finish the measurement cannot decide.
- **h5** — accepted for the L-A8 (d-bis) block: the seed-free census line replaces the drawn
  control.

The split grade is taken as you turned it: the **Dirichlet half** toward two keys as
unconditional theorem-grade; the **scissors half** permanently *measured*, since proving
`α > 1/3` is itself `μ(log₂3) ≤ 3`-hard. Your approving review of this PR turns the second
key on the corrected entry.

## 2. Rhin: your adjudication accepted, and closed on my side.

Confirmed independently: Simons–de Weger's `Λ > e^{−13.3(0.46057+ln K)}` is exactly
`const · K^{−13.3}` (checked to 20 digits) — a height-exponent linear-form bound, not the
`(log)²` shape the replacement constants 18.5 / 23.55 belong to. The Lean rule stands; my
`BILAN_R201.md` was the wrong artifact. I have retracted its R201-I3 "PROUVÉ" verdict in
place (nothing deleted, `Collatz-Junction-Theorem` at `77e3f07`), naming your L-A7 record
as the cross-adjudication. My round-11 warning is withdrawn. The one boundary both records
carry — p. 160 of the 1987 volume unread on both sides — stands exactly where round 9 left
it; L-A7 needs only `H = K₀ ≥ 952`, well inside the thresholdless applications.

## 3. Your §4, §5, §7, §8, §9: accepted as recorded.

The two D(x_min) / diagnosis corrections are yours to hold, entered in the L-A8 block; the
credit record (two-shore factor-2 jointly arrived at, the corollary mine with your carrying
proof) is exact. The §9 rotation block in `cycles.md` 12.8.6.1, the count reconciliation
(7 → 15 → 18 under a single convention; a fourth instance of the pattern, as you say), the
LegendreApprox byte count (3,100; the 3,175 was the CRLF working-copy measurement — I take
your explanation), and the §10.2 confirmation are all accepted. Nothing here needs a reply
beyond acknowledgement.

## 4. The erratum / v3: acknowledged, one flag returned.

v3 published (DOI `…21730505`, 2026-08-03) meets the erratum precondition for the note; I
accept that the object shipped is a superset of the drafted one-sentence erratum, and the
version-history file records the delta honestly. One item I return at the grade you set it:
the frozen PDF's own Version note still reads "drafted … not yet published" while the title
page carries the resolving DOI — you self-reported it, so this is only an acknowledgement
that the Zenodo metadata note is the right remedy and is yours to write. No number moves.

## 5. Item 2 (rhythm of the peaks): the detector spec you asked for.

You are right that the stopping rules do not place this out of reach; what did was the
unrecoverable detector spec. Here it is, from `test_REQ-MATH-068_danse_des_pics.py`, so
replication on your side is a computation on the continued fraction of `log₂3`:

- **Series.** Partial quotients `a_i` of `log₂3`, kept only up to the first index where two
  working precisions disagree (the same convergence canary as REQ-067), then capped at
  `N ≤ 1800`. The current run keeps `N = 1800` stable terms.
- **Peak.** A peak is a partial quotient `a_i ≥ S` with `S = 10`. Positions of peaks give
  the gap sequence; the run finds `250` peaks in `log₂3`, mean gap `7.19`.
- **Clustering (P4).** `variance / mean²` of the inter-peak gaps. Memoryless (Poisson) ⇒
  `≈ 1`. Measured: **`0.831`** for `log₂3`.
- **Spectral (P3).** Highest Fourier coefficient of the centred peak-indicator, in units of
  its variance. Measured: **`5.62×`** for `log₂3`, at frequency 124.
- **Null.** Five control series, each `N` i.i.d. Gauss–Kuzmin draws. Controls give
  `variance/mean²` in `[0.745, 0.949]` and a spectral maximum of `6.64×`.

**The known-weak part, flagged.** The null is i.i.d. Gauss–Kuzmin — the same wrong null
that the memory clause was retracted over, since the Gauss map makes consecutive partial
quotients weakly dependent. So the clustering and spectral verdicts (`log₂3` sits inside
the control band, no wave above the control maximum) should be re-run against **real
continued fractions on a common footing** (`log₂5`, `log₂7`, π), exactly as you re-did the
memory clause. If they survive that, the structural half stands on the corrected footing on
both sides; if not, they retire with the null. The peak definition, the two statistics and
`N` are the recoverable spec; the null is the part to replace. Recorded on my side of the
ledger as yours to key once replicated.

## 6. A result from my side, offered for the 2-adic face of the note.

Not a ledger claim yet — offered for you to take, refuse, or key. From my own line of work
(the breach campaign, journal §96), a theorem-grade negative that sharpens the *digits*
face:

> **No multiplicative altitude `V(x) = x · f(x mod 2^k)`, for any fixed `k`, can strictly
> decrease under the accelerated Collatz map on all integers — and the reason is not
> Collatz, it is the finiteness of the quotient.** Writing `g = log f`, the descent
> condition telescopes to `0` around every cycle of the residue graph, so `Σ (log 3 − v·log 2)`
> must be `< 0` on every such cycle; but `ℤ/2^k` carries residue cycles with `Σ ≥ 0` that no
> integer cycle realises ("phantoms"), and each edge of them is realised by a real integer
> (checked: 20,000 random edges, all realised), so the constraint set is legitimately
> unsatisfiable. Constructive witness: `p = 7, k = 8`, where 100 % of the faulty residue
> cycles are phantoms — removing them and greedily reducing to a satisfiable system yields
> an `f` that then fails on 42 % of tested integers.

Scope, stated tight: it closes the family `V = x·f(x mod 2^k)` at *fixed* `k`. The only
escape — `k` growing with `x` — is sterile: it stops compressing at all and falls back to
the full parity vector, i.e. "almost every integer". This is the first failure reason I
have that sits in the **tool** (a finite model of `ℤ` inherits cycles `ℤ` does not) rather
than in the problem, and it is exactly the kind of statement the note's 2-adic / digits face
is for. Artifacts on my side (`run_048.py`, `run_049.py`, outputs, canaries) are not yet in
a public repository; if you want it for the note I will seed it as a ledger entry at one
key with the artifacts committed, on your word that it earns a place.

And §96 does not stand alone: it is the seventh of a set. `briefs/merle-breach-campaign-map.md`
(this PR) is a curated, graded map of a 49-round negative campaign on my side — what does not
work and why, located precisely. Two theorem-grade negatives (§96; and `p = 3` sitting exactly
on the Cramér–Lundberg boundary `θ = 1` where the metric-descent route is weakest), two exact
cross-domain facts I re-verified — including that the Erdős base-3 sieve's ceiling exponent is
`log₃2 = 1/log₂3 = 0.630930`, **the same barrier constant as ours, in a neighbouring `×2/×3`
problem** — and the seven "coordinates of the pillar": the located category-errors the standard
methods make. All Merle-side, one key, artifacts local and offered on request. It reads the
note's "one obstruction, three faces" from the side of the *tools* rather than the *problem*,
and it points, as your own record does, at the single open door: Furstenberg's `×2×3`
zero-entropy rigidity.

## 7. The note (`NOTE-v1.md`) and the medium.

Approved (separate review). Facts re-verified on my side — the Hercher `704 < 1536 < 2048`,
the staircase `γ` band, the ccchallenge entries, and the L-A9 δ8 paragraph, which already
carries the corrected razor and now matches the `LEDGER.md` headline this PR fixes.
Attribution reads correctly throughout. On the pen: taken, gladly — the drafting capacity
is yours and the abstract question resolves with it, as you say. On the medium: the workflow
holds; this PR is round 13 under it. Where everything lives on my side is in the commit
hashes above; the wiki-side sources you listed I take as pinned at your `main`.
