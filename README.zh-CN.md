[English](README.md)

# Scientific Research Skills

这是一组面向科研工作的 agent skills：深度读文献、写生命科学论文、制作出版级科研图，以及撰写中文专利技术交底书。

这些 skills 不是一次性问答 prompt，而是工作流。每个 skill 都定义了任务步骤、质量检查、工具不可用时的降级方式，以及对应科研场景里的判断标准，让 agent 更像一个研究助理，而不是普通聊天机器人。

## Skills 一览

| Skill | 最适合做什么 | 主要输出 |
| --- | --- | --- |
| `literature-mentor` | 深度理解论文，尤其是逐图读懂文章 | 文章概览、逐图解释、批判性分析、研究启发 |
| `scientific-paper-writing` | 写作或修改生命科学和组学论文 | 标题、摘要、IMRAD 章节、rebuttal、cover letter、润色、自查 |
| `scientific-figure-making` | 制作出版级科研图 | 图形设计方案、Python/R 作图代码、可投稿导出的图形规范 |
| `patent-disclosure-desktop` | 挖掘专利点并撰写中文技术交底书 | 专利点列表、现有技术对比、交底书草稿、修订记录 |

## `literature-mentor`

### 简介

导师式文献阅读 skill。它通过 Zotero 或网络来源获取论文，然后像研究生导师一样带用户读文章：先看整篇文章的科学故事，再逐图拆解，最后总结方法学价值、局限和研究启发。

### 可以帮你做什么

- 根据题目、DOI 或 Zotero library 搜索论文。
- 阅读前先判断论文叙事类型：方法/工具型，还是科学发现型。
- 给出结构化概览：研究问题、背景缺口、核心创新、数据规模、技术路线，以及关键方法设计背后的逻辑。
- 一张图一张图解释，而不是只给一个浅层摘要。
- 解读图时综合三类信息源：图例、正文对应 Results/Methods 段落、表格或补充材料。
- 判断文字信息是否足够；如果必须看图片，会请用户上传图，而不是强行猜。
- 用三级证据标注区分：直接证据、可信推断、超出原文的推测。
- 讨论方法、局限、统计选择、过度解释风险，以及和牛基因组学/群体遗传学的关系。
- 最后输出凝练总结：问题是啥、解法是啥、发现个啥，以及这篇文章在领域里的位置。
- 主动提出研究生成性追问，帮助挖掘隐含假设、边界条件、失效场景，以及能否迁移到用户自己的数据。

### 典型用法

```text
使用 literature-mentor 逐图解读这篇论文的 DOI：...
```

```text
请像导师一样带我读 Zotero 里的这篇论文，重点看方法和可迁移的研究思路。
```

### 与类似文献阅读 skill 的区别

| 对比对象 | 区别 |
| --- | --- |
| 通用论文总结器 | 不停留在摘要层面；会逐图停顿，让用户追问方法和概念。 |
| PDF chat 工具 | 会显式判断图例和正文是否足够；需要视觉证据时会要求上传图片。 |
| 类似 `littleZ05/PaperLocus` 的论文定位工具 | 借鉴了叙事类型、文献定位和 claim/inference 分离，但保留更深入的逐图阅读框架。 |

### 参考来源

初版是围绕用户自己的工作流从零创建的：Zotero 支持的文献阅读、导师式解释、逐图停顿，以及结合群体遗传学背景的批判性分析。后续 `littleZ05/PaperLocus` 启发了叙事类型判断、文献定位总结，以及 claim、causal inference、extrapolation 的区分。

## `scientific-paper-writing`

### 简介

生命科学论文写作 meta skill。覆盖从选题、标题、摘要、引言、方法、结果、讨论，到图表说明、引用管理、cover letter、rebuttal、投稿前自查、翻译和润色的完整论文工作流。

它特别适合生命科学和组学方向，尤其是动物基因组学、群体遗传学、驯化、适应、选择、渗入、景观基因组学、结构变异、泛基因组、imputation panel 和多组学整合。

### 可以帮你做什么

- 按证据优先逻辑起草或修改论文段落。
- 改标题、摘要、引言、方法、结果、讨论和图注。
- 润色段落，同时保留用户原意，减少 AI 味。
- 检查 claim 是否有数字、效应量、引用或明确证据支撑。
- 根据 reviewer psychology 准备 rebuttal 和 cover letter。
- 投稿前进行 manuscript self-review。
- 中英互译，同时保留科学表达的准确性。
- 根据任务路由到 `references/tasks/`，并用 `references/meta/` 中的横向规则约束输出。

### 典型用法

```text
使用 scientific-paper-writing 修改这段群体基因组学论文的 Results。
```

```text
请根据这些结果写一段保守的 Discussion，避免 over-claim。
```

```text
请用这个 skill 起草对 reviewer comment 2 的回复。
```

### 与类似论文写作 skill 的区别

| 对比对象 | 区别 |
| --- | --- |
| 通用 academic-writing prompt | 更关注生命科学证据链、reviewer cognition、保守 claim 和具体数据支撑。 |
| 普通润色工具 | 不只是让句子更顺；还会检查逻辑、证据、术语、数字和 over-claim 风险。 |
| 重型 multi-agent review 系统 | 保持轻量，通过任务路由处理问题，不默认引入打分 rubric 或大型 review team。 |
| 偏哲学/人文学术写作 skill | 围绕 IMRAD、数据驱动 claim、方法可复现性、审稿回复和组学论文规范设计。 |

### 参考来源

最早版本是领域化的 `animal-popgen-paper-writing`，v1 从 14 篇动物群体基因组学论文中提炼规则，后续扩展为 `life-sci-paper-writing`，最后成为 `scientific-paper-writing`。

| 参考来源 | 吸收的思想 |
| --- | --- |
| 顶尖机构写作和作图资源 | 更强的去 AI 味指导、不确定性表达、节奏变化和 Discussion 立场控制。 |
| `Yuan1z0825/nature-skills` | Comment ID、rebuttal action tags、Hourglass check 和 section-move 参考。 |
| `Imbad0202/academic-research-skills` | 审稿意见解码和 Devil's Advocate self-check。 |
| `Galaxy-Dawn/claude-scholar` | 一句话论证检查和 Claim Audit。 |

评估但没有采纳：`lishix520/academic-paper-skills`，因为它和生命科学论文写作不够匹配；大型 numeric rubric、多 agent review team、PPTX 汇报生成和通用 Data Availability 模块，因为它们会增加复杂度但不能改善核心写作流程。

## `scientific-figure-making`

### 简介

出版级科研作图 skill。它不是直接开始写代码，而是先确定科学结论，再确定证据层级、图型、backend、统计标注和导出约束。

它支持 Python 和 R。Python 适合 matplotlib/seaborn 风格图；R 适合 `ggplot2`、`patchwork`、`ComplexHeatmap`、`ggtree` 或更符合群体遗传学惯例的图。

### 可以帮你做什么

- 围绕一个核心结论设计图。
- 根据证据层级选择图型，而不是凭习惯画图。
- 生成 grouped bars、trend lines、scatter plots、heatmaps、多面板图、Manhattan plots、XP-EHH regional plots、FST/pi heatmaps、PCA plots、ADMIXTURE/STRUCTURE bars、带 metadata 的系统发育树等。
- 判断 Python 还是 R 更合适。
- 应用出版级字体、配色、排版、图例、矢量导出和 DPI 规则。
- 使用色盲安全配色和灰度检查。
- 根据投稿要求和常见坑检查图。

### 典型用法

```text
使用 scientific-figure-making 为这个结果设计一张多面板科研图。
```

```text
帮我画 PCA 图，但先帮我明确核心结论和证据层级。
```

```text
请为这个带注释的矩阵设计一个 R ComplexHeatmap 作图流程。
```

### 与类似可视化 skill 的区别

| 对比对象 | 区别 |
| --- | --- |
| 通用作图助手 | 先做 Figure Contract：结论、证据层级、图型、backend、统计和导出约束。 |
| 探索性数据分析图 | 聚焦可投稿的出版级图，而不是临时 EDA 截图。 |
| Web 可视化工具 | 明确排除 Plotly、Altair、Bokeh、dashboard 和 web-first interactive graphics。 |
| Illustrator/Figma-first 信息图流程 | 聚焦可复现、代码驱动的科研图。 |

### 参考来源

原始结构来自 `ChenLiu-1996/figures4papers`，尤其是其中 `scientific-figure-making/` 目录和 reference 文件布局。后续吸收了：

| 参考来源 | 吸收的思想 |
| --- | --- |
| `ChenLiu-1996/figures4papers` | 起始实现、出版级作图 reference、demo 和作图模式。 |
| `Yuan1z0825/nature-skills` / `nature-figure` | R backend、Figure Contract、`figure-contract.md`、`r-backend.md` 和群体遗传学图型。 |
| `AcademicForge/scientific-visualization` | Okabe-Ito 配色、灰度检查、期刊列宽参考和 submission checklist。 |

评估但没有采纳：`AcademicForge/scientific-visualization` 中大量内联代码片段，因为它们占用上下文但没有增加决策结构；Flexoki 配色，因为它更适合 UI/代码审美，不适合作为科学图的色盲安全配色。

## `patent-disclosure-desktop`

### 简介

面向 Claude Desktop macOS 的中文专利挖掘和技术交底书 skill。它可以把项目材料、代码、设计文档或 PPT 转成候选专利点，并进一步生成结构化技术交底书草稿。

### 可以帮你做什么

- 收集技术主题、项目材料、发明人、权利人、输出路径和脱敏要求。
- 扫描设计文档、代码、Word 文件、PPT 或用户粘贴的文字。
- 提炼候选专利点，并让用户确认、合并或拆分。
- 通过 CNIPA 公布公告和 Google Patents 做现有技术检索。
- 撰写中文技术交底书，包括背景技术、发明内容、技术方案、实施例、附图说明和权利要求雏形。
- 需要时生成 Mermaid 系统图和流程图。
- 在工具可用时保存 `.md`，并尝试生成 `.docx`。
- 识别迭代修改意图，修订已有草稿，保存新时间戳版本，避免覆盖旧稿。

### 典型用法

```text
使用 patent-disclosure-desktop 从这个项目目录中挖掘专利点。
```

```text
帮我为这个算法起草一份中文技术交底书。
```

```text
请修改已有交底书的第 3 章，并补充一个实施例。
```

### 与类似专利写作流程的区别

| 对比对象 | 区别 |
| --- | --- |
| 通用专利写作 prompt | 包含项目扫描、专利点挖掘、查新、交底书撰写、自检和迭代处理。 |
| 只适用于 Claude Code 的专利流程 | 已适配 Claude Desktop macOS，支持 Desktop Commander 和降级逻辑。 |
| 手工交底书模板 | 在撰写前先分析技术问题、技术效果、现有技术区别和权利要求雏形。 |

### 参考来源

这个 skill 有一个明确来源：`handsomestWei/patent-disclosure-skill`。当前版本是把原本面向 Claude Code 的工作流移植到 Claude Desktop macOS。

| 原 Claude Code 版本 | 桌面适配版本 |
| --- | --- |
| 使用 `cnipa_epub_search.py` 和 Playwright | 使用内置 web search 检索 CNIPA 和 Google Patents。 |
| Claude Code `Read` / `Write` / `Bash` | Desktop Commander 风格的文件读写和 shell 降级。 |
| Python Office 转换脚本 | 优先 Word MCP，其次本地脚本，最终降级为 Markdown-only。 |
| 通过命令行工具渲染 Mermaid | 默认输出 Mermaid code block，可选 `npx mmdc` 渲染。 |
| helper script 记录迭代日志 | 桌面环境友好的手工追加/更新流程。 |

没有混入其他外部 skill 仓库。

## 安装

### 方式一：安装整个仓库

克隆仓库，然后把需要的 skill 目录复制到你的 agent runtime 使用的 skill 文件夹。

```bash
git clone https://github.com/guoyingwei6/scientific-research-skills.git
```

复制一个或多个 skill：

```bash
cp -R scientific-research-skills/literature-mentor ~/.codex/skills/
cp -R scientific-research-skills/scientific-paper-writing ~/.codex/skills/
cp -R scientific-research-skills/scientific-figure-making ~/.codex/skills/
cp -R scientific-research-skills/patent-disclosure-desktop ~/.codex/skills/
```

请把 `~/.codex/skills/` 替换成你所用 agent 的实际目录。

常见位置：

| Runtime | 常见 skill 目录 |
| --- | --- |
| Codex | `~/.codex/skills/` |
| Claude Code | `~/.claude/skills/` |
| Claude Desktop | Project Knowledge 或 user skill directory，取决于你的设置 |
| Gemini | `~/.gemini/skills/` |

安装后重启 agent。

### 方式二：只安装单个 skill

如果你的 agent 支持从 GitHub 子目录安装，可以只安装需要的目录，例如：

```text
https://github.com/guoyingwei6/scientific-research-skills/tree/main/scientific-paper-writing
```

## 让 agent 帮你安装

你也可以把下面的指令发给具备终端或文件访问权限的 agent：

```text
Install the scientific-paper-writing skill from:
https://github.com/guoyingwei6/scientific-research-skills

Copy the scientific-paper-writing directory into your local skills directory, then verify that the skill is available after restart.
```

```text
Install all skills from:
https://github.com/guoyingwei6/scientific-research-skills

Copy literature-mentor, scientific-paper-writing, scientific-figure-making, and patent-disclosure-desktop into the current agent's skills directory. Do not copy unrelated files. Verify the installation.
```

Claude Desktop 可以这样说：

```text
Use the skill folders from this repository as Project Knowledge:
https://github.com/guoyingwei6/scientific-research-skills

Install or import only the skill directories I need, and keep their SKILL.md files as the entrypoints.
```
