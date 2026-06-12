---
created: 2026-05-28 17:27
updated: 2026-05-28 17:27
---
# Figure Contract

A figure contract is filled before writing any code. It forces the scientific logic to precede the visual logic.
Adapted from Nature-figure practice.

---

## Contract Template

```
Core conclusion (one sentence):
  _______________________________________________

Evidence hierarchy:
  Primary panel (must show):   ________________
  Supporting panels:           ________________
  Panels to cut if space limited: ____________

Chart type (chosen after 1 & 2, not before):
  _______________________________________________

Backend:
  [ ] Python / matplotlib    [ ] R (see r-backend.md)

Statistics to display:
  Error bars:  ________________  (SD / SE / 95% CI?)
  Significance: _______________  (p-value / FDR / BF?)
  Effect size:  _______________  (optional but preferred)

Export constraints:
  Journal:      _______________
  Required DPI: _______________  (default: 300)
  Format:       _______________  (PDF+PNG / SVG+PNG)
  Max panels:   _______________
  Editable text needed: [ ] Yes  [ ] No
```

### Journal column widths (mm → inches)

| Journal | Single column | Double column | Max height |
|---------|--------------|---------------|------------|
| **Nature** / Nature sub-journals | 89 mm (3.5 in) | 183 mm (7.2 in) | 247 mm |
| **Science** | 55 mm (2.2 in) | 175 mm (6.9 in) | 230 mm |
| **Cell** | 85 mm (3.35 in) | 178 mm (7.0 in) | 228 mm |
| **PLOS ONE / PLOS Genetics** | 83 mm (3.27 in) | 173 mm (6.81 in) | 225 mm |
| **BMC Genomics / Genome Biol.** | 85 mm (3.35 in) | 170 mm (6.7 in) | 225 mm |

```python
mm_to_in = lambda mm: mm / 25.4
# Nature single-column: figsize=(mm_to_in(89), mm_to_in(70))
# Nature double-column: figsize=(mm_to_in(183), mm_to_in(120))
```

---

## Why this order matters

Choosing the chart type first leads to figures where the visual drives the story instead of the data. Reviewers notice when a figure is built around a plot type ("we used a heatmap") rather than a conclusion ("FST between Mongolian cattle and Indicus is highest at chromosome 14").

The contract locks in the conclusion first, so every downstream decision (panel order, axis orientation, colour assignment, annotation) serves that sentence.

---

## Pop-gen examples

### Example 1 -- PCA + admixture figure

```
Core conclusion:
  Mongolian cattle cluster distinctly from South China Indicus breeds,
  with intermediate individuals showing Taurine-Indicine admixture.

Evidence hierarchy:
  Primary:    PCA scatter (PC1 separates Taurine vs. Indicine)
  Supporting: Admixture bar (K=3, shows intermediate ancestry)
  Cut if space: PC3 vs PC4 panel

Chart type:
  Panel A -- scatter (PCA); Panel B -- stacked bar (admixture)

Backend: Python (matplotlib)

Statistics:
  Error bars: N/A
  Significance: N/A
  Label PC axes with explained variance %

Export: PDF + PNG, 300 DPI, Nature Communications style
```

---

### Example 2 -- Selection signal summary

```
Core conclusion:
  XP-EHH and FST jointly identify a 200-kb sweep region on BTA14
  harbouring PLAG1 as a candidate for body size in Mongolian cattle.

Evidence hierarchy:
  Primary:    Regional XP-EHH plot (BTA14, 25-26 Mb)
  Supporting: FST regional overlay; gene annotation track
  Cut if space: Genome-wide Manhattan (move to supplementary)

Chart type:
  Panel A -- genome-wide Manhattan (supplementary candidate)
  Panel B -- regional XP-EHH + FST dual-track
  Panel C -- gene model track

Backend: Python (matplotlib) for A+B; consider R (gggenes) for C

Statistics:
  XP-EHH threshold: top 1% empirical
  FST threshold: top 5% empirical
  Highlight: PLAG1 gene body only

Export: PDF + PNG, 300 DPI, editable SVG for panel B
```

---

## Contract vs. no contract (red flag check)

| Symptom | Diagnosis |
|---|---|
| User says "画个PCA" with no further context | No contract -- ask for core conclusion before any code |
| Colour assignment is arbitrary | Contract not filled -- no qualitative group list |
| Four panels but only one has a clear message | Evidence hierarchy not defined -- cut redundant panels |
| Chart type changed three times during revision | Contract filled too late -- chart type derived from aesthetics not logic |
| Reviewer says "Fig 2 is confusing" | Panel order violates evidence hierarchy -- primary not Panel A |

---

## Related files

- [SKILL.md](../SKILL.md)
- [design-theory.md](design-theory.md) -- palette policy and layout rules
- [api.md](api.md) -- POPGEN_PALETTE colour assignments
- [common-patterns.md](common-patterns.md) -- PCA, admixture, Manhattan code patterns
