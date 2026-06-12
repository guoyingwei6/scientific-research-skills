---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Reviewer 心理学

> 写作选择服务于 reviewer 的认知路径，不是作者的表达冲动。本文件给的是 reviewer 怎么读论文 + 在哪些点会停下来怀疑。
> 投稿前自查、答 reviewer 时优先加载本文件。

---

## Reviewer 的真实阅读路径（不是从头读到尾）

顶刊 reviewer 通常 1-2 周内审 3-5 篇稿，每篇大致 3-6 小时。**没人从头读到尾**。典型路径：

```
Step 1 (3-5 分钟):  Title → Abstract → Fig.1 → Conclusion 段
                    => 决定"这研究值不值得深入读"
                    => 这一步过不去，已经被打 reject

Step 2 (10-20 分钟): 跳读所有 Figures 和 caption → 跳读 Methods 关键参数
                    => 决定"data 支不支持 claim / 方法可不可信"

Step 3 (1-3 小时):   Results 正文 + Discussion
                    => 找 over-claim、找逻辑漏洞、找需要补的实验

Step 4 (~30 分钟):  Introduction 细读、Supplementary 抽查
                    => 写审稿意见
```

写作时**对 Step 1 的优化收益最高**——超过 50% 的 reviewer 决定在前 5 分钟形成。

---

## 3 秒决策（Step 1 内的 Step 1）

打开 PDF 的前 3 秒，reviewer 会扫到：

* **Title** — 关键词是否对、claim 是否过头
* **Author list** — 通讯作者是否有信誉、机构组合是否合理
* **Journal** — 已知信息（不是你能控制的）

3-30 秒：

* **Abstract 第 1 句** — 是不是空话开头（"Climate change is one of the most important challenges..."）
* **Abstract 末句** — claim 是否 over-claim
* **Figure 1** — 第一眼能不能理解

**写作启示**：
- Title 不要 over-claim 也不要平淡，不要把 method 当 claim
- Abstract 第 1 句直接进入具体 gap，不要泛泛而谈
- Figure 1 在 5 秒内能传达核心信息

---

## Reviewer 在哪些点会停下来怀疑

按发生概率从高到低：

### 1. 数字与 claim 不匹配
- "significantly higher" 后没数字 → 立即怀疑
- Abstract 报 184 个候选基因，Results 正文报 178 个 → 立即怀疑（数字一致性）
- "More than X-fold improvement" 但 figure 看上去不到 → 立即翻供

**→ 写作时**：每个数字在不同地方一致，每个程度词后跟数字。

### 2. 方法关键参数缺失
- "We performed PCA" 没说软件、版本、参数 → 怀疑能不能复现
- "After quality control" 没列阈值 → 怀疑过滤的合理性
- "Significant SNPs" 没给 P 值阈值或多重检验校正 → 怀疑是不是 fishing

**→ 写作时**：methods 关键参数全披露（version + threshold + multiple testing correction）。

### 3. 引用支持力度不够
- 引用 5 篇综述但具体 claim 没原创研究支持 → 怀疑作者没读原文
- 引用了某文章但 claim 实际上跟那文章结论相反 → 立即怀疑诚信
- 引用密度过低（一段全无引用）→ 怀疑作者立场来源

**→ 写作时**：每个 claim 至少 1 个原始研究支持（综述只补充）；reviewer 自己是该领域人，会知道哪些是关键文献。

### 4. Over-claim
- 引言"Here we show for the first time that..."（实际不是 first） → 怀疑
- "Causal" 关系但只有相关性证据 → 怀疑
- "Universally" / "always" 但只研究了 1 个 system → 怀疑
- "Will be useful for" + 一堆下游应用但本文没 demo → 怀疑

**→ 写作时**：参考 over_claim_guard.md。

### 5. 故事不闭环
- Introduction §4 说要做 A、B、C 三件事，Results 里 C 没出现 → 怀疑
- Abstract 强调 X 是关键，正文 X 占很小篇幅 → 怀疑
- Discussion 大段讨论的现象在 Results 里找不到对应数据 → 怀疑

**→ 写作时**：参考 workflow.md 的"全局检查"。

### 6. Figure 与正文脱节
- 正文 cite "Figure 2A" 但 caption 里没有 2A
- Figure 标尺/单位/图例不全
- Figure 颜色对色盲不友好（reviewer 可能本人有色觉缺陷）
- Heatmap 没颜色 scale；散点图坐标轴没单位

**→ 写作时**：参考 figures_tables.md（task 文件）。

### 7. 语言问题影响理解
- 长句 + 多重否定 → reviewer 读 2 遍还不懂 → 烦躁
- 时态混用 → 不知道是 method 还是 result 还是推论
- 缩写不定义就用 → reviewer 翻回去找

**→ 写作时**：constitution.md 时态宪法 + 长句拆短。

### 8. 结果"太干净"（怀疑数据造假或 cherry-pick）
- 所有 P 值都 < 0.001
- 所有效应都符合预期方向
- Sample size 在每个对比里都恰好 OK

**→ 写作时**：诚实呈现负结果、边缘显著结果、不一致结果——讲到 limitations。

---

## 不同期刊层级的 reviewer 心理差异

| 期刊层级 | reviewer 期待 | 写作侧重 |
|---|---|---|
| 顶刊（Nat / Sci / Cell 主刊）| broad impact + technical novelty + 故事性 | introduction 强调 broader question；discussion 谈 implication for the field beyond your system |
| 高影响子刊（Nat Commun / Sci Adv / Cell 子刊）| solid 工作 + 一个让人记住的发现 | abstract 必须有 1 句"这是新的什么"；figure 1 要有 wow factor |
| 顶级专业刊（Genome Biol / MBE / PNAS）| 方法严谨 + 在该领域 incremental but solid contribution | methods 必须详细；新颖性可以小但不能没有 |
| 二区（GSE / BMC Genomics / Anim Genet）| 数据扎实 + 报告完整 + 可复现 | 不要硬 push novelty；老老实实把数据/方法/结果讲清楚 |

**写作启示**：投稿前明确"这是给哪个层级写的"。同样一个研究，写成 Nat Commun 和 BMC Genomics 是不同的稿件。

---

## Reviewer 类型分布

每篇稿件通常 2-3 个 reviewer，类型有：

* **Domain expert**：精通本研究系统（你研究牛 → 牛领域专家）。
  - 关心：你这数据 vs 已发表的牛数据是否冲突；你的品种分类是否标准；你引用本领域核心文献是否到位
  - **应对**：详细引用本领域文献；明确说你的数据和已发表数据的关系

* **Method expert**：精通本研究方法（你用 GEA → GEA 方法专家）。
  - 关心：你的方法选择是否最优；参数是否合理；多重检验是否处理；alternative methods 你考虑没
  - **应对**：methods 写详细；解释为什么选这个而不是另一个

* **Generalist / Editor**：跨学科审，关心 broad impact。
  - 关心：这篇研究"so what"；non-specialist 能不能看懂 abstract；intro 和 discussion 是否能让其他领域人 follow
  - **应对**：abstract 和 introduction §1 要 accessible；专业术语首次出现给定义

**写作启示**：写 abstract 时给 generalist 写；写 methods 给 method expert 写；写 results 和 discussion 给 domain expert 写。

---

## 如何让 reviewer "找不到 reject 理由"

reviewer 通常**先有判断后找理由**——3 秒决定大概率 reject 的稿件，他们会**找证据支持 reject**。

让 reviewer 找不到 reject 理由的策略：

1. **Title + Abstract** 没有 over-claim 嫌疑（参考 over_claim_guard.md）
2. **Figure 1** 5 秒能懂
3. **关键参数** 全披露（reviewer 想质疑参数选择，发现你都列了，质疑就空了）
4. **Limitations 主动写**（reviewer 想 critique 你局限，发现你自己写了，critique 就空了）
5. **数据可用性 + 代码可用性 + supplementary** 都齐全（reviewer 想质疑可复现性，发现你都开放，质疑就空了）

> 顶刊 reviewer 的常态是"找茬模式"——你能把所有可被找的茬主动写出来，剩下的就是 critique 你的核心 claim 是否成立——而这本身已经是高水平讨论。

---

## 写 rebuttal 时的 reviewer 心理

参考 tasks/rebuttal.md。简要原则：

* reviewer 提批评时通常是真心觉得有问题，不是恶意找茬
* 即使 reviewer 误读你的论文，也是你写得不够清楚
* 80% 的批评都能通过修改论文响应；剩下 20% 才需要 argue
* argue 时不卑不亢——既不下跪也不对抗
* 每条响应都给"修改了哪里 / 没修改原因 / 需要 reviewer 进一步指引"

---

## 自我代入练习

写完任何章节后，把自己当 reviewer 代入：

1. 我是该领域人，看到 title + abstract，3 秒后愿意继续读吗？
2. 我看 figure 1，5 秒能理解吗？
3. 我看 methods 关键步骤，能复现吗？
4. 我看 abstract 末句的 claim，能在正文找到对应证据吗？
5. 我作为 critical reviewer，在哪些点最想 push back？这些点论文回应了吗？

代入失败的点 → 直接修改原稿。
