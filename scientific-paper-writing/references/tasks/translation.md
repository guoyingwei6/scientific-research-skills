---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Task: Translation / 中英翻译

> Translation 要回答的问题：**用户给的中文/英文，能不能翻译成另一种语言并保持科技论文的元规则**。
> 服务的场景：用户中文写思路 → 转英文论文，或反向。

## ⚓ 元层锚点

- `meta/constitution.md`：翻译后必须满足时态 / 数字 / 命名宪法
- `meta/over_claim_guard.md`：中文常用的"显著的、巨大的"翻译时容易 over-claim
- `meta/ai_artifacts.md`：翻译输出最容易出 AI 痕迹
- `meta/workflow.md`：先翻译再润色，分两步

---

## 任务本质

科技论文翻译不是字面对译,是**重写**——保留科学内容,但用目标语言的科技论文语境重新组织。

写得好的标志：母语者读起来**不像翻译稿**。

---

## 中→英翻译的核心错位

中文科技写作和英文科技写作有**结构性差异**,不只是词的替换：

| 维度 | 中文倾向 | 英文倾向 |
|---|---|---|
| 主语 | 经常省略（"分析了 100 个样本"）| 必须明确（"We analyzed 100 samples"）|
| 句长 | 长句堆叠（一个句子 3 个分句）| 短句拆分（每个 main idea 独立成句）|
| 时态 | 不严格区分 | 严格按章节 |
| 程度词 | 多用"显著、明显、强烈、重要"| 用具体数字而非程度词 |
| 因果 | 直接说"导致、决定"| 多用"associated / consistent with"|
| 句序 | 因果句多在后（because句尾）| topic-first（main idea 句首）|
| 转折 | "然而、但是"频繁 | 用句子结构表达转折 |
| 名词化 | 倾向"X 的 Y"结构 | 倾向 verb 结构 |

---

## 英→中翻译的核心错位

| 维度 | 英文倾向 | 中文倾向 |
|---|---|---|
| 长句 | 修饰从句堆叠 | 拆短句 |
| 物种学名 | 斜体 | 看格式（中文期刊也斜体）|
| 数字 + 单位 | "5 kb" 空格 | "5kb" / "5 kb" 看期刊 |
| 主语 | We / Our results | "本研究 / 我们 / 此外"轮换 |
| 程度词 | "significantly" + 数字 | "显著（P = ...）" |
| 介词使用 | "of" 多层叠 | 简化或拆句 |

---

## 通用工作流

### Step 1：识别原文章节
判断这段属于哪节（Methods / Results / Discussion 等）→ 拿对应 task 文件的元规则

### Step 2：理解原意
不要逐字翻译。先**读懂**原文 main message,再用目标语言重新表达。

### Step 3：翻译草稿
按目标语言的科技写作规范成稿。**主语不省略,长句拆短,时态严格**。

### Step 4：按元规则润色
翻译草稿往往有 AI 痕迹和翻译腔。按 `tasks/style_polish.md` 流程过一遍。

---

## 中→英常见翻译失败点

### 1. 主语省略
中：分析了 100 个样本的全基因组测序数据。  
❌ 直译：Analyzed whole-genome sequencing data of 100 samples.  
✅ 翻译：We analyzed whole-genome sequencing data from 100 samples.

→ 英文 Methods/Results **必须有主语**（We / Our results / The data 等）

### 2. 程度词过度
中：发现了大量与气候适应显著相关的位点。  
❌ 直译：A large number of loci significantly associated with climate adaptation were found.  
✅ 翻译：We identified 184 candidate loci associated with climate adaptation (P < 1.4 × 10⁻¹⁰).

→ 英文用**具体数字**替代"大量、显著"

### 3. 因果直译
中：气候因子驱动了局部适应。  
❌ 直译：Climate factors drove local adaptation.（reviewer 觉得 over-claim）  
✅ 翻译（保守）：Climate factors are associated with patterns of local adaptation.  
✅ 翻译（强表达 OK 时）：Climate factors are major drivers of local adaptation in our dataset.

参考 `over_claim_guard.md#因果替代`

### 4. 长句堆叠
中：通过整合 RDA、LFMM 和 BayPass 三种方法对 744 头牛进行分析,鉴定出 234 个高置信候选位点,这些位点富集于温度和降水相关的环境变量,提示气候因子在牛局部适应中的关键作用。  
❌ 直译（一句长句）：By integrating three methods (RDA, LFMM, BayPass) to analyze 744 cattle, we identified 234 high-confidence candidate loci, which were enriched for temperature- and precipitation-related variables, suggesting the critical role of climate factors in cattle local adaptation.  
✅ 翻译（拆 3 句）：We integrated RDA, LFMM, and BayPass on 744 cattle to identify 234 high-confidence candidate loci. These loci were enriched for temperature- and precipitation-related variables. Together, our results suggest that climate factors contribute substantially to local adaptation in cattle.

→ 英文每句一个 main idea；3 个分句 → 3 个独立句

### 5. 名词化
中：基因组的进化分析  
❌ 直译：The evolutionary analysis of the genome  
✅ 翻译：We analyzed genome evolution / We performed evolutionary analysis on the genome

→ 英文偏好 verb 结构（动词带主语）

### 6. "本研究"翻译
中：本研究通过 ... 揭示了 ...  
❌ 直译：This study revealed ... through ...  
✅ 翻译：Here, we [verb past] [object], revealing [finding].

→ 英文用 "Here, we ..." 是引言 §4 / abstract 标准开场

---

## 英→中常见翻译失败点

### 1. 修饰从句翻译
英: "We identified 184 candidate genes that were associated with climate variables and showed strong evidence of selection."  
❌ 直译: 我们鉴定了 184 个**与气候变量相关并表现出强烈选择证据的**候选基因。（修饰太长）  
✅ 翻译: 我们鉴定了 184 个候选基因,这些基因与气候变量相关,并表现出选择信号。

→ 中文拆短句

### 2. 物种学名
英: "*Bos taurus* (cattle)"  
✅ 翻译: 牛（*Bos taurus*）  
（学名仍斜体；中文括号内放学名,主语用通用名）

### 3. 程度词
英: "significantly higher (P < 0.001)"  
✅ 翻译: 显著更高（*P* < 0.001）  
（中文期刊 *P* 是否斜体看期刊；显著 + 数字保留）

### 4. 时态
英文严格区分时态;中文不严格,但在 Methods 中可以用"对...进行了..." / "采用..." / "使用..."等过去时。Discussion 中"提示"、"暗示"、"表明"对应 may suggest / suggest / indicate。

---

## Specific 术语翻译表

> 高频翻译歧义,挑选主要的：

| 英文 | 中文（推荐）|
|---|---|
| local adaptation | 局部适应 |
| genome-environment association (GEA) | 基因组-环境关联 |
| selection signature / signature of selection | 选择信号 |
| selective sweep | 选择性清除 |
| introgression | 渗入 |
| admixture | 混合 / 渗入（看语境）|
| linkage disequilibrium (LD) | 连锁不平衡 |
| effective population size (Ne) | 有效种群大小 |
| genetic load | 遗传负荷 |
| pleiotropy | 多效性 |
| convergent evolution | 趋同进化 |
| pangenome | 泛基因组 |
| structural variation (SV) | 结构变异 |
| imputation panel | 填充参考 panel / 填充参考集 |
| genomic offset / genetic offset | 基因组偏移 |
| reference panel | 参考 panel |
| breed | 品种 |
| population | 群体 / 种群 |
| robust | 稳健 |
| candidate variant / SNP | 候选变异 / 候选 SNP |
| putative role | 假定的作用 / 推测的作用 |
| outgroup | 外类群 |

---

## 元层雷区

### 1. 翻译过度直译
- 母语者读起来怪 = 失败
- 重在传达 main message,不在每个词的对应

### 2. 翻译丢失数字
- 翻译时容易把 "184" 译为 "many" / "数量众多"
- → 数字必须保留

### 3. 翻译加 over-claim
- "驱动" 直译 "drive" → 中→英时可能 over-claim
- 翻译时主动**保守化**

### 4. 翻译丢失时态信息
- 中文常用"...的"省略时态线索
- 翻译时**主动判断章节**,按 constitution 时态宪法分配

### 5. 翻译破坏术语统一
- 同一术语全文一致
- 不要"基因组-环境关联" 一处译 "GEA" 一处译 "基因组-环境关联分析" 一处译 "环境关联分析"

### 6. 文化语义错位
- "本文" / "本研究" / "本工作" 中文常见,英文统一为 "this study" / "we" / "our work"
- 英文 "elegant" / "beautiful" 对方法的赞美翻译为中文要意译

---

## 输出格式

按 `meta/user_tools.md`：

```
[完整翻译后的段落]

主要选择/调整：
1. [原文 X → 翻译 Y] — [原因]
2. [拆了一个长句] — [原因]
3. [程度词换数字 placeholder] — [原因]
```

---

## 自查清单（翻译输出前）

- [ ] 主语都明确（中→英）/ 修饰从句已拆（英→中）？
- [ ] 时态符合该章节宪法？
- [ ] 程度词后跟数字（不要"large"、"significant"裸用）？
- [ ] 因果关系保守表达？
- [ ] 物种学名 / 基因符号格式正确？
- [ ] 术语全文一致？
- [ ] 数字 / 单位保留完整？
- [ ] 没翻译腔（"It is worth mentioning that..." 这种）？
- [ ] AI 痕迹清理？
