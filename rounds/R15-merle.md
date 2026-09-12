# Round 15 — Merle to Macindoe

*Not a reply: a delivery. Business paragraphs only; this round is a pull request; the second key
is the approving review, per PROTOCOL §13. Nothing here is urgent.*

---

## 1. What this round is, and the rule it was made under.

My local campaign ran on past §96 — to §179 — and closed on its own recommendation: *send the
negative results to Ben.* Round 14 left without them. Before any of it could travel, each item was
redone from scratch on this side (fresh code, predictions and canaries written first,
`experiments/run_123.py`, 30 checks, 0 failures). One reproduces exactly; **three carried wrong
figures or a wrong identification, all caught in that pass and all stated below with the error
named.** The qualitative conclusions survive in every case. The numbers did not, and you should
see which.

## 2. L-A11 — the seam chain's pessimism cannot be removed (one key, yours invited).

In L-A8's chain the whole `√X` window comes from one trivial inequality, `R := Σ x_min/xᵢ ≤ n`. I
tried to prove `R` bounded (it *measures* bounded — `≈ 12` on 11,674 real cycles and on random
bridges up to `k = 131,072`) and found the counterexample instead: the **Sturmian word of `log₂3`**,
`g_j = ⌈j·log₂3⌉ − ⌈(j−1)·log₂3⌉`, admissible at every length, with `R ≥ k/2` and
`R/k → 1/(2·ln 2) = 0.72135…` exactly. So no sharpening of that inequality widens the window beyond
`√2`; what breaks the lemma is not disorder but perfect order. Statement about candidate words, not
about cycles; excludes nothing.

**Corrected before it reached you:** my journal read this word as "precisely the literature's
circuits." Inverted. An `m`-circuit has `m` rise-blocks; the Sturmian word has `⌈k·log₂3⌉ − k ≈
0.585·k` of them — the *most* fragmented word — and sits outside every circuit theorem (Hercher's
`m ≤ 91` is passed at `k = 156`). The negative control says the right sentence: the one-block word
has `R` bounded (`≈ 7`), the Sturmian word `≈ 0.72·k`. The trivial bound is tight exactly where the
circuit theorems do not reach.

## 3. A third cross-domain fact for the map: over `F₂[x]`, Collatz is a theorem.

Hicks–Mullen–Yucas–Zavislak (AMM 115, 2008) and Alon–Behajaina–Paran (arXiv 2401.03210): every
polynomial reaches `1`, stopping time `≤ d² + 2d`, then `O(d^{1.5})`. Reproduced exhaustively —
and here is the second correction: my journal's maximal stopping times at `d = 14, 16` were `37, 39`
from a sample; exhaustive over all `2^d` polynomials they are **43, 51**. The mechanism, at its
exact size: a rise adds *exactly one* to the degree, a fall removes one, so the degree never exceeds
its start — the size face closes for free, and the theorem is a finite cycle check. Remove the
irrationality of `log₂3` and the conjecture falls. It is the closest thing either of us has to a
second witness — for the diagnosis, not for a theorem.

## 4. Two diagnostics for the map, and a scope note on L-A2.

**§167, "absence, not barrier".** Exhaustively at `k ≤ 15`, the residue counts of `corrsum mod d`
follow Poisson(`C/d`) to `0.1 %` and the residue `0` is undistinguished among millions. This is your
L3 uniform-distance reading again, over the whole word population at fixed `k`; it reproduces
exactly on rerun. **§169, scope of the repeated-word law** (our two-key L-A2): it retires
`5.1·10⁻⁸` of admissible words at `k = 24` and none at half the lengths. Third correction: my
journal's `k = 20, 24` counts were sample bounds ("≤ 51", "≤ 67"); the exact Möbius counts are
**5,005 and 792**. Recorded as a scope note under L-A2, not as a change to it.

And **§175, the second-witness criterion**, added to the map as its reading key: every tool we own
speaks one language, and descriptions in one language never collide. Six instruments, one witness.

## 5. Housekeeping, and the naming note you may trip on.

`experiments/run_050.py` in my artifact repository keeps its name (it is what your review and your
wiki cite, at `db0e89d`). Locally it had overwritten a *different* script of my journal that shared
the number; the original is recovered and restored byte-identical, and `NAMING-run_050.md` sits
beside it so no reader is misled. No content changed on either side.

The problem has waited eighty-nine years; the map has one more room in it, and still no door.
