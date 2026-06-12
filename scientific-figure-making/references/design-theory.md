---
created: 2026-05-28 17:27
updated: 2026-05-28 17:27
---
# Publication Figure Design Theory

Derived from the figures4papers repository scripts, supplemented with Nature-journal palette and layout principles.

---

## 0) Palette Policy (load before choosing any colours)

> Adapted from Nature-figure practice.

- **Do not default to maximum hue separation.** In multi-panel figures, pick one coherent *baseline family* and one coherent *hero family*; reserve green/red only for delta markers or genuinely signed semantics (positive/negative, gain/loss).
- **Semantic consistency beats visual variety.** Reviewers read across panels; a colour that means "population A" in Figure 2 must mean the same in Figure 3.
- **Two palette modes** depending on figure type:
  - *ML/comparison figures* (method vs. baseline): use `PALETTE` in `api.md`.
  - *Population-genetics figures* (breed/population/ancestry): use `POPGEN_PALETTE` in `api.md`.
- **Qualitative (population labels)**: 6-10 distinguishable colours, colourblind-safe (see `POPGEN_PALETTE["qualitative"]`).
- **Diverging (FST, pi-ratio, selection score)**: anchor at a neutral mid-point; use only when the sign of the value is meaningful.
- **Sequential (depth, density, p-value)**: single-hue ramp; `magma` or `viridis` are safe defaults.
- **Fallback for general figures** (not ML, not pop-gen): use **Okabe-Ito** — distinguishable under all forms of colour blindness and in grayscale print.

```python
# Okabe-Ito (8 colours, colourblind-safe universal standard)
OKABE_ITO = [
    "#E69F00",  # orange
    "#56B4E9",  # sky blue
    "#009E73",  # bluish green
    "#F0E442",  # yellow
    "#0072B2",  # blue
    "#D55E00",  # vermillion
    "#CC79A7",  # reddish purple
    "#000000",  # black
]
# Usage: plt.rcParams['axes.prop_cycle'] = plt.cycler(color=OKABE_ITO)
```

- **Grayscale test rule**: Before finalising any figure, export a grayscale version. If groups are indistinguishable, switch to hatch/marker-shape encoding or Okabe-Ito.

---

## 1) Core Matplotlib Style System

Minimalist, high-contrast, publication-oriented:

- **Typography:**
  - Primary: `font.family = 'helvetica'` (16 scripts in figures4papers).
  - Practical fallback stack: `['Arial', 'Helvetica', 'DejaVu Sans', 'sans-serif']`.
- **Size hierarchy:**
  - Large bar/comparison figures: `font.size = 24`, `axes.linewidth = 3`.
  - Paper subfigures / compact analytic plots: `font.size = 15-16`, `axes.linewidth = 2`.
- **Axes cleanup:**
  - `axes.spines.right = False`
  - `axes.spines.top = False`
- **LaTeX:** `text.usetex = True` only when math-rich labels are needed and LaTeX is available.
- **Vector text:** `svg.fonttype = 'none'` for editable text in SVG exports.

---

## 2) Export and Output Policy

- **DPI defaults:** `dpi=300` standard; `dpi=600` for very dense bar panels.
- **Layout finalization:** `fig.tight_layout(pad=2)` default; `pad=1` for compact multi-panel.
- **Vector-first rule:** Always export SVG or PDF alongside PNG for editorial revisions.
- **File naming:** stable basenames under `figures/`; `finalize_figure` creates parent dirs.

---

## 3) Colour Palettes

### 3a) ML / Method-Comparison Palette

Use for benchmark bars, ablation studies, and method comparisons.
Semantic: blue = proposed, green = improvement, red = baseline/contrast, neutral = background.

```python
PALETTE = {
    "blue_main":      "#0F4D92",
    "blue_secondary": "#3775BA",
    "green_1": "#DDF3DE", "green_2": "#AADCA9", "green_3": "#8BCF8B",
    "red_1":   "#F6CFCB", "red_2":   "#E9A6A1", "red_strong": "#B64342",
    "neutral": "#CFCECE",
    "highlight": "#FFD700",
    "teal": "#42949E", "violet": "#9A4D8E",
}
```

### 3b) Population-Genetics Palette

Use for PCA, admixture, FST heatmap, Manhattan, regional selection plots.
See `api.md` for the full `POPGEN_PALETTE` dict.

| Semantic role | Suggested colours |
|---|---|
| **Qualitative groups** (populations/breeds) | 10-colour colourblind-safe set, see `POPGEN_PALETTE["qualitative"]` |
| **Diverging** (FST, pi-ratio, Tajima's D) | `RdBu_r` or custom `["#2166ac","#f7f7f7","#d6604d"]` |
| **Sequential** (p-value, depth, score) | `magma` or `viridis` |
| **Ancestry components** (admixture) | Qualitative set, same colours as PCA groups for consistency |
| **Highlight** (candidate gene, sweep region) | `"#E63946"` (single callout only) |
| **Neutral background** (non-significant SNPs) | `"#BDBDBD"` |

---

## 4) Layout and Composition Logic

- **Ultra-wide aspect ratios:** For 3-4 metrics or many categories in a row, use wide canvases (e.g., `figsize=(45, 12)` or `(28, 6)`). Width often 3-4x height for comparison bars.
- **Dedicated legend panels:** In complex multi-axis figures, assign one subplot solely to the legend (`ax.set_axis_off()`). Keeps data panels clean.
- **Non-redundant panel architecture:** Each panel must add information not visible in any other panel. If two panels show the same thing at different scales, merge or annotate instead.
- **Dynamic Y-axis scaling:** Tighten y-limits to relevant range (`data.min() - margin`); avoid fixed 0-100 when all values are in 85-95.
- **Consistency over embellishment:** All subplots in a row share the same font sizes, linewidths, and colour semantic mapping.

---

## 5) Bar Encoding Strategy

- **In-place annotation:** Scientific values printed directly above bars (36pt) for exact readability without grid.
- **Manual tick positioning:** `FixedLocator` for precise Y-axis granularity.
- **Strong edge treatment:** `edgecolor='black'`, `linewidth=1.5-3`.
- **Alpha-based ablation:** Same primary colour with varying `alpha` (0.2-1.0) for method completeness.
- **Hatch encoding:** For grayscale-safe subtype separation.

---

## 6) Trend / Line Encoding Strategy

- 2-4 primary curves per axis; consistent `linewidth=2-3`.
- `fill_between` for uncertainty bands.
- Minimal grid; rely on axis ticks and direct legend reading.

---

## 7) Scatter / PCA Encoding Strategy

- **Point size:** `s=30-60` for large datasets (>500 points); `s=80-120` for small.
- **Alpha:** `alpha=0.6-0.8`; lower alpha for overlapping dense clouds.
- **Population labels:** Prefer legend over per-point text unless n < 10 groups.
- **Ellipses:** 95% confidence ellipses per group are standard in pop-gen PCA; use `matplotlib.patches.Ellipse` with eigenvalue-scaled axes.
- **Explained variance:** Always label PC axes with percentage (e.g., `PC1 (12.3%)`).

---

## 8) Recommended rcParams Preset

```python
PUBLICATION_RCPARAMS = {
    "font.family": ["Arial", "Helvetica", "DejaVu Sans", "sans-serif"],
    "font.size": 16,            # 24 for large comparison bars
    "axes.spines.right": False,
    "axes.spines.top": False,
    "axes.linewidth": 2.5,      # 3 for big bars, 2 for compact
    "legend.frameon": False,
    "svg.fonttype": "none",
}
```

---

## Related files

- [SKILL.md](../SKILL.md) -- When to load this skill
- [api.md](api.md) -- PALETTE, POPGEN_PALETTE, and function contracts
- [common-patterns.md](common-patterns.md) -- Operational patterns
- [tutorials.md](tutorials.md) -- Hands-on flows
- [figure-contract.md](figure-contract.md) -- Conclusion-first workflow
- [r-backend.md](r-backend.md) -- R workflow for ComplexHeatmap / ggplot2
