# Figure Submission Checklist

Use this before sending figures to journal/co-authors. Two sections: universal + pop-gen specific.

---

## Universal Checks

### Format & Resolution
- [ ] Vector format (PDF/EPS/SVG) exported alongside raster
- [ ] Raster DPI ≥ 300 (line art: 600); never JPEG for graphs
- [ ] Figure dimensions match journal column width (see `figure-contract.md`)
- [ ] All fonts embedded in PDF/EPS

### Typography
- [ ] All text readable at final print size (minimum 6 pt after scaling)
- [ ] Axis labels include units in parentheses: `FST (×10⁻³)`, `Time (Ma)`
- [ ] Panel labels present (bold A, B, C… or lowercase per journal style)
- [ ] Sentence case for labels ("Gene expression" not "GENE EXPRESSION")
- [ ] Font consistent across all figures in manuscript (Arial or Helvetica)

### Colour & Accessibility
- [ ] Palette is colourblind-safe (Okabe-Ito / POPGEN_PALETTE / viridis)
- [ ] Figure tested in grayscale — groups still distinguishable
- [ ] No red-green encoding for categorical comparison
- [ ] Heatmap uses perceptually uniform colormap (viridis/cividis/RdBu); never `jet`

### Data Integrity
- [ ] Error bars present where applicable; type defined in caption (SD / SE / 95% CI)
- [ ] Statistical significance marked (p-value, FDR, or Bayes factor); threshold stated
- [ ] Y-axis starts at zero for bar charts unless scientifically justified and captioned
- [ ] No 3D effects (bar extrusion, pie 3D, surface distortion)
- [ ] No chart junk (unnecessary gridlines, decorative shadows, redundant backgrounds)

### Multi-panel Consistency
- [ ] Same colour semantic across all panels (population A = same colour in every figure)
- [ ] Same font size and linewidth across all panels in a figure
- [ ] Panel order follows evidence hierarchy (primary claim = Panel A)
- [ ] Legend complete; no orphaned colour/marker without label

---

## Pop-gen Specific Checks

### PCA / ADMIXTURE
- [ ] PC axes labelled with explained variance %: `PC1 (12.3%)`
- [ ] Sample size per population stated in legend or caption
- [ ] Admixture bar sorted by dominant ancestry component for readability
- [ ] K value selection method referenced (cross-validation or ΔK)

### Selection Signals (FST, XP-EHH, π-ratio)
- [ ] Significance threshold defined (empirical top X% or permutation-based)
- [ ] Genome-wide Manhattan and regional zoom consistent in SNP positions
- [ ] Candidate gene annotation matches reference genome version stated in Methods
- [ ] Both statistics (e.g., XP-EHH + FST) shown if joint evidence claimed

### Phylogenetic / Tree Figures
- [ ] Bootstrap or posterior support values shown (or explicitly omitted with reason)
- [ ] Outgroup labelled
- [ ] Branch length scale bar present
- [ ] Tip labels readable at print size

### Heatmaps (FST matrix, LD, gene expression)
- [ ] Colour scale anchored at meaningful midpoint (0 for diverging, min for sequential)
- [ ] Row/column order not arbitrary — sorted by geography, clade, or clustering
- [ ] Colourbar labelled with units

---

## Common Pitfalls

| Pitfall | Fix |
|---------|-----|
| JPEG for graphs | Switch to PNG (≥300 DPI) or PDF/SVG |
| 3D bar/pie chart | Flatten to 2D |
| Truncated y-axis on bar chart | Start at 0 or add axis break symbol |
| Red–green colour pair | Use blue–orange (Okabe-Ito) |
| Missing error bars | Add SD/SE/CI and define in caption |
| Inconsistent font sizes across figures | Set globally with rcParams before any plot |
| Text too small | Check at 100% zoom at final print dimensions |
| `jet` / `rainbow` colormap | Replace with `viridis`, `cividis`, or `RdBu` |
| Legend overlapping data | Move to dedicated panel or outside axes |
| Different colour for same population across figures | Lock with a palette dict at script top |

---

## Related files

- [figure-contract.md](figure-contract.md) — journal dimension table, contract template
- [design-theory.md](design-theory.md) — palette policy, Okabe-Ito, grayscale test rule
- [api.md](api.md) — POPGEN_PALETTE colour assignments
