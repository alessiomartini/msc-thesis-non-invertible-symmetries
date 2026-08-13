# Non-Invertible Symmetries of the 3d Complex Scalar — MSc Thesis (work in progress)

LaTeX source of the Master's thesis of **Alessio Martini**, Institute for
Theoretical Physics, University of Amsterdam, supervised by **Diego Hofman**.

Working title: *Non-invertible symmetries to study 3d complex scalar boson*.

> **Status: draft in progress.** The abstract, the introduction and the
> conclusions are still placeholders. Most of the written material currently
> sits under a section explicitly marked *Sparse Notes*: self-contained
> write-ups of the topics that will go into the final thesis, not yet stitched
> into a single argument. Passages in <span style="color:red">red</span> in the
> compiled PDF are the author's own open questions, deliberately left visible.

## What the thesis is about

The thesis develops the modern, topological reformulation of symmetry and
applies it to a concrete three-dimensional model.

- **Symmetries as topological operators.** An ordinary continuous global
  symmetry with group $G$ gives, via Noether, a conserved current $j^a$ whose
  Hodge dual is a closed $(d-1)$-form. Integrating it over a codimension-1
  surface produces an operator $U_g(\mathcal{M}_{d-1})$ that is invariant under
  continuous deformations of the surface — a *topological operator* — and whose
  fusion reproduces the group law. Reversing the logic (topological operator
  ⟹ symmetry) is what makes the notion *generalized*: it drops the requirement
  of a Noether current, of codimension 1, and eventually of invertibility.
- **Generalized global symmetries.** Higher-form symmetries (operators of
  higher codimension acting on extended objects), and the distinction between a
  topological operator and a symmetry defect.
- **Anomalies, in the modern formalism.** Anomaly inflow and the classification
  of anomalies through a bulk one-dimension-higher SPT phase; the resulting
  infrared constraint — an anomalous theory cannot flow to a trivially gapped
  vacuum; mixed anomalies between several symmetries, and what happens when one
  factor is gauged: higher-group structures, or non-invertible defects.
- **Applications.** The ABJ anomaly in 4d — the historical example where gauging
  turns a broken axial symmetry into a non-invertible one — and the main target,
  the complex scalar boson in 3d.

## Repository layout

```
main.tex            The whole thesis: one file, revtex4 document class
main.bib            BibTeX references
utphys.bst          Bibliography style (utphys, the standard hep-th style)
.github/workflows/  CI that compiles the draft on every push
```

## Building

Single-file `revtex4` document. Standard pdfLaTeX + BibTeX cycle:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

The document draws diagrams with TikZ and `xy`, so a reasonably complete TeX
distribution (TeX Live full, MacTeX) is expected.

## Continuous builds

`.github/workflows/` compiles `main.tex` on **every push** using
`xu-cheng/latex-action`, and publishes the resulting `main.pdf` as a **draft
GitHub Release** named `Draft <timestamp>`.

This means the latest compiled PDF is always available from the repository's
Releases page without cloning or installing LaTeX — convenient for sharing a
current draft with a supervisor. Releases are created as drafts, so nothing
becomes publicly visible until it is explicitly published.

## Related repository

- [`anomalies_qm_bsc_thesis`](https://github.com/alessiomartini/anomalies_qm_bsc_thesis)
  — the Bachelor's thesis, on the scale anomaly of the $1/x^2$ potential in
  quantum mechanics: the same theme (a classical symmetry broken by
  quantization) in its simplest possible setting.
