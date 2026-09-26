# Round 17 — Merle to Macindoe

*An erratum to our own round-14 retraction, one source read at last, and some kernel work offered for
information. Business paragraphs only; this round is a pull request stacked on round 16 (PR #6, still
awaiting your review); the second key is the approving review, per PROTOCOL §13.*

---

## 1. The round-14 retraction of the phantom census was itself wrong in part.

**What round 14 said.** In R14 §3(a) and in L-A10 I withdrew *"100 % of the faulty residue cycles are
phantoms at `p = 7, k = 8`"* in full: `run_048.py` "does not run", its P3/P4/P5 "were never produced",
"the file never tests `p = 7`", the figure "has no artifact behind it", and "it was the report that did
not listen". I had re-run the committed file. I had not read the archived outputs.

**What the record shows.** On 2026-08-05 at 20:33:12Z the working session wrote `run_048.py` — the version
that walks the word backwards and halts on its canary C3. Forty-four seconds later, at 20:33:56Z, it ran a
**corrected version from standard input** (`python3 - <<'PY'`), which was **never saved as a file**. Its
output was archived as `OUT_BRECHE-048.txt`, which opens on "CANARIS (apres correctif)" and carries the
`p = 7` rows, and its fingerprint was registered the same day beside the buggy file's (`fbcd923987a75419`
for the output, `9348ec25689b6edb` for the file). The research journal (§96) records the C3 bug and then
"Corrigé." A follow-up output settled the run's own control P5: the two "unknown" integers it reported,
`−10` and `−136`, are the even members of the known cycles `{−5, −7, −10}` and `{−17, …, −136}` — its list of
known values held odd members only. The canary was heard; the fix ran within the minute; the code that ran
was not kept.

**Recovered and re-run.** The corrected code was recovered verbatim from the session record on 2026-09-25
and re-run: its output is **byte-identical** to the archived one, sha256 prefix **`fbcd923987a75419`**, equal
to the fingerprint registered on 2026-08-05. It is now `experiments/run_127.py` in
`ericmerle3789/one-obstruction-three-faces-lean` at `8cb8a98`, a header added on top and nothing
below it changed; `run_127_output.txt` has the same sha256.

**What it computes.** The object is §96's: the residue graph `G(p, k)` on `ℤ/2^k` of the Terras half map
`T_p` (`x/2` or `(px+1)/2`) carrying **both lifts** — arcs `u → T_p(r) mod 2^k` for `r ∈ {u, u + 2^k}`. A
bounded depth-first search closes simple cycles; a cycle of length `L` with `j` odd steps is **faulty** when
`p^j > 2^L`, and **realised** when the rational point of its word, `x_w = N_w/(2^L − p^j)`, is an integer.
At `p = 7, k = 8` the run reports **330 faulty cycles, 0 realised**.

**The independent re-enumeration.** Fresh code, which reads only `run_127`'s output to compare tables
(`run_128`). Under `u ↦` its first `k` parity bits, `G(p, k)` *is* the de Bruijn graph `B(2, k)` for every
odd `p` — the Terras 1976 / Lagarias 1985 bijection, same proof — so its simple cycles are the primitive
necklaces whose `L` cyclic `k`-bit windows are distinct, and they are counted as Lyndon words; a canonical
graph search gives the same cycle sets at all nine `(p, k)` for `L ≤ 12`. Result: **330 faulty, 0
realised, and the run's search is exhaustive for `L ≤ 11`** (its 3000-pop cap never binds: at most 2037 pops
per start; its 600-cycle stop never fires). **The scope first written for it — length `≤ 12` — is wrong:**
that is the bound of the committed file, not of the corrected run, which extends a path only while it has
fewer than 11 vertices; the correct label is `L ≤ 11`. The absent parity check is **redundant**: by the
bijection, `x_w` follows its word automatically (0 exceptions to `L = 22`). **The `k = 6` rows undercount by
one** — `64 / 217 / 266`, not `63 / 216 / 265` at `p = 3, 5, 7` — because the run keys cycles by their sorted
vertex set, which merges two distinct, non-realised faulty cycles, `01011101111 / 01011110111` (`L = 11`,
`j = 8`). A second merge, `00001000101 / 00001010001` (`j = 3`), exists but is faulty for no `p ≤ 7` and
changes no row (`run_129`). At `k = 8` no merge occurs before `L = 14`: **330 is the exact count.**
**Extension:** to `L ≤ 22`, `256 606` faulty cycles at `(7, 8)`, **0 realised** (and 0 at `k = 6, 10`). A
realised faulty cycle would be a negative integer cycle of `T_7`; none occurs among these words (words
whose `k`-bit windows repeat are closed walks, not simple cycles, and are outside the count). The control fails as it must: at `p = 3` exactly three are realised, at
`L = 1, 3, 11` — the cycles of `−1`, `−5` and `−17` — and no others up to `L = 22`.

**The referee check.** The lab's mathematical referee (RT-1) re-enumerated with its own code — graph
built from `T_p`, Lyndon words by Duval's algorithm, 401 428 words to `L = 22`, predictions frozen before
the run — and reproduced the run's table exactly under the run's key, the vertex set (`63/88/97, 216/268/281, 265/330/345`;
realised `3/1/0`), the `k = 6` merge, the 253 cycles added at `L = 12` and the `256 606 / 0` to `L = 22`. The
second merge above is its finding.

**What stands, what changes, what does not.**
- **Stands:** the committed `run_048.py` does not run (C3 halts it) and never tests `p = 7` — true of that
  file, and its retraction header stays. Our one-word repair of that file, which emitted `x = −6`, says
  nothing about the version that actually ran.
- **Also wrong, and found while preparing this round: the cause we gave for that `−6`.** R14 §3(a) and L-A10
  say the repaired file "solves the word's linear equation without checking that the trajectory's parities
  follow the word". A missing parity check cannot produce an integer off every cycle — by the bijection below,
  every integer `x_w` follows its word. The committed accumulator **omits the factor `p` on an ascent**
  (`(num + 1)/2` where `(p·num + 1)/2` is meant): with `reversed` removed, the word `110` at `p = 3` gives
  `−3` instead of `−5`, and `011` gives `−6` instead of `−10`. Checked with exact arithmetic on every word up
  to length 12 (`run_130`): the faulty accumulator emits ten integers lying on no cycle, `−6` among them; the
  corrected one emits only points of the known cycles, each following its word.
- **Changes:** "never produced", "no artifact behind it" and "the report did not listen" are false. The
  figure has an artifact after all. **Grade restored at its true scope: VERIFIED** — `p = 7, k = 8`,
  `L ≤ 11` exhaustive, this object (both-lifts graph, faulty = `p^j > 2^L`, realised = integer point);
  three independent codes; not kernel.
- **Does not change:** §96's argument never needed the census. L-A10's two lines need no cycle, and
  phantom-ness remains *beside the point*.

The error is ours, twice over: in August the corrected code was run and not saved; in September **the
retraction inspected the file, not the archived outputs**. A retraction needs the same diligence as a claim.

**What the record now says, with nothing deleted.** Beside each place that carries the withdrawal, a dated
amendment pointing here: the L-A10 bullet "The phantom census is withdrawn in full" in `LEDGER.md`; the end
of R14 §3(a); the withdrawal block and the cross-side paragraph of `briefs/merle-breach-campaign-map.md`
(whose "never computed at all" was also wrong; your own 100 % figure is on your single-successor graph, and
the two remain unrelated); and R13 §6, where the figure was first quoted.

## 2. Rhin 1987, read at the source.

The Proposition of Rhin's §4 (Progress in Math. 71, p. 160; read in the copy deposited by the author, whose
extraction carries no page numbers — Simons–de Weger's "Proposition on p. 160" fits its place), formula
**(7)**: for integers `u₀, u₁, u₂` with **`H = max(|u₁|, |u₂|) ≥ 2`**, `|u₀ + u₁·log 2 + u₂·log 3| ≥ H^(−13.3)`
— **no threshold, and constant 1**; the proof uses Dubois–Toffin's simultaneous approximations for
`q ≤ 7.32·10¹²`. Formula **(8)**: `≥ H^(−7.616)` for `H ≥ H₀`, with `H₀` said to be effectively computable
and **not given**. This confirms your adjudication of 2026-07-30 in L-A7, which rested on four printed
carriers and left the printed hypotheses unread: the only hypothesis is `H ≥ 2` (the record states no
condition on `H`, and writes `>` where (7) prints `≥`), the unknown threshold belongs to (8) alone — the
7.616 that Wu 2003 cites — and L-A7's use, `H = K₀ ≥ 952`, sits inside (7). No number moves; I have
not edited the entry. One sentence on a second source, because §3 leans on it: Tijdeman–Wang 1988, Lemma 1 (Ellison), prints "`x > 10`" but lists `(10, 6)` among its
exceptions and its proof treats `10 ≤ x ≤ 27`, so the only coherent reading is `x ≥ 10` — a misprint in
the source.

## 3. For information only: what the lab proved in the kernel since round 16.

No new mathematics claimed; offered in case any of it is useful to the note, graded as it stands, no
ledger change requested. All of it on **Lean 4.34.0 + Mathlib v4.34.0**, every constant except the
marker `Tstar_open` (below) within `[propext, Classical.choice, Quot.sound]`, cold-rechecked by the lab's
Lean referee (fresh olean directory, the workshop cache removed from the path). The files are in the artifact repository at
`recheck-v4.34/Labo/` (commit `8cb8a98`) (21 modules, the import closure of the four results below), with `LABO.md` for what
each proves and how to build it (`lake build Labo.<module>`). The one `sorry` in that tree is the open
target T★ in `Blueprint.lean`, a marker nothing downstream uses.

- **The bridge.** For a parity word `w` (`N` letters, `r` ones), `d(w) = 2^N − 3^r`,
  `C(w) = Σⱼ 2^{pⱼ}·3^{r−1−j}`: if the orbit of `x` follows `w`, then `T^N(x) = x ⇔ x·d(w) = C(w)`; and
  conversely any integer solution of `x·d(w) = C(w)` follows `w` and is an `N`-cycle (through the
  parity-bit bijection, proved for every odd multiplier). Consequence: "every word with `d > 0`, a `1`, and
  `d | C` is a rotation of `(10)^k`" is equivalent to "every positive cycle is `{1, 2}`". Classical; the
  cycle equation is the one L-A2 and L-A11 already use.
- **FEN.** Every nonzero integer cycle of `T` has `N ≤ 2r`, with equality only on `{1, 2}` — both signs, from
  `|3y + 1| ≤ 4|y|` and the product identity indexed by the orbit. Classical for positive cycles: Eliahou
  1993, Thm 2.1.
- **Knight in orbit form.** No positive cycle of `T` whose parity word is a rotation of the balanced
  (Knight, upper Christoffel) word with `gcd(N, r) = 1`, other than `{1, 2}`; also in cycle-equation form.
  **Knight's theorem was formalised earlier by another author**: `github.com/tcosmo/Knight2026_lean`
  (Lean 4.28, main theorem in the form of Knight's Thm 5.4); **not re-run by us, and its code not read** (we
  read its summary). By that summary, ours differs only in form (the whole rotation class, `x > 0` in
  place of `d > 0`, `r = 1` included), and the `gcd > 1` reduction L-A11 draws from L-A2 is not formalised.
- **The empty two-block rung (Ck2).** Call the phases of `w` the integers `r·pⱼ − N·j`; if
  `gcd(N, r) = 1` and they form two runs of consecutive integers, then no integer `x`, of either sign,
  satisfies `x·d(w) = C(w)`. It is FEN against a fact of words — two blocks force `N ≥ 2r + 1` — so the rung
  is empty and consumes nothing of 3 beyond `3 + 1 ≤ 2²`. It is false for `5x+1` (`11000`).
- **On paper, signed by the lab's referee (not kernel).** No cycle with **three** phase blocks
  (`gcd(N, r) = 1`), both signs, **modulo Tijdeman–Wang Lemma 1 (Ellison)**: a normal form of three-block
  words and a size bound on `|d|` exclude every `N ≥ 28`, and the four remaining points `(5,3), (8,5), (11,7),
  (19,12)` are excluded by exact check; a second proof goes through Hadamard's inequality. Ellison's own proof
  is second-hand to us, and one step the referee named — a nonzero integer cycle other than `{−1}` has
  `N > r` — is still to be written into the proof.

## 4. What is asked of you.

The second key on **§1 only**: the erratum, the five in-place amendments (in four files), the amended header of `run_048.py`
(artifact repository, nine comment lines added, nothing removed), and `run_127`–`run_130` with their
outputs. §2 and §3 are for information; nothing in them asks for a key or a ledger line.

The problem has waited eighty-nine years; this round returns a number that was right all along, and only
mislaid.
