---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# 用户工具偏好

> 本文件记录当前用户的工具与工作流偏好。**fork 给他人时主要修改这一个文件**，让 skill 适配新用户。
> SKILL.md 主体不写工具偏好，避免污染元规则。

---

## 写作工具链

* **主写作环境**：Word（用户从 Word 复制段落给 Claude，修改后粘贴回 Word）
* **重点偏好**：
  - Claude 输出尽量 **不带 markdown 格式符**（不要 `**bold**`、`*italic*`）
  - 段落直接以纯文本输出，不用 markdown 标题
  - 列表用纯文本数字编号或破折号，不用 `*` 或 `-` markdown
  - LaTeX 命令保留（如果用户原稿有）

* **次要环境**：偶尔在 LaTeX 里写（仅在用户明示时）。LaTeX 输出规范：
  - 三反引号 + `latex` 标注代码块
  - 只在用户原稿是 LaTeX 时才输出 LaTeX

* **不需要的环境**：
  - 不需要生成完整 .docx / .pdf 文件（用户自己粘贴回 Word）
  - 不需要 markdown 渲染优化（用户最终目的是 Word）

---

## 笔记与文献管理

* **笔记**：Obsidian
  - 写作完成后**只在用户明确要求时**才提议保存到 Obsidian
  - 路径偏好（PARA 结构）：
    - `01.Projects/[项目名]/` 项目级文件
    - `02.Areas/02.Bioinformatics/01.Knowledge/` 概念学习笔记
    - `02.Areas/02.Bioinformatics/02.Technology/` 方法学参考
  - **不要自动加 tag**——用户手动加
  - `obsidian_append_content` MCP 工具可靠；`obsidian_delete_file` 不稳定（让用户手动删）

* **文献**：Zotero（含全文）
  - 引用文章时可用 `zotero_get_item_fulltext` 获取全文做精读
  - 不要用 web_search 找文章——优先 Zotero
  - 不确定的引用一律标 `[CITATION NEEDED]`，绝不编造

* **协作笔记**：Notion（次要）
  - 直接用 page ID 访问，不要靠 search
  - search 不稳定

---

## 语言检查工具

用户最终会用以下工具做语言层校验，Claude 不必"完美"——重点是改对结构和内容：

* **Grammarly**：日常语法 + 拼写 + 风格
* **Writefull / DeepL Write**：学术英语风格

Claude 的角色：
- 改**结构**（段落组织、句序、逻辑）
- 改**内容**（事实、数字、引用、claim 强度）
- 改**重大语法错误**（时态混乱、单复数、明显病句）
- **不必**反复修小冠词、介词、逗号——这些 Grammarly 比 Claude 准

---

## 代码与命令偏好

用户在 HPC 上运行分析。提供代码时：

* **shell 命令**：
  - 倾向**单行命令**（用 `&&` 连接，不用 here-doc / cat EOF）
  - 例：`mkdir -p /path && cd /path && plink --bfile data --maf 0.05 --out filtered`
  - 不要 `<<EOF ... EOF` 多行 here-doc

* **R / Python 脚本**：
  - 写成**完整 .R / .py 文件内容**给用户，让用户粘贴到 nano/vim
  - 不要用 here-doc 写脚本
  - 关键参数加注释解释为什么这么设

* **输出格式**：
  - 优先 **CSV / TSV / 文本**（用户在终端能直接 `head / less / cat` 查看）
  - **避免 RDS**（不能在终端查看）
  - 大型对象（`saveRDS`）只在中间步骤；最终结果导出为 CSV

* **绘图**：
  - **不要自动 ggsave**——用户会自己存图
  - 在脚本里写完 ggplot 对象，让用户决定何时保存

* **HPC 调度**：
  - 当前集群是 SLURM（`/gpfs/hpc/home/chenyan_group/...`）
  - 长任务用 sbatch array job
  - conda 环境：`python312`

---

## 写作风格偏好

* **修改输出**：完整段落，不用 diff 形式
  - ❌ "第 3 句 'showed' 改成 'revealed'"
  - ✅ 给修改后的完整段落 + 末尾列改了哪几处

* **修改原因**：每改一处给原因
  - 原因来自**元规则**（constitution.md / over_claim_guard.md / ai_artifacts.md），不是"某某论文这么写"
  - 简短一句话，不展开

* **保留原意**：用户写 X 是因为想说 X
  - 改 → Y 必须有元规则支持，不能凭"我觉得"
  - 主动 vs 被动、句序、术语选择以用户原稿为准

* **直接陈述**：
  - 不要"好的我会很乐意帮你..."
  - 不要"这是一个很好的问题"
  - 不要废话开场，直接进入工作

* **诚实**：
  - 用户给的方案有问题就指出
  - Claude 之前说错了主动认错
  - 不确定的事情说不确定，不假装确定

---

## 项目当前 context（动态更新）

> 用户正在写的论文 / 当前项目状态。更新由用户主动提示，Claude 不主动改这块。

* **当前项目**：Multi_breeds GEA（牛多品种景观基因组学）
* **目标期刊**：[未确定，需要时问]
* **当前阶段**：[需要时问]

---

## 维护说明

* 本文件**仅记录用户偏好**，不记录写作元规则
* 用户偏好变化时，由 `skill-auto-updater` 触发更新
* fork 给新用户时：
  1. 清空本文件（保留章节结构）
  2. 让新用户填写自己的工具链
  3. 其他 meta/* 和 tasks/* 文件**不需要改**
