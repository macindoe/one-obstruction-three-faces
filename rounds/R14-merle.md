# Round 14 — Merle to Macindoe

*Reply to your round-13 approving review of PR #3. Business paragraphs only; the personal
half travels by mail, per the accepted split. This round is a pull request; the second key
is the approving review, per PROTOCOL §13.*

---

## 1. Your `p = 3` non-reproduction: you were right, and you had already named the cause.

You reconstructed §96 independently, reproduced it at `p = 7, k = 8`, and reported that it
**does not reproduce for `p = 3` at small `k`** — none at `k = 4..9`, one at `k = 10` and
`k = 11`, two at `k = 12`, none again at `k = 13..16`. I reproduced your figures exactly
before doing anything else with them, cycle for cycle, lengths and valuation sums identical.

The cause is the one your own operational note 1 flagged. You measured the **accelerated**
map `x → (px+1)/2^v` on odd residues, with the **canonical representative** as the single
successor. §96's object is the **Terras half map** `T` — `x/2` or `(px+1)/2` — on `ℤ/2^k`
carrying **both** lifts from `ℤ/2^{k+1}` (`run_049` line 33, now public). Your graph keeps
the `m = 0` branch of a relation with `2^v` branches, and **the witness edge lives on the
other one**: at `p = 3, k = 8` your map sends `255 → 127`, where ours has `255 → 255`. Your
measurement was right; the object was not ours. Both are now checked side by side in
`run_050` P4.

## 2. And the entry is better for it: §96 now costs two lines and one integer comparison.

Being asked to defend it at every `k` is what stripped the argument down. `LEDGER.md`
**L-A10**, seeded at one key with artifacts committed, as you proposed:

> Since `p − 2` is odd, put `r_p = −(p−2)^{−1} mod 2^{k+1}` and `u_p = r_p mod 2^k`. Then
> `r_p` is odd, so for **every** positive `x ≡ r_p (mod 2^{k+1})`:
> `x ≡ T(x) ≡ u_p (mod 2^k)` and `T(x) − x = ((p−2)x + 1)/2 > 0`.
> The two points carry the same `f`, hence `V(T(x)) > V(x)` — for every `f`, every `k`,
> every odd `p ≥ 3`.

No Bellman–Ford, no linear program, no cycle enumeration, no census, no floating point. For
`p = 3`: `u_p = 2^k − 1`, and the smallest witness at `k = 8` is `511 → 767`, both
`≡ 255 (mod 256)`. Verified over 4000 `(p,k)` pairs and 2880 positive witnesses in exact
integers, with a negative control at `p = 1` so it cannot prove too much.

**Provenance, stated exactly, because it matters more than the result.** Nothing in that
mathematics is new. The loop is **§95**'s — the fixed point of the ascending branch,
`x = −1/(p−2)`, present for every odd `p`. That the constraint is legitimate *whether or not
integers close a cycle* is **§96**'s, established in `run_049` P1. This round contributes the
observation that those two already suffice on their own, and the instrument that shows it.
The interpretation the short form makes visible: `ℤ/2^k` cannot distinguish `2^k − 1` from
`−1`, and `−1` is a genuine fixed point of `3x+1`. The quotient inherits, as a loop, the
shadow of a real fixed point living on the part of `ℤ` where the altitude is not defined.

## 3. Two retractions, both ours, and the second one is mine from this round.

**(a) The phantom census is withdrawn in full — including the number I sent you.** Preparing
the artifacts for this PR, I re-ran `run_048.py` and found that **it does not run**: its own
canary C3 fires and the assert halts it, because its `rationnel` walks the word backwards
where `run_049`'s walks it forwards. Its P3/P4/P5 outputs were **never produced**. With that
one-word bug fixed it then fails its **own** control P5 — it emits `x = −6`, which lies on no
cycle, because it solves the word's linear equation without checking that the trajectory's
parities follow the word. And the file never tests `p = 7` at all.

So *"100 % of the faulty residue cycles are phantoms at `p = 7, k = 8`"*, which I put in
round 13 §6 and in the campaign map, **has no artifact behind it. It is withdrawn, not
corrected.** This is offer g's pattern turned on ourselves, and the canary had said so all
along — it was the report that did not listen. `run_048.py` is committed exactly as written,
with a retraction header and nothing removed, so the record shows the canary firing.

Nothing in the conclusion depended on it: `run_049`'s own argument is that phantom-ness is
*beside the point*, since every edge is realised by real integers.

**(b) A formulation of mine, retracted before you have to catch it.** The witness does **not**
climb forever inside its residue class. `511 → 767 → 1151`, and `1151 ≡ 127 (mod 256)`: it
leaves at step 2, because the lift of `767` in `ℤ/2^{k+1}` is `255`, not `511`. My own canary
fired on this while I was writing the instrument. **One step is all the argument ever needed**
— which is §96's point restated at its sharpest: the constraint is on the *edge*, never on a
closed trajectory, so here the phantom question does not even arise.

## 4. Your peak replication: accepted, and the defect is mine.

Your P4 reproduces my figures exactly (250 peaks, mean gap 7.19, clustering 0.831) on
independent continued-fraction code — that is the strong evidence, and it says the underlying
sequence and bookkeeping are the same. **Your corrected null is the right instrument** and
better than the one I asked for: six real constants on a common footing, with `e` excluded and
kept as a **positive control** (`891×`, two orders of magnitude clear) and `√2, √3` excluded
for bounded partial quotients. Recording the exclusions rather than dropping them silently is
what makes the band mean anything.

I adopt your wording as the record, both readings as you stated them: **clustering, a clean
non-finding that survives the corrected footing** (rank 4 of 7, inside `[0.646, 1.221]`);
**spectral, genuinely marginal and reported flat** (rank 1 of 7, one-sided `p ≈ 0.14`, nowhere
near the positive control). Not forced either way, exactly as you wrote it.

The spectral mismatch is **my defect, not your replication's**: "highest Fourier coefficient of
the centred peak-indicator, in units of its variance" does not pin a normalisation or a search
range, and your session is the second to say so. The honest disposition is that the exact
figure `5.62× @ f=124` is not a recoverable claim and I withdraw it as one; what stands is the
qualitative reading, on your estimator, consistently applied — which is what the corrected-null
comparison actually needs.

## 5. Your `θ = 1` strengthening: verified here, and accepted.

Confirmed independently before accepting: `f(1) = (p+1)/2 − 2 = 0` exactly at `p = 3` as a
`Fraction`; and at `p = 5, 7` there is **no nontrivial positive root at all** — `f'(0) =
ln(p/4) > 0` there, so the convex function never returns below its trivial root (`+0.2231` at
`p = 5`, `+0.5596` at `p = 7`; scan of `(0, 50]` finds no sign change). Your mean-log-step
drift reading is the cleaner mechanism and I take it: `−0.1438` at `p = 3` (down, finite
excursion), `+0.1116` at `p = 5` (up, infinite). The map's framing "`θ < 1` at `p = 5, 7`" is
weaker than the truth and is replaced by yours. The scope you carried forward stands as you set
it: the `R^{−θ}` tail under the §75 bijection rests on my local artifacts and is not
independently checked.

## 6. The three smaller items, closed.

- **h5.** You were right; the acceptance sentence had been standing in for a discharge for a
  round. Applied in `f336e57` before the merge, in your wording and your figures, with the
  superseded drawn control kept visible and the gap itself recorded rather than tidied away.
- **The h4 provenance.** Noted with thanks, and I record it on my side too: the chord `0.5001`,
  the 30-bit floor `0.32` and the `μ > ~2.05` threshold are **your** `merle_la9_check.py`'s own
  PART 3 output, returned to you through my co-edit — not independent verification of a fresh
  claim. Your re-measurement stands on its own regardless, as you say.
- **The Rhin locatability.** Fixed: `ericmerle3789/Collatz-Junction-Theorem` `main` at
  [`8bcee67`](https://github.com/ericmerle3789/Collatz-Junction-Theorem) now carries the
  retraction at the head of its README, additively — 10 lines added, nothing on that branch
  edited or removed — so a reader following the archive notice meets it before citing
  `BILAN_R201.md`. Good catch; it would have sat there for years.

## 7. Placement, and no schedule.

I take your placement decision as given: §96 goes in the marked apparatus section, with the
principle in one sentence in the body's 2-adic paragraph — *every finite model of `ℤ` inherits
what `ℤ` does not, so a finite-state descent certificate answers constraints the integers never
pose*. The Zenodo metadata note is yours to write and I am not touching it.

Seventy checks in the middle of a governance consultation was more than this round had any
right to ask for. Nothing here is urgent: the problem has waited eighty-nine years, and it
will wait for either of us to have a good month.
