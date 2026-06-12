---
created: 2026-05-28 17:27
updated: 2026-05-28 17:27
---
# Common Patterns for Publication Figures

These patterns are used across the repository for consistent, publication-ready figures. Apply them when building bar charts, multi-panel layouts, and print-safe graphics. Step-by-step flows that use many of these ideas are in [tutorials.md](tutorials.md); for chart types not covered there, use the closing section of that file and [demos.md](demos.md).

---

## Ultra-wide aspect for multi-metric panels

For 3-4 metrics or many categories in a single row, use a wide canvas so bars/labels don't crowd vertically.

- **Example:** `figsize=(45, 12)` or `(28, 6)`.
- **Rule:** Width often 3-4× height for comparison bars.
- **Why:** Lets the reader scan left-to-right without squinting; keeps y-axis and legend readable.

---

## Dedicated legend panel

When multiple curves or groups make the legend large, put it in its own subplot so it doesn't cover data.

- **Steps:**
  1. Create one extra subplot (e.g. last in the grid).
  2. Call `ax.set_axis_off()` on that axis.
  3. Build the legend on that axis (e.g. gather handles/labels from other axes and call `ax.legend(handles, labels)` there), or use a single legend that you place in the extra axis.
- **Result:** Data panels stay clean; legend is fully visible.

---

## Categorical bars without x-tick labels

When the x-axis is "method" or "condition" and the legend already identifies them, hide x ticks and rely on the legend/title.

- **Code:** `ax.set_xticks([])` or set tick labels to empty.
- **Use when:** Many methods across multiple metrics; names are in the legend or panel title.

---

## Dynamic y-axis scaling

Tighten y-limits to the relevant range so differences are visible instead of squashed.

- **Idea:** Use something like `data.min() - margin` to `data.max() + margin` (e.g. margin = small fraction of range or one std).
- **Avoid:** Fixed 0-100 when all values are in 85-95; use e.g. 80-100 instead.

---

## Bar edge and hatch for print-safe separation

Bars that differ only by fill can blur in grayscale. Use edges and optional hatching.

- **Edges:** `edgecolor='black'`, `linewidth=1.5`-`3` for clear separation.
- **Hatch:** Same color with different hatch (e.g. `'/'`, `'\\'`, `'.'`) for ablation or subgroups so they remain distinct in print.

---

## Semantic color mapping

Stick to the skill palette so "proposed vs baseline" is consistent across figures.

- **Blues:** Proposed method / key result.
- **Greens:** Improvements / positive variants.
- **Reds:** Baselines / contrasts / alternatives.
- **Neutral:** Reference or background categories.
- **Highlight:** Single callout only.

See [design-theory.md](design-theory.md) for the full palette and [api.md](api.md) for `PALETTE` and `DEFAULT_COLORS`.

## Related files

- [SKILL.md](../SKILL.md) — When to load this skill
- [api.md](api.md) — `PALETTE`, helpers, validation
- [demos.md](demos.md) — Real scripts mirroring these patterns
- [design-theory.md](design-theory.md) — Visual and color theory
- [tutorials.md](tutorials.md) — Walkthroughs that apply these patterns


---

## Population-Genetics Figure Patterns

### PCA scatter with 95% confidence ellipses

```python
from matplotlib.patches import Ellipse
import numpy as np

def add_confidence_ellipse(ax, x, y, color, n_std=2.0, **kwargs):
    cov = np.cov(x, y)
    vals, vecs = np.linalg.eigh(cov)
    angle = np.degrees(np.arctan2(*vecs[:, 0][::-1]))
    w, h = 2 * n_std * np.sqrt(vals)
    ellipse = Ellipse(xy=(x.mean(), y.mean()), width=w, height=h,
                      angle=angle, edgecolor=color, fc='None',
                      linewidth=1.5, linestyle='--', **kwargs)
    ax.add_patch(ellipse)
```

- Always label axes: `ax.set_xlabel(f"PC1 ({var1:.1f}%)")`.
- Use `POPGEN_PALETTE["qualitative"]` colours, consistent with admixture figure.
- Prefer legend over per-point text when n > 6 groups.

---

### Admixture / STRUCTURE bar plot

- Sort individuals by dominant ancestry component, then by population label.
- Use the **same** qualitative colours as the corresponding PCA -- cross-figure consistency is a reviewer expectation.
- Stacked bar width should be uniform and very thin (`width=1.0`, no gap) for large n.
- Add population/breed labels below the x-axis with rotated text or a bracket annotation.

```python
# Minimal stacked bar skeleton
fig, ax = plt.subplots(figsize=(14, 2.5))
bottom = np.zeros(n_samples)
for k, color in zip(range(K), POPGEN_PALETTE["qualitative"]):
    ax.bar(range(n_samples), Q[:, k], bottom=bottom, color=color,
           width=1.0, linewidth=0)
    bottom += Q[:, k]
ax.set_xlim(0, n_samples)
ax.set_ylim(0, 1)
ax.set_yticks([0, 0.5, 1])
ax.spines['top'].set_visible(False)
ax.spines['right'].set_visible(False)
```

---

### FST heatmap (symmetric matrix)

- Use `ComplexHeatmap` in R for annotated matrices; for Python use `seaborn.heatmap` with `cmap='RdBu_r'`.
- Set `vmin`/`vmax` symmetrically: `vmax = max(|FST|)`, `vmin = -vmax` (or 0 if all values are positive).
- Mask diagonal; mask upper or lower triangle to avoid redundancy.
- Cluster rows/cols by hierarchical clustering; show dendrogram.

```python
import seaborn as sns
mask = np.triu(np.ones_like(fst_matrix, dtype=bool))  # upper triangle
sns.heatmap(fst_matrix, mask=mask, cmap='magma', vmin=0, vmax=fst_matrix.max(),
            annot=True, fmt='.3f', linewidths=0.3,
            cbar_kws={'label': 'FST'})
```

---

### Manhattan / XP-EHH regional plot

- Alternate chromosome colours between two neutrals from `POPGEN_PALETTE["qualitative"]` (e.g., index 0 and 5).
- Use `POPGEN_PALETTE["highlight"]` for candidate gene annotation only.
- Use `POPGEN_PALETTE["nonsig"]` (`#BDBDBD`) for points below significance threshold.
- Genome-wide significance line: `ax.axhline(-np.log10(5e-8), linestyle='--', color='red', linewidth=1)`.
- Keep point size small (`s=4-8`) for genome-wide plots; larger (`s=20-40`) for regional zooms.
