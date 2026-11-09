---
created: 2026-11-09
updated: 2026-11-09
---
# Data Integrity and Render QA

Absorbed from the ZZD academic skill 1.4.0 figure route (reviewed 2026-11-09) and adapted to this skill. Load before writing plotting code and again before delivery.

---

## Data fidelity

- Every plotted value and statistic comes from real data or clearly labelled simulated data. Image generation never substitutes for data plots; never reconstruct precise values from image pixels.
- Fix the comparison, units, observation unit (individual vs. SNP vs. window), uncertainty definition, and the question the figure answers before choosing the layout.
- Show negative or inconsistent results that bear on the claim. Do not use different axis scales across panels to make an effect look larger.
- Shaded bands come only from an explicit SD, SE, or CI. Do not accept a plotting library's default band as uncertainty.
- Do not connect lines across missing observations. Show missing cells in heatmaps as a separate colour, never as zero.
- Use a diverging colormap only when a real centre value exists. Panels being compared share a normalization and colour scale, or the difference is stated.
- Bar lengths start at zero. For small differences in a narrow range, prefer point-and-interval plots over truncated bars; mark any necessary truncation.
- Radar plots: state each axis's original scale, direction, and normalization; polygon area is not evidence of overall superiority; do not fill missing values with zero or the mean.
- Example data, thresholds, model names, and statistics from demos or reference repos never enter the user's figure.

## Input boundary checks in code

- Check array dimensions, category and series lengths, label order, missing-value policy, and error-bar shape before plotting.
- Do not let `zip()` silently truncate mismatched lists, and do not wrap plotting in broad `try/except` or invent default values that hide data problems. Fail with a message naming the missing column or mismatched length.
- Statistical estimates and tests are computed in the analysis layer; the plotting layer does not redefine them.

## Runtime hygiene

- In batch or headless runs, set a non-interactive backend before importing `pyplot`, and close figures when done.
- Confirm the requested font is actually installed and covers every character used (Greek letters, minus sign, CJK). Choose a covering fallback rather than letting glyphs drop silently.
- Keep style changes inside the current figure context (`plt.rc_context`) when other figures share the session.
- Write outputs to a new path; keep the script, data source, and processing parameters next to the figure.

## Export and render-then-verify

- Choose formats by use: SVG/PDF for editing and submission, PNG/TIFF for preview or journal raster requirements. DPI applies to raster output at the final physical size; it does not determine vector text quality.
- Editable SVG needs `svg.fonttype = 'none'`, then confirm real text objects exist in the file. For PDF, set and check font embedding.
- After export, open or render the actual file and check clipping, long labels, legend overlap, error bars, panel letters, and final dimensions. A script exiting with code 0 is not evidence the figure is correct.
- When composing multi-panel figures: vector panels stay vector with isolated IDs; raster panels are drawn at the target pixel size instead of being silently rescaled. A PNG composite is never described as editable.
- When rebuilding an image as PPTX, draw.io, or Illustrator, keep geometry, text, and scientific relations as native editable objects. Embedding a whole bitmap does not count as editable; report unsupported elements instead of rasterizing them silently.

## Related files

- [figure-contract.md](figure-contract.md) -- decide the claim before the chart
- [submission-checklist.md](submission-checklist.md) -- final journal checks
