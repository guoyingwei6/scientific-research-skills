---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Task: Abstract

> Abstract 要回答的问题：**3 秒之内 reviewer 能不能抓到核心贡献**。
> 服务的 reviewer 决策：值不值得继续读。

## ⚓ 元层锚点

- `meta/constitution.md`：时态分段（背景现在 / 方法过去 / 结果过去 / 结论现在）+ 数字格式
- `meta/over_claim_guard.md`：abstract 末句是 over-claim 高发区
- `meta/reviewer_psychology.md`：3 秒决策核心——abstract 第 1 句和末句最关键
- `meta/ai_artifacts.md`：abstract 是 AI 痕迹最显眼的地方（一段就被识别）

---

## 任务本质

Abstract 不是论文压缩版，是**论文广告**。所有写作选择服务于一件事：让 reviewer / editor / 读者在 30 秒内决定继续读还是跳过。

写得好的标志：reviewer 看完 abstract，**能用一句话复述本文核心 contribution**。

---

## 通用工作流

### Frame
- 我的 main message 用 1 句话怎么说？
- 我的 N (sample size / data scale) 是多少？这是 reviewer 第一时间看的硬指标
- 我的 1-2 个**最具体的发现**是什么？(数字 + 含义)
- 我的 1 句话 implication 是什么？

### Outline
6 元素结构（顺序固定）：

```
[Background]    1-2 句  现在时   领域大背景，不空话
[Gap]           1 句    现在时   具体 gap，不笼统
[Methods/Data]  1-2 句  过去时   what we did + scale
[Findings]      3-5 句  过去时   具体数字 + 关键基因/模式
[Implication]   1 句    现在时   could / may，保守
```

### Draft
abstract 写**最后**——所有章节定型后再写。提前写的 abstract 大概率与正文不一致。

### Self-review
- 6 元素都齐吗？
- abstract 数字 = results 数字 = figure 数字？
- 末句是不是 over-claim？

---

## 6 元素填充示范

> 以景观基因组学论文为例（句式可迁移）。注意每元素之间**没有 firstly/secondly 这种过渡词**——AI 痕迹。

[Background] 现在时:
> "Climate change exerts strong selective pressure on natural populations, driving local adaptation across diverse taxa."

[Gap] 现在时:
> "However, the genetic basis of climate adaptation in cattle has been characterized only at the regional or single-breed level, leaving global-scale patterns largely uncharacterized."

[Methods/Data] 过去时:
> "We integrated three GEA methods (RDA, LFMM, and BayPass) on 744 cattle from 85 breeds across Eurasia and Africa, jointly analyzing 28 climate variables."

[Findings] 过去时（最重要，给数字）:
> "We identified 3,165 high-confidence candidate SNPs associated with climate adaptation. Cross-validation across the three methods retained 234 SNPs (7.4% of single-method candidates), of which the strongest signals lay near *TSHR* and *PTK2*—genes previously implicated in cold tolerance and high-altitude adaptation."

[Implication] 现在时（保守）:
> "These candidate variants provide putative targets for breeding climate-resilient cattle and offer comparative insights into convergent climate adaptation across mammals."

---

## 元层雷区（跨方向通用）

### 1. 第 1 句空话开头
❌ "Climate change is one of the most important challenges of our time."  
❌ "With the rapid development of sequencing technologies, ..."  
❌ "Genome-wide association studies (GWAS) have become a powerful approach ..."  
✅ 直接抛具体现象 / 具体问题

### 2. Background 太长
- background 最多 2 句。不要 4 句铺垫
- abstract 总长 150-300 词（看期刊），background 占 ≤ 20%

### 3. Gap 含糊
❌ "However, the genetic basis remains unclear."  
✅ "However, GEA on cattle have been limited to specific breeds or regions."

### 4. 方法只列名不给 scale
❌ "We performed GEA analysis."  
✅ "We integrated three GEA methods (RDA, LFMM, BayPass) on 744 cattle from 85 breeds and 28 climate variables."

scale 是 reviewer 第一时间扫的硬数字（n samples × n features × n methods）。

### 5. Findings 没数字
❌ "We identified many candidate SNPs."  
✅ "We identified 3,165 high-confidence candidate SNPs."

abstract 是**数字密度最高**的地方。

### 6. Implication over-claim
❌ "Will revolutionize cattle breeding."  
✅ "Provide putative targets for breeding."

参考 `over_claim_guard.md`# 应用前景。

### 7. 缩写不必要的多
- abstract 短，每个缩写都要给全称→ 占空间
- 只用 ≥ 2 次的缩写才定义；一次就用全称
- 通用缩写（DNA / RNA / SNP / GWAS）不必定义

### 8. Findings 流水账
❌ "We did A. We did B. We did C. We did D."  
✅ 把 findings 按"主→次"组织，最 striking 的发现先写

### 9. 把 Methods 写成 Findings
❌ "We sequenced 744 cattle and performed GEA."（这不是 finding）  
✅ "GEA identified 3,165 candidate SNPs..."（动作做出 finding）

### 10. 数字不一致
abstract 报 184 个候选基因 → results 必须也是 184。投稿前 final check。

---

## 长度规范

| 期刊类型 | 典型 abstract 长度 |
|---|---|
| Nature 主刊 | 150 词以内（极短）|
| Nature Communications | 150-200 词 |
| Cell 系 | 150 词左右 + Highlights bullet（4-5 条）|
| Science 主刊 | 125 词以内 + One-sentence summary |
| Sci Adv | 150 词以内 |
| Genome Biology / MBE / PNAS | 200-250 词 |
| BMC 系 / GSE | 250-350 词，**结构化**（Background / Results / Conclusions） |

> 投稿前查目标期刊的 instructions for authors，是否要求结构化 abstract / 字数上限。

---

## 结构化 abstract 适配

部分期刊（BMC, GSE, Genet Sel Evol, BMC Genomics 等）要求结构化标题：

```
Background  | 1-2 句（领域背景 + gap）
Results     | 5-8 句（methods + findings 合并；数字密度最高）
Conclusions | 1-2 句（implication）
```

注意：**结构化 abstract 的"Methods"通常不单独成段**，是融在 Results 里的。

---

## 跨方向 illustration

> 按方案 B，挑差异化最大的几个方向：

### 景观基因组学 / GEA
- background：气候作为 selective pressure（不要"climate change is one of...")
- methods：n breeds × n environments × n GEA methods
- findings：候选 SNP 数 + 强信号基因 + 跨方法 overlap
- implication：climate-resilient breeding / conservation

### 选择信号
- background：选择是塑造 functional variation 的核心机制
- methods：n samples + n statistics（FST + iHS + XP-EHH 等）
- findings：n candidate sweeps + top 候选基因功能
- implication：marker-assisted selection / cross-species convergent evolution

### 群体结构 / 系统地理学
- background：物种全球分布的复杂性
- methods：n breeds × n countries × n SNPs
- findings：n 个独立 lineage / 关键 admixture event / 时间窗
- implication：保育单元 / breeding history

### Imputation panel
- background：低成本基因组学需要高质量 panel
- methods：panel size + benchmark dataset + 比较 panel 数
- findings：concordance/r² 在某 MAF/coverage 范围下提升 X%
- implication：低成本 GWAS / 育种基因组学应用

### 多组学整合
- background：基因型 → 调控 → 表型 链条
- methods：WGS + RNA-seq + ATAC-seq 等组学组合 + n samples
- findings：n eQTL / n co-localized signals + 关键调控元件
- implication：functional priorization 框架

---

## Highlights / One-sentence summary

部分期刊（Cell 系、Curr Biol、iScience 等）除了 abstract 还要：

### Cell-style Highlights（4 条 bullet）
每条 ≤ 85 字符。模板：
- 1: Methodological innovation
- 2: Key finding 1
- 3: Key finding 2
- 4: Implication

例：
- *Three GEA methods are integrated on 744 cattle across Eurasia and Africa*
- *Climate-related candidate SNPs are enriched near genes for cold and altitude*
- *Cross-validation reduces single-method candidates by 92%*
- *Variants provide targets for breeding climate-resilient cattle*

### Science-style One-sentence summary
50 词以内，给 non-specialist 读者。模板:
> "[What you did] [revealed/identified] [main finding], which [implication]."

例：
> "Integrated genome-environment association on 744 cattle from 85 breeds reveals candidate variants for climate adaptation, providing targets for climate-resilient breeding."

---

## 自查清单（写完 abstract 后）

- [ ] 6 元素都齐？
- [ ] 第 1 句不是空话开头？
- [ ] Background ≤ 2 句？
- [ ] Methods 给了 scale (n samples × n features)？
- [ ] Findings 至少 3-5 个数字？
- [ ] Implication 用了情态动词（may / could）？
- [ ] 时态对（Background 现在 / Methods 过去 / Findings 过去 / Implication 现在）？
- [ ] 数字与 results / figures 一致？
- [ ] 总长在期刊限制内？
- [ ] 没用过多过渡词（firstly / secondly / furthermore）？
- [ ] AI 痕迹清理？
