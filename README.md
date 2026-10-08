# UFD: The Base Motion Without Physics

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23171454.svg)](https://doi.org/10.5281/zenodo.23171454)

**A corrective edition, version 2.0.** A short mathematical text about one
noisy motion on a landscape, with every physical claim of the 2025 versions
withdrawn.

By **C. Valdepeñas**. Drafted by an AI system (Claude, by Anthropic) working
for the author. **Stated up front: every check so far is by AI systems from
one provider and by machine recomputation. No person and no AI system of
another provider has checked this text.**

## What UFD is, in plain words

A point moves across a landscape: a function `J` that gives a "height" to
every point. The motion has three parts:

- one part circulates without changing the height;
- one part slides down the slope, faster or slower according to a mobility `G`;
- and one part is noise.

The text fixes one way of doing the calculus with noise (Itô, with the
conversion from Stratonovich written out) and one constant noise level `ε`.
It then states fifteen numbered statements about this motion (U-01 to U-15),
each with its hypotheses, a status, a check level and a proof or a textbook
reference. Two examples of what it says: with noise, the mean height can rise;
and the equilibrium law proportional to `exp(−J/ε)` is stationary when the
noise is paired with the mobility, the drift carries the correction `ε div G`,
the circulating part has no sources, `exp(−J/ε)` is integrable and the motion
is well posed. It is textbook material stated carefully, not a new theory.

Two annexes answer five questions on the base motion of GTPA v1.2 and trace
what happened to each 2025 claim.

## Status

- **Published on Zenodo on 2026-10-05**, version 2.0:
  [10.5281/zenodo.23171454](https://doi.org/10.5281/zenodo.23171454).
- **It supersedes v1.0, v1.1 and v1.2 (2025)**, whose physical claims
  (particles, mass, quantization, physical constants, gravity, the
  unification of physical theories) are **withdrawn**. No symbol in v2.0 has a
  physical reading. The 2025 records stay on Zenodo as history.
- All versions: concept DOI
  [10.5281/zenodo.17643572](https://doi.org/10.5281/zenodo.17643572).

## How it was checked

As the record states, with check levels from strongest to weakest:
(1) formally checked in Lean; (2) the decisive calculation recomputed by
machine; (3) read by an independent AI context; (4) written only.

- The statements and proofs were read by independent AI contexts from the
  same provider as the drafting model (Claude, by Anthropic). Their findings
  were repaired and the repairs re-checked.
- The decisive calculations were recomputed by machine (symbolic algebra and
  seeded numerics): 24 agree, 0 disagree.
- Nothing is checked in Lean.
- Each statement in the text gives its own level.

## Files

| File | On the Zenodo record | What it is |
|---|---|---|
| `UFD-v2.0.pdf` | yes | The published edition, byte-identical to the file on the Zenodo record. |
| `UFD-v2.0.md` | no | The Markdown source of `UFD-v2.0.pdf`; same text, not deposited. |
| `LICENSE` | no | CC BY-NC-SA 4.0, the licence of the Zenodo record. |
| `CITATION.cff` | no | Citation metadata (version DOI). |

The released texts are copied byte for byte from the author's working
repository. They contain a few provenance lines that name files of that
repository; those files are not part of this one.

## How to cite

Valdepenas, C. (2026). *UFD: The Base Motion Without Physics. A Corrective
Edition* (Version 2.0). Zenodo.
[https://doi.org/10.5281/zenodo.23171454](https://doi.org/10.5281/zenodo.23171454)

See `CITATION.cff`. This repository is a mirror of the Zenodo record and is
not connected to Zenodo's GitHub integration: the DOIs above are the only
ones.

## Relation to the other two repositories

- **GTPA** ([github.com/cvaldepenas/gtpa](https://github.com/cvaldepenas/gtpa);
  [10.5281/zenodo.23195763](https://doi.org/10.5281/zenodo.23195763)). UFD
  is the base motion that GTPA builds on: GTPA models an agent that acts on
  this motion, and GTPA v2.1 uses UFD v2.0 unchanged.
- **MATH, Winding Metastability**
  ([github.com/cvaldepenas/winding-metastability](https://github.com/cvaldepenas/winding-metastability);
  [10.5281/zenodo.21776817](https://doi.org/10.5281/zenodo.21776817)). No
  dependence. The reversible diffusion on the torus studied there is one
  standard example of the UFD motion (Section 5 of the text): an example of
  the motion and nothing more. No statement of UFD rests on it, and results
  proved for that case do not extend to other cases of the motion. Nothing in
  GTPA rests on MATH either (MATH ↔ GTPA = UNBOUND).

## En español

UFD 2.0 es un texto matemático corto sobre un movimiento con ruido en un
paisaje `J`: una parte gira sin cambiar la altura, otra baja por la pendiente
según una movilidad `G`, y otra es ruido. Retira todas las afirmaciones
físicas de las versiones de 2025 (v1.0, v1.1 y v1.2), que quedan en Zenodo
como historia. Se publicó el 05-10-2026 (10.5281/zenodo.23171454). Lo han
leído IAs independientes del mismo proveedor (Claude, de Anthropic) y las
cuentas decisivas se rehicieron por máquina (24 coinciden, 0 discrepan);
nada está comprobado en Lean y ninguna persona lo ha revisado. Es el
movimiento de base sobre el que se construye GTPA; MATH es solo un ejemplo,
no un apoyo.
