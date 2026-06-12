---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Task: Outline / 列大纲

> Outline 要回答的问题：**正式动笔前,论文骨架是什么 + 每节 main message 是什么**。
> 服务的场景：写论文初期,或者大改稿（restructure）阶段。

## ⚓ 元层锚点

- `meta/workflow.md`：写作四步法的 Step 2（Outline 阶段）
- `meta/over_claim_guard.md`：outline 阶段就要想 take-home 强度
- 各 task 文件的"通用骨架"是 outline 的填充模板

---

## 任务本质

Outline 不是"列 IMRAD 标题",是**为每段写一句 main message**。

写得好的标志：用户**只看 outline 就知道全文故事线 + 每段说什么**——动笔时只需要把 main message 扩成段落。

---

## 通用工作流

### Step 0：一句话论证（动笔前必填）

在开始任何 outline 之前，先用这个句式写出全文核心论证：

> **In [system/problem], we show [advance] using [approach], supported by [evidence], with [boundary].**

填不出来 = 核心论证没想清楚，不要开始写。这句话后续会成为：
- Abstract 的 core finding 句
- Introduction §4 的最后一句
- Discussion §1 的 take-home
- Cover letter 的核心贡献句

示例（选择信号论文）：
> In Mongolian cattle adaptation to harsh steppe environments, we show that 184 candidate sweep regions enriched for thermotolerance and feed-efficiency genes using FST + XP-EHH multi-statistic intersection, supported by convergence with previously reported bovine selection signals, with the caveat that functional validation is absent.

### Step 1：定 1 个 take-home
全文核心 take-home，1 句话（从 Step 0 的论证句提炼）。这一句话决定 abstract 末句 / discussion §1 / cover letter §2。

### Step 2：从 take-home 反推章节

```
[take-home: ...]
↓
Abstract:    [6 元素填充]
Title:       [3 个候选,对齐 take-home]
Introduction: [4 段漏斗 → §4 必须 deliver take-home]
Methods:     [按数据流分小节]
Results:     [小节顺序 = 故事弧 → 最后一小节是 take-home 的关键证据]
Discussion:  [§1 take-home + §2-3 解读 + §4 implication + §5 limitation]
Figures:     [4-6 个 main figure,Fig N = take-home 关键 figure]
```

### Step 3：每段一句 main message
```
Introduction §1: [大背景 main message]
Introduction §2: [已知知识 main message]
Introduction §3: [gap main message]
Introduction §4: [本研究 main message + scale]

Results §1: [描述性 setup main finding]
Results §2: [核心 finding 1]
Results §3: [核心 finding 2]
...

Discussion §1: [take-home + 1 句]
Discussion §2: [机制解读]
...
```

### Step 4：列每段配套要素
每段写明：
- main message（1 句）
- 关键证据 / 数字 / figure
- 关键引用（如适用）
- 时态（防止动笔时混乱）

### Step 5：故事弧 sanity check
- Introduction §3 的 gap → Discussion 都回应了吗？
- Introduction §4 承诺的事 → Methods/Results 都 cover 了吗？
- Abstract take-home → Discussion §1 take-home 一致吗？

---

## Outline 模板

```
=========
一句话论证: In [system/problem], we show [advance] using [approach],
            supported by [evidence], with [boundary].

Take-home: [1 句提炼]
Title: [3 个候选，最终选 1]
Target journal: [期刊 + 层级]
Scale: [n samples × n features × n methods]

=========
ABSTRACT
- Background: [...]
- Gap: [...]
- Methods/Data: [...]
- Findings: [...]
- Implication: [...]

=========
INTRODUCTION
§1: [main msg] | refs: [list 2-3]
§2: [main msg] | refs: [list 3-5]
§3: [main msg] | gap 类型: [data gap / method gap / theory gap] | refs: [list 2-3]
§4: [main msg] | scale: [n × n × n]

=========
METHODS
M1 Sample/Data:        [outline]
M2 Sequencing:         [outline]
M3 Mapping:            [outline]
M4 Variant calling:    [outline]
M5 [Core analysis 1]:  [outline + 关键参数]
M6 [Core analysis 2]:  [outline + 关键参数]
M7 Statistical:        [outline + multiple testing]

=========
RESULTS
R1 [Title]: [main finding] → Fig 1
R2 [Title]: [main finding] → Fig 2
R3 [Title]: [main finding] → Fig 3
R4 [Title]: [main finding] → Fig 4-5
R5 [Title]: [main finding] → Fig 6

=========
DISCUSSION
D1: Take-home [1 句]
D2: [机制 / 解读 1]
D3: [机制 / 解读 2 / 跨物种比较]
D4: Implication for [应用]
D5: Limitations [2-4 条具体的]

=========
FIGURES (main, 4-6 个)
Fig 1: [描述] (panel A/B/C)
Fig 2: [描述]
...

TABLES (如有)
Table 1: [描述]

SUPPLEMENTARY
Fig S1-S5: [描述]
Table S1-S3: [描述]
```

---

## Outline 阶段最常见错误

### 1. 跳过 Step 0 直接 outline
- 没填一句话论证就开始列章节
- 结果：每节看似齐全,合起来没主线
- → 先填 Step 0，再 take-home，再章节

### 2. Results 章节按方法顺序而非故事顺序
- 习惯按"我们做了 PCA → 然后 ADMIXTURE → 然后 GEA → 然后 functional"
- 但 main message 角度看,PCA / ADMIXTURE 是 setup,GEA 是 core,functional 是 follow-up
- → 按**故事弧** organize

### 3. Introduction §4 太空
- §4 写 "We performed comprehensive analysis on cattle"
- 没具体 scale,没具体方法,没 deliverable
- → §4 必须有 n × n × n + key methods + key finding hint

### 4. Discussion 跟 Introduction 不闭环
- Introduction §3 提了 3 个 gap,Discussion 只回应 1 个
- → outline 阶段就要查 gap 闭环

### 5. Figures 顺序与 Results 不对齐
- Outline 列 Fig 1-6,但跟 Results §1-5 没明确映射
- → 每个 figure 标"对应 Results 哪一节"

### 6. Take-home 太宽
- "We characterized the genetic basis of ..."（太空）
- "We identified 234 candidate climate-adaptive variants enriched in temperature- and precipitation-related genes"（具体）
- → Outline 阶段强迫自己**用数字定 take-home**

### 7. Limitation 没 outline
- 很多人 outline 跳过 Discussion §5 (limitations)
- 等到写 Discussion 时才想 → 临时 generic 的 limitation
- → outline 阶段就列 2-4 条具体 limitation

---

## 跨方向 illustration

### 景观基因组学 / GEA 论文 outline 关键
- Results §1 必有 environmental variable PCA / 相关性 / Köppen 底图采样
- Results §2 必有 variation partitioning（pure climate / pure geo / shared）
- Results §3-N 各 GEA 方法 + 多方法 overlap
- Discussion §3 必有 cross-species convergent climate adaptation
- Discussion §5 必有 GEA 的局限（candidate ≠ causal / 环境变量代理性）

### 选择信号论文 outline 关键
- Results §1 群体 setup
- Results §2-N 多统计量 + 候选区间 + 候选基因 follow-up
- Discussion §3 demographic confounding 必有讨论
- Limitations 必含"功能验证缺失"

### Imputation panel 论文 outline 关键
- Methods 必有详细的 panel construction + benchmark dataset
- Results 必有 r²/concordance 按 MAF / coverage 分层 + 与现有 panel 比较
- Discussion 必有"应用场景说明"（什么物种 / 群体 / coverage 用本 panel 最合适）

### SV / 泛基因组论文 outline 关键
- Methods 必有 long-read coverage / 组装 N50 / SV caller 详细
- Results 必有 SV size / type 分布 + 与 SNP 对比
- Discussion 必有"短读长漏掉的功能变异"

---

## 长度与详尽度

| 用途 | outline 详尽度 |
|---|---|
| 自己起草用 | 每段 1-2 句 main message + 关键 refs |
| 与共作者讨论用 | 每段 2-3 句 + 关键数字预留 + figure 草图 |
| Grant / 投稿前 outline 重审 | 详尽到接近段落级 |

---

## 自查清单（outline 完成后）

- [ ] 一句话论证填完了（Step 0）？
- [ ] Take-home 用 1 句话能说清？
- [ ] 每段都有 1 句 main message？
- [ ] Results 章节按**故事弧**而非方法顺序？
- [ ] Introduction §3 的 gap 在 Discussion 都回应？
- [ ] Introduction §4 承诺的事 Methods/Results 都 cover？
- [ ] Figures 顺序与 Results 章节对齐？
- [ ] Discussion §5 (limitations) outline 了 2-4 条具体的？
- [ ] Title 给了 3 个候选？
- [ ] Abstract 6 元素都 outline 了？
- [ ] 数字/scale 在 outline 里就明确（不是"补充再说"）？
