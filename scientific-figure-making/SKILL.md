---
name: scientific-figure-making
description: "Covers publication-ready figures for academic papers, slides, and reports. Python backend (matplotlib/seaborn): bars, trends, scatter, heatmaps, multi-panel layouts with publication house style, print/vector export conventions, and parity with figures4papers demos. R backend (ggplot2, patchwork, ComplexHeatmap): use when the user needs annotated heatmaps, admixture bar plots, or any figure type better served by R. Population-genetics figure types are explicitly in scope: PCA scatter, admixture/STRUCTURE bars, FST heatmap, Manhattan/XP-EHH regional plot, phylogenetic tree with metadata. Always start from the figure contract (core conclusion -> evidence hierarchy -> chart type) before writing code. Do not use for interactive dashboards or web viz (Plotly, Altair, Bokeh), exploratory-only plots without a publication target, or Illustrator/Figma-first infographic workflows."
created: 2026-05-28 17:27
updated: 2026-05-28 17:27
---

# Scientific figure making

Open `references/` only as needed; do not preload every file. **Always begin with the figure contract** (Step 0 below) before opening any reference file or writing code.

## Step 0 -- Figure Contract (mandatory, before any code)

Before selecting a chart type or writing a single line, fill in the contract mentally (or ask the user if unclear):

1. **Core conclusion** -- What is the one sentence this figure must communicate?
2. **Evidence hierarchy** -- Which panel carries the primary claim? Which panels are supporting evidence?
3. **Chart type** -- Selected *after* answering 1 & 2, not before.
4. **Backend** -- Python (matplotlib) or R? See `references/r-backend.md` for the decision rule.
5. **Statistics** -- What error bars, p-values, or effect sizes must appear?
6. **Export constraints** -- Journal DPI/format requirements; SVG editable text needed?

> If the user says "draw a PCA" without more context, ask: what comparison is the core message?
> Colours by population? By admixture proportion? That answer determines layout and palette before any code.

## When to load this skill

- Figures for **papers, slides, or reports** requiring **publication-grade** output (fonts, palette, spines, legends, export).
- **Python / matplotlib** requests: grouped bars, trend lines, heatmaps, scatter, multi-panel grids, PDF/SVG/high-DPI.
- **R requests**: ComplexHeatmap, ggplot2/patchwork multi-panel, ggtree, CMplot -- use `references/r-backend.md`.
- **Population-genetics figures**: PCA scatter, admixture bars, FST/pi heatmap, XP-EHH regional plot, Manhattan plot, phylogenetic tree + metadata strips.
- References to **figures4papers** `figure_*` projects or "same style as the repo figures."

## When not to load

- **Plotly, Altair, Bokeh**, or other interactive / web-first plotting.
- **EDA-only** plots where seaborn or pandas is enough without a publication target.
- **Illustrator / Figma-first** layout or infographic (not data plots).

## Related files

| File | Open when |
|------|-----------|
| [references/figure-contract.md](references/figure-contract.md) | Detailed contract template + pop-gen examples |
| [references/tutorials.md](references/tutorials.md) | End-to-end walkthroughs (bar, trends, heatmap) |
| [references/api.md](references/api.md) | Function signatures, PALETTE, POPGEN_PALETTE, validation rules |
| [references/common-patterns.md](references/common-patterns.md) | Layout patterns, legend panel, print-safe bars, pop-gen patterns |
| [references/design-theory.md](references/design-theory.md) | Typography, palette policy, export policy |
| [references/r-backend.md](references/r-backend.md) | R workflow: ComplexHeatmap, ggplot2, patchwork, export |
| [references/demos.md](references/demos.md) | Canonical figure_* demo links in figures4papers |
| [references/submission-checklist.md](references/submission-checklist.md) | Pre-submission checklist: universal + pop-gen specific; common pitfalls |
