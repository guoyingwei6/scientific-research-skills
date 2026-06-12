---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# AI 痕迹识别与去除

> 当前期刊编辑和 reviewer 对 AI 生成文本的识别能力越来越强（部分期刊已用 AI detector）。**写作时主动避免 AI 痕迹**，比成稿后亡羊补牢容易得多。
> 本文件不是为了应付 AI detector，而是为了写出**像研究者本人写的科技论文**。
>
> ⚠️ **黑名单是快照，不是终态**：随着 `delve`、`pivotal` 等词被广泛点名，有意识的作者已在主动过滤，这些词的频率正在下降；但新的 AI 偏好词持续涌现（如近年来 `via` 在论文标题中频率显著上升）。建议每隔半年参考 excess vocabulary 类研究（如 Kobak et al., *Sci. Adv.* 2025；Geng & Trotta 2025）更新黑名单。

---

## 痕迹分三层

修改顺序：**先内容（第3层）→ 再句式（第2层）→ 最后词汇（第1层）**。这与 workflow.md 的"修改三层法"一致——AI 痕迹的根源往往不是词汇而是结构。

---

## 第 1 层：词汇痕迹（最浅但最显眼）

### 高频 AI 词汇黑名单

下列词在生命科学论文里**不是绝对禁用**，但 AI 用得过多。出现频率高于"每千词 1 次"就该警惕。

| 黑名单词 | 出现频率 | 替换思路 |
|---|---|---|
| delve / delve into | AI 高频 | examine / investigate / analyze |
| leverage / leveraging | AI 高频 | use / apply / make use of |
| showcase | AI 高频 | demonstrate / show / present |
| pivotal | AI 高频 | key / important / central |
| stems from | AI 高频 | results from / arises from / is due to |
| underscore | AI 中频 | highlight / emphasize / support |
| underpins | AI 中频 | underlies / supports |
| bolster | AI 中频 | strengthen / support |
| facilitate | AI 中频 | enable / allow / help |
| nuanced | AI 中频 | detailed / subtle / specific（看语境） |
| robust | 滥用风险 | reliable / consistent — 不是结果都"robust"，要看是不是真的有 robustness check |
| comprehensive | 滥用风险 | 真的覆盖完整再用，否则 detailed / thorough |
| seamless / seamlessly | AI 高频 | smoothly / without disruption / 删 |
| navigate / navigating | AI 高频 | address / handle / 删 |
| harness / harnessing | AI 高频 | use / employ |
| crucial / critical | 滥用风险 | important / essential（不是所有事都 crucial） |
| paramount | AI 中频 | essential / most important |
| myriad | AI 高频 | many / numerous / various |
| plethora | AI 高频 | many / abundance |
| realm | AI 中频 | field / area / domain |
| landscape（隐喻） | AI 中频 | 实指 landscape genomics 时保留；隐喻"the landscape of X"换 the field/state of X |
| intricate | AI 中频 | complex / detailed |
| elucidate | AI 高频 | reveal / clarify / show — 不过这词在生物学正经常用，不必一刀切 |
| cutting-edge / state-of-the-art | AI 高频 | recent / latest / advanced |
| meticulous / meticulously | AI 高频 | careful / thorough / with attention to detail |
| innovative / innovatively（自我声称）| AI 高频 | 删——直接陈述新颖之处，不要自贴标签 |

### 副词与连接词

| AI 偏好 | 替代 / 删除 |
|---|---|
| Notably / Importantly | 直接陈述事实，让数据自己说重要 |
| Furthermore / Moreover（每段开头） | 偶尔可以，不要每段都用 |
| In conclusion / In summary（句中） | 这两词只能出现在 conclusion 段落 |
| It is worth noting that | 直接说，不要预告 |
| Interestingly / Surprisingly | 真的 surprising 才用；reviewer 看到太多会觉得 cherry-picking |
| Indeed | 滥用风险 |
| Indeed, ... | 删 |

### 程度词

AI 倾向极端：

| AI 偏好 | 实际写作 |
|---|---|
| significantly + 没数字 | 改 P 值 / 删 |
| substantially / considerably | 给具体数字 |
| dramatically / drastically | 看是否真的 dramatic |
| highly + adj | "highly significant" 已经被滥用，改 P 值 |
| extremely | 几乎没必要在科技论文里 |
| very | 删 |

---

## 第 2 层：句式痕迹（中等深度，最易被识别）

### 排比三件套

AI 极度偏爱"3 个并列项"结构：
- "X is fast, accurate, and comprehensive"
- "Our approach offers improved A, enhanced B, and superior C"
- "We address the challenge of A, B, and C"

实际写作里 2 项或 4 项的并列也很常见。**不是不能用 3 项**，而是不要每段都来一组。

### 过度对仗

AI 喜欢"While A, B" / "Although A, B" / "Despite A, B" 句式开头，并且喜欢**对仗工整**。

```
While X provides Y, Z offers W. While α captures β, γ enables δ. ...
```

每段都这样开头很怪。**实际科研写作里直陈句更多**。

### 句首"信号词"叠加

AI 喜欢段首固定开法：
- "Firstly..." → "Secondly..." → "Finally..."
- "On one hand..." → "On the other hand..."
- "First, ..." → "Second, ..."

不是禁用，但**整篇论文里这种结构出现 3+ 次** = AI 痕迹。

### 句末"总结"

AI 喜欢句末加一个"This X" 总结：
- "..., underscoring the importance of climate factors. This finding highlights..."
- "..., consistent with previous studies. This consistency suggests..."

每个段落最后都有"This X" 总结句 = AI 痕迹。

### 长度均匀化

AI 写出的段落**长度趋于均匀**——每段都 5-7 句。
真实科研写作有节奏：有的段落 3 句（强调式），有的 10 句（详细论证）。

**修改信号**：检查每段句数，如果 80% 段落都是 5-7 句 → 拆掉一些，合并一些。

---

## 第 3 层：结构痕迹（最深，最难发现）

### "完美的" IMRAD 结构

AI 倾向于把每节都写得**结构完整、面面俱到**：
- Introduction 必有 4 段（背景 / 已知 / gap / 本研究）
- Methods 必按软件版本号顺序列
- Discussion 必"回顾 + 比较 + implication + 局限"

真实顶刊论文常**不完全对仗**——某些 section 长，某些短，某些跳过常规结构。

**修改信号**：每节段数完全对称 → 大概率 AI。

### "过度铺垫"

AI 喜欢在直接讲事情前先铺垫：
> "To better understand the genetic basis of climate adaptation, we first explored the population structure of our samples. To this end, we performed PCA analysis. The results showed..."

实际写法：
> "PCA revealed three clusters corresponding to ..."

直接得多。

### "声明式 transition"

AI 段间过渡常用声明：
> "Having established X, we next turned to Y."
> "With this in hand, we proceeded to..."

真实写作过渡更隐式——下一段第一句就直接进入新话题，**不用预告**。

### "中性态度"

AI 写 discussion 时倾向"中立全面"——好处坏处都讲一遍但都不深。
真实研究者写 discussion **有立场**——明确说"X 比 Y 更可信因为..."、"我们认为..."。

---

## 检查与修改流程

### 写作时（预防）

1. **写 outline 时就检查**：每段是否被 AI 模板（如"背景 → 数据 → 方法 → 结果"）僵化
2. **首句检查**：每段第一句是否过度依赖"While / Although / Notably / Importantly"
3. **黑名单词频**：成稿后用编辑器搜索黑名单词，超频的换掉
4. **数字密度**：模糊词（significantly、substantially）后**必跟数字**

### 改稿时（治疗）

3 步：

```
[Step 1 — 第 3 层] 通读全文，看结构是否过于"完美"
  - 段数是否对称
  - 过渡是否过度声明式
  - Discussion 是否中立无立场

[Step 2 — 第 2 层] 段落级
  - 排比三件套出现频率
  - "While / Although" 对仗出现频率
  - 段首"信号词"使用频率
  - 段末"This X" 总结使用频率
  - 段长是否均匀化

[Step 3 — 第 1 层] 词汇级
  - 黑名单词搜索替换
  - 副词删除（Notably / Importantly / Furthermore 减半）
  - 程度词后必跟数字
```

---

## 一个具体改写示例

**AI 风格原稿**：
> Notably, our analysis showcases the pivotal role of climate factors in driving local adaptation. Furthermore, we leverage a comprehensive dataset to delve into the intricate relationships between genetic variation and environmental gradients. Importantly, this study underscores the critical importance of integrating multiple GEA methods to robustly identify candidate adaptive loci.

**改写后**：
> We identified 184 candidate loci associated with 23 climate variables (P < 1.4 × 10⁻¹⁰; BF > 30). The strongest signals lay in temperature- and precipitation-related variables (n = 1,584 and 870 SNPs, respectively). Cross-validation across RDA, LFMM, and BayPass retained 234 high-confidence candidates—34% of the LFMM single-method set—demonstrating that single-method analyses likely include substantial false positives.

差别：
- 黑名单词全清（Notably, showcases, pivotal, leverage, comprehensive, delve, intricate, Importantly, underscores, critical, robustly）
- 数字密度大增（4 个 claim, 6 个数字）
- 直陈而非"highlight the importance of"
- 有立场（"single-method analyses likely include substantial false positives"）

---

## 红线（这些情况坚决不要做）

- 用 AI detector 反向"洗稿"——这是猫鼠游戏，写好内容比对抗 detector 更可持续
- 因怕 AI 痕迹就不用任何高级词——`elucidate` / `nuanced` 在合适语境是好词
- 把所有黑名单词机械替换——上下文优先于规则。"facilitate"在某些医学论文里是标准用法
- 删完所有副词——不是所有副词都是 AI 痕迹

---

## 与 over_claim_guard 的边界

本文件管"**像不像 AI 写的**"，over_claim_guard.md 管"**有没有过度声称**"。
有重叠（"robust"、"comprehensive"既是 AI 词又是过度声称风险），但视角不同：

- 改 AI 痕迹：从"读者怀疑这是 AI"角度
- 改 over-claim：从"reviewer 怀疑你 over-state"角度

冲突时**优先 over-claim**——AI 痕迹是面子问题，over-claim 是里子问题。
