# Looking for Continuous Non-Invertible Symmetries in the 3d Complex Scalar Boson — MSc Thesis

Master's thesis of **Alessio Martini**, MSc in Theoretical Physics, Institute for
Theoretical Physics, University of Amsterdam, supervised by **Dr. Diego Hofman**.
Defended **24 June 2026**.

| File | |
| --- | --- |
| [`continuous_non_inv_sym_in_3d_OFFICIAL.pdf`](continuous_non_inv_sym_in_3d_OFFICIAL.pdf) | **The thesis as submitted — 103 pages.** |
| [`Cont_NonInv_Symm_Engineering___master_thesis_presentation.pdf`](Cont_NonInv_Symm_Engineering___master_thesis_presentation.pdf) | The defence talk, *How to Engineer Continuous Non-Invertible Symmetries* — 40 slides. |

## Abstract

The thesis studies generalized global symmetries in quantum field theory,
focusing on the **3d XY-model** and its relation to the **abelian Higgs model**
through **particle–vortex duality**. The driving question concerns the emergent
**1-form symmetry** of the spontaneously-broken phase: is that infrared symmetry
already encoded in the ultraviolet data, as a non-invertible symmetry?

The answer is **negative, and that is a result rather than a dead end**: the
emergent symmetry *cannot* be captured as a non-invertible symmetry in the UV
with the topological tools and frameworks currently available.

The **main original contribution** is constructive: an explicit extension of
**continuous non-invertible defects to general spacetime dimensions and
arbitrary $p$-form degrees**, within mixed 't Hooft anomalies. Using the
**Symmetry TFT (SymTFT)** framework, four scenarios are analysed:

| Scenario | Anomaly | Outcome |
| --- | --- | --- |
| 1 | Cubic, $F_A \wedge F_B \wedge F_B$ | **Works** — generates a continuous non-invertible symmetry on the boundary |
| 2 | Linear mixed, $F_A \wedge F_B \wedge F_C$ | **Works** |
| 3 | Quartic, $F_A \wedge F_B \wedge F_C \wedge F_D$ | **Fails** |
| 4 | Quadratic, $F_A \wedge F_B$ | **Fails** |

Scenarios 3 and 4 are included deliberately. A method that succeeds everywhere
it is tried has not been tested; by exhibiting where the construction breaks
down, the thesis maps the **exact boundaries of the framework** rather than only
its successes.

## How the thesis is built

The document is long because it is self-contained: it develops the whole modern
picture of symmetry before applying it.

| § | Chapter | Content |
| --- | --- | --- |
| II | Ordinary and generalized global symmetries | Noether currents as closed $(d-1)$-forms; topological symmetry operators; charged operators, representations and selection rules; higher **$p$-form symmetries** and their $(d-p-1)$-dimensional defects; fusion rules; **gauging and the dual symmetry**; non-invertible symmetries, where group-like fusion gives way to **categorical fusion** |
| III | The space of topological defects | Simple vs. non-simple operators; **higher fusion categories** as symmetry structures; topological local operators and dual symmetry operators |
| IV | Anomalies | Terminology first, then the description in terms of topological operators: **anomaly inflow** and anomaly polynomials |
| V | Mixed anomalies and their gauging | Continuous symmetries and **higher-group** formation; discrete gauging in the presence of anomalies; "wild" anomalies and non-invertible defects |
| VI | Symmetry Topological Field Theory | Construction of the discrete SymTFT, its Hamiltonian formulation and the choice of boundary conditions; 't Hooft anomalies inside it; then **continuous $U(1)$ symmetries** via $\mathbb{R}$ and $U(1)$ bulk gauge fields ($\mathbb{R}\times\mathbb{R}$ and $U(1)\times\mathbb{R}$ formulations) and dynamical gauging |
| VII | **Laboratory** | The machinery applied, model by model: the free fermion and the **ABJ anomaly in 4d**; the complex scalar and abelian-Higgs model in 3d with its **web of dualities**; the **Maxwell model** coupled to electric and magnetic charges, in its dual-photon formulation, with the special cases of three and four dimensions; a **superfluid with a topological term**; and the **Goldstone–Maxwell model** — the last two both gauging a **$(-1)$-form symmetry** |
| VIII | Outlook | The four engineering scenarios above, an intrinsic SymTFT formulation of continuous non-invertible symmetries, conclusions, and open questions |

### The Interludes

Nine short sections labelled **Interlude A–I** are threaded through the main
argument, each taking up a question that would otherwise derail it: local
symmetries; generalized symmetries in **non-relativistic** settings; gauging on
manifolds **with boundaries**; genuine vs. non-genuine operators; topological
operators vs. symmetry defects; the **generalized Landau paradigm**;
consequences of generalized symmetries; **hydrodynamics**; and **dynamical
gravity**.

They are the most browsable part of the thesis — each is readable on its own.

## The source

`main.tex` is the LaTeX source of the submitted thesis — a single `revtex4`
document of about 2,200 lines, imported from the Overleaf project it was written
in. It has been checked against the committed PDF: every section heading and a
sample of prose passages match, so the source in this repository is the one that
produced `continuous_non_inv_sym_in_3d_OFFICIAL.pdf`, not a later revision.

```
main.tex        The thesis
main.bib        40 references
utphys.bst      Bibliography style (utphys, the standard hep-th style)
images/         15 figures used by the text — TikZ diagrams exported to PDF,
                plus three raster images
```

### Building

Standard `revtex4` cycle — pdfLaTeX and BibTeX, no special engine required:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

The document draws diagrams with TikZ and `xy`, so a reasonably complete TeX
distribution (TeX Live full, MacTeX) is expected.

`.github/workflows/build.yaml` runs the same build on **every push** with
`xu-cheng/latex-action`, publishing `main.pdf` and `main.bbl` as a **draft
GitHub Release** named `Draft <timestamp>`. A current build is therefore always
available from the Releases page without a local TeX installation.

Build artefacts (`.aux`, `.bbl`, `.log`, `.synctex.gz`, and the CI's
`main.pdf`) are gitignored; the submitted PDF is committed under its own name so
it is never overwritten by a local build.

## AI declaration

The thesis carries an explicit declaration (p. 99): generative AI tools were used
for brainstorming, literature search, conceptual clarification, translation and
English-language editing, with all output systematically verified against primary
sources. The physics, and the original contribution in particular, are the
author's own.

## Related repository

- [`bsc-thesis-scale-anomaly-in-qm`](https://github.com/alessiomartini/bsc-thesis-scale-anomaly-in-qm)
  — the Bachelor's thesis, on the scale anomaly of the $1/x^2$ potential: the
  same theme, a classical symmetry broken by quantization, in the simplest
  setting quantum mechanics allows.
