---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Task: Results

> Results 要回答的问题：**data 看上去是什么 + 这些 data 支不支持你想 claim 的**。
> 服务的 reviewer 决策：claim 有没有 evidence。

## ⚓ 元层锚点

- `meta/constitution.md`：**绝对过去时**（描述图表本身用现在时）+ 数字格式
- `meta/over_claim_guard.md`：Results 不下结论，只**报告发现**
- `meta/reviewer_psychology.md`：第 1 大怀疑信号 = 数字与 claim 不匹配
- `meta/workflow.md`：写完一段就自审

---

## 任务本质

Results 是 **data 与 claim 之间的桥**。每个 sub-claim 必须有数字或 figure/table 支撑。

Results 写得好的标志：reviewer 跟着读完每个小节后，**心里默念"这个 claim 我接受"**——不是因为你说服了，而是因为你**报告了数据**。

---

## 通用工作流

### Frame
- 这一节的 main result 是什么？(用一句话)
- 这一节用什么 figure/table 支撑？(figure/table 顺序与 results 章节顺序对齐)
- 这一节的发现引出 Discussion 里哪个论点？

### Outline
按"分析类型分小节"，每小节内**先 main finding，再 supporting details**：

```
§1 [小节标题: 描述性的，不要"Result 1"]
  - Main finding (1 句)
  - 数据支撑 (具体数字 + figure cite)
  - 进一步细节 (如有)

§2 [小节标题]
  ...
```

### Draft
每段开头是一个 main finding。**不写引言式过渡**。如果需要前置说明，1 句话内交代。

### Self-review
- 每段开头是不是一个具体 finding？
- 每个 claim 后是不是跟着数字 + figure cite？
- 用了"significant" 没跟数字？
- 用 results 写出 discussion 的话？(常见错误)

---

## 通用骨架

### 小节顺序原则
按"故事弧"组织，不是机械按方法顺序：
- 通常：**描述性结果 → 关键发现 → 验证 / 深化**
- 描述性结果（样本概览、QC、群体结构、PCA）通常在前，作为 setup
- 核心发现放正中位置（占篇幅最多）
- 验证 / 功能注释放后面

### 单段三件套
```
[Topic sentence: main finding (现在时陈述发现 / 过去时陈述行动 + 现在时陈述结果)]
[Supporting evidence: 具体数字 + figure/table cite]
[(可选) Bridge: 1 句过渡到下一段或下一发现]
```

例：
> Climate variables clustered into temperature- and precipitation-related groups (Figure 1F). After VIF filtering (threshold = 10), we retained 32 of the 130 variables for downstream analyses. The first two RDA axes explained 47.4% and 4.8% of the constrained variance, respectively (Figure 2A).

---

## 数字与 claim 的配对

**每个 claim 必须配数字或 figure/table cite**。模式：

| Claim 类型 | 必须配 |
|---|---|
| "X is higher / lower than Y" | 具体数字 + 显著性 |
| "X is associated with Y" | 效应量 + P 值 + N |
| "X cluster / group" | 距离指标 + figure cite |
| "X pattern" | 描述指标 + figure cite |
| "Most / Majority of Z are W" | 百分比 + N |

**反例（典型 over-claim）**：
> "Allele frequencies showed strong geographic differentiation among breeds."

→ "strong" 不算证据。改：
> "Allele frequencies differed substantially among breeds (mean pairwise FST = 0.12, range 0.03–0.42; Figure S2). FST between taurine and indicine cattle reached 0.50 (Table S3)."

---

## 时态规则的应用

| 句子类型 | 时态 |
|---|---|
| 我们做了什么（行动）| 过去时："We performed PCA..." |
| 数据 / 结果显示什么 | 过去时："Three clusters were observed..." / "PCA revealed..." |
| Figure / Table 本身呈现什么 | 现在时："Figure 1A shows..." |
| 通论性事实（非本文结果）| 现在时："*TSHR* is a known thyroid receptor..." |

**最常见错误**：把 results 写成"data shows X is Y"——是 over-claim（因果/通论）。改"data showed X was Y"或"X differed by Y%"。

---

## 元层雷区（跨方向通用）

### 1. 没数字的"显著"
❌ "Significantly different among breeds."  
✅ "Differed among breeds (P = 1.2 × 10⁻⁴, ANOVA)."

每个 "significant" / "significantly" 后**必须跟数字**。

### 2. Results 写成 Discussion
❌ "We identified TSHR, a gene known to play a critical role in thyroid hormone synthesis, suggesting selection for cold adaptation."  
✅ "We identified *TSHR* as the top candidate (P = 4.6 × 10⁻¹³, BF = 78). *TSHR* encodes the thyroid-stimulating hormone receptor (Reference)."

discussion 的"意义解读"放 Discussion；results 只**报告发现**。

### 3. 缩写突然出现
- 缩写要么在 Methods 定义，要么在 Results 第一次出现时定义
- 不要 Results 里突然冒出来 EAT / SAI / ABC
- 缩写一致性：定义后全文坚持

### 4. Figure cite 错位
- 正文 cite "Figure 2A" → caption 里必须有 2A
- caption 顺序（A, B, C）与正文 cite 顺序对齐
- 正文必须 cite 所有 figure（每个 figure 至少出现 1 次在正文）

### 5. 数字不一致
- Abstract 报 184 个候选基因 → Results 必须也是 184，不是 178 或 192
- supplementary 里的数字也要一致
- 投稿前**全文搜数字**做最后一道一致性检查

### 6. 罗列式 vs. 故事式
❌ "We did A. We did B. We did C. We did D."（流水账）  
✅ "After observing pattern A in PCA, we asked whether B. To address this, we performed C, which revealed D."（有逻辑链）

但**不要过度过渡**——AI 痕迹（参考 ai_artifacts.md）。每 3-4 段 1 个连接句即可。

### 7. Sub-finding 没分段
- 一段讲一件事
- 同一段塞 3 个不同发现 = 读起来眼花
- 拆段，每段 1 个 main finding

### 8. 没给样本量
- "Allele frequency was 0.45" 没说**在多少个样本中**
- 关键数字配 N：("0.45 in EAT cattle, n = 47")

### 9. Effect size 缺失
- 只报 P 值不够
- 顶刊要求 effect size + CI（OR / β / FST / 百分比 + 95% CI）
- "P < 0.001" 但 effect size 0.001% = trivially significant

### 10. Trivial significance
- 海量样本 + 海量比较 → P 值很容易超过阈值
- 报告 effect size 让 reviewer 自己判断 biological significance

---

## 跨方向 illustration

> 元规则的演示，不是范式模板。

### 群体结构 / 系统地理学
小节顺序：sample 概览 → 全基因组 SNP 数 → PCA → ADMIXTURE → tree → FST
- 关键数字：n SNPs after QC, n PCs explaining X% variance, optimal K, mean FST range
- Figure：PCA scatter + ADMIXTURE bar + tree + FST heatmap

### 驯化 / 人口动态
小节：demographic inference 输入 → coalescent 估计 → 时间窗 → 与考古/化石证据对应
- 关键数字：Ne 时间序列 + 95% HPD / 分歧时间 + CI / migration 比例
- 注意：所有时间估计**带 CI**，不要单点估计

### 选择信号
小节：每种统计量分析 → 阈值确定 → 候选区间 → 候选基因
- 关键数字：每统计量的 top X% 或经验 P 值 / 多统计量交集 SNP 数 / 候选基因数
- Manhattan plot + 候选区间 zoom-in 是标志性图

### 渗入 / 杂交
小节：D / f-stat 总览 → 高分辨 RFMix / IBDMix → 候选区间
- 关键数字：D-stat + Z-score / 渗入比例 + CI / 渗入区间 length

### 景观基因组学（GEA）
小节常见顺序：
1. 样本与环境概览（n breeds × n environments，环境变量 PCA / 相关性热图）
2. Variation partitioning（pure climate / pure geography / shared / residual %）
3. 各 GEA 方法结果（RDA / LFMM / BayPass 各自候选 SNP 数）
4. 多方法交集（Venn / 候选 SNP 数 / KEGG enrichment）
5. 候选基因聚焦（关键基因 + EHH + allele frequency map）
- 关键 figure：环境变量 PCA + RDA biplot + 多方法 Venn + 候选基因 manhattan + EHH
- 候选基因要给：基因名 + chromosome:position + nearest 环境变量 + P 值 + BF + 已知功能

### SV / 泛基因组
小节：组装质量 → SV calling → SV 数与类型分布 → SV 与 SNP 比较 → 功能注释
- 关键数字：N50 / contig 数 / SV 数（按类型）/ 与 SNP 重叠率

### Imputation panel
小节：panel 构建概览 → benchmark dataset → concordance / r² 按 MAF 分层 → 与现有 panel 比较
- 关键数字：concordance / r² 在 MAF bin 内 / 与现有 panel 在同一 benchmark 上的差距

### 多组学整合
小节：每 omic 数据 QC → cis-eQTL/ATAC-QTL → 与 GWAS/选择候选共定位 → 功能 prioritization
- 关键数字：n eQTL / n co-localized signals / 富集 P 值

---

## 篇幅与配图对齐

* **每个小节配 1 个主 figure**（多面板可一起算 1 个）
* Results 章节数 ≈ 主 figure 数（典型顶刊 4-6 个主 figure）
* 不要 8 个 figure 但 Results 只 3 节——剩下的塞 Discussion 反而怪
* **Supplementary figure 不算**

---

## 自查清单（写完 Results 后）

- [ ] 每段开头是一个**具体 finding**？
- [ ] 每个"significant" / "strong" / "high" 后跟数字？
- [ ] 每个 claim 后跟 figure / table cite？
- [ ] 时态：行动过去时 + figure 描述现在时 + 通论现在时？
- [ ] 缩写首次出现给全称？
- [ ] 数字在 abstract / results / figure / supplementary 一致？
- [ ] effect size + CI 都给了（不是只 P）？
- [ ] 关键数字配样本量？
- [ ] 没有把 discussion 解读塞进 results？
- [ ] Figure 顺序与正文 cite 顺序对齐？
- [ ] AI 痕迹（"underscore" / "highlight the importance of" / "remarkably"）清理过？
