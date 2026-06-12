---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Task: Style polish / 通用润色

> Style polish 要回答的问题：**用户给一段话，能不能让它读起来像该领域研究者本人写的科技论文**。
> 服务的场景：用户随手给一段，没有明确任务（"看看这段写得怎么样"）。

## ⚓ 元层锚点

- `meta/constitution.md`：所有硬规则
- `meta/ai_artifacts.md`：AI 痕迹三层识别 + 修改流程
- `meta/over_claim_guard.md`：过度声称
- `meta/workflow.md`：修改三层法（论证逻辑 → 句子结构 → 词汇排版）

---

## 任务本质

Style polish 是**最常见的 fallback 任务**——用户语义模糊时（"看看这段"、"帮我润色"）默认走这里。

写得好的标志：用户**接受 80% 以上的修改**，且修改原因都是**元规则支持**而不是"我觉得"。

---

## 通用工作流

### Step 0：风格锚点（可选，但优先）

如果用户贴了**自己以前发表的段落**作为参照样本，先提取其风格特征再润色：

1. **句长节奏**：短句多 vs. 长句嵌套？段内是否有节奏变化？
2. **被动/主动比例**：倾向主动陈述还是被动结构？
3. **数字密度**：claim 后立即跟数字，还是先陈述再补数字？
4. **transition 风格**：显式（"Next, we..."）还是隐式（直接进入下一个发现）？
5. **术语偏好**：有无特定域内词汇的用法习惯？

提取后，用这些特征约束 Step 3 的词汇选择 —— **优先匹配用户自己的风格，而不是"标准学术风格"**。

> 用户没有提供样本 → 跳过此步，按元规则处理。

---

### Step 1：识别这段属于哪一节
即使用户没说，从内容判断：
- 有"We performed... using software vX"+ 过去时 → Methods
- 有"Three clusters were observed..." + 数字 → Results
- 有"These findings suggest..." → Discussion
- 等等

→ 拿对应 `tasks/[section].md` 的 self-review 清单作为checking 项

### Step 2：按修改三层法过

**第 1 层**：论证逻辑
- 这段 main message 是什么？1 句能说清吗？
- 有没有 sub-claim 跳跃？
- 这段是否其实该拆成 2 段 / 该合并到上一段？

**第 2 层**：句子结构
- 长句 > 40 词的拆
- 被动改主动（除非强调对象）
- 时态混乱整理
- 信息密度高的句子放段首

**第 3 层**：词汇 / 排版
- AI 词清理（参考 ai_artifacts.md 词汇黑名单）
- over-claim 替换（参考 over_claim_guard.md）
- 数字格式（参考 constitution.md 数字宪法）
- 缩写 / 物种学名 / 软件版本号

### Step 3：输出

按 `meta/user_tools.md` 的偏好输出：
- 完整修改后段落（不用 diff）
- 末尾列改了哪几处（≤ 5 项），每项 1 句话原因
- 原因来自元规则，不是"某某论文这么写"

---

## 输出模板

```
[修改后的完整段落]

主要修改：
1. [改动 X] — [元规则原因]
2. [改动 Y] — [元规则原因]
3. ...
```

例：

> [修改后段落]
>
> 主要修改：
> 1. 把 "showcases" 改为 "demonstrates" — AI 黑名单词
> 2. 把 "significantly higher" 后加上 "(P = 1.4 × 10⁻⁴)" — 数字密度宪法
> 3. 把 "drives" 改为 "is associated with" — over-claim 替换（相关 vs. 因果）
> 4. "BWA" 后加版本号占位 [v?.?.?] — 让用户填
> 5. 把 "PCA shows" 改 "PCA showed" — Methods 时态宪法

---

## 元层雷区（润色时最常见错误）

### 1. 过度修改
- 用户原稿用 X 表达 = 用户想说 X
- 改成 Y 必须有元规则支持
- 不要凭"我觉得这样更好"改

### 2. 改坏作者意图
- 句序 / 主动被动 / 术语 = 作者风格选择，**保留**
- 除非违反元规则（时态错 / over-claim / 数字缺）

### 3. 替换式润色
- 不要把整段重写
- 用户给段是为了**改**而不是**重写**
- 如果觉得需要重写，明确说"这段建议结构层重组，是否要重写？"，给用户选

### 4. 删掉用户的关键 claim
- 用户写"strong selection"——你改 "consistent with selection"
- 这是 over-claim 替换，OK
- 但**不要直接删 claim**（"有些 selection happening"），保留 claim 但弱化措辞

### 5. 不解释原因
- 每改一处必须给原因（按 user_tools.md 偏好）
- 原因来自**元规则**（constitution / over_claim_guard / ai_artifacts），不是"某某论文这么写"

### 6. 改 Grammarly 的活
- 用户最终会用 Grammarly / Writefull
- 不必反复修小冠词（a/an/the）/ 介词 / 逗号
- Claude 的角色是改**结构 + 内容 + 重大语法**，不是 micro-edit

### 7. 一次改太多导致用户不知道改了什么
- 单段一次改 ≤ 5 处
- 改超过 5 处 → 给用户两个版本（"轻度修改" + "重度修改"）让选

---

## 跨方向 illustration

> 润色时的 over-claim 在不同方向有 specific 雷区：

### 景观基因组学
- "candidate SNP / variant" 不要写"causal" / "adaptive SNP" 
- "associated with [climate variable]" 不要"driven by climate"
- "putative role in adaptation" 不要"determines adaptation"

### 选择信号
- "signature consistent with positive selection" 不要"under positive selection"（除非有功能验证）
- "putative selective sweep" 不要"selective sweep"（除非有 EHH+频谱+demographic 都过）

### 群体结构
- "shares the highest ancestry" 不要 "originated from"
- "is consistent with migration A→B" 不要 "migrated from A to B"

### 多组学整合
- "candidate regulatory variant" 不要 "causal regulatory variant"
- "shows eQTL signal" 不要 "regulates expression"

---

## "看看这段写得怎么样"的处理流程

最模糊的任务。处理顺序：

1. **判断是哪个章节** —— 从内容线索判断（不询问用户）
2. **快速过 self-review checklist** —— 用对应 task 文件的清单
3. **找 top 3 问题** —— 不是所有问题都列，只挑最关键的 3 个
4. **给修改 + 解释** —— 完整段落 + ≤ 5 项原因列表
5. **结束**：不要"还需要我再改吗 / 还有其他问题吗" 这种废话

> 用户偏好里有 "focus explicitly on what I ask for"，润色完一段就停，不主动揽活。

---

## 自查清单（输出前）

- [ ] 修改原因都来自元规则（不是"我觉得"）？
- [ ] 没改坏用户原意？
- [ ] 改动数 ≤ 5 个？
- [ ] 输出的是完整段落（不是 diff）？
- [ ] 没去 micro-edit Grammarly 的活？
- [ ] 没说"还要不要再改"？
- [ ] 如果用户提供了风格样本，改动是否匹配其风格特征（而不是通用学术风格）？
