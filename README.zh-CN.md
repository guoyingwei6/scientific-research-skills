---
created: 2026-06-12 18:18
updated: 2026-06-12 18:18
---
[English](README.md)

# Scientific Research Skills

一组可复用的科研工作流 agent skills，重点覆盖文献深度阅读、出版级科研作图、生命科学论文写作和专利技术交底书生成。

## 包含的 skills

| Skill | 用途 |
| --- | --- |
| `literature-mentor` | 基于 Zotero 全文的导师式文献深度解读，强调先整体理解，再逐图拆解。 |
| `scientific-figure-making` | 使用 Python 或 R 制作出版级科研图，覆盖群体遗传学图型和多面板排版。 |
| `scientific-paper-writing` | 面向生命科学和组学论文的写作支持，覆盖题目、摘要、引言、方法、结果、讨论、rebuttal、cover letter 和润色等任务。 |
| `patent-disclosure-desktop` | 面向中国专利挖掘和技术交底书撰写的桌面 agent 工作流。 |

## 仓库结构

每个一级目录都是一个独立的 skill package。大多数 skill 都包含一个 `SKILL.md` 入口文件，部分 skill 还包含 `references/` 支撑材料。

```text
scientific-research-skills/
├── literature-mentor/
├── scientific-figure-making/
├── scientific-paper-writing/
└── patent-disclosure-desktop/
```

## 来源与演化

### `literature-mentor`

`literature-mentor` 是从零创建的，并不是从某个外部 GitHub 仓库复制而来。它的第一版来自一次需求讨论：agent 应该如何通过 Zotero MCP 辅助读论文，尽可能获取全文，像研究生导师一样解释文章，并带着用户逐图理解论文。

原始设计聚焦生命科学和群体遗传学论文的导师式阅读流程：先给出文章整体概览，再逐图解读。每张图的理解都综合三类信息源：图例、正文中对应的 Results 或 Methods 段落，以及相关表格或补充材料。由于 Zotero MCP 不一定能直接提取 PDF 图片，这个 skill 会显式检查文字信息是否足够；如果视觉信息不足，会要求用户上传图片，避免基于不完整信息强行解读。

| 参考来源 | 吸收或改编的内容 |
| --- | --- |
| 初版无外部仓库 | 初始流程来自用户自己的需求：Zotero 支持的文献阅读、导师式解释、逐图停顿、结合牛基因组学和群体遗传学背景进行批判性分析。 |
| `littleZ05/PaperLocus` | 后续吸收了理念层面的改进：方法/工具型论文与科学发现型论文的叙事类型判断、文献定位总结，以及更清晰地区分 claim、causal inference 和 extrapolation。 |

评估 `PaperLocus` 后，核心流程并没有被替换。三信息源综合框架、逐图停顿机制和信息充分性检查都被保留下来，因为它们更适合深度读文献，而不是只做泛泛的论文定位。因此，这个 skill 本质上仍然是原创的，只是在后期从 `PaperLocus` 吸收了一层概念增强。

它的实际强项在于阅读节奏：不是一次性丢出整篇论文摘要就结束，而是先建立文章地图，再在每张主要图后停下来，让用户追问方法或概念问题，确认理解后再继续。最后会输出一个三段式凝练总结：问题是啥、解法是啥、发现个啥。同时，它保持三维阅读视角：学习方法、批判证据、提取可迁移到用户自己基因组学项目中的启发。

### `scientific-paper-writing`

`scientific-paper-writing` 不是从通用 academic writing prompt 复制来的。它最早是一个针对动物群体基因组学的领域化写作 skill，原名 `animal-popgen-paper-writing`。第一版围绕用户自己的研究场景构建：牛基因组学、群体遗传学、品种鉴定、基因组品种成分、选择、渗入、适应、imputation panel、结构变异、泛基因组和生命科学组学论文。

v1 版本从 14 篇动物群体基因组学顶刊论文中提炼范式，例子覆盖牛驯化、景观基因组学、多组学、结构变异、泛基因组、山羊、绵羊、系统发育和群体基因组学方法。后来 skill 改名为 `life-sci-paper-writing`，再改为 `scientific-paper-writing`。名称变宽了，但核心设计没有变：从生命科学研究的证据逻辑出发，而不是套一个通用作文模板。

后续这个 skill 选择性吸收了多个公开或社区 skill 仓库和写作资源的优点。目标不是把所有内容合并进来，而是只借鉴真正能提升审稿可读性、claim discipline 和 manuscript workflow 的机制。

| 参考来源 | 吸收或改编的内容 |
| --- | --- |
| 顶尖机构写作和作图资源 | 在 `references/meta/ai_artifacts.md` 中增强去 AI 味和正向写作指导，包括更具体的不确定性表达、节奏变化、Discussion 中的立场表达，以及适当的一人称判断句。 |
| `Yuan1z0825/nature-skills` | 启发了 rebuttal 和润色流程的改进：Comment ID tracking、action tags、Hourglass check，以及 `style_polish.md` 中的 section-move 参考表。 |
| `Imbad0202/academic-research-skills` | 启发了 `rebuttal.md` 中的 Step 0 审稿意见解码流程，以及 `self_review.md` 中的 Devil's Advocate self-check。 |
| `Galaxy-Dawn/claude-scholar` | 启发了 `outline.md` 中的一句话论证检查，以及 `self_review.md` 中的 Claim Audit。 |

也有一些参考被明确评估但没有采纳。例如，`lishix520/academic-paper-skills` 更偏哲学领域和 Claude Code 架构，不适合生命科学论文写作。其他仓库里的 0-100 打分 rubric、多 agent review team、PPTX 汇报生成、通用 Data Availability 模块等，也因为会让 skill 变重但不能改善核心写作流程而没有引入。

所以最终的 `scientific-paper-writing` 是一个混合体：先根据具体生命科学研究领域重新创建，再选择性吸收其他 skill 系统中的好机制。它和通用 academic writing skill 的主要区别在于，它把论文写作看作证据路由和 reviewer cognition 问题：标题、摘要、结果段、discussion claim、figure caption、cover letter 和 rebuttal 都应该降低审稿人的理解成本，同时保守地表达数据真正能支持的结论。

在内部结构上，它是一个 meta skill，而不是单一 prompt。`SKILL.md` 会把 title、abstract、introduction、methods、results、discussion、cover letter、rebuttal、self-review、style polish、translation 和 outline 等任务路由到对应的 task reference 文件。横向规则放在 `references/meta/` 下面，包括写作 workflow、引用和命名规范、over-claim 控制、reviewer psychology 和 AI-artifact cleanup。这比一个扁平的大 prompt 更容易维护和扩展。

### `scientific-figure-making`

`scientific-figure-making` 的来源不同。它的第一版基于 `ChenLiu-1996/figures4papers` 中的 `scientific-figure-making/` skill 目录，继承了初始结构：`SKILL.md` 以及 `api.md`、`design-theory.md`、`common-patterns.md`、`demos.md`、`tutorials.md` 等 reference 文件。

原始版本已经是一个可用的出版级作图 skill，但后来进一步针对生命科学和群体遗传学场景重塑。当前版本不再只是一个 matplotlib 风格助手，而是一个 figure-planning workflow：先确定科学 claim，再确定证据层级，然后选择 backend 和图型。

| 参考来源 | 吸收或改编的内容 |
| --- | --- |
| `ChenLiu-1996/figures4papers` | 作为起始实现和文件结构来源，提供原始 publication-figure references 和 demo-oriented workflow。 |
| `Yuan1z0825/nature-skills` / `nature-figure` | 启发了一次大改：加入 R backend 支持，包括 `ggplot2`、`patchwork`、`ComplexHeatmap`；引入 Figure Contract 哲学；新增 `figure-contract.md` 和 `r-backend.md`；重写 `SKILL.md`、`design-theory.md`、`api.md`、`common-patterns.md`；并加入 PCA scatter、ADMIXTURE bars、XP-EHH regional plot 等群体遗传学图型。 |
| `AcademicForge/scientific-visualization` | 启发了定向增强：Okabe-Ito 色盲安全配色、灰度测试规则、期刊列宽参考，以及 `references/submission-checklist.md` 中的通用检查、群体遗传学专项检查和常见坑。 |

一些想法被评估后没有采纳。`AcademicForge/scientific-visualization` 中大量内联代码片段占用上下文但没有增加太多决策框架，因此没有引入。Flexoki 配色也被评估并拒绝，因为它更适合 UI/代码审美，不适合作为色盲安全的科学作图配色。

最终版本把 `figures4papers` 的实用作图模式和更强的科学设计层结合起来。它强调的不是“画一张好看的图”，而是先问：这张图要支撑什么 claim？哪个 panel 承担主要证据？Python 还是 R 更合适？导出和印刷约束是什么？是否符合群体遗传学领域的图形规范？

它也明确限定了自己不该处理什么：interactive dashboards、没有出版目标的探索性 EDA 图、Illustrator/Figma-first infographic 都不在范围内。这样可以让它保持专注：制作可复现、能经受同行评审和印刷导出要求的 publication-grade figures。

### `patent-disclosure-desktop`

`patent-disclosure-desktop` 有一个非常明确的外部来源：`handsomestWei/patent-disclosure-skill`。它是从原版面向 Claude Code 的专利交底书工作流移植而来，并适配到 Claude Desktop macOS 环境。这个 credit 也保留在 `SKILL.md` 里。

核心 8 步流程继承自原版：信息收集、项目扫描、专利点挖掘、用户确认、联网查新、大纲预览、交底书撰写和自检。主要变化是运行环境适配，而不是专利写作逻辑本身的改变。

| 原 Claude Code 版本 | 桌面适配版本 |
| --- | --- |
| 使用 `cnipa_epub_search.py` 和 Playwright 查新 | 使用内置 web search 检索 `epub.cnipa.gov.cn`、Google Patents 等来源。 |
| Claude Code 文件和 shell 工具 | Desktop Commander 风格的文件读写，并带明确降级逻辑。 |
| Python 脚本进行 Office 文档转换 | 三级降级：优先 Word MCP，其次本地脚本，最后 Markdown-only 输出。 |
| 通过本地命令行工具渲染 Mermaid | 默认输出 Mermaid code block；如环境支持，可选用 `npx mmdc` 渲染。 |
| 通过 helper scripts 记录迭代日志 | 使用更适合桌面环境的手工追加/更新流程。 |

这个 skill 没有混入其他外部 skill 仓库。它的价值主要在于移植：保留原始专利交底书结构，同时让这个流程能在不具备 Claude Code 完整工具链的桌面 agent 环境中使用。

桌面版本还增加了实际写作中需要的 guardrails：不要求用户说出“迭代”这个词，也能识别继续修改交底书的意图；修订稿会另存为新的时间戳文件，不覆盖旧稿；保留修订记录；交付前在内部检查 claim 一致性、现有技术区别、术语统一、Mermaid 引用和脱敏情况。

## 安装

把需要的 skill 目录安装或复制到你的 agent runtime 使用的 skill 文件夹中。如果运行时支持从 GitHub 安装，可以根据运行时约定安装整个仓库根目录，或安装某个指定子目录。

## 说明

- 这些 skills 尽可能写成可跨 agent 环境迁移的形式。
- 部分工作流会提到 Zotero、web search、Python、R 或桌面文件读取工具等可选能力。skill 文本中包含工具不可用时的降级逻辑。
- 不要把私人凭据、本地 secret 或 token 提交到这个仓库。

