# UFD: The Base Motion Without Physics

**A corrective edition, version 2.0.** Zenodo concept DOI
10.5281/zenodo.17643572. C. Valdepeñas. Text of 2026-09-27, §1 revised 2026-10-05; the publication
date is the one on the record.

**In short.** UFD v2.0 is a short mathematical text. It states one stochastic
differential equation on `R^n` (with one paired variant), on a landscape `J`,
with three parts: one part circulates without changing `J`, one slides down `J`
scaled by a mobility `G`, and one is noise. It declares one calculus convention
(Itô, with the Stratonovich conversion written out) and one constant noise
level `ε`, and it states fifteen numbered statements about the motion (U-01 to
U-15), each with its hypotheses, a status, a check level and a proof or a
textbook reference. It withdraws every physical claim of UFD v1.0, v1.1 and
v1.2 (Section 1). It is textbook material stated carefully, not a new theory.

**How it was checked.** Check levels, strongest first: (1) formally checked in
Lean; (2) the decisive calculation recomputed by machine; (3) read by an
independent AI context; (4) written only. The convention, the statements and
the proofs of Sections 3 and 4, and the answers of Annex A, come from the
working nucleus UFD-NUCLEO v0.1 (drafted 2026-09-25, repaired 2026-09-26). It
was drafted by an AI system (Claude, by Anthropic) working for the author, and
read by three other Claude contexts, independent of the drafting one but from
the same provider: mathematics passed, fidelity to the sources passed, plain
language failed; every finding was repaired, and the repairs were re-checked
and passed on 2026-09-26. On 2026-09-26 the decisive calculations were
recomputed by machine from the stated hypotheses (symbolic algebra and seeded
numerics); for the answers of Annex A and the statements they rest on, 24
agree and 0 disagree. U-12 (d) and U-13 (b), (c) were recomputed with the
GTPA v2 blocks that use them (GTPA v2, Result 1.4; crosswalk rows EG-02.4 and
EG-09.3, blocks B-07, B-10, B-11). Each statement below gives its level.
Nothing here is checked in Lean. No person and no AI system of another
provider has checked it. Sections 3 and 4 reproduce the nucleus with its internal cross-references
removed, two headings renamed and a few words changed (for instance "SDE"
written as "equation"); no hypothesis, statement or proof step was changed.
Statuses are given per part; U-12 (e), a vocabulary item, is marked
`DECLARED`.
Section 1, the "In words" lines and the short forms of the annexes were
written for this edition from the sources named in them (level 4 until they
are read).

## 1. What changed from v1.x

**v1.x.** Three versions were published under this concept in 2025: v1.0
(2025-11-18, 10.5281/zenodo.17643573), v1.1 (2025-11-21,
10.5281/zenodo.17662668) and v1.2 (2025-12-20, 10.5281/zenodo.17994168). Their
record descriptions on Zenodo (public metadata, read on 2026-09-27) present UFD
as a physical theory: stable particles as critical points of a landscape `J`,
mass given by the curvature (the Hessian) of `J` at those points, quantization
as the survival of topological invariants under noise and physical constants as
geometric ratios. The descriptions of v1.0 and v1.1 add the gauge structure of
the Standard Model and applications to high-energy physics, cosmology and
condensed matter; the description of v1.2 presents UFD as a realization of the
author's TECD framework, with gravity, electromagnetism and quantum mechanics
as projections of one geometric and stochastic reality.

**Withdrawn.** v2.0 withdraws every physical claim of v1.0, v1.1 and v1.2. They
are withdrawn as claims, not argued again here. No statement of this edition
identifies `J`, its curvature, its critical points, the noise or the time
parameter with anything physical, and no statement is about a particle, mass,
charge, spin, force, physical field, spacetime, temperature or physical
constant. The curvature of `J` at a critical point is a number that classifies
the point (U-12); it is not a mass. The name UFD is kept only so that this
edition stands on the same record line; "unified field" is not a claim of
v2.0.

**Kept, and stated once.** What remains is the mathematical core behind v1.x:
a stochastic differential equation with three terms on a landscape `J` (the
description of v1.2 calls it "the 3-term Stochastic Differential Equation"). In
v2.0 the three terms are a part that circulates without changing `J`, a part
that slides down `J` scaled by a mobility `G`, and noise. The equation is
stated once: on `R^n`, not on a field space; in the Itô convention, with the
Stratonovich conversion written out; with one constant noise level `ε`, which
is not a temperature; and with the facts that hold for it, each under its
hypotheses (Sections 3 and 4).

**Mathematical statements corrected.** Four statements about the motion are
corrected here. Each says what the public v1.2 contains, and each was checked
against its PDF on 2026-10-05 (page numbers in brackets).

- [PDF pp. 16, 20, 22] v1.2 states that the mean of `J` decreases in time
  "for macroscopic states" (pp. 16, 20) or "for any state significantly
  displaced from equilibrium" (p. 22), writes the rate on p. 16 as
  `−E⟨∇J, G∇J⟩ ≤ 0` with no noise term, and reads this as the direction of
  time. With noise that rate is wrong: the exact rate has a second term that
  can be positive (U-05); for instance, started at the bottom of a valley, the
  mean of `J` rises (U-06). The restriction to "macroscopic" or displaced
  states is not a stated hypothesis. What holds instead is stated with its
  hypotheses: without noise `J` never increases (U-04); U-07 says what does
  not increase, and under which hypotheses.
- [PDF pp. 9, 25, 26; p. 22 writes `exp(−J/D)`] v1.2 states that, with the noise linked to the mobility `G`, the law of
  the motion settles to a unique stationary density proportional to
  `exp(−2J/D)`. In general this does not follow. The density proportional to
  `exp(−J/ε)` solves the stationary equation under the named pairing
  hypothesis (P): the noise is paired with the same mobility, `ΣΣᵀ = 2εG`, the
  drift carries the correction `ε div G`, and the circulating part has no
  sources (U-08 (a)). The law it defines is stationary when moreover
  `exp(−J/ε)` has a finite integral and the motion is well posed
  (U-08 (b)). With the pairing but without that correction, or with the
  Stratonovich correction in its place, it is in general not stationary once
  `G` varies from point to point (U-09). Uniqueness of the stationary law, and
  convergence to it, are not claimed.
- [PDF pp. 8, 13, 15, 22] v1.2 writes the noise in the Stratonovich form on an
  infinite-dimensional field space, and calls the Itô trace term a
  Stratonovich correction. v2.0 works in finite dimension, takes the Itô form
  as the reference, and writes the conversion term every time (C1 to C3,
  U-02); U-05 (d) gives the term that the Stratonovich reading adds, and
  U-14 (d) shows what a silent change of convention does.
- [PDF pp. 3, 10, 33] v1.2 states that topological invariants carry infinite barriers against
  the noise. v2.0 makes no topological claim and no infinite-barrier claim. For
  exits from a valley it states only the gradient-case law of U-13 (b), in
  which the exponential rate is the height `ΔJ` of the lowest pass, a finite
  number.

**Which texts were compared.** The tables of Annex B were typed against the
author's research texts of 19 and 21 November 2025, not against the public
PDFs of v1.0 to v1.2. The four statements of Section 1 were checked against
the public v1.2 PDF (`UFD.pdf`, 144 pages, SHA-256
`19a7a7f8d50cbf8e4cb073985861570e50c533f503c7342bffa22af3b2c2cf2f`).

**What v2.0 does not do.** It does not replace the files of v1.0, v1.1 or v1.2:
they stay on the record as history. Annex A answers five questions
about the base motion of GTPA v1.2 (10.5281/zenodo.17994303). Apart from those
answers, v2.0 gives no verdict on any other record of the same author (for
instance TECD or UTHA), and none of its statements rests on them.

## 2. How to read this text

- Every statement has an ID `U-nn`, its types and hypotheses, one status, one
  check level, and a proof or a reference. The "In words" line after each
  statement is a plain summary; it adds nothing.
- Statuses: `DECLARED` (conventions, definitions, standing hypotheses);
  `PROVED_HERE` (complete proof in this text, checkable by hand);
  `STANDARD_FACT` (textbook fact with an exact locator; a short derivation is
  added where it is cheap); `OPEN` (none among U-01 to U-15; open points are
  listed in Section 7 and not asserted).
- Check levels: (1) Lean (none here); (2) the decisive calculation recomputed
  by machine on 2026-09-26 and agreed; (3) read by an independent AI context
  only; (4) written only. Where a statement combines a proved part and a cited
  textbook fact, the level given is that of the proved part; a cited textbook
  fact is at level 3 unless the derivation written here was recomputed (U-02 (b)).
- Most statements are standard. U-08's drift recipe, for instance, is the one
  of Ma, Chen & Fox (2015) with `D = εG`, `Q = −εA`.
- Notation. `⟨u,v⟩` and `|u|` are Euclidean. For matrices: `Mᵀ`, `Tr M`,
  `M ⪰ 0` (positive semidefinite), `M ≻ 0` (positive definite). `∇J` is the
  gradient and `D²J` the Hessian. For a matrix field `G`:
  `(div G)_i = sum_j ∂_j G_ij`. For a matrix field `A`:
  `(div_c A)_j = sum_i ∂_i A_ij` (divergence of the columns). `Σ_k` is the k-th
  column of `Σ` and `DΣ_k` its Jacobian. Sums are written `sum` (the letter `Σ`
  is kept for the noise matrix); ranges: `i, j, l` over `1..n`, `k` over
  `1..m`.
- Words. The three parts of the motion are called circulating (`A∇J`), sliding
  (`−G∇J`) and noise (`Σ dW`). `J` is a landscape: a function, with no unit.
  Words from physics appear only in Section 1 (the withdrawn claims), in
  explicit negations (for instance C4, Section 6, U-12 (e), U-14 (e)), in the
  quotations and paraphrases of Annexes A and B, in the titles of references
  and in the list at the end. No statement asserts or uses them.

## 3. The declared convention

- C1. State space `R^n`, `n` finite. No field space, no Sobolev space.
- C2. Reference form: Itô. The motion is
  ```text
  (M)   dq_t = [ A(q_t) ∇J(q_t) − G(q_t) ∇J(q_t) ] dt + Σ(q_t) dW_t
  ```
- C3. Stratonovich input is converted with its correction written out
  (`c_Σ = ½ sum_k (DΣ_k) Σ_k`, U-02). Conventions are never swapped silently
  (U-14 (d) shows what a silent swap does).
- C4. One noise level `ε > 0`: a constant parameter, not a temperature. It
  enters only through the named pairing hypothesis (P) of U-08. (P) constrains
  the noise and also the drift: `ΣΣᵀ = 2εG`, `div_c A = 0`, and the drift of
  (M) is replaced by `b_P := (A − G)∇J + ε div G`. So under (P) the motion is
  the paired variant
  ```text
  (M_P)   dq_t = [ (A − G)∇J + ε div G ](q_t) dt + Σ(q_t) dW_t ,     ΣΣᵀ = 2εG ,
  ```
  whose drift equals that of (M) (same `A`, `G`, `J`) if and only if
  `div G ≡ 0`, for instance when `G` is constant. (P) may hold or not; nothing
  is derived from it unless a statement says so.
- C5. First order. The declared equation is (M) on `R^n` for unpaired use, and
  (M_P) under (P); both are first-order Itô equations on `R^n`. Systems with an
  auxiliary variable `p` are separate objects (U-11).
- C6. Coefficients do not depend on time.

*Status* `DECLARED` · *check* 3. Annex A, A-6, records what this convention
settles.

## 4. Statements

### U-01 — Types and standing hypothesis

*Status* `DECLARED` · *check* 3

Integers `n, m ≥ 1`.

- State `q ∈ R^n`. Landscape `J ∈ C²(R^n; R)`.
- Circulating matrix `A: R^n → R^{n×n}`, `A(q)ᵀ = −A(q)`, locally Lipschitz
  (`C¹` wherever a divergence of `A` is used).
- Mobility `G: R^n → R^{n×n}`, `G(q)ᵀ = G(q) ⪰ 0`, locally Lipschitz (`C¹`
  wherever `div G` is used).
- Noise amplitude `Σ: R^n → R^{n×m}`, locally Lipschitz (`C²` wherever a
  Stratonovich conversion is used).
- `W` is a standard `m`-dimensional Brownian motion on a filtered probability
  space `(Ω, F, (F_t), P)` satisfying the usual conditions; `q_0` is
  `F_0`-measurable.
- Standing hypothesis (H): the drift of the equation under consideration and
  `Σ` are locally Lipschitz, and for every initial condition the Itô equation
  has a strong solution defined for all `t ≥ 0` (no explosion). With locally
  Lipschitz coefficients strong solutions are pathwise unique
  [Karatzas–Shreve 1991, Thm 5.2.5]; globally Lipschitz coefficients are
  sufficient for (H) [Øksendal 2003, Thm 5.2.1, stated there for
  `E|q_0|² < ∞`; a general `F_0`-measurable `q_0` reduces to that case by
  solving from the bounded starts `q_0 1_{|q_0| ≤ N}` and patching on the
  `F_0`-events `{|q_0| ≤ N}`, on each of which the uniqueness argument makes
  the solutions agree].
- No unit, time scale or observable is attached to any symbol, and no symbol is
  assigned to anything outside mathematics. An application outside this text
  must declare its state, units, time scale and observable; none is declared
  here.

*In words.* The state is a point of `R^n`; `J` is a landscape (a function); `A`
makes the motion circulate, `G` is the mobility and `Σ` the noise amplitude; the
motion is assumed to exist, to be unique and not to escape to infinity.

### U-02 — The motion and the conversion rule

*Status* (a), (c) `DECLARED`; (b) `STANDARD_FACT` · *check* (b) 2; (a), (c) 3

(a) The motion is the Itô equation (M) of Section 3. Its parts: circulating
`A∇J`, sliding `−G∇J` (down `J`, scaled by the mobility), noise `Σ dW`.

(b) Conversion. Let `Σ ∈ C²` and `b̃` be locally Lipschitz. A continuous
semimartingale `q` solves the Stratonovich equation
`dq = b̃(q) dt + Σ(q) ∘ dW` if and only if it solves the Itô equation

```text
dq = [ b̃(q) + c_Σ(q) ] dt + Σ(q) dW,     c_Σ := ½ sum_k (DΣ_k) Σ_k,
i.e.  (c_Σ)_i = ½ sum_{k,l} Σ_lk ∂_l Σ_ik .
```

Derivation from the standard definition `∫ Y ∘ dW^k := ∫ Y dW^k + ½ ⟨Y, W^k⟩`
(continuous semimartingales `Y`): in both forms the martingale part of `q^l` is
`sum_k ∫ Σ_lk(q) dW^k` (a conversion changes only bounded-variation terms). By
Itô's formula the martingale part of `Σ_ik(q)` is
`sum_{l,k'} ∫ ∂_l Σ_ik(q) Σ_lk'(q) dW^k'`, so
`d⟨Σ_ik(q), W^k⟩_t = sum_l ∂_l Σ_ik(q_t) Σ_lk(q_t) dt`. Summing over `k`,
`∫ Σ(q) ∘ dW = ∫ Σ(q) dW + ∫ c_Σ(q) dt`, which gives both directions.
[Protter 2005, Ch. V, §5; Pavliotis 2014, §3.2; Øksendal 2003, §3.3.]

(c) Rule. Every statement that starts from Stratonovich input writes `c_Σ`
explicitly. `c_Σ = 0` when `Σ` is constant, and then the two readings coincide.

*In words.* The rule is written in the Itô form; input written in the
Stratonovich form gets, written out, a correction that comes from how the noise
changes from point to point.

### U-03 — The circulating part leaves J unchanged

*Status* `PROVED_HERE` · *check* 2

(a) For every `q`: `⟨∇J(q), A(q)∇J(q)⟩ = 0`.

Proof. For any `v ∈ R^n` the number `vᵀAv` equals its own transpose
`vᵀAᵀv = −vᵀAv`, so it is `0`. Take `v = ∇J(q)`. ∎

(b) For a general vector field `X`, `⟨∇J, X⟩ = 0` is an extra hypothesis, not
automatic, even when `X` circulates for some other function. Counterexample:
`n = 2`, `J(q) = q₁²/2`, `S = [[0, 1], [−1, 0]]`, `h(q) = q₂`,
`X := S∇h = (1, 0)`. `X` is divergence-free and `⟨∇h, X⟩ = 0` by (a) applied to
`h`, but `⟨∇J(q), X⟩ = q₁ ≠ 0` whenever `q₁ ≠ 0`.

*In words.* What circulates around `J` does not change `J`, by antisymmetry
alone; something that circulates around another function can change it.

### U-04 — Without noise, J never increases

*Status* `PROVED_HERE` · *check* 2

Let `Σ ≡ 0` and let `q: [0, T) → R^n` be a `C¹` solution of
`q̇ = (A − G)∇J(q)`. Then

```text
d/dt J(q_t) = − ⟨∇J(q_t), G(q_t) ∇J(q_t)⟩ ≤ 0,
```

with equality at time `t` if and only if `G(q_t)∇J(q_t) = 0`.

Proof. Chain rule: `d/dt J(q_t) = ⟨∇J, q̇⟩ = ⟨∇J, A∇J⟩ − ⟨∇J, G∇J⟩`; the
first term is `0` by U-03 (a) and the second is `≥ 0` because `G ⪰ 0`. For the
equality case let `G^{1/2} ⪰ 0` be the symmetric square root:
`⟨v, Gv⟩ = |G^{1/2}v|²`, which is `0` iff `G^{1/2}v = 0` iff `Gv = 0`. ∎

So the decrease rate of `J` along the noiseless motion is `⟨∇J, G∇J⟩` (U-10
compares it with `|∇J|²` and `|G∇J|²`).

*In words.* Without noise, `J` never rises: it goes down exactly at the rate
`⟨∇J, G∇J⟩` and stops only where `G∇J = 0`.

### U-05 — The rate of J with noise

*Status* (a) `STANDARD_FACT`; (b), (c), (d) `PROVED_HERE` · *check* (c), (d) 2; (a), (b) 3

(a) For `f ∈ C²(R^n)` the generator of (M) is

```text
L f = ⟨(A − G)∇J, ∇f⟩ + ½ Tr( ΣΣᵀ D²f ),
```

and Itô's formula gives, for every solution of (M),

```text
J(q_t) = J(q_0) + ∫_0^t LJ(q_s) ds + ∫_0^t ∇J(q_s)ᵀ Σ(q_s) dW_s,
LJ = − ⟨∇J, G∇J⟩ + ½ Tr( ΣΣᵀ D²J )          (by U-03 (a)).
```

[Øksendal 2003, Thm 4.2.1 (Itô formula) and Thm 7.3.3 (generator).] `Σ` enters
`L` only through `ΣΣᵀ`.

(b) Expected rate. If for some `T > 0` (I1) `E|J(q_0)| < ∞`,
(I2) `E ∫_0^T |Σᵀ∇J(q_s)|² ds < ∞` and (I3) `E ∫_0^T |LJ(q_s)| ds < ∞`, then
for `0 ≤ t ≤ T`

```text
E[J(q_t)] = E[J(q_0)] + ∫_0^t E[LJ(q_s)] ds,
```

and if `s ↦ E[LJ(q_s)]` is continuous, `d/dt E[J(q_t)] = E[LJ(q_t)]`.
Proof: take expectations in (a); under (I2) the stochastic integral has mean `0`
[Øksendal 2003, Thm 3.2.1]; under (I3) Fubini exchanges `E` and `∫ ds`; the
last claim is the fundamental theorem of calculus. ∎ Without (I1)–(I3) only
the pathwise identity (a) is claimed.

(c) Sign of the noise term. `½Tr(ΣΣᵀD²J)(q) ≥ 0` wherever `D²J(q) ⪰ 0`, and
`> 0` wherever `D²J(q) ≻ 0` and `Σ(q) ≠ 0`. Proof: for `P ⪰ 0`, `Q ⪰ 0`,
`Tr(PQ) = Tr(Q^{1/2} P Q^{1/2}) ≥ 0`; if `Q ≻ 0` and this trace is `0`, the
positive semidefinite matrix `Q^{1/2}PQ^{1/2}` is `0`, so `P = 0`. Apply with
`P = ΣΣᵀ` (nonzero iff `Σ ≠ 0`) and `Q = D²J`. ∎ Where `J` is convex the noise
term pushes `E[J]` up; `G ⪰ 0` does not fix the sign of the rate.

(d) Stratonovich reading of the same symbols. If the noise term of (M) is read
as `Σ ∘ dW` (`Σ ∈ C²`), U-02 (b) adds `⟨c_Σ, ∇f⟩` to `Lf`, so
`LJ = −⟨∇J, G∇J⟩ + ⟨∇J, c_Σ⟩ + ½Tr(ΣΣᵀD²J)`. The added term has no fixed sign:
`n = m = 1`, `Σ(q) = q` gives `c_Σ(q) = q/2`, and with `J(q) = q` it equals
`q/2`.

*In words.* With noise, the mean of `J` changes at the rate "what goes down
through `G`" plus "what goes up through the noise" (a trace term, non-negative
where `J` is convex); the second can win.

### U-06 — With noise, the mean of J can rise: two worked instances

*Status* `PROVED_HERE` · *check* 2

(a) Instance: `n = 1`, `J(x) = x²/2`, `A = 0` (every 1×1 antisymmetric matrix is
`0`), `G = 1`, `Σ = √(2ε)` with `ε > 0`, deterministic start `x_0`:

```text
dx_t = − x_t dt + √(2ε) dW_t .
```

Claim: `E[J(x_t)] = ½ [ x_0² e^{−2t} + ε (1 − e^{−2t}) ]`, hence
`d/dt E[J(x_t)] = (ε − x_0²) e^{−2t}`. In particular, from the minimum
(`x_0 = 0`), `E[J(x_t)] = (ε/2)(1 − e^{−2t})` is strictly increasing on
`[0, ∞)` with derivative `ε > 0` at `t = 0`; and `E[J]` increases for all
`t ≥ 0` whenever `|x_0| < √ε`.

Proof. The coefficients are globally Lipschitz, so (H) holds [Øksendal 2003,
Thm 5.2.1]. The process `x_t = x_0 e^{−t} + √(2ε) ∫_0^t e^{−(t−s)} dW_s` solves
the equation: by Itô's product rule
`d(e^t x_t) = e^t dx_t + e^t x_t dt = √(2ε) e^t dW_t`. The stochastic integral
has mean `0` and, by the Itô isometry [Øksendal 2003, Cor. 3.1.7], variance
`2ε ∫_0^t e^{−2(t−s)} ds = ε(1 − e^{−2t})`. So
`E[x_t²] = x_0² e^{−2t} + ε(1 − e^{−2t})`; halve and differentiate. ∎

Cross-check with U-05: `LJ = −x² + ε` and `E[LJ(x_t)] = (ε − x_0²)e^{−2t}`
((I1)–(I3) hold because `x_t` is Gaussian). The instance has positive mobility,
nonzero noise and zero circulating part, and it also satisfies the pairing (P)
of U-08 (`ΣΣᵀ = 2ε = 2εG`, `G` constant so `ε div G = 0`). Positive mobility
therefore does not make `E[J]` decrease.

(b) Even-dimensional instance. `n = m = 2`, `J(q) = |q|²/2`, `G = I`,
`Σ = √(2ε) I`, and either `A = 0` or `A = S := [[0, 1], [−1, 0]]` (then
`A∇J = Sq` is a rotation field: it is divergence-free and, by U-03 (a), leaves
`J` unchanged). In both cases `LJ = −|q|² + 2ε`, and from `q_0 = 0`

```text
E[J(q_t)] = ε (1 − e^{−2t}),       d/dt E[J(q_t)] = 2ε e^{−2t} > 0 .
```

Proof. The coefficients are globally Lipschitz, so (H) holds as in (a); the
equation is `dq_t = (A − I) q_t dt + √(2ε) dW_t`. Put `R_u := e^{uA}`: the
identity if `A = 0`, a rotation matrix if `A = S`; in both cases `R_u` is
orthogonal. By Itô's product rule,
`d(e^{t(I − A)} q_t) = e^{t(I − A)} [(I − A) q_t dt + dq_t] = √(2ε) e^{t(I − A)} dW_t`,
so from `q_0 = 0`, `q_t = √(2ε) ∫_0^t e^{−(t−s)} R_{t−s} dW_s`. By the Itô
isometry,
`E|q_t|² = 2ε ∫_0^t e^{−2(t−s)} Tr(R_{t−s} R_{t−s}ᵀ) ds = 4ε ∫_0^t e^{−2(t−s)} ds = 2ε(1 − e^{−2t})`;
halve. ∎ This instance also satisfies (P) (`ΣΣᵀ = 2εI = 2εG`, with `G` and `A`
constant).

*In words.* A counterexample that can be checked by hand: started at the bottom
of the valley, the noise makes the mean of `J` rise (also in the plane, with or
without a circulating part); a positive mobility is not enough for it to go
down.

### U-07 — What does not increase

*Status* `PROVED_HERE` · *check* (a′), (b) 2; (a) 3

(a) Sufficient condition for `E[J]` non-increasing. Assume (H) for (M), `J`
bounded below (`J ≥ −c`, `c ≥ 0`), `E|J(q_0)| < ∞`, and `LJ ≤ 0` on `R^n`,
that is

```text
½ Tr( ΣΣᵀ D²J ) ≤ ⟨∇J, G∇J⟩     at every point.
```

Then `(J(q_t))_{t≥0}` is a supermartingale; in particular `t ↦ E[J(q_t)]` is
finite and non-increasing.

Proof. Let `τ_N := inf{t ≥ 0 : |q_t| ≥ N}`. On `[0, τ_N]` the integrand
`Σᵀ∇J(q)` is bounded (if `|q_0| ≥ N` then `τ_N = 0`), so
`M^N_t := ∫_0^{t∧τ_N} ∇J(q)ᵀΣ(q) dW` is a martingale, and
`|J(q_{t∧τ_N})| ≤ |J(q_0)| + max_{|x|≤N} |J(x)|` is integrable. By U-05 (a) and
`LJ ≤ 0`, for `s ≤ t`:
`J(q_{t∧τ_N}) = J(q_{s∧τ_N}) + ∫_{s∧τ_N}^{t∧τ_N} LJ(q_r) dr + M^N_t − M^N_s ≤ J(q_{s∧τ_N}) + M^N_t − M^N_s`,
hence `E[J(q_{t∧τ_N}) | F_s] ≤ J(q_{s∧τ_N})`. No explosion gives `τ_N → ∞`
a.s., so `q_{t∧τ_N} → q_t` and `q_{s∧τ_N} → q_s`. Since `J + c ≥ 0`, the
conditional Fatou lemma gives
`E[J(q_t) + c | F_s] ≤ liminf_N E[J(q_{t∧τ_N}) + c | F_s] ≤ J(q_s) + c`.
With `s = 0`, `E[J(q_t)] ≤ E[J(q_0)] < ∞`, and `J(q_t) ≥ −c`, so every
`J(q_t)` is integrable; the displayed inequality is the supermartingale
property, and its expectation gives `E[J(q_t)] ≤ E[J(q_s)]`. ∎

(a′) Reach of (a). The pointwise condition fails at every critical point `q*`
with `D²J(q*) ≻ 0` and `Σ(q*) ≠ 0`: there `⟨∇J, G∇J⟩ = 0` while
`½Tr(ΣΣᵀD²J) > 0` (U-05 (c)). So (a) never applies on a region that contains a
non-degenerate minimum (`D²J ≻ 0` there) where the noise does not vanish, in
agreement with U-06.

(b) Kullback–Leibler divergence under the pairing. Assume (P) of U-08 with
`G ∈ C²`, `Z := ∫ e^{−J/ε} < ∞`, `π := e^{−J/ε}/Z`, and let `ρ_t` be the density
of the law of `q_t`. Assume (R): `ρ` is a classical, strictly positive solution
of the Fokker–Planck equation `∂_t ρ = L*ρ` on `(0, ∞) × R^n`, every integral
below is finite, differentiation under `∫` is allowed, and every integration by
parts below has vanishing boundary terms. Let `h_t := ρ_t/π` and
`KL(ρ_t‖π) := ∫ ρ_t ln h_t dq`. Then

```text
d/dt KL(ρ_t‖π) = − ε ∫ ρ_t ⟨∇ ln h_t, G ∇ ln h_t⟩ dq ≤ 0 .
```

Moreover `KL(ρ‖π) = (1/ε) ( E_ρ[J] + ε ∫ ρ ln ρ ) + ln Z`, so under (P) and (R)
the quantity that cannot increase is `E[J(q_t)] + ε ∫ ρ_t ln ρ_t`: the mean of
`J` plus `ε ∫ ρ_t ln ρ_t`, a term that goes down as the law spreads out. It is
not `E[J]` itself. (`KL` is a divergence, not a metric; (b) proves that it does
not increase, not that it decreases strictly.)

Proof. In flux form `∂_t ρ = −div j` with `j := b_P ρ − ε div(Gρ)`, where
`div(Gρ)_i := sum_j ∂_j(G_ij ρ)` (this is `L*` for
`Lf = ⟨b_P, ∇f⟩ + ε Tr(G D²f)`, the generator under (P)). With `ρ = hπ` and
`∇π = −π∇J/ε`: `ε div(Gρ) = ε (div G) hπ + ε π G∇h − hπ G∇J` and
`b_P ρ = hπ [(A − G)∇J + ε div G]`, so `j = hπ A∇J − ε π G∇h`. By U-08 (★),
`div(πA∇J) = 0`, hence `div(hπA∇J) = π⟨∇h, A∇J⟩` and
`π ∂_t h = −π⟨∇h, A∇J⟩ + ε div(πG∇h)`. Then
`d/dt ∫ π h ln h = ∫ π ∂_t h (ln h + 1)`. The circulating part contributes
`−∫ ⟨∇(h ln h), πA∇J⟩ = ∫ h ln h · div(πA∇J) = 0`; the other part contributes
`ε ∫ (ln h + 1) div(πG∇h) = −ε ∫ ⟨∇ ln h, πG∇h⟩ = −ε ∫ ρ ⟨∇ ln h, G∇ ln h⟩`,
which is `≤ 0` because `G ⪰ 0`. The identity for `KL` follows from
`ln h = ln ρ + J/ε + ln Z` and `∫ ρ = 1`. ∎ Checking (R) for given coefficients
is a separate task, not done here.

*In words.* For the mean of `J` not to rise it is enough that the noise never
pushes harder than the slope (and that condition fails at the bottom of a
curved valley where there is noise); with the paired noise and regularity
conditions, what does not rise is the divergence from the equilibrium law (not
a distance): the mean of `J` plus a term that goes down as the law spreads out.

### U-08 — The pairing of noise and mobility

*Status* (a), (c), (d) `PROVED_HERE`; (b) `STANDARD_FACT` · *check* (a), (c) 2; (b) 3; (d) as U-09

Pairing hypothesis (P), a named hypothesis and not an axiom: `ε > 0` constant;
`A ∈ C¹` with `div_c A = 0` (`sum_i ∂_i A_ij = 0` for every `j`); `G ∈ C¹`;
`ΣΣᵀ = 2εG`; and the drift is

```text
b_P := (A − G)∇J + ε div G ,       (div G)_i = sum_j ∂_j G_ij .
```

The paired motion is (M_P) of Section 3, `dq = b_P(q) dt + Σ(q) dW`. Its drift
equals that of (M) (same `A`, `G`, `J`) if and only if `div G ≡ 0` (for
instance `G` constant), since `ε > 0`. The noise is paired with the same `G`
that scales the slide.

(a) Stationary equation in weak form. Let `ρ_J := e^{−J/ε}`. For every
`f ∈ C_c^∞(R^n)`,

```text
∫ (Lf) ρ_J dq = 0 ,       Lf = ⟨b_P, ∇f⟩ + ε Tr( G D²f )
```

(infinitesimal invariance), and pointwise

```text
(★)   div( ρ_J A∇J ) = 0 .
```

Proof. Integrate the second-order term by parts once (`f` has compact support,
`G_ij ρ_J ∈ C¹`) and use `∇ρ_J = −ρ_J ∇J/ε`:
`∫ ε sum_{i,j} G_ij ∂_i∂_j f ρ_J = −ε ∫ sum_{i,j} ∂_i f ∂_j(G_ij ρ_J) = −∫ ⟨∇f, ε div G − G∇J⟩ ρ_J`.
Adding `∫ ⟨b_P, ∇f⟩ ρ_J`, the `G∇J` and `div G` terms cancel:
`∫ (Lf) ρ_J = ∫ ⟨∇f, ρ_J A∇J⟩ = −∫ f div(ρ_J A∇J)`. Now
`div(ρ_J A∇J) = sum_{i,j} [∂_i ρ_J A_ij ∂_j J + ρ_J (∂_i A_ij) ∂_j J + ρ_J A_ij ∂_i∂_j J] = −(ρ_J/ε)⟨∇J, A∇J⟩ + ρ_J ⟨div_c A, ∇J⟩ + ρ_J Tr(AᵀD²J)`.
The first term is `0` by U-03 (a), the second by `div_c A = 0`, the third
because `Tr(AᵀH) = 0` for antisymmetric `A` and symmetric `H`
(`Tr(AᵀH) = Tr(HᵀA) = Tr(AH) = −Tr(AᵀH)`). ∎

(b) From (a) to the law. If moreover `Z := ∫ ρ_J < ∞` and the martingale
problem for `(L, C_c^∞(R^n))` is well posed (for every initial law exactly one
solution in law, without explosion; for instance under (H) for `b_P` and `Σ`:
pathwise uniqueness implies uniqueness in law [Karatzas–Shreve 1991,
Prop. 5.3.20], and solutions of the martingale problem correspond to weak
solutions [ibid., §5.4]), then `μ_J := ρ_J/Z` is invariant: `q_0 ~ μ_J` implies
`q_t ~ μ_J` for every `t ≥ 0`. [Ethier–Kurtz 1986, Ch. 4, Thm 9.17
(Echeverría): `C_c^∞(R^n)` is an algebra, dense in the continuous functions
vanishing at infinity, on which `L` satisfies the positive maximum principle; a
probability measure with `∫ Lf dμ = 0` for all such `f` admits a stationary
solution of the martingale problem, and uniqueness identifies it with the
motion. The same drift recipe, with `D = εG`, `Q = −εA`, is Ma, Chen & Fox
2015, Thm 1.] Uniqueness of the invariant law and convergence to it are not
claimed.

(c) Status of (P). (P) is independent of U-01 and U-02: motions without it are
well defined and can have other invariant laws. U-15 with `σ² ≠ 2εγ` has the
invariant law `N(0, σ²/(2γk))`, not `N(0, ε/k) ∝ e^{−J/ε}`; and `Σ ≡ 0` with
`G ≠ 0` is a motion too. Given `G` and `ε`, (P) fixes `ΣΣᵀ` (the only way `Σ`
enters `L`, U-05 (a)) and the drift correction `ε div G`, and it requires
`div_c A = 0`: it is a constraint on the coefficients, not a law of the motion.

(d) The correction `ε div G` is needed: with the pairing `ΣΣᵀ = 2εG` but
without the correction, or with the Stratonovich correction in its place,
`e^{−J/ε}` is in general not stationary (U-09 (ii)–(iv), one dimension).

*In words.* If the noise is paired with the same mobility `G` (`ΣΣᵀ = 2εG`),
the correction term `ε div G` is added and the circulating part has no sources,
then `e^{−J/ε}` solves the stationary equation; if moreover its integral is
finite and the motion is well posed, the law proportional to it is an
equilibrium. The pairing is a named hypothesis that may hold or not, not an
axiom.

### U-09 — The correction is needed: one dimension

*Status* `PROVED_HERE` · *check* 2

Setting: `n = m = 1`, `V ∈ C²(R)`, `g ∈ C²(R)` with `g > 0`, `ε > 0`,
`σ := √(2εg)` (so `σ² = 2εg`: the pairing with mobility `g`).

(i) The Stratonovich equation `dX = −g(X)V'(X) dt + σ(X) ∘ dW` has the Itô form

```text
dX = [ −g V' + (ε/2) g' ](X) dt + σ(X) dW .
```

Proof. U-02 (b) with `n = m = 1`: `c_Σ = ½σσ' = ¼(σ²)' = ¼(2εg)' = (ε/2)g'`. ∎

(ii) More generally, for the Itô equation `dX = b(X) dt + σ(X) dW` with
`b := −gV' + αεg'` (`α ∈ R`; `α = 0`: the uncorrected Itô reading, that is
(M) with the pairing; `α = ½`: the Stratonovich reading (i); `α = 1`: the
paired motion of U-08, since `div G = g'`), write the stationary Fokker–Planck
operator as `L*ρ = −(bρ)' + ε(gρ)'' = −j'` with flux `j := bρ − ε(gρ)'`. Then
`ζ_α := e^{−V/ε} g^{α−1}` has zero flux, and `ρ_V := e^{−V/ε}` satisfies

```text
L*ρ_V = (1 − α) ε ( g' ρ_V )' .
```

Proof. `(gζ_α)' = (e^{−V/ε} g^α)' = e^{−V/ε} g^α (−V'/ε + αg'/g)`, so
`ε(gζ_α)' = ζ_α (−gV' + αεg') = bζ_α` and `j = 0`. For `ρ_V`:
`ε(gρ_V)' = εg'ρ_V − gV'ρ_V`, so
`j = (−gV' + αεg')ρ_V − εg'ρ_V + gV'ρ_V = (α − 1)εg'ρ_V` and
`L*ρ_V = −j' = (1 − α)ε(g'ρ_V)'`. ∎ For `α = ½` the zero-flux density is
`∝ e^{−V/ε} g^{−1/2}`, not `e^{−V/ε}`.

(iii) Characterization. If `α ≠ 1`, `V` is bounded below and `g > 0` on `R`,
then `L*ρ_V ≡ 0` if and only if `g` is constant. Proof. If `g` is constant,
`g' = 0`. Conversely `L*ρ_V ≡ 0` with `α ≠ 1` gives `(g'ρ_V)' ≡ 0`, so
`g' = C e^{V/ε}` for a constant `C`. If `C > 0` then
`g' ≥ C e^{(inf V)/ε} =: δ > 0`, so `g(x) ≤ g(0) − δ|x|` for `x < 0` and `g`
becomes negative, a contradiction; `C < 0` is symmetric (`x > 0`). So `C = 0`
and `g` is constant. ∎

(iv) An explicit instance, at the level of the law. `V(x) = ½ ln(1 + x²)`,
`g(x) = 1 + x²`, `0 < ε < 1`, `α = ½` (the Stratonovich reading). The Itô form
is `dX = −(1 − ε)X dt + √(2ε(1 + X²)) dW`, whose coefficients are globally
Lipschitz, so (H) holds. `ρ_V = (1 + x²)^{−1/(2ε)}` is integrable because
`1/ε > 1`, and by (ii)
`L*ρ_V(x) = ½ε(g''ρ_V + g'ρ_V') = (ε − x²/(1 + x²)) ρ_V(x)`, so
`L*ρ_V(0) = ε > 0`. Hence `μ_V := ρ_V/∫ρ_V` is not an invariant law: if it
were, then for every `f ∈ C_c^∞(R)` Dynkin's formula
`E f(X_t) − E f(X_0) = E ∫_0^t Lf(X_s) ds` (the term `∫ f'(X)σ(X) dW` has a
bounded integrand, hence mean `0`), with `X_s ~ μ_V` for all `s`, would give
`t ∫ Lf dμ_V = 0`; integrating by parts (compact support), `∫ f L*ρ_V = 0` for
all `f`, so the continuous function `L*ρ_V` would vanish identically,
contradicting `L*ρ_V(0) = ε`. The zero-flux density of this instance is
`ζ_{1/2} = (1 + x²)^{−1/(2ε) − 1/2}`. ∎

So the pairing `σ² = 2εg` alone does not give `e^{−V/ε}`: the drift must carry
the full correction `εg' = ε div G` (`α = 1`), which is what U-08 builds in.

*In words.* A calculation that can be checked by hand: with Stratonovich noise
paired with a mobility that changes from point to point, `e^{−V/ε}` in general
does not solve the stationary equation; the density with zero flux is
`e^{−V/ε}·g^{−1/2}`; only with the full correction (the one of U-08) does
`e^{−V/ε}` solve it.

### U-10 — Comparing |∇J|², |G∇J|² and ⟨∇J, G∇J⟩

*Status* `PROVED_HERE` · *check* 2

Let `G` be a symmetric positive semidefinite `n×n` matrix and `c ≥ 0`.

(a) The following are equivalent: (1) `⟨v, Gv⟩ = c|v|²` for all `v`;
(2) `|Gv|² = c²|v|²` for all `v`; (3) `G = cI`. Proof. (3) ⇒ (1), (2) directly.
(1) ⇒ (3): `G − cI` is symmetric with zero quadratic form, hence `0`
(polarization: `⟨u, Bw⟩ = ¼(⟨u+w, B(u+w)⟩ − ⟨u−w, B(u−w)⟩)` for symmetric
`B`). (2) ⇒ (3): `|Gv|² = ⟨v, G²v⟩`, so `G² = c²I`; each eigenvalue `λ ≥ 0`
of `G` satisfies `λ² = c²`, so `λ = c`, and a symmetric matrix with the single
eigenvalue `c` is `cI`. ∎ Every vector is a gradient at a given point
(`v = ∇J(q)` for `J(x) = ⟨v, x⟩`), so the three quantities are proportional,
with factors that do not depend on the gradient, at a point `q` iff
`G(q) = c(q)I`; with the same factors at every point iff `G ≡ cI`.

(a′) The pair `|Gv|²`, `⟨v, Gv⟩` alone behaves differently: for `k ≥ 0`,
`|Gv|² = k⟨v, Gv⟩` for all `v` iff `G² = kG` iff `G = kP` with `P` an
orthogonal projection (`P = Pᵀ = P²`; `G = 0` if `k = 0`). Proof.
`|Gv|² − k⟨v, Gv⟩ = ⟨v, (G² − kG)v⟩`, and `G² − kG` is symmetric, so the
identity for all `v` is `G² = kG` (polarization). Then every eigenvalue `λ` of
`G` satisfies `λ² = kλ`, that is `λ ∈ {0, k}`, so `G = kP` with `P` the
orthogonal projection onto the eigenspace of `k` (and `G = 0` if `k = 0`); the
converse is `(kP)² = k²P = k(kP)`. ∎ Example: `G = diag(1, 0)` gives
`|Gv|² = ⟨v, Gv⟩ = v₁²` for all `v`, although `G` is not a multiple of `I`.

(b) For a mobility that is neither a multiple of `I` nor of a projection there
is no single factor for any pair: for `G = diag(1, 2)`, `v = e₁` gives
`(|v|², |Gv|², ⟨v, Gv⟩) = (1, 1, 1)` and `v = e₂` gives `(1, 4, 2)`.

(c) If the eigenvalues of `G` lie in `[λ, Λ]` (`0 ≤ λ ≤ Λ`), then for all `v`:
`λ|v|² ≤ ⟨v, Gv⟩ ≤ Λ|v|²` and `λ⟨v, Gv⟩ ≤ |Gv|² ≤ Λ⟨v, Gv⟩`. Proof.
Diagonalize `G = sum_i λ_i u_i u_iᵀ`; with `v_i := ⟨u_i, v⟩`,
`⟨v, Gv⟩ = sum_i λ_i v_i²` and `|Gv|² = sum_i λ_i² v_i²`, and `λ ≤ λ_i ≤ Λ`
gives `λλ_i ≤ λ_i² ≤ Λλ_i`. ∎ So the three are comparable when `G` is uniformly
positive definite and bounded, but equal up to one factor only when `G` is a
multiple of the identity.

(d) The decrease rate of `J` along the noiseless motion is `⟨∇J, G∇J⟩` (U-04).
It is a fixed multiple of `|∇J|²` for every landscape only when `G = cI`, and of
`|G∇J|²` only when `G = kP` (a multiple of a projection); in general it is
neither.

*In words.* The three "speeds" (without `G`, with `G`, or with `G` squared)
agree up to one factor only if the mobility is the same in every direction
(`G = c·I`); the one that measures how fast `J` goes down is `⟨∇J, G∇J⟩`.

### U-11 — Systems with an auxiliary variable are different objects

*Status* (a) `PROVED_HERE`; (b) `STANDARD_FACT`; (c) `STANDARD_FACT` + `PROVED_HERE` · *check* 2 for the proved parts ((a); the normalization in (b); the identification of the limit in (c)); the cited limit theorems 3

Here `p ∈ R^n` is an auxiliary variable and `M` a constant symmetric positive
definite matrix (neither is given any reading). A (q,p) system is any
stochastic differential equation on `R^{2n}` of the form `dq = M^{−1}p dt`,
`dp = F(q, p) dt + Σ_p(q, p) dW`, with `F`, `Σ_p` locally Lipschitz and no
explosion.

(a) In a (q,p) system `t ↦ q_t` is `C¹` and has zero quadratic variation. A
solution of (M) has `⟨q^i⟩_t = ∫_0^t (ΣΣᵀ)_ii(q_s) ds` [quadratic variation of
Itô integrals: Karatzas–Shreve 1991, §3.2]. If `q_0` is deterministic and
`Σ(q_0) ≠ 0`, then `Tr(ΣΣᵀ)(q_0) = sum_{i,k} Σ_ik(q_0)² > 0`, some
`(ΣΣᵀ)_ii(q_0) > 0`, and by continuity `⟨q^i⟩_t > 0` for every `t > 0`, a.s.
Quadratic variation is a functional of the path (limit in probability of sums
of squared increments), so the `q`-paths of a (q,p) system and those of (M)
with `Σ(q_0) ≠ 0` never have the same law. A change of convention (U-02 (b))
changes only the drift of (M), never its state space or its noise term; so no
(q,p) system is the Itô or Stratonovich rewrite of (M) when `Σ ≠ 0`. Proof of
the first sentence: `q_t = q_0 + ∫_0^t M^{−1}p_s ds` with `p` continuous, so
`q` is `C¹`, of finite variation on compacts, and a continuous path of finite
variation has zero quadratic variation. ∎

(b) Limit, constant coefficients. Let `∇J` be globally Lipschitz, `γ > 0`,
`m > 0`, `ε > 0`, `M = mI`, and write the (q,p) system with `v := p/m`:

```text
dq = v dt ,     m dv = [ −∇J(q) − γ v ] dt + √(2εγ) dW ,     q(0) = q_0 , v(0) = v_0 .
```

As `m → 0`, almost surely `q^m → q` uniformly on compact time intervals, where

```text
dq = − γ^{−1} ∇J(q) dt + √(2ε γ^{−1}) dW ,     q(0) = q_0 ,
```

that is (M) with `A = 0`, `G = γ^{−1} I` and `ΣΣᵀ = 2εG`. [Nelson 1967,
Ch. 10, Thm 10.1, with `β = γ/m`, `b = −∇J/γ` and Wiener process
`w = √(2ε/γ) W`; Pavliotis 2014, §6.5.1.] The first-order mobility is the
inverse of the coefficient `γ` of `v = M^{−1}p` (equivalently of `p` when
`M = I`), and the noise `2εγ` of the (q,p) system becomes `ΣΣᵀ = 2εG` in the
limit. Normalization: if a (q,p) system is written with a coefficient `Γ` of
`p` itself (`dq = M^{−1}p dt`, `dp = [−∇J − Γp] dt + Σ_p dW`) and `M = mI`, it
is the system above with `γ = mΓ`: its noise reads `Σ_pΣ_pᵀ = 2εmΓ`, and the
limit (taken with `γ = mΓ` fixed) has mobility `(mΓ)^{−1}`.

(c) Limit with a q-dependent coefficient. For `n = 1`, `dq = v dt`,
`m dv = [F(q) − γ(q) v] dt + σ(q) dW` with `F = −J'`, `σ² = 2εγ`,
`γ ≥ c_γ > 0`, and coefficients and their derivatives bounded: as `m → 0`,
`q^m` converges in probability, uniformly on `[0, T]`, to the solution of the
Itô equation

```text
dq = [ F/γ − γ' σ² / (2γ³) ](q) dt + (σ/γ)(q) dW
```

[Hottovy, McDaniel, Volpe & Wehr 2015, Thm 1 and §III (one dimension); the
multi-dimensional, matrix-valued case is their Thm 1, with the extra drift given
by a Lyapunov equation]. Proved here: with `G := 1/γ` (so `G' = −γ'/γ²`) this
limit is exactly

```text
dq = [ −G J' + ε G' ] dt + √(2εG) dW ,
```

because `γ'σ²/(2γ³) = εγ'/γ² = −εG'` and `σ/γ = √(2εγ)/γ = √(2εG)`. The extra
term `εG'` (a noise-induced drift) is the correction `ε div G` of U-08: the
limit is the paired motion (M_P) with `A = 0`, which is not (M) unless
`G' ≡ 0`.

(d) Not claimed: that (M) arises only in this way; anything about the (q,p)
system beyond (a)–(c); the multi-dimensional q-dependent case beyond citation.

*In words.* A system with an auxiliary variable `p` (a "second-order" system)
is another equation, not the same one written differently; it is related to the
first-order one through a limit; in one dimension, with the noise paired with
the coefficient (σ² = 2εγ), if the coefficient changes from point to point that
limit brings exactly the correction of U-08.

### U-12 — Critical point, Hessian, local curvature

*Status* `PROVED_HERE`; (e) `DECLARED` · *check* (d) 2; (a)–(c), (e) 3

Let `∇J(q*) = 0`, `H* := D²J(q*)` with eigenvalues `λ_1 ≤ … ≤ λ_n`.

(a) `J(q* + δ) = J(q*) + ½⟨δ, H*δ⟩ + o(|δ|²)` as `δ → 0` (Taylor's theorem
with Peano remainder, `J ∈ C²`).

(b) If `λ_1 > 0`, `q*` is a strict local minimum: for `|δ|` small,
`J(q* + δ) − J(q*) ≥ ¼λ_1|δ|² > 0` (`δ ≠ 0`). Proof: choose `r > 0` with
`|o(|δ|²)| ≤ ¼λ_1|δ|²` for `|δ| < r`, and use `½⟨δ, H*δ⟩ ≥ ½λ_1|δ|²`. ∎

(c) If `λ_1 < 0 < λ_n`, `q*` is not a local extremum (a saddle): along unit
eigenvectors `u_±`, `J(q* + t u_±) − J(q*) = ½λ_± t² + o(t²)`, of opposite
signs for small `t ≠ 0`. ∎

(d) If `H* ⪰ 0` is singular the second-order test is inconclusive: `J = x⁴`
(strict minimum) and `J = x³` (no extremum) both have `H* = 0` at `0` ("flat
directions").

(e) Vocabulary. The curvature of `J` at `q*` in the unit direction `u` is
`⟨u, H*u⟩`. "Rigidity" (in Spanish, "rigidez") names this number and nothing
else: not a mass, not a property of any person or object.

*In words.* At an equilibrium point, the curvature of `J` (its Hessian) says
whether the point is the bottom of a valley or a saddle; where it is singular
(flat directions) it does not decide;
"rigidity" is that curvature and nothing more: it is not a mass.

### U-13 — Basin, exit time, barrier

*Status* (a) `DECLARED`; (b) `STANDARD_FACT` + `PROVED_HERE`; (c) `PROVED_HERE` · *check* (b), (c) 2 (the proved parts); the cited exit law 3

(a) Let `f: R^n → R^n` be locally Lipschitz with global flow `φ_t`, and `q*` an
asymptotically stable equilibrium. Basin:
`B(q*) := {q : φ_t(q) is defined for all t ≥ 0 and φ_t(q) → q* as t → ∞}`. For
a continuous process `q_t` and an open `D ⊂ R^n`:
`τ_D := inf{t ≥ 0 : q_t ∉ D}`, with `inf ∅ := +∞`.

(b) Gradient subcase. Declared subcase: `A = 0`, `G = I`, `Σ = √(2ε) I`, so (M)
reads `dq = −∇J dt + √(2ε) dW`. Let `D`, `q*` and `J` satisfy the hypotheses of
Dembo–Zeitouni 1998, §5.7 (standing assumptions and (A-1)–(A-4); in particular
`D` is bounded, `q*` is its unique equilibrium, and noiseless trajectories
started in the closure of `D` converge to `q*`). Then for every `q ∈ D`

```text
lim_{ε→0} ε ln E_q[τ_D] = min_{y ∈ ∂D} ( J(y) − J(q*) ) =: ΔJ .
```

Standard fact: `lim ε ln E_q[τ_D] = inf_{y∈∂D} V(q*, y)`, with quasipotential
`V(q*, y) := inf { I_T(φ) : T > 0, φ(0) = q*, φ(T) = y }` and rate
`I_T(φ) = ¼ ∫_0^T |φ̇ + ∇J(φ)|² dt` (their `√ε σ` noise with `σ = √2 I`)
[Dembo–Zeitouni 1998, Thm 5.7.11; Freidlin–Wentzell 2012, Ch. 4]. Proved here:
`V(q*, y) = J(y) − J(q*)` for every `y` whose noiseless trajectory converges to
`q*` (in particular every `y ∈ ∂D`). Lower bound:
`|φ̇ + ∇J|² = |φ̇ − ∇J|² + 4⟨φ̇, ∇J(φ)⟩ ≥ 4 d/dt J(φ(t))`, so
`I_T(φ) ≥ J(y) − J(q*)`. Upper bound: let `ψ̇ = −∇J(ψ)`, `ψ(0) = y`, so
`ψ(S) → q*`. On `[0, 1]` go straight from `q*` to `ψ(S)`; then set
`φ(1 + u) := ψ(S − u)` for `u ∈ [0, S]`, which has `φ̇ = ∇J(φ)` and ends at
`y`. The second piece costs `¼∫|2∇J(φ)|² = ∫⟨φ̇, ∇J(φ)⟩ = J(y) − J(ψ(S))`.
The segment costs at most `¼((1 + L)|ψ(S) − q*|)²`, where `L` is a Lipschitz
constant of `∇J` near `q*` and `∇J(q*) = 0`; this tends to `0` as `S → ∞`. ∎
Outside the declared subcase this text claims nothing about which quantity sets
the exponential rate (in general a quasipotential, which need not be `ΔJ`).

(c) `ΔJ` alone does not fix `E[τ_D]`. For `c > 0`, replacing `(A, G, Σ)` by
`(cA, cG, √c Σ)` turns every solution `q` of (M) into `t ↦ q_{ct}` in law;
hence `E[τ_D]` is divided by `c` while `J` and `ΔJ` are unchanged. Proof: put
`q̃_t := q_{ct}` and `W̃_t := c^{−1/2} W_{ct}`, a standard Brownian motion for
`F̃_t := F_{ct}`. Substituting `s = cu`,
`q̃_t = q_0 + ∫_0^t c b(q̃_u) du + ∫_0^t √c Σ(q̃_u) dW̃_u` (for the stochastic
integral, the left-point sums of `∫_0^{ct} Σ(q_s) dW_s` along `{c u_i}` equal
those of `∫_0^t √c Σ(q̃_u) dW̃_u` along `{u_i}`). So `q̃` solves the equation
with coefficients `(cb, √cΣ) = ((cA − cG)∇J, √cΣ)`; by uniqueness in law its law
is that of the rescaled motion, and `τ_D(q̃) = τ_D(q)/c` path by path. ∎ In
(b), `E[τ_D]` also depends on `ε`, which `ΔJ` does not contain.

*In words.* The basin of a valley and the exit time are defined precisely; in
the declared gradient case the height of the pass `ΔJ` sets the exponential
rate of exit (outside that case nothing is claimed), and even there it does not
fix the mean exit time by itself: the scale of the mobility and the noise level
also count.

### U-14 — Invariants

*Status* `PROVED_HERE`; (e) `DECLARED` · *check* (d) 2; (a)–(c), (e) 3

(a) Noiseless. `f` locally Lipschitz, `I ∈ C¹`, `⟨∇I, f⟩ = 0` on `R^n` ⇒
`I(φ_t(q))` is constant where the solution exists (chain rule).

(b) Pathwise, with noise. For `I ∈ C²` and a solution of an Itô equation
`dq = b dt + Σ dW` satisfying (H):
`dI(q_t) = LI(q_t) dt + ∇I(q_t)ᵀΣ(q_t) dW_t` with
`LI = ⟨b, ∇I⟩ + ½Tr(ΣΣᵀD²I)`. Then: `I(q_t) = I(q_0)` for all `t ≥ 0`, a.s.,
for every deterministic `q_0`, iff `LI ≡ 0` and `Σᵀ∇I ≡ 0` on `R^n`. Proof.
"If": both integrals vanish. "Only if": fix `q_0`. The continuous
semimartingale `I(q_t)` is constant, so its quadratic variation
`∫_0^t |Σᵀ∇I(q_s)|² ds` is `0` for all `t`, a.s.; the integrand is continuous
in `s`, so `|Σᵀ∇I(q_0)|² = lim_{t→0} t^{−1} ∫_0^t |Σᵀ∇I(q_s)|² ds = 0`. Then
the martingale part is `0`, `∫_0^t LI(q_s) ds = 0` for all `t`, and the same
argument gives `LI(q_0) = 0`. As `q_0` is arbitrary, both vanish everywhere. ∎

(c) In expectation. If `LI ≡ 0`, `E|I(q_0)| < ∞` and
`E ∫_0^T |Σᵀ∇I(q_s)|² ds < ∞`, then `E[I(q_t)] = E[I(q_0)]` for `t ≤ T` (as in
U-05 (b), with `I` in place of `J`: these are (I1) and (I2), and (I3) holds
trivially). Conversely, if `LI` and `|Σᵀ∇I|²` are bounded and
`E[I(q_t)] = I(q_0)` for all `t` and every deterministic `q_0`, then `LI ≡ 0`:
`E[I(q_t)] − I(q_0) = ∫_0^t E[LI(q_s)] ds`; divide by `t` and let `t → 0`
(bounded convergence, continuous paths). ∎ Continuity, or the word "topology",
does not replace these conditions.

(d) Example: why conventions must not be swapped silently. `n = 2`, `m = 1`,
`R := [[0, −1], [1, 0]]`, `σ > 0`, `Σ(q) := σRq`, `I(q) := |q|²`.

- Stratonovich reading `dq = σRq ∘ dW`. By U-02 (b),
  `c_Σ = ½(σR)(σRq) = −½σ²q`, so the Itô form is `dq = −½σ²q dt + σRq dW`
  (this is (M) with `A = 0`, `G = I`, `J(q) = σ²|q|²/4`). Then
  `Σᵀ∇I = 2σ⟨Rq, q⟩ = 0` and
  `LI = ⟨−½σ²q, 2q⟩ + σ²|Rq|² = −σ²|q|² + σ²|q|² = 0` (`R` is orthogonal). By
  (b), `|q_t| = |q_0|` for all `t`: the circle is invariant.
- Silent swap (the same symbols read as Itô, `dq = σRq dW`). Itô's formula
  gives `d|q|² = 2⟨q, σRq⟩ dW + σ²|Rq|² dt = σ²|q|² dt`, so
  `|q_t|² = |q_0|² e^{σ²t}` on every path: the radius grows exponentially.

(e) Vocabulary. An observable `I` persists over a declared horizon `[0, T]` if
it is conserved there in the sense of (a), (b) or (c). "Persistence" means this
and nothing else: not health, identity or truth.

*In words.* A quantity is conserved on every path only if neither the drift nor
the noise moves it (`LI = 0` and `Σᵀ∇I = 0`); for example, the same "turning"
noise keeps the radius fixed when it is read correctly (Stratonovich with its
correction) and makes it grow without limit when the convention is changed
silently; "persisting" means only keeping the declared observable over a
declared horizon.

### U-15 — The Ornstein–Uhlenbeck toy

*Status* `PROVED_HERE` · *check* (b), (c) 2; (a), (d) 3

`J(x) = ½kx²`, `dx = −γkx dt + σ dW`, `k > 0`, `γ > 0`, `σ ≥ 0` (this is (M)
with `n = 1`, `A = 0`, `G = γ`, `Σ = σ`).

(a) Noiseless relaxation: `x(t) = x_0 e^{−γkt}`; time scale `1/(γk)`.

(b) With noise: `x_t = x_0 e^{−γkt} + σ ∫_0^t e^{−γk(t−s)} dW_s` (check as in
U-06) is Gaussian with mean `x_0 e^{−γkt}` and variance
`σ²(1 − e^{−2γkt})/(2γk)` (Itô isometry). For `σ > 0`: if `x_0 ~ N(0, v)` is
independent of `W`, then `x_t ~ N(0, σ²/(2γk) + (v − σ²/(2γk))e^{−2γkt})`,
which equals `N(0, v)` for all `t` iff `v = σ²/(2γk)`; so `N(0, σ²/(2γk))` is
the invariant Gaussian law, and from any deterministic `x_0` the law of `x_t`
converges to it (mean and variance converge).

(c) Consistency with U-08: with `σ² = 2εγ` (the pairing `ΣΣᵀ = 2εG`) the
invariant variance is `ε/k` and the invariant density is
`∝ exp(−kx²/(2ε)) = exp(−J/ε)`.

(d) Separation and its limit: `k` (curvature of `J`, U-12), `γ` (mobility) and
`σ` (noise amplitude) play three distinct roles, but the motion depends on `k`
and `γ` only through `γk`: two toys with equal `γk` and `σ` have the same law.
From the motion alone `k` and `γ` cannot be separated; `J` must be declared
independently. None of them can be read off from a conversation.

*In words.* A toy with one quadratic valley: without noise it relaxes in a time
`1/(γk)`; with noise it keeps trembling with variance `σ²/(2γk)`; with the
paired noise the law comes out exactly as `e^{−J/ε}`; and the curvature `k` and
the mobility `γ` can be told apart only if `J` is declared separately.

## 5. One standard example: reversible diffusion on the torus

Fix `N ≥ 3`, `κ > 0`, `β > 0`, and `J(θ) = κ sum_i (1 − cos(θ_{i+1} − θ_i))` on
the torus `T^N = (R/2πZ)^N` (indices mod `N`). The reversible diffusion
`dθ = −∇J(θ) dt + √(2/β) dW` on `T^N` is studied in a separate record by the
same author: *Winding Metastability: a verified research program on
metastability of reversible diffusions on the torus* (Zenodo concept DOI
10.5281/zenodo.21776817). It is the image, under the covering map
`R^N → T^N`, of the motion (M) with `n = m = N`, `A = 0`, `G = I`,
`Σ = √(2/β) I`, `ε = 1/β` and the periodic lift of `J` as landscape; since
`div G = 0`, (M) and (M_P) coincide and (P) holds. The state space of this text
stays `R^N`. The identification, with what may and may not be inferred from
it, is written out in the binding record MATH-OBR-N0-v1 (2026-09-26; one
independent AI read, same provider, passed). It is an example of the motion and
nothing more: no statement of this edition rests on it, and results proved for
this case do not extend to other cases of the motion.

## 6. What this edition does not say

- No physics: no particle, mass, gravity, physical field, spin, charge, vacuum,
  temperature, Boltzmann constant, friction, inertia, momentum, clock, arrow of
  time, entropy production, physical constant or gauge object. `J` is a
  function with no unit; `p` and `M` in U-11 are an auxiliary variable and a
  matrix; `ε` is a parameter.
- No applied or empirical claim: no person, mind, agent, body or organization
  instantiates any symbol.
- No infinite-dimensional, topological or infinite-barrier claim.
- No statement rests on another work of the author.
- No verdict on the 2025 editions as a whole beyond Section 1: their physical
  claims are withdrawn; the claims of the 2025 research texts are traced one by
  one in Annex B (re-proved, replaced or not carried); Section 1 corrects four
  statements of the public v1.2, checked against its PDF.
- Every statement is local, conditional on its hypotheses and formal; none
  claims human, cross-provider or formal (Lean) verification.

## 7. Open points (not asserted)

- Uniqueness of the invariant law of the paired motion, and convergence to it.
- Checking hypothesis (R) of U-07 (b) for concrete coefficients.
- Exit rates outside the gradient subcase (quasipotentials).
- A full comparison of the 2025 research texts with the public v1.0, v1.1 and
  v1.2 (not made; Annex B types the research texts).
- Whether an unstated restriction of the field setting of GTPA v1.2 (its
  Ax 1.3) would exclude the finite-dimensional counterexamples of Annex A (A-2,
  A-3).

## 8. References

Records:

- C. Valdepeñas, *UFD: Unified Field Dynamics. A Geometric and Topological
  Framework for Unified Field Dynamics*, Zenodo, v1.0 10.5281/zenodo.17643573
  (2025-11-18), v1.1 10.5281/zenodo.17662668 (2025-11-21), v1.2
  10.5281/zenodo.17994168 (2025-12-20); concept 10.5281/zenodo.17643572.
- C. Valdepeñas, *GTPA: General Theory of Physical Agency. A Topological
  Instantiation of TECD Dynamics within UFD Geometry*, v1.2, Zenodo,
  10.5281/zenodo.17994303 (2025-12-20). Page numbers in Annex A are PDF page
  indices of GTPA v1.2.

Textbooks and papers (locators as used above):

- A. Dembo, O. Zeitouni, *Large Deviations Techniques and Applications*, 2nd
  ed., Springer, 1998. §5.7, Thm 5.7.11.
- S. N. Ethier, T. G. Kurtz, *Markov Processes: Characterization and
  Convergence*, Wiley, 1986. Ch. 4, Thm 9.17.
- M. I. Freidlin, A. D. Wentzell, *Random Perturbations of Dynamical Systems*,
  3rd ed., Springer (Grundlehren 260), 2012. Ch. 4.
- S. Hottovy, A. McDaniel, G. Volpe, J. Wehr, "The Smoluchowski-Kramers limit
  of stochastic differential equations with arbitrary state-dependent
  friction", *Comm. Math. Phys.* 336 (2015) 1259–1283 (arXiv:1404.2330).
  Thm 1 and §III.
- I. Karatzas, S. E. Shreve, *Brownian Motion and Stochastic Calculus*, 2nd
  ed., Springer, 1991. §3.2; Thm 5.2.5; Prop. 5.3.20; §5.4.
- Y.-A. Ma, T. Chen, E. B. Fox, "A Complete Recipe for Stochastic Gradient
  MCMC", NeurIPS 28 (2015) (arXiv:1506.04696). Thm 1.
- E. Nelson, *Dynamical Theories of Brownian Motion*, Princeton University
  Press, 1967 (2nd ed. online, 2001). Ch. 10, Thm 10.1.
- B. Øksendal, *Stochastic Differential Equations*, 6th ed., Springer, 2003.
  Cor. 3.1.7, Thm 3.2.1, §3.3, Thm 4.2.1, Thm 5.2.1, Thm 7.3.3.
- G. A. Pavliotis, *Stochastic Processes and Applications*, Springer (Texts in
  Applied Mathematics 60), 2014. §3.2, §6.5.1.
- P. E. Protter, *Stochastic Integration and Differential Equations*, 2nd ed.,
  Springer, 2005. Ch. V, §5.

## Annex A. Five questions on the base motion of GTPA v1.2

GTPA v1.2 builds on the same three-part motion. Five questions about that
motion were answered with the statements of this text (the IDs are those of the
question list used for the GTPA v1.2 audit). Each answer has exactly one
verdict: `HOLDS_UNDER_STATED_HYPOTHESES`, `FAILS_WITH_COUNTEREXAMPLE`,
`ILL_POSED_AS_WRITTEN` (with the repair adopted) or `OPEN`. In GTPA v1.2 the
drift term in the place of the circulating part is written `X_H`; v1.2 does not
define it in terms of `∇J`. Quotations are from GTPA v1.2; they are quoted, not
asserted.

| Row | Question (short) | Verdict | Check | Rests on |
|---|---|---|---|---|
| A-1 · EG-02.3 | Mobility: which quadratic form is the decrease rate of `J`? | `ILL_POSED_AS_WRITTEN` | 2 | U-04, U-05, U-06, U-10 |
| A-2 · EG-02.7 | Is App C's equation the Itô form of Ax 1.2? | `FAILS_WITH_COUNTEREXAMPLE` | 2 | U-02, U-05, U-11, U-14 |
| A-3 · EG-03.0 (Thm 1.1 half) | Is `E[dJ/dt] ≤ 0`? | `FAILS_WITH_COUNTEREXAMPLE` | 2 | U-03, U-04, U-05, U-06, U-07 |
| A-4 · EG-02.h | First order or (q,p)? | `ILL_POSED_AS_WRITTEN` | 2 | U-02, U-11 |
| A-5 · pairing (FDT–Γ) | Which coefficient pairs with the noise? | `ILL_POSED_AS_WRITTEN` | 2 | U-05, U-08, U-09, U-11, U-15 |
| A-6 · EG-09.1, EG-09.2 | Which equation; which level | settled by declared convention | 3 | Section 3 |

### A-1 · EG-02.3 — mobility and the decrease rate of J

Question: under which conditions on the mobility `G(q)` do `|∇J|²`, `|G∇J|²`
and `⟨∇J, G∇J⟩` coincide up to a constant? Which one is the decrease rate of
the equation of Ax 1.2 (p.17)? Is Protocol 11.1's `tau` the same clock?
Locators: Ax 0.2 (p.16) "d(tau) / dt ~ || grad J(q) ||^2"; Def 1.2 (p.19) and
summary 1.3 (p.5) "d(tau) / dt ~ || G(q) * grad J(q) ||^2"; Protocol 11.1
(p.60) "d(tau)/dt = Ramp( 0 -> 1, T_boot )".

Verdict `ILL_POSED_AS_WRITTEN`. `tau` is defined only up to "~", with three
different right-hand sides (two functions of the state and a ramp in time), so
it has no single referent. The three quadratic quantities are proportional,
with factors that do not depend on the gradient, at a point iff
`G(q) = c(q)I`, and with one factor everywhere iff `G ≡ cI` (U-10 (a)); the
pair `|G∇J|²`, `⟨∇J, G∇J⟩` alone is proportional iff `G` is a multiple of an
orthogonal projection (U-10 (a′)). The decrease rate of `J` along the noiseless
motion is `⟨∇J, G∇J⟩` (U-04), neither printed form in general: Ax 0.2's form
matches it up to one factor, for every landscape, only when `G = cI`, and
Def 1.2's only when `G` is a multiple of an orthogonal projection (U-10 (a′),
(d)); for `G = diag(1, 2)`, `|G∇J|²/⟨∇J, G∇J⟩` is `1`
at `∇J = e₁` and `2` at `∇J = e₂` (U-10 (b)). With noise the expected rate is
`E[LJ]`, which adds the trace term and can be positive (U-05, U-06). Protocol
11.1's `tau` belongs to GTPA's agent layer. Repair adopted: no `tau` and no
clock; the one object is the decrease rate of `J` (U-04 without noise, U-05
with noise); any time reading of it is a hypothesis downstream of this text.

### A-2 · EG-02.7 — Itô or Stratonovich

Question: is App C's equation the Itô form of Ax 1.2's Stratonovich equation?
If so, where is the conversion term `½ sum_k (DΣ_k) Σ_k`, and is it Thm 6.1's
"Correction_Ito"? Is the (q,p) system of App C a lift of Ax 1.2 or a different
dynamics? Locators: Stratonovich declared on p.5, p.16 (Ax 0.3), p.17 (Ax 1.2),
p.18, p.63 (App A) and p.86 (App G); plain products on p.43 and p.70 (App C.1);
Thm 6.1 on p.38.

Verdict `FAILS_WITH_COUNTEREXAMPLE`. The Itô form of Ax 1.2 is
`dq = [X_H − G∇J + c_Σ] dt + Σ dW` (U-02 (b)); neither this equation nor `c_Σ`
is printed in v1.2, although Ax 0.3 (p.16) says that the implementation of
noise in the agent (for exploration) must include the geometric drift
correction term; no page writes that term. App C.1 is neither that equation
nor any rewrite of Ax 1.2: its state is `(q, p) ∈ R^{2n}` and its `q`-paths
have zero quadratic variation, while those of Ax 1.2 with `Σ ≠ 0` do not
(U-11 (a)).
Counterexample, `n = 1`: `X_H = 0`, `G = 1`, `J = q²/2`, `Σ = 1` (constant, so
the two readings of Ax 1.2 coincide), `M = 1`, `Γ = 1`. Ax 1.2 gives
`dq = −q dt + dW`, with `⟨q⟩_t = t`; App C.1 gives `dq = p dt`,
`dp = (−q − p) dt + dW`, with `⟨q⟩_t = 0`; the laws of the `q`-paths differ.
Thm 6.1's term is not `c_Σ`: `c_Σ` is built from first derivatives of `Σ` and
vanishes when `Σ` is constant, while the printed Thm 6.1 expression contains
second derivatives of a map of the state and no derivative of `Σ` (with
`Σ ≡ 1` and `φ(q) = q²`, `c_Σ = 0` while the Itô term of `φ` is `1`). App C.1
also puts `X_H`, a drift of the first-order equation, into the `p`-equation; its
relation to a first-order motion is a limit, not an identity (U-11 (b), (c)).
Repair adopted: Itô is the reference form; Stratonovich input is converted with
`c_Σ` written out; U-14 (d) shows what a silent swap does; (q,p) systems are
separate objects (C2, C3, C5; U-02, U-11).

### A-3 · EG-03.0, Theorem 1.1 half — does the mean of J decrease?

Question: for the Stratonovich equation of Ax 1.2, is `E[dJ/dt] ≤ 0`? This
needs `⟨∇J, X_H⟩ = 0` and control of the positive trace term induced by the
noise. Locators: Thm 1.1 (p.19) "d(J) / dt <= 0 (in expectation)", with no proof
block; Ax 1.2 (p.17); the gloss of `X_H` (p.18). v1.2 never states
`⟨∇J, X_H⟩ = 0`. (The Theorem 9.1 half of the question belongs to the GTPA
audit, not to this text.)

Verdict `FAILS_WITH_COUNTEREXAMPLE`. Noise: Ax 1.2 with `n = 2`,
`J = |q|²/2`, `G = I`, `Σ = √(2ε) I` (constant, so the Stratonovich and Itô
readings coincide) and `X_H = Sq` with `S = [[0, 1], [−1, 0]]`, a rotation field
that preserves area and has `⟨∇J, X_H⟩ = 0`, or `X_H = 0`. From `q_0 = 0`,
`E[J(q_t)] = ε(1 − e^{−2t})`, strictly increasing, with
`d/dt E[J] = 2εe^{−2t} > 0` (U-06 (b)). Circulating part without noise:
`n = 2`, `J = q₁²/2`, `G = I`, `Σ = 0`, `X_H = (1, 0)` (divergence-free; it
circulates for `h(q) = q₂`, not for `J`); then `dJ/dt = q₁ − q₁²`, which is
`1/4 > 0` at `q₁ = 1/2` (U-03 (b)). Scope: v1.2 places Ax 1.2 on an unspecified
Sobolev space and fixes no `J`, `G` or `Σ`; both counterexamples are instances
of the printed equation on the finite-dimensional state space declared here.
Repair adopted: "E[J] decreases" is withdrawn as a law; U-04, U-05 and U-07
are stated in its place, each with its hypotheses.

### A-4 · EG-02.h — first order or (q,p)

Question: the first-order equation of Ax 1.2 (pp.17–18) and the (q,p) form
printed as the same equation in App C.1 (p.70) disagree. Locators: Ax 1.2
(p.17), first order in `q`, mobility `G(q)`, Stratonovich noise; App C.1
(p.70), a (q,p) system with a term `−Γp`; App B.1 (p.67), which attributes that
term to the same equation; a third variant on p.43; Ax 1.3 (p.18), a Sobolev
space.

Verdict `ILL_POSED_AS_WRITTEN`. v1.2 gives one name to at least two
non-equivalent equations (and p.43 prints a third); they are not the same
equation in any convention (U-11 (a); instance in A-2). The (q,p) form puts
`X_H` in the `p`-equation and has no mobility `G`; the first-order form has no
`Γ`. The relation that mathematics supplies is a limit, not an identity: with
constant coefficients, the small-`m` limit of a (q,p) system whose coefficient
of `v = M^{−1}p` is `γ` is the first-order motion with `G = γ^{−1}` (U-11 (b);
`G = (mΓ)^{−1}` when `Γ` multiplies `p` itself and `M = mI`); with a
q-dependent coefficient (one dimension, paired noise) the limit carries the extra drift `εG'`, so it is the
paired motion (M_P) with `A = 0` (U-11 (c)). Repair adopted: one base motion,
the first-order Itô equation (M) on `R^n`, with its paired variant (M_P) under
(P); (q,p) systems are separate objects that must be declared with their
relation to (M); the Sobolev state space is not adopted.

### A-5 · the pairing of noise and coefficient (FDT–Γ)

Question: v1.2 relates `ΣΣᵀ` to twice a coefficient `Γ` times a temperature
factor (Ax 0.3, p.16; Thm 4.1, p.31, with a time-dependent `Γ(t)` and a
time-dependent level; summary 4.3, p.7). Which coefficient of which equation
does `Γ` pair with, and is the relation a constraint that fixes `Σ` or a
separate axiom? Locators: Ax 1.2 (p.17), where the slide is scaled by `G(q)`
and there is no `Γ`; pp.43, 67, 70, 71, where `Γ` multiplies `p`; p.66, where
the same letter names another object.

Verdict `ILL_POSED_AS_WRITTEN`. v1.2 never says which coefficient its `Γ` is:
the first-order equation has `G` and no `Γ`; `Γ` multiplies `p` in the (q,p)
forms, whose noise acts in a different equation (U-11 (a)); Thm 4.1's `Γ(t)`
depends on time and belongs to no printed equation. Ax 0.3's right side does not
depend on `q`, while Thm 4.1's depends on `t`: two relations under one name. For
the first-order motion, the pairing under which `e^{−J/ε}` is stationary pairs
the noise with the same `G` that scales the slide, `ΣΣᵀ = 2εG`, together with
the drift correction `ε div G` and `div_c A = 0` (U-08). The pairing alone is not
enough: the Stratonovich reading leaves the factor `g^{−1/2}`, the uncorrected
Itô reading leaves `g^{−1}`, and for every correction `αεg'` with `α ≠ 1` (and
`V` bounded below) `e^{−V/ε}` is stationary only when `g` is constant (U-09).
For a (q,p) system the coefficient in play is the coefficient `γ` of
`v = M^{−1}p`; in the small-`m` limit the mobility is `G = γ^{−1}` and the
noise `2εγ` becomes `ΣΣᵀ = 2εG` (U-11 (b)); with `Γ` multiplying `p` and
`M = mI`, `γ = mΓ`. Repair adopted: the pairing is the named hypothesis (P) of
U-08, a constraint on the coefficients that fixes `ΣΣᵀ = 2εG` given `G` and
`ε`, adds `ε div G` to the drift and requires `div_c A = 0`; it is neither an
axiom nor a consequence of the motion (U-08 (c)). There is no temperature: one
constant parameter `ε > 0`.

### A-6 · EG-09.1 and EG-09.2 — settled by declared convention

| Question | Settled by this text | What GTPA v1.2 says |
|---|---|---|
| EG-09.1: which equation, which calculus, which state space | The first-order Itô equation (M) on `R^n`; under (P) its paired variant (M_P), equal to (M) iff `div G ≡ 0` (C1, C2, C4, C5) | Inconsistent: Ax 1.2 (first order, Stratonovich, p.17) against App C.1 ((q,p), noise as a plain product, p.70; App B.1, p.67) and a third variant (p.43); a Sobolev state space (p.18) |
| EG-09.2: which level, which coefficient `Γ` pairs with, constraint or axiom | No temperature; one constant `ε > 0`; the noise pairs with `G` through the named hypothesis (P), a constraint and not an axiom (C4, U-08) | Inconsistent: a level `T` (p.16) against a time-dependent level (pp.7, 31); `Γ` never identified |

The settlement is by declaration; it does not claim to recover what v1.2
meant. Check level 3 (a declaration and a reading).

## Annex B. Lineage: what happened to the 2025 UFD claims

**Texts typed.** The tables below were typed in July 2026, in a claim atlas and
a claim ledger of the author's formal-mathematics program, against the author's
research texts: UFD of 19 November 2025 (3039 lines) and "UFD II" of 21 November
2025 (54 articles on foundations, particles, interactions, gravity, cosmology,
condensed matter, information and predictions; 6687 lines). They were not typed
against the public PDFs of v1.0, v1.1 or v1.2; the 19 November text is dated
between v1.0 (18 November) and v1.1 (21 November). "Not carried" means only
that a claim does not enter this edition; it is not a verdict on the claim.

**B.1 Claims about the base motion (line numbers of the research texts).**

| 2025 claim | Fate in v2.0 |
|---|---|
| A three-term equation with Stratonovich noise on a field space; the circulating part written `J_symp * grad J` (UFD 19-11, lines 123–142) | Replaced in finite dimension: (M) in Itô form with the conversion written out (U-01 to U-03); the circulating part keeps the form `A∇J` with `A` antisymmetric; the field space is not adopted |
| The law of the motion converges to a density `∝ exp(−2J/D)` (19-11, lines 136–142 and 519–521; UFD II, lines 996–1126) | Replaced by U-08 (stationarity under (P), with the correction `ε div G`); U-09 shows the failure without it; convergence and uniqueness not claimed. The exponent's normalization differs inside the 19-11 text (`exp(−2J/D)` at lines 141 and 521, `exp(−J/D)` at line 431) |
| `d/dt E[J] = −E⟨∇J, G∇J⟩ + ½ Tr(…)`, with the conclusion that `J` is minimized; the mean of `J` decreases ('for macroscopic states'; 'far from equilibrium' is not a hypothesis) (19-11, lines 166–174, 291–313, 381–440; UFD II, lines 3982–4068) | False as a law (U-06). The two-term shape survives as the Itô generator (U-05 (a)); the Stratonovich reading adds a different term (U-05 (d)); replaced by U-04 and U-07 |
| The noise amplitude is linked to the mobility `G(q)` (19-11, line 503) | Kept as the named hypothesis (P) (U-08), with `ε` a parameter and no temperature; uniqueness not claimed |
| Local Taylor expansion at a critical point (19-11, lines 207–213) | Re-proved in finite dimension (U-12 (a)); its physical reading is not carried |
| Hessian eigenvalues are masses (19-11, lines 143–165) | Not carried: the Hessian is curvature only (U-12 (e)) |
| Wells with a positive Hessian are metastable under small noise (19-11, lines 601–641) | Replaced by definitions and the gradient-case exit law (U-13 (b)); nothing outside that case |
| Topological invariants carry infinite barriers (19-11, lines 191–197) | Not carried; no topological claim |

**B.2 All 121 claims of the two texts, by class.**

| Class (atlas) | 19-11 | 21-11 | Fate in v2.0 |
|---|---:|---:|---|
| Exact match with a proved result of that program | 0 | 0 | none |
| Re-proof required | 12 | 3 | 4 re-proved or replaced in finite dimension (U-01 to U-04, U-12, U-13 in the gradient case); the others not carried (topology, homotopy groups, Green functions, linear flows, classes of admissible landscapes) |
| Counterexample or conflict | 11 | 8 | 4 checked again here (U-06, U-09); 3 about infinite barriers not carried; 12 not carried |
| Source gap (physical identifications) | 29 | 26 | Not carried; only the mathematical part of two rows is used (the pairing, U-08, U-09) |
| Metaphor only | 5 | 3 | Not carried |
| Empirical claim | 3 | 21 | Not carried |
| Total | 60 | 61 | 121 |
