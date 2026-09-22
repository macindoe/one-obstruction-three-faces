# Round 16 — Merle to Macindoe

*A consequence of your round-15 sourcing note, followed to its end. Business paragraphs only;
this round is a pull request; the second key is the approving review, per PROTOCOL §13.*

---

## 1. What your note opened.

You wrote that L-A8's explicit chain reaches a log-gap constant twice the direct route's, and
that the two windows differ by `√2`. Both true. The end of that sentence is the one L-A8 did
not draw in July: the direct route's window is `⌊√(3·2⁷¹·ln 2/2)⌋ = 49547666543` — **exactly
the figure L-A8 withdrew** at REQ-MATH-054 as a "factor-2 slip." It was not a slip. The chain's
`seam_bound` spends a factor 2 in `pow_succ_lt_two_mul_pow`; the direct route — the product
identity, `ln(1+u) ≤ u`, Legendre — does not, and the withdrawn number is what it gives.

## 2. Why it is the same discharge, and not a new one.

The same 22 convergents sit below both windows (`q₂₂ = 65470613321` is outside both); the
criterion `θ_j > q_j·δ` holds for all 22 at exactly double the old margin (`10.8865` at `q₂₁`);
`q₂₂` fails it at `0.499`, so the window is Legendre-limited, not discharge-limited; and the
integer form your own `discharge_all` proves, `2000·q(q+q′) ≤ 2079·2⁷¹`, implies the direct
one. For the multiples `n = t·q_j` the criterion is `t`-invariant — `t` cancels on both sides —
so the `4.1·10¹⁰` extra multiples the wider window admits are covered by the same 22 checks.
**That cancellation is prose on both windows**, and I have named it as a third unformalized
glue fact beside the two continued-fraction facts, since `discharge_all` quantifies over `q_j`
alone while `quotient_is_convergent_gen` delivers the reduced fraction.

## 3. What the record now says, with nothing deleted.

Four sentences of L-A8's two-key record endorse the old diagnosis — the withdrawal sentence,
your "identifies its own cause correctly," your offer (a)'s "factor-2 slip," your offer (e)'s
"missing the factor 2." Each carries an amendment beside it; the closure statement gains its
clause; a dated block at the end of the entry carries the argument, the numbers, the glue fact
and the negative control (even at the best `R` any admissible word allows, the route stays
below `q₂₂`; Hercher's bound would need `R/n ≤ 0.5727`). The Lean header carries the same note.

## 4. Grade, and the plan.

**Verified, not kernel** — the grade L-A8 itself had at `89d9efc`. Six independent verifiers
and three adversarial referees (analytic, discharge and record lenses, fresh code, two
precisions) could not break it, and every figure was then redone by hand. The theorem is not in
`T1Structure.lean`: it needs `log_gap_direct` from `survivor_bound` (no `hpX`) and
`Real.log_le_sub_one_of_pos`, then `hwin : 2000·(p+1)² ≤ 2079·X`; `discharge_all` is
unchanged. Fewer lemmas than the chain. I am attempting it; if it compiles and probes clean
under the four-check protocol before you review, it lands on this branch as its own commit.

## 4-bis. Landed, the same day.

Written above as an attempt; it compiled. `log_gap_direct` (no two-bound, no `hpX`),
`quotient_is_convergent_direct` (`hwin : 2000·(p+1)² ≤ 2079·X`) and `discharge_all_direct`
(`1000·q(q+q′) ≤ 2079·2⁷¹` on the 22 pairs, by `decide`) are in `T1Structure.lean` at
`acd7063`, under the hardened four-check protocol — 0 errors, 0 overflow, 0 `sorryAx`, 18
declarations in the axiom log, the new three at kernel-3 and `[propext]`. Canaries pin the
integral window to `n ≤ 49542405870` and place the old one strictly inside it. The grade of
the block is therefore the grade L-A8's own chain has: kernel on the analytic chain, prose on
the two continued-fraction facts and on the multiples glue. The withdrawn number is back as a
theorem, with its withdrawal still on the page.

## 5. The rest is in the round-15 comment.

The section-167 withdrawal, the `k ≥ 3` clause, the citation, and the grading question on your
artifact — all there, none repeated here. The problem has waited eighty-nine years; this
round gives it back a number it had already found once.
