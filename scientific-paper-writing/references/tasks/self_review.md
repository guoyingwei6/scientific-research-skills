---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Task: Self-review / 投稿前自查

> Self-review 要回答的问题：**reviewer 在哪些点会卡住？我能不能在投之前自己先把这些 fix 掉**？
> 服务的 reviewer 决策：找不到 reject 理由。

## ⚓ 元层锚点

- `meta/constitution.md`：所有宪法条目都是自查项
- `meta/reviewer_psychology.md`：reviewer 的怀疑信号清单 = 自查清单
- `meta/over_claim_guard.md`：over-claim 自查
- `meta/ai_artifacts.md`：AI 痕迹自查
- `meta/workflow.md`："写完整篇后的全局检查"

---

## 任务本质

Self-review **不是再读一遍**，而是**用 reviewer 视角扫雷**。

写得好的标志：你能在 reviewer 之前把所有可被找的茬主动 fix 或主动声明（limitations）。

---

## 三层 self-review

按 `meta/workflow.md` 的修改三层法，但这里是**已成稿后**的最终扫描：

### 第 1 层：论证逻辑（占 40% 时间）
- 全文故事线连贯吗？
- Introduction §3 的 gap 在 Discussion 里都回应了吗？
- Introduction §4 承诺做的事，Methods/Results 都做了吗？
- Abstract 的 take-home 在正文找得到证据吗？
- Discussion 解读的现象在 Results 里都有数据吗？

### 第 2 层：句子结构（占 30% 时间）
- 每段是否一个 main message？
- 有没有应该拆 / 应该合的段落？
- 时态混乱？（搜 "is" / "are" 在 Methods/Results 里出现）
- 长句拆得够细吗（> 40 词的句子）？

### 第 3 层：词汇 / 排版（占 30% 时间）
- 数字格式统一？
- 缩写一致？
- 软件版本号齐？
- AI 痕迹清理？
- 物种学名斜体一致？

---

## 投稿前检查清单（按章节）

### Title
- [ ] 12-25 词内（按期刊规范）
- [ ] 没 over-claim（first / novel / comprehensive 慎用）
- [ ] 没 AI 词（unravel / shed light on）
- [ ] 物种 + scope + key word 都在
- [ ] 跟 Abstract 第 1 句 finding 对得上

### Abstract
- [ ] 6 元素齐（background → gap → methods → data → findings → implication）
- [ ] 第 1 句不是空话开头
- [ ] Methods 给了 scale (n × n)
- [ ] Findings 至少 3-5 个数字
- [ ] Implication 用情态动词
- [ ] 时态分段对（参考 constitution.md）
- [ ] 总长在期刊限制内
- [ ] 数字与正文一致

### Introduction
- [ ] §1 第一句不是空话
- [ ] §3 的 gap 是具体的、真实的
- [ ] §4 承诺的事在正文都做到
- [ ] "first" / "novel" 加 "to our knowledge"
- [ ] 引用密度 2-5 个 / 段
- [ ] AI 词清理（pivotal / underscore / leverage）
- [ ] 总长 5-10% 全文

### Methods
- [ ] 全部过去时
- [ ] 每个软件 + 版本号
- [ ] 每个 filter + 阈值
- [ ] 多重检验校正方法
- [ ] 缩写定义
- [ ] 软件名拼写按官方
- [ ] 章节顺序按数据流
- [ ] 数据 / 代码 / accession 全
- [ ] 伦理批文（如适用）

### Results
- [ ] 每段开头一个具体 finding
- [ ] 每个 "significant" 后跟数字
- [ ] 每个 claim 后 figure / table cite
- [ ] 时态：动作过去时 / figure 描述现在时
- [ ] 没把 discussion 解读塞进 results
- [ ] 数字内部一致 + 与 abstract / figures 一致
- [ ] effect size + CI（不只 P 值）
- [ ] 关键数字配 N

### Discussion
- [ ] Take-home 1-2 个
- [ ] 与 introduction §3 闭环
- [ ] Implication 用保守表达
- [ ] Limitations 2-4 条**具体的**
- [ ] 每条 limitation 给 future direction
- [ ] 没贬低前人
- [ ] 没重复 Results 数字
- [ ] AI 痕迹（shed light / underscore）清理
- [ ] 篇幅在合理范围

### Figures / Tables
- [ ] caption 现在时
- [ ] caption self-contained
- [ ] 样本量 n / 统计方法 / 显著性标注 / 颜色含义 / 单位都齐
- [ ] 编号顺序 ↔ 正文 cite 顺序
- [ ] 数字三方对照（figure / caption / 正文）一致
- [ ] 色盲友好
- [ ] supplementary 编号对齐

### 引用 / 参考文献
- [ ] 参考文献列表里每篇都在正文出现
- [ ] 正文每个 cite 都在参考文献列表
- [ ] 引用格式按期刊规范
- [ ] 自引比例 < 20%
- [ ] 没 [CITATION NEEDED] 残留

### 全局
- [ ] 数字一致性（abstract / results / figure caption / supplementary）
- [ ] 缩写定义一次后全文一致
- [ ] 物种学名首次斜体 + 全称
- [ ] 没 [需要确认] 残留
- [ ] 没 placeholder（[X.XX%] / [n=XX]）残留

---

## "找不到 reject 理由"策略

参考 `reviewer_psychology.md`。投稿前主动做：

### 1. 主动写 Limitations
- 不写 limitations = reviewer 自己找
- 写了 limitations = critique 落空一半

具体的 limitation > 笼统的 limitation。  
"未来需要更多样本"几乎对所有研究都成立 → 不是真 limitation。

### 2. Methods 完整披露
- 关键参数全列 → reviewer 想质疑参数选择，发现你都列了
- 软件版本号全 → reviewer 想说"无法复现"，无从下嘴
- 多重检验明确 → reviewer 想说 "fishing"，已经被你堵住

### 3. 数据 / 代码全开放
- accession number 提交前先存好
- 代码 GitHub 公开（甚至 Zenodo DOI）
- raw data 暂时不能开放也要在 data availability 里说明

### 4. Supplementary 要充实
- main figure 的所有控制实验 / 敏感性分析放 supplementary
- 数据 QC 步骤详细放 supplementary
- reviewer 想质疑 X，supplementary 已经回应过

---

## 反向自查：reviewer 角色扮演

成稿后做一次"假装是 reviewer"：

### Reviewer Type 1: Domain expert
- 我研究这个物种 / 这个领域 → 这数据跟我已发表 / 已知结果一致吗？
- 你引用我领域核心文献了吗？
- 你的品种 / 群体分类符合标准吗？

### Reviewer Type 2: Method expert
- 我熟悉你用的方法 → 你参数选择合理吗？
- 你考虑 alternative methods 吗？
- 你处理 multiple testing / population structure / batch effect 了吗？

### Reviewer Type 3: Generalist / Editor
- 我不在这领域，但读 abstract → "so what"？
- Introduction §1 我能 follow 吗？
- 你的 take-home 在更 broad 的 context 里有意义吗？

---

## Devil's Advocate self-check（投稿前最后一关）

> **触发时机**：全文成稿，准备投稿前。完成上面三类 reviewer 角色扮演后，专门用这一轮找**论证上最脆弱的点**。
> 目标不是找错别字，是找"最强的反驳"——reviewer 如果想否定这篇论文，他会用什么理由？

逐一过以下 7 个维度，每个维度用 1-3 句话写下"最强攻击"，然后决定：修改论文 / 加 limitation / 不需要处理。

### 1. 最强反驳（Strongest Counter-Argument）
- 如果有人想否定你的核心结论，他最有力的理由是什么？
- 你的 Discussion 里有没有主动提到并回应这个反驳？
- 如果没有 → 加一段。如果有 → 确认表达够清楚。

### 2. Cherry-picking 检测
- 你展示的 candidate genes / regions / variants，是基于客观标准筛选的，还是事后挑看起来有故事的？
- 统计截断值（FST top 5% / XP-EHH |Z| > 2）是投稿前定的还是看了结果后定的？
- 如果有主观成分 → 在 Methods 里说明筛选标准的预先设定，或在 Discussion 里承认。

### 3. Confirmation bias 检测
- 你的解读是否只关注了支持结论的基因/信号，忽略了同等显著但不符合叙事的结果？
- 你有没有报告 null results 或 negative findings？
- 如果有遗漏 → 补充或在 Discussion 说明。

### 4. 逻辑链完整性
- 从数据到结论，每一步推断都有证据支撑吗？
- 有没有"跳步"——从信号直接跳到功能解释，中间缺乏文献或实验支持？
- 群体遗传学高发跳步：选择信号 → 功能基因 → 适应表型，每步都需要文献或辅助分析。

### 5. 过度泛化检测
- 你的样本覆盖的群体/地理范围，是否支持你做出的宏观结论？
- 是否用"cattle"指代了实际只研究了"Chinese indigenous breeds"的结论？
- 如果有 → 缩小结论的 scope，或在 Discussion 说明推广的前提条件。

### 6. 替代解释分析
- 你观察到的信号，除了你提出的解释，还有哪 1-2 种替代解释？
- 这些替代解释被你排除了吗？用什么方法排除的？
- 如果没有排除 → 在 Discussion 里列出替代解释 + 为什么你认为自己的解释更合理。

### 7. "So what?" 测试
- 如果结论成立，对领域有什么具体影响？对育种实践有什么用？
- Implication 段够具体吗，还是停在"提供了参考"这类空话？
- 如果空洞 → 往下追问一层：谁会用这个结果，怎么用，改变什么决策？

---

## Claim Audit（逐条核查主要 claim）

> **触发时机**：Devil's Advocate 完成后，或用户说"帮我检查 claim 是否有证据支撑"。
> 目的：对论文中每一个主要 claim 给出明确判决，不留模糊地带。

对 Discussion / Abstract / Introduction §4 中的每个主要 claim，逐条填写：

```
Claim: [原文 claim，完整引用]
Verdict: keep | weaken | revise | remove
Evidence used: [支撑这个 claim 的具体数据 / figure / 引用]
Missing evidence: [缺什么才能让这个 claim 成立，或"无"]
Overclaim risk: high | medium | low
Suggested wording: [如果需要修改，给出修改后的措辞]
```

### 常见 verdict 判断标准

| Verdict | 适用情况 |
|---|---|
| **keep** | 有直接数据支撑，措辞保守，bound 清楚 |
| **weaken** | 数据支持方向正确但不充分；需要降级情态动词（may / suggest / indicate 替换 demonstrate / prove） |
| **revise** | Claim 本身方向对，但措辞有 over-claim / scope 过宽 / 缺 boundary |
| **remove** | 无数据支撑，且无法在当前研究范围内补充；或与其他 claim 完全重复 |

### 群体遗传学高风险 claim 类型

| Claim 类型 | 高发问题 | 默认处理 |
|---|---|---|
| "gene X is associated with trait Y" | 相关 ≠ 因果，且群体遗传信号 ≠ 功能验证 | weaken → "candidate gene" / "putatively associated" |
| "our results suggest positive selection" | 多种统计量只找到 1 个 | weaken → "evidence consistent with" |
| "cattle breed X adapted to environment Z" | 样本量小 / 单一群体 | weaken + 加 boundary |
| "first report of X in Y species" | 未系统检索文献 | revise → 加 "to our knowledge" |
| "these variants can be used for breeding" | 无验证数据 | weaken → future direction |

---

## 红线（投稿前必查）

下列问题任何一个**必须 fix** 才投稿，不要"先投投看再说"：

- 数字在 abstract / results / figure 不一致
- "first" / "novel" 没搜过文献验证
- 关键 effect size 缺失（只 P 值）
- Methods 关键软件没版本号
- Figure caption 与 figure 错位
- supplementary 编号与正文 cite 顺序不对
- 数据 accession 没拿到 / 没公开
- 引用列表里有论文没在正文出现
- 残留 [CITATION NEEDED] / [需要确认] / placeholder
- 缩写定义后第二次出现又写全称（不一致）

---

## 工具配合

参考 `meta/user_tools.md`：

- 语法层：Grammarly / Writefull
- 引用层：Zotero
- 数字一致性：搜索全文关键数字（如 "184 candidate"）
- 缩写一致性：搜索全文每个缩写第一次出现位置

---

## Self-review 时长

- **段落级 self-review**：写完每段 30 秒
- **章节级 self-review**：写完每章 5-10 分钟
- **全文 self-review**：投稿前 2-4 小时
- **重投 self-review**：每个 reviewer 意见 fix 后 1-2 小时

> 加起来 self-review 时长 ≈ 写作时长的 30-40%。值得。
