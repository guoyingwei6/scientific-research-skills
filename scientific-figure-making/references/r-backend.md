---
created: 2026-05-28 17:27
updated: 2026-05-28 17:27
---
# R Backend Reference

Use R when:
- The figure needs **ComplexHeatmap** (annotated row/column tracks, clustering, colour legends).
- Multi-panel layout requires **patchwork** alignment that is easier than matplotlib `GridSpec`.
- Phylogenetic trees with metadata strips: **ggtree**.
- CMplot for circular or rectangular Manhattan plots.
- The user already has analysis output in R (ADMIXTURE Q-matrix, TreeMix, etc.).

Use Python (matplotlib) when:
- The user's data pipeline is Python-first.
- Figures are simple scatter / bar / line without complex annotation tracks.
- Integration with existing figures4papers style is required.

---

## 1) ComplexHeatmap (FST matrix, genotype heatmap)

```r
library(ComplexHeatmap)
library(circlize)

# FST matrix heatmap with population annotation
col_fun <- colorRamp2(c(0, 0.1, 0.3), c("#F7F7F7", "#FCAE91", "#D6604D"))

ha <- HeatmapAnnotation(
  Population = pop_labels,
  col = list(Population = setNames(QUALITATIVE_COLORS[1:n_pop], pop_names))
)

Heatmap(fst_matrix,
  name = "FST",
  col = col_fun,
  top_annotation = ha,
  left_annotation = rowAnnotation(Population = pop_labels,
                    col = list(Population = setNames(QUALITATIVE_COLORS, pop_names))),
  cluster_rows = TRUE,
  cluster_columns = TRUE,
  show_row_dend = TRUE,
  show_column_dend = TRUE,
  row_names_gp = gpar(fontsize = 8),
  column_names_gp = gpar(fontsize = 8),
  cell_fun = function(j, i, x, y, width, height, fill) {
    if (abs(fst_matrix[i, j]) > 0.1)
      grid.text(sprintf("%.3f", fst_matrix[i, j]), x, y, gp = gpar(fontsize = 6))
  }
)
```

**Export:**
```r
pdf("figures/fst_heatmap.pdf", width = 8, height = 7)
draw(ht)
dev.off()
```

---

## 2) Admixture bar plot (ggplot2 + patchwork)

```r
library(ggplot2)
library(patchwork)
library(tidyr)
library(dplyr)

# Q_df: columns = K1..Kn, rows = individuals; add pop/sort columns
q_long <- Q_df %>%
  arrange(Population, desc(K1)) %>%
  mutate(ind = row_number()) %>%
  pivot_longer(starts_with("K"), names_to = "Component", values_to = "Proportion")

p_admix <- ggplot(q_long, aes(x = ind, y = Proportion, fill = Component)) +
  geom_bar(stat = "identity", width = 1, position = "stack") +
  scale_fill_manual(values = QUALITATIVE_COLORS) +
  facet_grid(. ~ Population, scales = "free_x", space = "free") +
  theme_classic(base_size = 10) +
  theme(
    axis.text.x = element_blank(),
    axis.ticks.x = element_blank(),
    strip.text = element_text(angle = 90, hjust = 0),
    legend.position = "bottom",
    panel.spacing = unit(0.5, "mm")
  ) +
  labs(x = NULL, y = "Ancestry proportion")
```

**Key rule:** Use the same `QUALITATIVE_COLORS` order as the PCA scatter in the paired figure.

---

## 3) Qualitative colour vector (R)

```r
# Colourblind-safe 10-colour set (Paul Tol "Bright" scheme)
QUALITATIVE_COLORS <- c(
  "#4477AA", "#EE6677", "#228833", "#CCBB44", "#66CCEE",
  "#AA3377", "#BBBBBB", "#332288", "#EE3377", "#99EE66"
)
```

---

## 4) Export conventions

| Format | Use case | Code |
|---|---|---|
| PDF (vector) | Main figure for submission | `ggsave("fig.pdf", width=8, height=6, units="in")` |
| SVG (editable) | For editorial revision | `ggsave("fig.svg", width=8, height=6)` |
| PNG (raster) | Supplementary / preprint | `ggsave("fig.png", dpi=300, width=8, height=6)` |

For ComplexHeatmap, always use `pdf()` + `draw()` + `dev.off()` rather than `ggsave`.

---

## 5) Backend decision rule

```
Does the figure need row/column annotation tracks AND clustering?
  YES -> ComplexHeatmap (R)
  NO  -> Is the primary figure type a ggplot2 chart (violin, boxplot, bar)?
           YES -> ggplot2 (R)
           NO  -> Is the user's pipeline Python-first?
                    YES -> matplotlib (Python)
                    NO  -> ask the user
```

---

## Related files

- [SKILL.md](../SKILL.md)
- [design-theory.md](design-theory.md) -- palette policy
- [api.md](api.md) -- POPGEN_PALETTE (Python equivalent)
- [common-patterns.md](common-patterns.md) -- Python pop-gen patterns
