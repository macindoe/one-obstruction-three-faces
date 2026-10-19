# Round 20 — Merle to Macindoe

*Our key on round 19, the same credit discipline applied to our own entries, and the round-18 housekeeping you
offered. Business paragraphs only; the personal half travels by mail. Based on `main` at `481bfc9` (PR #8
merged after your six amendments were applied verbatim, `ed493a6`). Touches no line of PR #9.*

---

## 1. Your round 19: our key

Turned, in our approving review of PR #9, on the `NOTE-v1.md` correction and on all four claims of L-A12.
Artifact: `experiments/run_131.py` at `ericmerle3789/one-obstruction-three-faces-lean@9ae501d`. It is fresh code
from the text alone, 96,119 checks, 0 failures, with the predictions frozen before it ran. Simons–de Weger and
Halbeisen–Hungerbühler were read at source; for Rozier 1991 and Brox 2000 we hold only Lagarias's annotations,
which agree with your characterisations. The review carries three notes, none blocking: the source for "m ≤ 75";
the rows behind "[2.92, 10.42]"; and our second regime, the dynamics.

## 2. The same discipline on our side: L-A1 and L-A4 are older than us

Your round 19 sent us back to Halbeisen–Hungerbühler 1997 at source. Two of our entries are there.

**L-A1, the transport recurrence.**
- *The corollary.* The gcd with `q` is the same at every rotation, so one divisibility condition carries all
  the others. This is HH 1997, Lemma 9, eqs. (14)–(15), p. 238. They state it over all `l` letter rotations
  of the parity word, with the unreduced `2^l − 3^n`, for `2^l − 3^n > 0`; the `p` block rotations are a subset.
- *Seifert 1988.* Seifert 1988 (Discrete Math. 68, 293–298, Theorem 1 and the remark after it) already gives
  the one-condition criterion.
- *The recurrence itself.* It is HH's eq. (13), the Terras step on cycle numerators, composed over a block.

The dictionary is `ϕ_HH(w) = 2^{m_0}·R_0 − q`, which is the seam identity's `N_0`.

**L-A4, and L-A2 with it.**
- The cocycle our Lean key proves is HH's eq. (4). It holds for `W0 = ϕ + q` too, because `q` obeys the same law.
- The descent and the gcd climb are immediate consequences of it.
- HH's reformulation (A′) on p. 238 restricts the cycle question to non-periodic words for this reason.

**Checked.** `experiments/run_132.py` (same commit) runs on 3,000 random profiles with `q` of both signs:
12,000 checks, 0 failures. It checks the dictionary, eq. (13) letter by letter, the gcd over all letter
rotations against `gcd(q, R_r)` over block rotations, the block recurrence as the composed step, and eq. (4)
on `ϕ` and on `W0`.

**What we propose** (prose untouched everywhere; notes added beneath):
- L-A1 gains a *Prior literature* paragraph. "Found independently and essentially simultaneously" stays,
  read as a simultaneous rediscovery. What stays the entry's:
  - the block form in [1]'s `R_r`;
  - the seam identity;
  - the sign-free statement;
  - the kernel artifact.
- L-A4 gains the same kind of paragraph, and L-A2 a one-line pointer to it.
- `NOTE.md`'s architecture line for L-A1/L-A2 gains the two citations.
- The collaboration block's two lines (L-A1; L-A2/L-A4) say "rediscovery" and cite HH. Because this changes
  text you approved, **the block stays off the site until you approve these two lines here.**

**How we missed it.** Our lab's internal registry had HH eq. (4) and Seifert's rotation fact noted since
September. The shared ledger never received them. This is a propagation failure on our side, of the same
kind as the R201-I3 retraction that once stayed on one branch.

**Next on our side.** The same sweep over the remaining Merle entries (L-A5 to L-A11), source by source. One
item is already flagged. L-A10's witness residue `2^k·m − 1` is the one Dhiman–Pandey (arXiv 2601.12772,
preprint, 2026) use for their 2-adic ghost cycles. We will read it at source before any wording.

## 3. Round-18 housekeeping, as you offered it

- **Reading note.** Reworded to your wording of 2026-10-17, with a dated parenthesis saying why.
- **L-A8, round-16 block.** A dated line records the second key your PR #6 review turned, quoting your round-18
  sentence.
- **L-A9.** A condition-met note under the `stays DRAFT` sentence, quoting your round-13 key.
- **L-A11.** Knight's year is now 2026, with your Crossref note.
- **`PROTOCOL.md` §8.** "Rounds are pull requests": the R11 §13 agreement, now written into the protocol.

## 4. What needs your key

- the L-A1 *Prior literature* paragraph;
- the L-A4 paragraph and the L-A2 pointer;
- the `NOTE.md` line;
- the collaboration block's two credit lines.

Everything else in §3 is your own wording or your own request.
