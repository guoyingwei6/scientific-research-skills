---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Task: Figures & Tables

> Figures/Tables 要回答的问题：**reviewer 跳读图表时能不能 standalone 看懂 + figure 是不是支撑了 results 的 claim**。
> 服务的 reviewer 决策：data 严不严谨 + 视觉传达专不专业。

## ⚓ 元层锚点

- `meta/constitution.md`：caption 用现在时（绝对）+ 数字格式
- `meta/reviewer_psychology.md`：reviewer Step 2 = "跳读所有 figures + caption"——figure 本身要 self-contained
- `meta/over_claim_guard.md`：caption 不下结论，只描述

---

## 任务本质

Figure/Table 是论文最被仔细看的部分。**reviewer 真实读 figure caption 比读正文段落多 3 倍时间**。

写得好的标志：reviewer 不读正文，**只看 figure + caption** 就能理解核心 finding。

---

## Figure caption 通用骨架

```
[Title sentence: 简短描述这个 figure 是什么]
(A) [Panel A 描述 + 关键参数（n / 颜色 scale / 单位）]
(B) [Panel B 描述]
...
[Optional: 缩写、统计方法、数据来源说明]
```

例：
> Figure 1. Population structure of 744 cattle from 85 breeds. (A) Geographic distribution of sampling locations, colored by phylogenetic group (n = 10 groups). (B) Principal component analysis of 5.07 million LD-pruned SNPs, with PC1 (8.2%) and PC2 (3.5%) capturing taurine–indicine and African–Eurasian splits, respectively. (C) ADMIXTURE clustering at K = 7 (CV error = 0.245). AFI: African indicine; AFT: African taurine; EUT: European taurine; EAT: East Asian taurine.

**关键**：caption 必须 standalone——不读正文，只看 figure + caption 能理解的程度。

---

## Caption 写作元规则

### 1. 时态：现在时（绝对）
- "Figure 1 shows ..." / "PCA reveals ..." / "Boxplots represent ..."
- **不**用 "Figure 1 showed" 即使数据是过去做的

### 2. 信息层次
- Title sentence：一句话 main message（图传达的核心信息）
- Panel descriptions：每个 panel 的具体内容
- Technical details：缩写定义 / 统计方法 / 数据来源

### 3. 必须包含
- **样本量** n
- **统计方法**（"Mann-Whitney U test" / "Spearman correlation" / "Bonferroni-corrected"）
- **显著性标注**含义（"\* P < 0.05, ** P < 0.01" 等）
- **颜色 / 形状的含义**（color legend 说明 vs. 颜色 scale 含义）
- **缩写定义**（即使正文已定义，caption 里再定义一次——caption 必须 self-contained）
- **单位**（"in Mb" / "in years" / "in % of variance"）

### 4. 避免
- ❌ 把 finding 写在 caption（"PCA reveals strong differentiation"）→ "Strong" 是 claim, 应该放 Results
- ❌ 长达 200 词的 caption（除非是高度信息密集的 figure）
- ❌ caption 里的"Significantly different"没说什么 test
- ❌ 不一致的 panel 编号（正文 cite 2A 但 caption 里只有 A B C 没标）

---

## Figure 设计的元规则

### 颜色
- **色盲友好**：避免红绿单独区分（约 8% 男性色盲）；用 ColorBrewer / viridis 调色板
- **白底优先**：除非投稿期刊偏好黑底
- **打印兼容**：黑白打印仍能区分（用 hue + brightness）
- **少即是多**：≤ 8 类用 categorical palette；连续变量用 sequential / diverging

### 字号
- 主图刊出尺寸：单栏（~85 mm 宽）/ 双栏（~180 mm 宽）
- 字号下限：刊出尺寸下 axis label ≥ 7 pt，axis tick ≥ 6 pt
- 不要在 200 dpi 下看着大但 600 dpi 排版后挤成蚂蚁

### 信息密度
- **每个 figure 一个 main message**
- 7-8 个 panel 已经偏多；超过 9 个考虑拆成 2 个 figure
- main figure 4-6 个；剩下进 supplementary

### 排版
- Panel 标签 A B C D 左上角，**字号大于 axis label**
- 所有 panel 共享一个 color legend / scale bar 时放在最右或最下
- 坐标轴一致：同类指标的多个 panel 用同一 scale，便于比较

---

## Table 设计

### 何时用 Table 而非 Figure
- **数值精确度重要**：reader 需要看具体数值时
- **多变量结构化对比**：一个 8 列 × 12 行的对比，table 比 figure 清楚
- **不适合 figure 化**：纯文本类信息（基因列表 + 功能注释）

### Table caption
```
Table 1. [Title sentence: 表格内容]
Footnote a: [Methodology / abbreviation / 单位 / sample size]
```

### Table 内规范
- 数字对齐：右对齐或小数点对齐
- 显著性标注：上标 *
- 单位放表头，**不**放每个 cell
- N 数放表头或 footnote
- 缩写在 footnote 定义

---

## Supplementary Figure / Table

- 命名 Figure S1, Table S1（或 Figure S1.1 / Supplementary Figure 1）
- caption 与 main 同样要 self-contained
- 主文 cite 顺序与 S 编号顺序对齐（先 cite 的先编号）
- supplementary 的 figure / table 通常**没篇幅压力**，可以详细

---

## Figure 与 Results 章节的对齐

| Figure | 对应 Results 小节 | 主 message |
|---|---|---|
| Fig 1 | sample 概览 / setup | 谁、哪里、整体结构 |
| Fig 2-3 | 核心发现 1, 2 | 具体的关键 finding |
| Fig 4-5 | 验证 / 深化 | follow-up evidence |
| Fig 6 (如有) | 整合 / 模型 | 综合所有 evidence |

> 反面：figure 顺序与 results 章节脱节 = reviewer 找不到对应数据 = 怀疑

---

## 常见错位（写完图表后必查）

| 错位类型 | 表现 |
|---|---|
| 编号错位 | 正文 cite Fig 2A 但 caption 里没 A |
| 顺序错位 | 正文先 cite Fig 3 再 cite Fig 2 |
| 数字错位 | figure 里 P = 0.001 / caption 写 P < 0.05 / 正文写 highly significant 但没数字 |
| Panel 错位 | caption 描述 panel A 是 PCA 但 figure A 实际是 box plot |
| 缩写错位 | figure legend 用 "EAT" / caption 没定义 |
| 单位错位 | figure axis 是 Mb / caption 写 kb |
| 样本量错位 | figure 标 n=47 / caption 写 n=50 |

> 投稿前**逐 figure** 走一遍 caption ↔ figure ↔ 正文 三方对照

---

## 跨方向 illustration

> 按方案 B,挑差异化最大的：

### 景观基因组学 / GEA 标志性图
- **采样地图 + 气候底图**（Köppen-Geiger / temperature 等高线）+ 品种着色
- **环境变量 PCA / 相关性热图**：n × n 变量矩阵
- **RDA biplot**：constrained / unconstrained 两版
- **多方法 Venn**：RDA / LFMM / BayPass 候选 SNP 重叠
- **Allele frequency geographic map**：候选 SNP 在地图上的频率梯度
- **EHH / haplotype bifurcation**：选择信号验证
- **Genomic offset map**：未来气候情景下的脆弱性空间分布

### 选择信号
- **Manhattan plot**：每统计量一个轨道，多统计量叠加
- **候选区间 zoom-in**：基因模型 + LD heatmap + 多统计量轨道
- **EHH decay**：候选位点周围的 EHH 衰减曲线

### 群体结构 / 驯化
- **PCA scatter**：PC1 vs. PC2，可能 + PC3
- **ADMIXTURE bar**：K 范围扫描 + 每 K 的 CV error
- **Phylogenetic tree** / **NJ network**
- **FST heatmap** 或 **migration arrow map** (Estimated Effective Migration Surfaces)

### Imputation panel
- **Concordance / r² by MAF bin**：line plot 按 MAF 分层
- **Comparison with existing panels**：bar / box plot
- **Coverage-r² curve**：不同测序 coverage 下的 imputation 精度

### SV / 泛基因组
- **SV size distribution**：histogram by type (DEL/INS/INV/DUP)
- **Pangenome graph 可视化**：core/dispensable gene 比例
- **SV-trait association Manhattan**

---

## 自查清单（提交前对每个 figure / table）

- [ ] caption 用现在时？
- [ ] 样本量 n 给了？
- [ ] 统计方法标了？
- [ ] 显著性标注含义说明？
- [ ] 颜色 / 形状含义说明？
- [ ] 缩写在 caption 内定义？
- [ ] 单位都标了？
- [ ] 编号 / 顺序与正文 cite 对齐？
- [ ] 数字 / 样本量 / P 值在 figure / caption / 正文一致？
- [ ] 色盲友好？
- [ ] 字号在刊出尺寸下可读？
- [ ] 每个 figure 一个 main message（不超载）？
- [ ] supplementary 编号顺序与正文 cite 对齐？
- [ ] caption 没下结论（"reveal" 这种留给正文）？
