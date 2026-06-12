---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Task: Introduction

> 引言要回答的问题：**我为什么做这个研究？读者凭什么应该 care？**
> 服务的 reviewer 决策：值不值得继续读 + 这个 gap 是不是真的 gap。

## ⚓ 元层锚点

写引言前默认遵守：
- `meta/constitution.md`：时态宪法（§1-2 现在时 / §3 视情况 / §4 过去时）+ 引用密度
- `meta/over_claim_guard.md`：尤其首创性陷阱（"first" / "novel"）
- `meta/ai_artifacts.md`：黑名单词（pivotal / underscore / leverage / delve into 在引言尤其常见）
- `meta/workflow.md`：Frame → Outline → Draft → Self-review

---

## 任务本质

引言不是"写背景"。引言是**说服 reviewer**：(i) 这个领域有个具体 gap (ii) 这个 gap 重要 (iii) 你的研究恰好填这个 gap。

引言写得好的标志：reviewer 看完最后一段时**预测得出你接下来 Methods/Results 会做什么**。

---

## 通用工作流

### Frame（框定）
回答 1-2 句：
- 我的 main message 是什么？("This paper fills the gap of X by doing Y on Z dataset")
- 读者读完引言带走的"一个核心 take-home"是什么？

### Outline（骨架）
默认走漏斗式（Workflow A），骨架 4 段，每段一个 main message：

```
§1 [大背景 / 领域问题的 importance]
   - 1-2 个奠基引用
   - 数字或具体现象支撑

§2 [已知知识：前人做了什么 + 知道了什么]
   - 3-5 个原创研究引用
   - 时间顺序或方法学顺序

§3 [Gap：哪些没解决 / 哪些方法局限]
   - 直接说出 gap，不要绕
   - 每条 gap 配 1-2 个引用支撑

§4 [本研究：为何能填这个 gap + 数据规模 + 关键 contribution]
   - 你的物种/数据/方法/发现一句话说清
   - 不剧透 specific 数字（留给 Results）
```

### Draft（成稿）
每段 4-7 句。引言总长**正文 5%-10%**（比如全文 5000 词，引言 250-500 词；Nature 系限制更严）。

### Self-review（自审）
- §4 写的"本研究做了什么"和 §3 的 gap 对得上吗？
- §3 的 gap 是否真的没人做过？(over-claim 风险)
- §1 第一句是不是空话开头？

---

## 通用骨架（漏斗式 4 段，最大公约数）

§1 — 大背景钩子：
- 第一句直接抛出领域核心问题或现象
- 不要"With the rapid development of..." / "In recent years..." 这种空话开头
- 用具体数字 / 现象 / scope 把读者拉进来

§2 — 已知知识：
- 前人 N 年的 progress 概述
- 不要单调列举（"X et al. did Y. Z et al. did W. ..."），按方法学发展或时间逻辑组织
- 重点引用本领域奠基论文 + 近 3-5 年高引文章

§3 — Gap：
- 明确 gap 类型：(a) 数据缺失（某物种/区域/层级没人做过）(b) 方法局限（前人方法在某些场景失效）(c) 理论争议（不同假说没定论）
- 每条 gap 配证据支撑（引用 + 简短陈述）
- **gap 必须真实**——别为了讲故事编造 gap

§4 — 本研究：
- 一句话核心 contribution
- 数据规模（n samples, n SNPs, n environmental variables 等）
- 方法整合（如果是多方法研究）
- **不剧透具体数字**（"We identified 184 candidate genes" 这种留给 Abstract/Results）

---

## 通用范例（漏斗式开篇句）

> 以景观基因组学论文为例，但句式可迁移：

§1 第一句模板：
- "Climate change exerts major selective pressure on natural populations, driving local adaptation across diverse taxa."
- 关键不在"climate change"，在**主语-动词-宾语直接到位**，不绕。

§4 起句模板：
- "Here, we [verb past tense] [N samples / dataset] from [scope] and integrated [methods] to identify [target]."
- "Here, we" 是引言 §4 的标准开场。

> 元规则：**§1 第一句的主语 = 你研究的 broader phenomenon**；**§4 第一句以"Here"或"In this study"为锚**。这两条跨方向通用。

---

## 三种工作流的选择

参考 `meta/workflow.md`：

| Workflow | 适用场景 | §1 起句 |
|---|---|---|
| A 漏斗式 | 默认 / 大多数研究论文 | 大背景 → 收窄 |
| B 倒漏斗 | Nat Commun Brief / 方法 / tools | 直接抛"我们做了什么" |
| C Story-driven | Cell / Sci Adv / 有 striking phenomenon | 具体现象/observation |

不确定就用 A。

---

## 元层雷区（跨方向通用）

### 1. 空话开头
❌ "With the rapid development of sequencing technologies, ..."  
❌ "Climate change is one of the most important challenges of our time."  
❌ "Genome-wide association studies (GWAS) have become a powerful tool..."  
✅ 直接抛具体问题或数字

### 2. 综述化
- 引言不是 mini review。每个 claim 1-2 个引用足够，不要 5+
- 出现 "Many studies have shown..." + 8 个 cite = 综述化警告

### 3. Gap 注水
❌ "However, the genetic basis of X remains unclear."（笼统）  
✅ "However, GEA on cattle have been limited to specific breeds or regions, leaving global-scale climatic adaptation patterns largely uncharacterized."（具体）

### 4. §4 过度承诺
- 列了 5 件本文要做的事，正文只做了 3 件 → reviewer 立刻质疑
- §4 列出的事必须 Methods/Results 全部覆盖

### 5. 首创性 over-claim
- 引言里的 "first" / "novel" / "unprecedented" 是 reviewer 第一时间去 PubMed 验证的对象
- 没 100% 把握 → 加 "to our knowledge"
- 参考 `over_claim_guard.md`#唯一性

### 6. 时态混乱
- 通论性事实 → 现在时（"Local adaptation is shaped by ..."）
- 引用前人具体研究 → 过去时（"Smith et al. identified ...")
- 你自己做了什么 → 过去时（"Here we sequenced ..."）

### 7. 引言 vs Discussion 边界
- 引言：**为什么做** + **做了什么**（不展开为什么这么做）
- Discussion：**意味着什么** + **局限性** + **broader implication**
- 不要在引言里大段讨论结果意义——那是 Discussion 的事

---

## 跨方向 illustration

> 元规则的演示，**不是范式模板**。具体写作必须根据用户初稿和数据。

### 群体结构 / 系统地理学
- §1 钩子：物种全球分布 + 经济文化重要性 + 育种历史复杂性
- §3 gap 常见：某地区/某品种没系统采样 / 高分辨率基因组数据缺失 / 多群体整合分析少
- §4 关键：n breeds × n individuals × n countries

### 驯化 / 人口动态
- §1 钩子：驯化是研究 recent rapid evolution 的天然实验
- §3 gap 常见：驯化时间/地点争议 / 多次独立驯化假说 / 古代-现代连续性证据缺失
- §4 关键：包含古 DNA / 多大陆采样 / 长读长测序

### 选择信号
- §1 钩子：选择是塑造功能性遗传变异的核心机制
- §3 gap 常见：单一统计量假阳性高 / 跨物种 convergent 信号识别难
- §4 关键：多统计量整合 / 跨群体 / 功能验证

### 渗入 / 杂交
- §1 钩子：杂交在物种适应中的双面作用（rescue vs. genetic load）
- §3 gap 常见：渗入比例估计精度 / adaptive vs. neutral introgression 区分
- §4 关键：高密度 SNP / 多源群体 / 功能 follow-up

### 景观基因组学 / GEA
- §1 钩子：气候变化作为 selective pressure
- §3 gap 常见：单一 GEA 方法假阳性 / 单物种/单区域研究 / 气候 vs. 地理共线问题
- §4 关键：多方法交叉验证 / 全球或大陆尺度 / 数据整合（WorldClim / NCEP / CHELSA 等）

### SV / 泛基因组
- §1 钩子：短读长测序遗漏的功能变异
- §3 gap 常见：SV 检测精度 / pangenome 在非模式物种缺失 / SV 与表型关联少
- §4 关键：长读长 / 多个体高质量组装 / pangenome graph

### Imputation panel
- §1 钩子：低成本基因组学需要高质量参考 panel
- §3 gap 常见：现有 panel 在某物种/某群体精度不够
- §4 关键：n 样本 × MAF 覆盖 × 测序覆盖度

### 多组学整合
- §1 钩子：变异 → 调控 → 表型 链条断裂
- §3 gap 常见：cis-regulatory 注释少 / tissue-specific 数据缺失
- §4 关键：WGS + RNA-seq + ATAC-seq + ChIP-seq 等多层整合

---

## 自查清单（写完引言后）

- [ ] §1 第一句**不是空话开头**？
- [ ] §1-2 用现在时（通论），§3 引用混合时态，§4 过去时？
- [ ] §3 的 gap 是**具体的**还是笼统的？
- [ ] §3 的 gap 是**真实的**？(没人做过 / 做得不够 / 方法局限)
- [ ] §4 列的 contribution 是否 Methods/Results 都覆盖到？
- [ ] "first" / "novel" / "unique" 加了 "to our knowledge" 吗？
- [ ] 引用密度合理（每段 2-5 个）？
- [ ] AI 黑名单词清理过（pivotal / underscore / leverage / delve into）？
- [ ] 引言总长在正文 5%-10%？
- [ ] 数字密度：除了 §4 提样本规模，§1 是否有具体数字 / 现象支撑钩子？
