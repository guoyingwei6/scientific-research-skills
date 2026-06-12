---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Task: Rebuttal / Response to reviewers

> Rebuttal 要回答的问题：**reviewer 的每个意见是否得到回应 + editor 是否觉得我们 acted in good faith**。
> 服务的 editor + reviewer 决策：accept / minor / major / reject。

## ⚓ 元层锚点

- `meta/over_claim_guard.md`：rebuttal 不是辩论赛，保守表达
- `meta/reviewer_psychology.md`：reviewer 提出 critique 时通常真心觉得有问题
- `meta/constitution.md`：reviewer 引用要精确

---

## 任务本质

Rebuttal 不是为了**赢辩论**，是为了**让 reviewer 满意**。reviewer 满意的两条路径：
1. **改论文**：80% 的 critique 都能通过修改回应（这是首选）
2. **解释清楚**：剩下的需要 polite argue

写得好的标志：reviewer 重新审稿时**找不到自己原意见没被认真对待的地方**。

---

## 通用工作流

### Frame
- 这个 critique 是**误解** / **不同看法** / **真问题**？
  - 误解 → 在论文里说清楚（你写得不够清楚 = 你的责任）
  - 不同看法 → polite argue + 新数据 / 引用支持
  - 真问题 → 改论文 + 谢谢 reviewer

- 这条 critique 改起来**成本多高**？
  - 改 1 段 → 必改
  - 加 1 个分析 → 看价值
  - 重做实验 / 重测序 → 才考虑 argue

### Outline
每个 reviewer 的回应整体结构：

```
[General response to Reviewer #N]
1 段感谢 + 总览修改

[Comment 1.1: 引用 reviewer 原文]
[Response 1.1: 我们的回应]
[Change 1.1: 我们改了哪里 + 修改后的段落 / 新增内容]

[Comment 1.2: ...]
...
```

### Draft
**逐条**回应。即使 reviewer 给的"列举式 critique"，每条单独回应。

### Self-review
- 每条 critique 都被回应了吗？
- 我有没有 hidden 跳过的 critique？
- 语气是否不卑不亢？

---

## 三种 critique × 三种回应模板

### Type A: Critique 成立 → 改论文
**最常见，60-70% 的 critique**。

模板：
```
We thank Reviewer #N for raising this important point. We have now [具体修改：added X analysis / clarified Y in the text / corrected Z]. The revised text reads (page X, line Y):

"[修改后的段落]"

This addresses the concern by [explanation]. We believe this strengthens the manuscript.
```

### Type B: Critique 是误解 → 改论文 + 解释
**次常见，20-30%**。reviewer 误读 = 你写得不够清楚 = 你的责任。

模板：
```
We thank Reviewer #N for this comment. We agree the original text was unclear. To clarify: [简短重述 reviewer 的误解]. In fact, [事实是什么]. We have revised the text to make this explicit (page X, line Y):

"[修改后的段落]"
```

**不要**说 "Reviewer # N misunderstood" / "As we clearly stated" / "This is mentioned in section X"——这些是攻击式语气。

### Type C: Critique 不成立 → polite argue
**最少，5-10%**。需要给证据 / 引用支持。

模板：
```
We thank Reviewer #N for raising this point. We respectfully [agree / partly agree, but would like to clarify why we made this choice / believe an alternative interpretation is supported]:

[1-2 句解释 + 证据]

[引用支持：published evidence / new analysis / supplementary]

That said, we acknowledge this is an area where [reasonable concern]. We have added a sentence in Discussion (page X, line Y) to acknowledge this consideration:

"[新加的句子]"
```

注意：**polite argue 的同时通常仍要在论文里加一句承认 reviewer 的考虑**——给 reviewer 台阶。

---

## 元层雷区（高发陷阱）

### 1. 跳过 critique
最严重的错误。reviewer 重审时第一时间扫**他自己说过的话**，找他的话有没有被回应。

→ **每条 critique 都要单独标号回应**。即使 reviewer 列了 10 条琐碎的 typo，10 条都要回。

### 2. 防御式语气
❌ "As we clearly stated in section 3, ..."  
❌ "Reviewer's comment is incorrect because ..."  
❌ "This is a misreading of our analysis."

→ 改成感谢 + 改进。"We thank Reviewer for this comment. To make this point clearer, we have ..."

### 3. 太软弱
❌ "We will revise this in the next version"（reviewer 现在就要看修改）  
✅ "We have revised the text to clarify this point. The revised text reads: ..."

回应即修改。不要"承诺以后改"。

### 4. 不引用具体页/行
- 每个修改要给"Page X, Line Y" 或 "Section X.X"
- reviewer 不会自己翻找
- 修改后的段落直接贴在 response 里（黄色高亮在新稿里 + 完整段落贴在 response 里）

### 5. 一次性大改没说清楚
- 如果做了大改（重排章节 / 新分析），在 General response 段开头**总览**
- 然后每条具体 critique 再细化

### 6. 实验做不到的还硬辩
- reviewer 说"做 X 实验验证"——做不到的话 polite 解释为什么
- 不要不回应（隐式拒绝）
- 替代方案：补 supplementary analysis / 引用前人验证 / 在 Discussion 写为 limitation

### 7. 表格 vs. 散文
- 长 rebuttal 建议用**表格化**：左 critique，右 response
- 短 rebuttal 散文更友好
- 看 critique 数量：< 10 条散文 OK；≥ 10 条考虑表格

### 8. Reviewer 互相矛盾时
- Reviewer 1 说加 X，Reviewer 2 说删 X → 不要选择性回应
- 在 General response 段说明，然后给折衷方案
- "We acknowledge that Reviewer 1 and Reviewer 2 had differing views on X. We have chosen to [Y solution] because [reason]. We hope this addresses both concerns."

---

## Rebuttal 文档结构

```
Response to Reviewers
[Manuscript ID, Title]

Dear Editor [and Reviewers],

We thank the Editor and three Reviewers for their thoughtful and constructive comments. We have carefully revised the manuscript in response to all comments. The major revisions include: [3-5 条总览]. Below we provide point-by-point responses to each comment.

Sincerely,
[通讯作者]

==========
Editor's Comments:
[Comment 0.1: ...]
[Response 0.1: ...]

==========
Reviewer #1
[General response 1: 总览]

Comment 1.1: "[引用 reviewer 原文]"
Response 1.1: [回应 + 修改]
Change 1.1: [page X, line Y; 贴段落]

Comment 1.2: ...
...

==========
Reviewer #2
[General response 2]
...

==========
Reviewer #3
[General response 3]
...
```

---

## 修改稿配套

rebuttal 需要配 2 个版本的 manuscript：

1. **Tracked changes**：所有修改留痕（Word track changes / LaTeX changes 包）
2. **Clean version**：accepted 修改后的版本

部分期刊只要其中之一；多数顶刊两个都要。

---

## 跨方向 illustration

> 按方案 B,挑差异化的：

### 景观基因组学 / GEA
常见 critique：
- "RDA 没控制 population structure" → 解释 / 加 pRDA 分析
- "环境变量代理性问题" → 加 limitation / 引用支持
- "候选 SNP 不是 causal" → 改 "candidate" 措辞 / 加 limitation
- "未来气候情景的不确定性" → 加多情景 sensitivity

### 选择信号
常见 critique：
- "demographic confounding 没控制" → 加 neutral simulation / 引用 demographic-corrected method
- "单一统计量" → 加多统计量交集 / 解释为什么够
- "功能验证缺失" → 加 limitation / 在 Discussion 提 future direction

### Imputation panel
常见 critique：
- "panel diversity 不够" → 比较多 cohort / 加 limitation
- "rare variant 精度低" → 给分 MAF 的 r²
- "vs. 商业 panel 比较" → 加 benchmark vs. 1KGP / TOPMed 等

---

## 自查清单（投递前）

- [ ] 每条 critique 都单独标号回应
- [ ] 每条 response 给具体修改 + page/line
- [ ] 修改后的段落贴在 response 内
- [ ] 语气不卑不亢（没"as we clearly stated"）
- [ ] 不能做的实验给替代方案 + acknowledged
- [ ] reviewer 互相矛盾时有 General response 说明
- [ ] tracked changes + clean version 都准备好
- [ ] data / code 如有更新也同步开放
- [ ] 邀请 reviewer 重新审稿时找不到被忽略的 critique

---

## 时间安排

- 拿到 critique → 先**冷静 24-48 小时**再开始写
  - 第一反应往往是"这 reviewer 不懂"，冷静后通常发现有道理
- Major revision 通常 给 1-3 个月，不要拖到最后一周
- 写完 rebuttal 让**共作者通读** + 时间允许的话给一个**没参与原研究的同事**读
