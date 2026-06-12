---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# 保守表达 Guard

> 生命科学顶刊 reviewer 对 over-claim 高度警觉。**写作时主动用保守表达**，不等 reviewer 来 push。
> 本文件不是教用户"写得软弱无力"——而是教用户**精确表述证据强度**，强证据强表达，弱证据弱表达。

---

## 程度递减词梯子

按确定性从高到低：

```
demonstrate / show / prove
  ↓
reveal / identify / find
  ↓
indicate / suggest
  ↓
support / be consistent with / be in line with
  ↓
may indicate / could suggest / appear to / seem to
  ↓
hint at / point toward / not exclude the possibility
```

**使用原则**：
- 直接证据 + 因果实验：用 demonstrate / prove
- 强相关 + 多方法验证：用 reveal / identify
- 显著相关但单方法：用 indicate / suggest
- 趋势性 + 与前人一致：用 support / consistent with
- 边缘显著或预测性：用 may / could
- 极弱信号或假说：用 hint / point toward

---

## 因果替代

科技论文 over-claim 第一大坑是**把相关说成因果**。

| ❌ over-claim | ✅ 保守 |
|---|---|
| caused by | associated with / linked to |
| drives / driving | contributes to / is associated with |
| underlies / underpins | may underlie / is consistent with a role in |
| controls / regulates | is associated with / may regulate |
| determines | influences / shapes |
| responsible for | implicated in / associated with |
| results in | is followed by / co-occurs with |
| due to | possibly due to / consistent with |

**例外**：以下情况可以说因果：
* 实验干预（基因敲除、CRISPR 编辑、药物处理）+ 表型变化
* 孟德尔随机化 / 工具变量分析
* 强遗传连锁 + 多代验证
* 已知机制（已发表）+ 你的数据再次验证

否则全部走相关性表述。

---

## 唯一性 / 首创性替代

第二大坑是**夸大首创性**——这是 reviewer 会立即去 PubMed 搜的事。

| ❌ over-claim | ✅ 保守 |
|---|---|
| First | First **to our knowledge** / Among the first |
| First time | First systematic / First comprehensive |
| Novel | Recent / Not yet reported in [specific subsystem] |
| Unique | One of the few / Distinct from |
| Unprecedented | Substantial / Notable |
| Pioneering | Early / Initial |
| Previously unknown | Not extensively characterized |

**红线**：除非你 100% 确定真的是 first（搜过 PubMed + Google Scholar + bioRxiv），否则一律加 "to our knowledge"。

---

## 普适性替代

第三大坑：**研究了 1 个 system，claim 适用于所有 system**。

| ❌ over-claim | ✅ 保守 |
|---|---|
| Always / Never | Generally / Rarely |
| All [systems] | The [systems] examined |
| In all cases | In the cases studied |
| Universally | Across the breeds analyzed |
| Any [population] | The populations sampled |
| Without exception | With few exceptions / Generally |

**写法**：限定 scope 到你实际研究的范围。"In our 85 cattle breeds spanning Eurasia and Africa, ..."  比 "In cattle, ..." 更准确。

---

## 效应大小替代

第四大坑：**用 strong / large 而不给数字**。

| ❌ over-claim | ✅ 保守 |
|---|---|
| Strong selection | r² = 0.X / FST = 0.Y |
| Large effect | β = X.XX (95% CI: ...) |
| Significant improvement | Improved by X% |
| Substantial increase | Increased from X to Y (P = ...) |
| Major contribution | Accounted for X% of variance |
| Strong association | P = X.XX × 10⁻XX, OR = X.XX |
| Highly significant | P < 1 × 10⁻¹⁰ |
| Robust | Consistent across [N] independent runs / Stable to [perturbation] |

**写法**：模糊形容词后必跟具体数字。如果数字本身就支撑了"strong"，就不需要"strong"——数字自己说话。

---

## 时间与因果先后替代

第五大坑：**当代数据反推古代因果**。

| ❌ over-claim | ✅ 保守 |
|---|---|
| Selection X drove the divergence | The divergence is consistent with selection X |
| Adaptation occurred at X kya | Coalescent estimates suggest divergence ~X kya (95% HPD: ...) |
| Originated in [region] | Most likely originated in [region], based on [evidence] |
| Migrated from A to B | The data are consistent with migration from A to B |

**注意**：demographic inference 是估计，不是事实。报告时给 95% HPD / CI，**不要给单点估计**当确定值。

---

## 应用前景替代

第六大坑：**讲一堆下游应用但本文没 demo**。

| ❌ over-claim | ✅ 保守 |
|---|---|
| Will revolutionize X | Has potential implications for X |
| Will be widely used | May be useful for / Could inform |
| Provides a definitive answer | Adds to the growing evidence |
| Solves the problem of X | Addresses one aspect of X |
| Translatable to clinical practice | Suggests directions for [future] clinical research |
| Ready for breeding application | Provides candidate targets for breeding programs |

**红线**：discussion 里讲 implication 时，区分"我们 demo 了" vs "未来可以做" 。前者用现在时强表述；后者用 may / could 弱表述。

---

## 比较替代

第七大坑：**和前人比较时贬低别人**。

| ❌ over-claim | ✅ 保守 |
|---|---|
| Previous studies failed to ... | Previous studies were limited by ... |
| In contrast to flawed reports | Building on earlier work / Extending recent reports |
| Outperforms all previous methods | Compares favorably with [specific methods] / Improves upon [specific aspects] |
| Resolves the long-standing controversy | Provides additional evidence for [side] of the ongoing debate |

**写法**：批评前人时**就事论事**——他们的方法在 X 方面有局限，不是他们的研究不好。

---

## 高频"陷阱句式"清单

下列句式在生命科学论文里**频繁触发 reviewer over-claim 警报**。每条都给替代：

| 陷阱句式 | 安全替代 |
|---|---|
| "Our results demonstrate X." (X 是因果) | "Our results are consistent with X." |
| "This is the first study to ..." | "To our knowledge, this is among the first systematic ..." |
| "X is highly conserved." | "X is conserved across [the N species examined]." |
| "X plays a critical role in Y." | "X has been implicated in Y / X may contribute to Y." |
| "These findings have important implications for ..." | "These findings provide candidate [genes/loci/markers] for further study in ..." |
| "X is a key driver of Y." | "X is associated with Y." |
| "Robustly identified" | "Identified by [N] independent methods / replicated across [N] datasets" |
| "Strongly support" | "Are consistent with / Provide evidence in line with" |

---

## 子方向 illustration

按你确认的方案 B，方向 specific 内容以"元规则的 illustration"形式出现。下面这些是高频陷阱：

### 景观基因组学 / GEA
- ❌ "Causal SNP" / "Adaptive SNP" → ✅ "Candidate SNP" / "Putatively adaptive SNP" / "SNP associated with [environmental variable]"
- ❌ "X drives climate adaptation" → ✅ "X is associated with [climatic variable], suggesting a putative role in climate adaptation"
- ❌ "Future climate change will drive maladaptation" → ✅ "Genomic offset analysis suggests these populations may face higher risk of maladaptation under future scenarios (assuming current GEA captures relevant adaptation)"
- ❌ "Adaptation occurred during [historical period]" → ✅ "The geographic pattern of [allele frequency] is consistent with adaptation during [period]"

### 选择信号
- ❌ "Under positive selection" + 单一方法 → ✅ "Showing signatures consistent with positive selection (FST > X, iHS > Y)"
- ❌ "Recent selective sweep" → ✅ "Putative recent selective sweep based on [statistic + threshold]"
- ❌ "Caused by domestication" → ✅ "Likely associated with domestication, although alternative explanations including [drift / linked selection / demographic effects] cannot be excluded"

### 群体结构 / 系统地理学
- ❌ "X breed originated from Y" → ✅ "X breed shares the highest ancestry component with Y in our ADMIXTURE analysis"
- ❌ "Migrated from A to B" → ✅ "The data are consistent with migration from A to B; we cannot exclude [alternative model]"

### 渗入 / 杂交
- ❌ "Adaptive introgression" + 单一证据 → ✅ "Introgression with [allele frequency / haplotype evidence], the adaptive significance of which requires functional validation"
- ❌ "Hybridization with Y caused trait Z" → ✅ "Trait Z is associated with introgression from Y, consistent with adaptive introgression"

### Imputation panel
- ❌ "Most accurate panel for [species]" → ✅ "Achieves [concordance / r²] of X, comparable with [or better than] existing panels for [specific MAF / coverage range]"
- ❌ "Universal panel for [species]" → ✅ "Suitable for [specified populations / coverage]"

### 多组学整合
- ❌ "X gene regulates Y" → ✅ "X gene shows [eQTL / accessible chromatin / expression] consistent with regulation of Y"
- ❌ "Causal regulatory variant" → ✅ "Candidate regulatory variant supported by [N] orthogonal lines of evidence"

---

## 反向校准：何时**不该**保守

保守不等于无力。下列情况**应该用强表达**：

* **直接实验验证的因果关系**：你做了 KO + 表型 = 用 demonstrate
* **多方法 / 多数据集 / 多物种重复验证**：用 robustly / reliably (后跟具体证据)
* **已发表机制 + 你的数据再现**：可以说 confirms / validates
* **强统计信号 + 大效应**：用 strong + 数字（数字够强时强表达 OK）

> 软弱写作 = 该强表达时不敢；保守写作 = 弱证据不强说。区别很大。

---

## 自查清单（写完段落后扫一遍）

- [ ] 用了 "first" / "novel" / "unique" 吗？是不是真的搜过文献？没搜就加 "to our knowledge"
- [ ] 用了 "drive" / "cause" / "underlie" 吗？有没有干预实验支持？没有就改 "associated with"
- [ ] 用了 "all" / "always" / "universally" 吗？scope 限定到你实际研究范围了吗？
- [ ] 用了 "significantly" / "strongly" / "substantially" 吗？后面跟数字了吗？
- [ ] 用了 "robust" / "comprehensive" 吗？真的做了 robustness check / 真的覆盖完整吗？
- [ ] 讲了 implication for X / Y / Z 吗？这些 implication 你 demo 了吗？没 demo 的加 "may" / "could"
- [ ] 比较前人时贬低了吗？改成"就事论事"

---

## 与 ai_artifacts 的边界

参考 ai_artifacts.md 末尾的"与 over_claim_guard 的边界"。简要：
- ai_artifacts 管"像不像 AI"
- 本文件管"有没有 over-state"
- 冲突时**优先本文件**
