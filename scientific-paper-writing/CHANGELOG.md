---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# CHANGELOG

记录 `life-sci-paper-writing` 元技能的版本演进、范式来源与覆盖度。

颗粒度按"基于哪些论文做了多大幅度更新"为单位，不按 commit 级。

---

## v2.0 — 2026-04-28（元技能架构重构）

### 重大变更

- **从"动物群体基因组学方向 specific"扩展到"生命科学组学通用"**。skill 名从 `animal-popgen-paper-writing` 改为 `life-sci-paper-writing`。
- **架构从单层文件夹改为双层 meta + tasks**：
  - `meta/`：元原则层（6 文件），横切所有任务
  - `tasks/`：任务层（15 文件），按用户在做什么分文件
  - 取消旧版扁平结构（14 文件平铺）
- **去方向绑定**：方向 specific 的内容（GEA、selection signature、imputation panel 等的具体范式）以"元规则的 illustration"形式散落在 task 文件里，**不再单独维护方向模块**。
- **路由机制升级**：SKILL.md 内嵌任务路由表 + 方向识别逻辑，不再外置 `_index.md`。
- **工具偏好独立**：用户工具偏好（Obsidian / LaTeX / grammarly 等）从 SKILL.md 主体抽出到 `meta/user_tools.md`，便于将来 fork。

### 新增文件

| 文件 | 状态 | 备注 |
|---|---|---|
| `meta/constitution.md` | 🟡 草稿 | 时态/语态/数字/命名/引用宪法 |
| `meta/workflow.md` | 🟡 草稿 | 写作四步法 + 修改三层法 |
| `meta/ai_artifacts.md` | 🟡 草稿 | AI 痕迹识别与去除 |
| `meta/reviewer_psychology.md` | 🟡 草稿 | reviewer 怎么读、3 秒决策、雷区清单 |
| `meta/over_claim_guard.md` | 🟡 草稿 | 保守表达句库 |
| `meta/user_tools.md` | 🟡 草稿 | 用户工具偏好（fork 时主要改这个） |
| `tasks/title.md` | 🟡 草稿 | |
| `tasks/abstract.md` | 🟡 草稿 | |
| `tasks/introduction.md` | 🟡 草稿 | |
| `tasks/methods.md` | 🟡 草稿 | |
| `tasks/results.md` | 🟡 草稿 | |
| `tasks/discussion.md` | 🟡 草稿 | |
| `tasks/figures_tables.md` | 🟡 草稿 | |
| `tasks/citation_management.md` | 🟡 草稿 | |
| `tasks/cover_letter.md` | 🟡 草稿 | |
| `tasks/rebuttal.md` | 🟡 草稿 | |
| `tasks/self_review.md` | 🟡 草稿 | |
| `tasks/style_polish.md` | 🟡 草稿 | |
| `tasks/translation.md` | 🟡 草稿 | |
| `tasks/ideation_topic.md` | 🟡 草稿 | |
| `tasks/outline.md` | 🟡 草稿 | |

状态图例：⚪ 未开始 · 🟡 草稿 · 🟢 完成 · 🔵 已审 · 🔴 需重写

---

## v1.0 — 2026-04（初版）

基于 14 篇动物群体基因组学顶刊论文范式提炼，单层架构。

### 范式来源

| 论文 | 方向 | 主要贡献于 |
|---|---|---|
| Chen et al. 2018 (Nat Commun) | 牛驯化与起源 | introduction.md / methods.md |
| Chen et al. 2023 | 牛景观/适应 | introduction.md / discussion.md |
| Lyu et al. 2024 | 牛群体基因组 | results.md / figures_tables.md |
| Xia et al. 2023 | 牛多组学整合 | methods.md |
| Xia et al. 2025 | 牛群体基因组 | results.md |
| Kim et al. 2020 | 牛 SV/泛基因组 | methods.md |
| Rossi et al. 2024 | 牛群体基因组 | results.md |
| Wu et al. 2018 | 山羊群体基因组 | introduction.md |
| Mei et al. 2018 | 绵羊群体基因组 | results.md |
| He et al. 2025 | 山羊基因组 | discussion.md |
| Si et al. 2024 | 多物种基因组 | methods.md |
| Du et al. 2024 | 群体基因组方法 | methods.md |
| Li et al. 2020 | 牛/羊系统发育 | introduction.md |
| Zhang et al. 2023 | 群体基因组 | results.md |

---

## 待补充范式来源（v2.x 后续吸收）

以下范式论文已在 v2.0 重构期间识别但**尚未系统提炼**，留作后续版本逐个吸收：

### 景观基因组学方向
| 论文 | 关键贡献 | 拟吸收到 |
|---|---|---|
| Sun et al. 2026 (iMeta) | 牛 GEA: GEMMA + LFMM + BayPass 三方法整合 | tasks/methods.md (作为方法披露完整性的 illustration) |
| Zhao et al. 2025 (GSE) | 鸡 GEA: 19 BIO + LFMM + Samβada + RDA | tasks/results.md (作为多方法 Venn 的 illustration) |
| Kebede et al. 2024 (BMC Genomics) | 鸡景观基因组学 + SDM + 4 环境梯度采样 | tasks/methods.md (作为采样策略的 illustration) |
| Chen J et al. 2023 (Heredity) | 裸大麦 pRDA 四模型 + variation partitioning | tasks/results.md (variation partitioning 写法) |
| Su et al. 2026 (JIPB) | 山荆子 T2T + GEA + genomic offset | tasks/discussion.md (climate-resilient breeding implication) |
| Teng et al. 2025 (Sci Adv) | 藏酋猴 popgen + landscape + offset + multi-niche | tasks/discussion.md (整合论文 framing) |
| Aguirre-Liguori et al. 2021 (Nat Ecol Evol) | FOLDS 框架 (gene flow + offsets + load + dispersal + SDMs) | meta/over_claim_guard.md (concept anchor) |
| Dauphin et al. 2023 (TREE) | 综述: GEA 统计方法 / 采样设计 / 环境数据局限 | meta/reviewer_psychology.md (该领域 reviewer 关心什么) |
| Grummer et al. 2019 (TREE) | 水生景观基因组学综述 | tasks/introduction.md (开篇钩子的 illustration) |
| Ferrero-Serrano & Assmann 2019 (Nat Commun) | Arabidopsis 1131 材料 + 204 环境变量 + CLIMtools | tasks/methods.md (大尺度环境变量整合的 illustration) |

### 其他方向（未来扩充）
| 方向 | 状态 |
|---|---|
| 单细胞/空间组学 | 暂无 |
| 古 DNA/aDNA | 暂无 |
| 表观组/甲基化 | 暂无 |
| 微生物宏基因组 | 暂无 |
| 系统发育/分子进化 | 暂无 |

---

## 维护原则

1. **每次重大更新写一个版本块**（v2.1, v2.2, ...），列清楚改了哪些文件、为什么改、范式来源是哪些论文。
2. **文件状态表**始终保持最新，方便一眼看出哪个文件还是 TODO、哪个已经过审。
3. **范式来源**追踪到论文级别，便于后续撤回某个范式时知道影响哪些文件。
4. **不删除历史版本块**——即使某个范式被推翻，也保留记录说明"为什么推翻"。
