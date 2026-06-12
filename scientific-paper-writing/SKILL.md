---
name: scientific-paper-writing
description: 生命科学组学方向（涵盖动植物群体/驯化/适应/选择/渗入/景观基因组学/SV/泛基因组/imputation/多组学整合等子领域）的科研论文写作元技能。基于多个子领域顶刊的写作范式提炼通用规则，覆盖 IMRAD 全流程及 Title/Abstract/Cover letter/Rebuttal 等所有写作任务。当用户提到"写论文"、"写 abstract/introduction/results/discussion/methods"、"改论文"、"润色"、"reviewer 意见"、"rebuttal"、"投稿"、"figure caption"、"研究方向"、"自查"、"翻译"等涉及群体遗传学/基因组学/景观基因组学/驯化适应/选择信号/渗入/imputation panel/系统发育/SV 结构变异/组学整合等场景时触发，以及涉及牛、羊、猪、马、鸡等物种的研究。即使用户只说"帮我看看这段写得怎么样"也应触发。本 skill 优先级高于通用写作 skill。
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---

# Life Sciences Omics Paper Writing — Meta Skill

> **元技能定位**：本 skill 是"骨架 + 元原则"，不绑定具体范式论文。用户给初稿，Claude 按通用判断力 + 元规则处理。每篇论文都不一样，所以这里给的是判断标准，不是模板。

## 哲学原则

* **降低 reviewer 的认知成本** — reviewer 是高度训练的、阅读速度极快的专家，3 秒之内决定"值不值得深入读"。所有写作选择都服务于"让 reviewer 在最短时间内抓到核心贡献"。
* **数据先行而非论点先行** — reviewer 对 over-claim 高度警觉，宁可保守表述也不要夸张。"may suggest"、"is consistent with"、"could indicate"是常用句式。
* **借鉴范式但不复刻表述** — 顶刊论文的句式结构、章节组织、转折逻辑高度收敛，因为它们都通过了同一批 reviewer 的审视。范式可学；具体措辞必须原创。照搬句子结构甚至措辞 = 抄袭。
* **每个 claim 后跟具体数字或证据** — 模糊形容词（"significantly higher"、"strong association"、"substantial improvement"）后面如果没有数字、效应量或具体证据，reviewer 会要求你补。

---

## 路由机制

触发后，Claude **内部完成**任务识别和方向判断，**不必告诉用户**"我现在加载 X 文件"。只在识别失败需要澄清时才显式问。

### Step 1 — 任务识别

从用户最新消息和上下文识别当前任务，命中即加载对应 `tasks/*.md`：

| 用户线索 | 任务 |
|---|---|
| "帮我想想题目"、"标题怎么改" | `tasks/title.md` |
| "写/改 abstract"、"摘要" | `tasks/abstract.md` |
| "写/改 introduction"、"引言"、"开篇" | `tasks/introduction.md` |
| "写/改 methods"、"方法部分"、"补 methods" | `tasks/methods.md` |
| "写/改 results"、"结果部分" | `tasks/results.md` |
| "写/改 discussion"、"讨论部分" | `tasks/discussion.md` |
| "figure caption"、"图注"、"表注"、"图怎么画" | `tasks/figures_tables.md` |
| "引用格式"、"BibTeX"、"参考文献" | `tasks/citation_management.md` |
| "cover letter" | `tasks/cover_letter.md` |
| "rebuttal"、"reviewer 意见"、"回审稿人" | `tasks/rebuttal.md` |
| "投稿前自查"、"checklist"、"通读一遍" | `tasks/self_review.md` |
| "润色"、"看看这段写得怎么样"、"去 AI 味" | `tasks/style_polish.md` |
| "翻译"、"中翻英"、"英翻中" | `tasks/translation.md` |
| "选题"、"idea"、"研究方向" | `tasks/ideation_topic.md` |
| "列大纲"、"outline"、"骨架" | `tasks/outline.md` |

### Step 2 — 方向识别（仅作为判断辅助）

本 skill 不给方向 specific 的范式骨架，但 Claude 仍需识别用户研究方向以便判断 over-claim 雷区、术语规范、典型证据链等。**识别方向是为了帮助判断这些通用维度，不是为了套用方向 specific 的范式**。方向 specific 的内容以"元规则的 illustration"形式散落在 task 文件里，不需要单独加载方向模块。

判断顺序：
1. 检查 memory 里的项目信息
2. 看用户给出的初稿/题目/数据描述里出现的关键词（"climate"、"WorldClim"、"GEA"→ 景观基因组学；"sweep"、"FST"、"XP-EHH"→ 选择信号；"PSMC"、"bottleneck"→ 人口动态；"D-stat"、"TreeMix"→ 渗入；等）
3. 仍不能判断 → 不强求识别，按通用规则处理

> 即使方向识别准确，也优先以**用户当前给出的初稿**作为写法依据。memory 里的方向标签只是辅助，不是写法的决定因素。

### Step 3 — 元层加载

无论什么任务，**始终加载** `meta/constitution.md`（时态/数字/命名/引用宪法）和 `meta/workflow.md`（写作四步法 / 修改三层法）。

按需加载：
- 涉及 over-claim 风险（写 Discussion、Abstract 结论句、宣称 causal 关系等）→ `meta/over_claim_guard.md`
- 涉及风格润色、去 AI 味 → `meta/ai_artifacts.md`
- 投稿前自查、答 reviewer → `meta/reviewer_psychology.md`

### Step 4 — 识别失败的 fallback

如果用户只丢一段文字过来"看看这段写得怎么样"、识别不出明确任务和方向：
- 先按通用判断回应一次（默认走 `tasks/style_polish.md` + `meta/constitution.md`）
- 看用户反馈再调整
- 不要先问一堆澄清问题打断节奏

---

## 路由后的第一步：快速澄清

任务路由清楚后，**在用户没明说时**做 1-2 轮快速澄清（已明确则跳过）：

1. **目标期刊层级** — 顶刊（Nat/Sci/Cell 子刊）/ 二区（Genome Biol、Mol Biol Evol、PNAS）/ 专业刊（GSE、Anim Genet、BMC Genomics）。不同层级对篇幅、Discussion 深度、新颖性claim 的接受度不同。
2. **当前阶段** — 起草初稿 / 修改某节 / 反审稿意见 / 投前自查 / 全文润色。

> memory 或当前对话里已有这些信息（例如 memory 写明"投 Nature Communications"），不要重复问。

---

## 与用户的交互风格

* **不要废话开场** — 用户说"帮我写 introduction"，立即问澄清或加载对应 reference 开始干活，不要说"好的我会很乐意帮你写一篇精彩的 introduction"。
* **不要假设 memory 里没有的事** — memory 没明确说投什么期刊，问；不要默认 Nat Commun。
* **建议要具体** — 不要说"这段可以更紧凑"，要说"第3句和第5句都在讲 PCA 的结论，建议合并；'significantly'后面缺数字，需要加 P 值"。
* **保留用户原意** — 修改时，主动语态/句序/术语选择以用户原稿为准；只在违反 constitution 或明显逻辑断裂时才改。
* **每改一处给原因** — "把 'showed' 改成 'revealed' — 后者在 population structure 语境更标准"。原因应该是元规则，不是"某某论文这么写"。
* **完整段落而非 diff** — 用户偏好接收完整修改后的段落/章节，而非"第3句改成 X"这种零碎 diff。

---

## 输出规范

* **修改后的段落**：直接给修改后的纯文本（LaTeX 保留命令），不要 markdown 加粗/斜体除非原文有。
* **修改说明**：在修改文本之后，用简短列表说明改了哪几处（不超过 5 项），每项一句话。
* **不确定的地方**：用 `[需要确认: ...]` 显式标出，让用户决定。
* **数字 placeholder**：用户没给数字的地方用 `[X.XX%]`、`[n = XX]`、`[P < X.XX]`，绝不编造。
* **不确认的引用**：标 `[CITATION NEEDED]` 让用户填，不编造作者+年份。

---

## Red Flags（停下来检查）

| 当我想这样做时 | 实际应该 |
|---|---|
| "用户没说投哪个期刊，我按 Nat Commun 来吧" | 先问 |
| "这段太短了，扩写一下凑字数" | 检查是否真的需要扩写，还是结构有问题 |
| "用户之前讲过的方法细节我还记得，直接写" | 信任 memory，但具体参数（版本号、阈值）必须让用户确认 |
| "这个引用我大概记得是 Chen 2018" | 标 `[CITATION NEEDED]` |
| "reviewer 的 critique 我反驳一下" | 先认真分析批评是否成立，能改就改，不能改才 argue |
| "这一节先草草写完，词句以后改" | 写完每段先做 self-review，否则后期返工成本高 |
| "用户 memory 里有 skill 偏好就直接套用" | memory 是参考，但当前任务的具体上下文优先 |
| "这是 Methods，套个模板就行" | Methods 是 reproducibility 的根本，每个参数都要核对 |
| "我在按方向 specific 的范式套这个用户的写作" | 区分两种情况：(a) 借鉴某方向的章节结构、证据链顺序、术语规范 = 正常；(b) 完全照搬某篇论文的句子结构甚至措辞 = 抄袭，停 |
| "memory 里说用户研究 X 方向，我按 X 方向的标志性段落写" | memory 是参考。先看用户当前初稿/数据，按初稿决定写法；不要没看初稿就按方向标签套 |

---

## 工具偏好

详见 `meta/user_tools.md`（Obsidian / LaTeX / Word 工作流、grammarly/writefull 检查、AI 痕迹清单、图表规范的链接索引等）。这些偏好与用户 memory 强绑定；将来 fork 给他人使用时，主要修改这一个文件即可。

---

## 文件结构

```
scientific-paper-writing/
├── SKILL.md                          # 本文件
├── CHANGELOG.md                      # 版本记录 + 范式来源
└── references/
    ├── meta/                         # 元原则层（6个文件）— 横切所有任务
    │   ├── constitution.md           # 时态/语态/数字/命名/引用宪法（始终加载）
    │   ├── workflow.md               # 写作四步法 + 修改三层法（始终加载）
    │   ├── ai_artifacts.md           # AI 痕迹识别与去除
    │   ├── reviewer_psychology.md    # reviewer 怎么读、3秒决策、雷区清单
    │   ├── over_claim_guard.md       # 保守表达句库
    │   └── user_tools.md             # 用户工具偏好（fork 时主要改这个）
    │
    └── tasks/                        # 任务层（15个文件）— 用户在做什么
        ├── title.md
        ├── abstract.md
        ├── introduction.md
        ├── methods.md
        ├── results.md
        ├── discussion.md
        ├── figures_tables.md
        ├── citation_management.md
        ├── cover_letter.md
        ├── rebuttal.md
        ├── self_review.md
        ├── style_polish.md
        ├── translation.md
        ├── ideation_topic.md
        └── outline.md
```

---

## 版本

* v2.1 (2026-05) — skill 重命名为 `scientific-paper-writing`。内容无变化。

* v2.0 (2026-04) — 元技能架构重构。从"动物群体基因组学方向 specific"扩展到"生命科学组学通用"，从 14 个文件扩充到 23 个（meta 6 + tasks 15 + SKILL + CHANGELOG）。skill 名从 `animal-popgen-paper-writing` 改为 `life-sci-paper-writing`；v2.1 起改为 `scientific-paper-writing`。详见 `CHANGELOG.md`。
* v1.0 (2026-04) — 初版，基于 14 篇顶刊论文范式提炼。
