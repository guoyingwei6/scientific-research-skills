---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Task: Title

> Title 要回答的问题：**3 秒扫一眼，reviewer 知不知道这是研究什么 + 用了什么方法 + 找到了什么**。
> 服务的 reviewer 决策：值不值得打开 PDF。

## ⚓ 元层锚点

- `meta/over_claim_guard.md`：title 是 over-claim 第一现场（reviewer 第一眼看到）
- `meta/reviewer_psychology.md`：3 秒决策核心
- `meta/ai_artifacts.md`：title 里的"unraveling" / "shedding light on" / "deciphering" 是高密度 AI 痕迹

---

## 任务本质

Title 是**唯一会被检索到的句子**——PubMed / Google Scholar / 同行扫文献都看 title。

写得好的标志：3 秒内能扫出"研究什么 + 怎么做 + 找到了什么或想问什么"。

---

## 三种典型句式

### A. 主-谓-宾陈述句（最常见）
> "Climate factors drive the local adaptation of Old World cattle"

模板：[环境/驱动力] [drive / shape / underlie] [现象] in/of [系统]

适合：能用一句话陈述核心 take-home 的研究。

### B. 描述短语（无谓语）
> "Genomic basis of climate adaptation in 744 globally distributed cattle"

模板：[研究对象/主题] in/of [系统/规模]

适合：偏 descriptive / resource paper / 没有强 take-home 的研究。

### C. 冒号 + 双层结构
> "Climate-driven adaptation in cattle: genome-environment associations across 85 breeds"

模板：[high-level concept]: [specific approach/scope]

适合：想同时传达"概念 + 具体做法"的研究；适合较长 title。

---

## 长度

| 期刊类型 | 典型 title 长度 |
|---|---|
| Nature 主刊 / Cell | 12-15 词 |
| Nat Commun / Sci Adv | 12-18 词 |
| 专业刊 | 15-25 词 |

> 平均 12-15 词最合适。短了信息不足，长了 title 像 abstract。

---

## 元层雷区

### 1. Over-claim
❌ "Reveals the genetic basis of climate adaptation"（reveal = 强 claim）  
❌ "Comprehensive landscape genomic analysis"（comprehensive = 不能轻易用）  
✅ 退一步：identify / characterize / dissect

### 2. AI / 文学性词汇
- "Unraveling the mysteries of ..." ❌
- "Shedding light on ..." ❌
- "A journey into ..." ❌
- "Decoding ..." ❌
- "The hidden world of ..." ❌

### 3. 缩写不定义
- title 里**慎用缩写**——读者扫描时不一定认识
- 通用缩写（SNP / GWAS / RNA-seq）OK
- 专业缩写（GEA / pRDA / RFMix）尽量展开或避免

### 4. 太泛
❌ "A study of cattle genomics"（太泛）  
✅ "Genome-environment associations identify climate-adaptive variants in 85 cattle breeds"

### 5. 把 Method 当 Claim
❌ "Whole-genome sequencing of 744 cattle"（仅是 method，没 finding）  
✅ "Whole-genome sequencing reveals climate-adaptive variants in 744 cattle"

适合纯 resource paper 的话 method-as-title 可以；但研究类论文要有 finding。

### 6. 包含太多关键词
- title 不是 SEO
- 4-5 个核心 keyword 足够
- 塞 7-8 个 keyword 反而显得 desperate

### 7. 物种 / 数字不显眼
- 物种 / scale 是搜索关键词，**title 里要有**
- "Climate adaptation in livestock" ⚠️ "livestock" 太泛
- "Climate adaptation in cattle" ✅
- "Climate adaptation in 744 cattle from 85 breeds" ⚠️ 数字进 title 看个人风格

---

## 跨方向 illustration

> 按方案 B,挑最有差异化的方向：

### 景观基因组学 / GEA
- 关键词：climate / environment / adaptation / GEA / landscape / association
- 范例风格：
  - "Climate factors drive the local adaptation of Old World cattle"
  - "Genome-environment associations identify climate-adaptive variants in chickens"
  - "Landscape genomics reveals adaptive differentiation under climate gradients"

### 群体结构 / 系统地理学 / 驯化
- 关键词：origin / domestication / population structure / phylogeography / migration
- 范例风格：
  - "Whole-genome resequencing reveals the demographic history of African cattle"
  - "Multiple origins and patterns of selection in domestic sheep"

### 选择信号
- 关键词：selection / adaptation / sweep / signature
- 范例风格：
  - "Signatures of selection in Tibetan sheep reveal high-altitude adaptation"
  - "Convergent selective sweeps across pig breeds adapted to extreme climates"

### Imputation panel / Resource paper
- 关键词：reference panel / imputation / resource / atlas
- 范例风格：
  - "A reference panel for low-coverage sequencing in cattle"
  - "Genomic atlas of [species]: [scale] reveals [main feature]"

### SV / 泛基因组
- 关键词：pangenome / structural variation / graph / long-read
- 范例风格：
  - "A pangenome of [species] uncovers structural variants underlying [trait]"

### 多组学整合
- 关键词：integrative / multi-omic / regulatory / cis-eQTL
- 范例风格：
  - "Integrative multi-omics identifies regulatory variants underlying [trait] in [species]"

---

## Title brainstorm 流程

如果用户让"想几个 title 选项"：

1. **找 1 句 take-home**（abstract 第 1 句 finding）
2. **从 take-home 抽 3 个核心元素**：(1) 物种/系统 (2) 现象/方法 (3) 发现
3. **生成 3-5 个候选**，每个偏不同风格（A 陈述句 / B 描述短语 / C 冒号双层）
4. **检查每个候选**：
   - 长度合理？
   - 没 over-claim？
   - 没 AI 词？
   - 关键词全？
5. **让用户选**——不要直接定 1 个

---

## 自查清单（定 title 前）

- [ ] 12-25 词（按期刊规范）？
- [ ] 没 over-claim（first / novel / comprehensive / unique 慎用）？
- [ ] 没 AI 痕迹词（unravel / shed light on / decode / journey）？
- [ ] 物种 / scale / 关键方法名都在 title？
- [ ] 不滥用缩写？
- [ ] 不只是 method，给了 finding 或 question？
- [ ] 3 秒扫一眼能传递"研究什么 + 怎么做 + 找到了什么"？
