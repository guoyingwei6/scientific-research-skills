---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# 写作工作流

> 写作和修改的**流程方法论**。和 constitution（硬规则）互补：constitution 管"对错"，workflow 管"按什么顺序做"。
> 跟 constitution 一样，本文件被默认始终加载。

---

## 写作四步法（每个章节都适用）

无论写 introduction 还是 methods，都按 Frame → Outline → Draft → Self-review 四步走。**不要跳步**。

### Step 1 — Frame（框定）

写第一个字之前，先用 1-2 句话回答：

* **这一节的 main message 是什么**？(reader 读完这一节应该带走的一个核心 take-home)
* **这一节服务于谁的什么决定**？
  - Introduction → reviewer 决定"这研究值不值得读"
  - Methods → reviewer 决定"这研究能不能复现 / 方法可不可信"
  - Results → reviewer 决定"data 支不支持 claim"
  - Discussion → reviewer 决定"这研究有没有 broader impact"
* **这一节的边界**？(哪些不该在这里讲，要留给其他节)

> Frame 阶段最忌讳：直接开始打字。打字前不知道 main message，写出来一定散。

### Step 2 — Outline（列骨架）

列**段落级**而不是句子级的骨架。每一段一个 main message + 关键数字/证据 + 主要引用。建议格式：

```
§1 [main message]
   - 证据 1: [...]
   - 证据 2: [...]
   - 引用: [...]
§2 [main message]
   ...
```

**骨架质量自检**：
- 每段是否只承担 1 个 main message？(2 个就该拆)
- 段落顺序是否有逻辑递进？(时间 / 因果 / 空间 / 一般→特殊)
- 各段加起来是否回答了 Frame 阶段的 main message？

### Step 3 — Draft（成稿）

只有骨架确定后才打字成文。原则：

* **段落内部三件套**：topic sentence (1 句立论) + supporting evidence (2-4 句证据/数字/引用) + bridge sentence (1 句过渡到下一段，可选)
* **不要边写边查文献**：先把骨架填上，引用先标 `[CITATION NEEDED]`，写完一段再批量补引用。中途跳出去查文献会打断思维链。
* **数字先用 placeholder**：手边没有的数字标 `[X.XX%]`、`[n=XX]`，写完一段再批量补。
* **不要边写边润色**：草稿阶段允许句子糙、词不准。Step 4 自查时再统一改。

### Step 4 — Self-review（自审）

**写完一段就自审一次**，不要写完整章节再回头。每段过 4 个问题：

1. **Main message 是否一句话能说出来**？说不出来 = 段落散，重写
2. **每个 claim 后面有没有数字或证据**？模糊形容词后面没数字 = 加数字或删形容词
3. **时态/数字/命名是否符合 constitution**？
4. **有没有 over-claim**？情态动词够不够保守？(参考 over_claim_guard.md)

> 自审时**不要修句子结构**，只查 4 个问题中的硬伤。句子级润色留到全文成稿后统一做（见下方"修改三层法"）。

---

## 修改三层法（顺序不能反）

修改时分 3 层，**从大到小**：

### 第 1 层：论证逻辑（最先做）
- 段落顺序对不对？有没有应该提前的 take-home 被埋在中间？
- 段落之间的过渡是否自然？(如果改一段需要改 3 段才说得通，说明逻辑有问题)
- 有没有 main message 重复？两段在讲同一件事 → 合并
- 有没有 main message 缺失？claim 跳跃太大 → 加段
- 该删的删：reviewer 不关心、对 main message 不必要的细节

### 第 2 层：句子结构
- 长句拆短句（顶刊平均句长 20-25 词，>40 词必须拆）
- 被动改主动（除非强调对象）
- 句序：信息密度高的放句首
- 重复用词换同义词或改句式
- 检查时态/语态一致性

### 第 3 层：词汇/排版（最后做）
- AI 痕迹词汇替换 (参考 ai_artifacts.md)
- 数字格式统一 (参考 constitution.md#数字宪法)
- 标点排版 (en-dash vs hyphen，希腊字母 unicode)
- 缩写一致性
- 引用格式

**为什么顺序不能反**：你刚精心润色完一句话的措辞，第 1 层修改时把这段整段删了，前面的功夫白费。先大改后小改，效率高 5 倍以上。

---

## 三种 introduction 工作流

不同人有不同的 introduction 起手姿势，没有绝对优劣，看个人习惯：

### A — 从外往内（漏斗式，最经典）
- §1 大背景（领域/问题的 importance）
- §2 已知知识（前人做了什么）
- §3 gap（未解决的具体问题）
- §4 本研究（怎么填补 gap）

适合：常规研究论文，reviewer 期待这种结构最熟悉。

### B — 从内往外（倒漏斗式）
- §1 直接抛出本研究做了什么
- §2 退一步：为什么这个问题重要
- §3 前人做到哪一步
- §4 我们的 contribution 与前人区别

适合：某些 Nature 系子刊（尤其 Nat Commun 的 Brief Communications）；适合方法论 / tools 类论文；让 reviewer 立刻知道你做了什么。

### C — Story-driven（故事驱动）
- §1 用一个具体现象/observation 开场
- §2-3 这个现象引出的 broader question
- §4 我们的研究

适合：偏 narrative 的期刊（Cell 系、Sci Adv）；适合有令人 striking 的 phenomenon 作为开场的研究。

> 选哪个：默认 A。除非用户明确说投 Nat Commun 短文 / Cell / Sci Adv 这类风格化期刊，再考虑 B 或 C。

---

## 数字密度自检

写完任何段落后扫一遍这 4 个问题：

1. 这段有几个 claim？
2. 每个 claim 后面跟了几个数字 / 几个具体证据？
3. 数字够不够 specific？("highly significant" 改成 "P = 1.4 × 10⁻¹⁰") (避免：significantly / substantially / strongly / large / small / many / few + 没数字)
4. 数字能不能在 figure / table / supplementary 里追溯？

**典型反例**：
> "Cattle exhibit remarkable adaptation to diverse climates."
> 没有数字。"diverse" 是空话。改：
> "Cattle breeds in our dataset span 70° in latitude and 4,500 m in elevation, with mean annual temperatures ranging from −15 °C to 32 °C."

---

## 写完整篇后的全局检查

每章节单独自审过后，整稿写完时还要做 1 次**全局**检查：

| 维度 | 检查内容 |
|---|---|
| Title ↔ Abstract | Title 里的关键词是否都在 abstract 出现？反之亦然？|
| Abstract ↔ Conclusion | Abstract 最后一句和 Conclusion 最后一句是否说同一件事？|
| Abstract 数字 ↔ Results 数字 | n、P、effect size 在 abstract 和 results 一致 |
| Introduction §4 ↔ Methods | 引言承诺要做的事，methods 是不是都涵盖了 |
| Methods ↔ Results | results 报的每个数都能在 methods 找到对应的方法 |
| Results ↔ Discussion | discussion 讨论的每件事都能在 results 找到证据 |
| Figure caption ↔ 正文 | 正文里 cite 了 Figure 1 但 caption 里没有这个内容 = 错位 |
| 缩写 | 全文搜索每个缩写：第一次出现是否给了全称 |
| 引用 | 引文列表里每篇是否在正文出现过；正文每个 cite 是否在引文列表 |

---

## 卡壳时怎么办

写不下去 / 反复改一段都不满意时：

1. **先停下来重做 Frame**：很可能是 main message 不清楚才写不下去
2. **退一层做 Outline**：先列骨架，骨架对了句子自然
3. **跳到下一节**：introduction 卡住先写 methods，写完 methods 引言会清楚
4. **写中文 → 翻译**：中文表达更贴近思路时，先用中文写，再用 translation.md 工具流翻译

---

## 与他人协作时

* **共改时**：用 track changes / 评论模式，不要直接覆盖
* **每改一处给原因**：不解释 reviewer 不知道你为啥改
* **保留作者原意优先**：作者用 X 表达说明 X 是他想说的；你改成 Y 必须有元规则支持，不能凭"我觉得"
* **大改前先沟通**：删 1 整段、调整章节顺序前先和共作者商量
