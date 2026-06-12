---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Task: Ideation / 选题与研究方向

> Ideation 要回答的问题：**这个 idea 值不值得花 6-12 个月做 + 投出去能不能 publishable**。
> 服务的场景：用户在选题阶段、提 grant 阶段、想新方向。

## ⚓ 元层锚点

- `meta/over_claim_guard.md`：选题时不要 over-promise
- `meta/reviewer_psychology.md`：选题阶段就要想"reviewer 会怎么看"
- `meta/user_tools.md`：用户**主动说想 brainstorm 时**才走这个 task；不主动揽活

---

## 任务本质

Ideation 不是"想点什么都行",是**评估 idea 的可行性 + 投稿性**。

写得好的标志：3-5 个 idea 摆出来,用户能基于 evidence 选 1-2 个深做。

---

## 触发条件

按 `meta/user_tools.md` 偏好:**用户明确说要 brainstorm 才走**。常见触发语：
- "帮我想想..." / "帮我头脑风暴..." / "我有个想法..."
- "下一个研究方向..." / "最近想做..."
- "能不能从 X 数据挖出新 idea"

不主动启动 ideation——用户给初稿时优先走具体写作 task。

---

## 通用工作流

### Step 1：澄清出发点
用户的 idea 通常**不完整**。澄清：
- 现有什么数据 / 资源？
- 想解决什么科学问题（vs. 想发哪个期刊）？
- 时间窗口（半年 / 一年 / 长期）？
- 是 standalone 研究还是 series 中的下一步？

### Step 2：找 idea 的 hook
每个好 idea 必须有一个**hook**:
- 新数据（前人没有的物种 / 规模 / 测序类型）
- 新方法（前人方法 + 你的改进 / 整合）
- 新视角（已有数据用前人没用的角度看）
- 新对比（跨物种 / 跨地区 / 跨时间）

没 hook 的 idea = "我也来做一个 GWAS",不值得做。

### Step 3：评估 publishability
对每个候选 idea 问：
- 假设我们做出来,take-home 用 1 句话怎么说？
- 这个 take-home 值得发哪个层级期刊？
- 已发表的 X 篇相关研究,我们的 contribution 是什么？

### Step 4：评估可行性
- 数据/资源够吗？
- 时间/计算够吗？
- 关键风险？(eg "如果某个变量没显著怎么办")

### Step 5：给用户 3-5 个候选,让选

---

## 评估 idea 的 6 维度

| 维度 | 高质量 idea | 低质量 idea |
|---|---|---|
| **Novelty** | 新数据 / 新方法 / 新角度 | "再做一遍 X" |
| **Importance** | broader implication | 自娱自乐 |
| **Feasibility** | 数据 / 方法都到位 | "如果未来能拿到 X 数据" |
| **Differentiation** | 跟已发表论文有清晰边界 | 跟 X 团队即将发的论文撞车 |
| **Risk** | 关键变量有 backup 计划 | 单点失败论文就废 |
| **Timing** | 现在做正合适 | "5 年前应该做"或"再等等更好" |

每个 idea 给 6 个维度打分（高 / 中 / 低）

---

## 选题阶段不要做的事

### 1. 不要被"reviewer 会要 X"绑架
- 选题阶段不应过度优化"投稿 friendliness"
- 真正驱动力应是**科学问题** + **数据/方法的真实价值**
- "reviewer 会满意" 留到写作阶段

### 2. 不要追热点
- 当前热点在你研究做出来时可能已过气（生命科学领域 2-3 年周期）
- 追热点只在数据已经到位 + 能赶 timing 的情况下才合理
- 长期看,**深度 > 热度**

### 3. 不要 over-promise
- "这个 idea 能改变 X 领域" → 大概率高估
- 保守估计 take-home,超额完成更安全

### 4. 不要忽略前人
- 选题前**深度文献调研**——尤其近 2 年
- 与已发表 X 论文的边界要清楚
- 同 group 的近期 preprint 也要查（有人在做同样的事）

### 5. 不要同时上 5 个项目
- 选题阶段往往同时有多个 idea
- 选 1-2 个**最值得做的**,其他放 backlog

---

## 跨方向 idea 模式

> 按方案 B,挑差异化的：

### 景观基因组学 / GEA 方向 idea 类型
- **新物种** GEA：之前没做过的物种
- **更大尺度**：cross-continent / global / 时间序列（古今对比）
- **整合多 GEA 方法**：3+ 方法 + 候选位点 follow-up（已经在做）
- **结合 SDM + GEA + genomic offset**：未来气候情景
- **跨物种 convergent climate adaptation**

### 选择信号方向
- **新方法 + 已有数据**:DAF-based 新统计量 vs. 传统 iHS
- **跨多群体 convergent sweep**
- **古 DNA 验证现代 sweep 时间窗**

### Imputation panel 方向
- **多样性扩展**:已有 panel 加非洲 / 极端环境品种
- **跨物种 panel benchmark**:不同物种 panel 的精度差异
- **低 coverage + GLIMPSE**:针对超低 coverage 的 panel 优化

### SV / 泛基因组方向
- **某物种第一个 pangenome**
- **SV-trait 大规模 GWAS**:前人 SNP-only 漏掉的信号
- **Long-read + short-read 整合 SV calling**

### 多组学整合方向
- **新 tissue / cell type specific eQTL**
- **跨物种 cis-regulatory conservation**
- **变异 → 调控 → 表型**完整证据链 follow-up

---

## Idea 表达的标准模板

输出 idea 时,**每个 idea 用一段固定结构**说清：

```
Idea N: [一句话 idea]

Hook: [novelty 是什么]
Take-home if successful: [1 句话发现]
Target journal level: [估计层级]
Required data/method: [需要什么]
Key risk: [最大风险]
6-dimension score: Novelty/Importance/Feasibility/Differentiation/Risk/Timing
```

例：

> **Idea 3: 整合 SV + SNP-based GEA 揭示牛气候适应的结构变异基础**
>
> Hook: 已有牛 GEA 都基于 SNP；SV 在适应中的作用未系统刻画
> Take-home if successful: 我们识别 N 个 climate-associated SV，揭示了 SNP-only GEA 漏掉的结构变异机制
> Target journal level: 顶级专业刊（GR / GBE）或 Nature Communications
> Required data/method: long-read assembly 多个体（pangenome 数据可用？）+ SV 检测 + 与现有 SNP-based 候选位点对比
> Key risk: SV 检测精度不足；很多物种长读长数据有限
> Score: Novelty 高 / Importance 中 / Feasibility 中 / Differentiation 高 / Risk 中 / Timing 高

---

## 自查清单（输出 idea 前）

- [ ] 给了 3-5 个 idea（不是 1 个,也不是 10 个）？
- [ ] 每个 idea 有明确 hook？
- [ ] 每个 idea 有 1 句 take-home？
- [ ] 每个 idea 估计了目标期刊层级？
- [ ] 每个 idea 列了关键风险？
- [ ] 6 维度打分了？
- [ ] 没 over-promise（"这会 revolutionize..."）？
- [ ] 没追热点（除非 timing + 数据真的到位）？
- [ ] 调研了相关近 2 年文献（明确说哪些是已做 vs. 没做）？

---

## 后续：从 idea 到论文

用户选定 1-2 个 idea 后,进入：
- 数据 / 方法的可行性详细评估
- 写 outline → tasks/outline.md
- 写正文 → tasks/introduction.md / methods.md / 等
