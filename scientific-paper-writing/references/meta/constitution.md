---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# 写作宪法

> 跨章节、跨方向、跨期刊**永远遵守**的硬规则。每个 task 文件都默认引用本文件。
> 元规则不绑定方向，但举例时优先用生命科学组学场景。

---

## 时态宪法

| 章节/段落 | 默认时态 | 例外情况 |
|---|---|---|
| Abstract — Background | 现在时 | "X is a ..." / "Climate change exerts..." |
| Abstract — Methods | 过去时 | "We sequenced ..." / "Genomes were aligned to ..." |
| Abstract — Results | 过去时 | "We identified 184 candidate genes" |
| Abstract — Conclusion | 现在时 | "These results provide insights into ..." |
| Introduction §1-2（已知背景） | 现在时 | 通用规律用现在时："Local adaptation is driven by ..." |
| Introduction §3（前人研究） | 过去时 | 引用具体研究："Kebede et al. identified ..." |
| Introduction §3（前人结论仍成立） | 现在时 | 通论性结论："Domestication is associated with ..." |
| Introduction §4（本研究目的） | 过去时 + 部分现在时 | "Here, we sequenced ... and present a ..." |
| Methods | **过去时**（绝对） | 即使流程是通用的，写本研究的 Methods 时一律过去时。仅描述**软件功能**时可用现在时（"PLINK supports ..."），但不推荐 |
| Results | **过去时**（绝对） | "We identified ..." / "Allele frequency ranged from ..." |
| Results 中描述图表本身 | 现在时 | "Figure 2 shows ..." / "The heatmap depicts ..." |
| Discussion — 重述发现 | 过去时 | "We found that ..." |
| Discussion — 解读意义 | 现在时 | "These results suggest that X is associated with ..." |
| Discussion — 推论/推测 | 现在时 + 情态动词 | "may indicate" / "could explain" |
| Discussion — 局限性 | 现在时 | "A limitation of this study is ..." |
| Figure/Table caption | **现在时**（绝对） | "Figure 1 shows the geographic distribution of ..." |
| Cover letter | 现在时为主 | "We are pleased to submit ..." |

**最常见错误**：Methods/Results 误用现在时。检查信号词：见到 "is", "are", "shows", "reveals" 出现在 Methods/Results 里要警惕（除非是描述软件特性或图表本身）。

---

## 语态宪法

* **生命科学顶刊近 10 年趋势是主动语态优先**。"We sequenced 100 genomes" 优于 "100 genomes were sequenced"。
* **被动语态保留场景**：
  - 强调对象而非执行者："Reads were aligned to the reference genome (BWA-MEM v0.7.17)."
  - 步骤连续多个时为简洁起见
  - Figure caption 默认被动："Samples are grouped by ..."
* **最忌讳**：Methods 通篇被动 + 无主语 + 长句叠句（典型工程英语翻译腔）。
* **修订时**：被动 → 主动通常 (i) 句子更短 (ii) 主体更清楚 (iii) reviewer 觉得更可信。

---

## 数字宪法

### 表达规范
| 场景 | 标准 | 反例 |
|---|---|---|
| 句首 | 拼写："Twenty-six samples were ..." | ❌ "26 samples were ..."（句首） |
| 整数 < 10（非测量） | 拼写："three breeds" | ❌ "3 breeds" |
| 整数 ≥ 10 / 任何带单位的数字 | 阿拉伯数字："27 SNPs" / "5 kb" / "0.05 cM" | |
| 百分比 | "30%"（不留空格，除非期刊要求） | "30 %" 视期刊 |
| 范围 | en-dash："5–10 Mb" / "P = 1.4 × 10⁻¹⁰" | ❌ "5-10 Mb"（hyphen） |
| 样本量 | "(n = 100)" 或 "n = 100"，斜体 *n* | |
| 显著性 | "P < 0.001" 或 "P = 1.2 × 10⁻⁴"，斜体 *P* | ❌ "p < 0.001"（小写 p 视期刊） |
| 估计值 ± 误差 | "0.45 ± 0.02" | |
| 置信区间 | "(95% CI: 0.40–0.52)" | |
| 千分位 | 1,000,000 用逗号；基因组学领域常省（"1000000"） | 看期刊 |
| 小数前导零 | 必须保留："0.05"，不写 ".05" | |
| 小数位 | P 值/效应量 2-3 位有效数字；测量值看精度 | 不要 P = 0.0123456789 |

### 内容规范
* **每个 claim 后必须有数字或具体证据**。模糊词（"significantly higher"、"strongly associated"、"substantial"、"considerable"、"a large number"）后没数字 = 红旗。
* **绝不编造数字**。用户没给的数字标 `[X.XX%]` / `[n = XX]` / `[P < X.XX]`，让用户填。
* **数字一致性自检**：abstract 报的数字必须等于 results 正文等于 figure caption 等于 supplementary table。最常见失败：投稿前改了一个数没同步改另一处。

---

## 命名宪法

### 物种与基因
| 项目 | 规则 |
|---|---|
| 拉丁学名 | 斜体首字母大写属名："*Bos taurus*" / "*Capra hircus*" / "*Arabidopsis thaliana*" |
| 学名缩写 | 全称首次出现后可缩："*B. taurus*"。同段落内属首字母重复缩写不变 |
| 通用名 | 正体小写："cattle" / "sheep"（除非期刊要求大写） |
| 基因符号 | **斜体 + 大写**（人/动物）："*TSHR*" / "*LCT*" |
| 基因符号 | **斜体 + 首字母大写其余小写**（小鼠等模式生物按各物种规范） |
| 蛋白质 | **正体大写**："TSHR" / "LCT" |
| 等位基因 | 上标或破折号："*TSHR*^A^" / "*LCT*-13910*T*" |
| 染色体 | "BTA18" (cattle) / "OAR3" (sheep) / "Chr18"（通用）。首次出现说明清楚 |
| 品种代号 | 全大写缩写，文中首次给全称："East Asian taurine (EAT)" |

### 软件与数据库
| 项目 | 规则 |
|---|---|
| 软件名 | 首次出现给版本号："BWA-MEM v0.7.17" / "PLINK v1.9" / "BayPass v2.31" |
| 软件名大小写 | 按官方文档（PLINK 全大写、BayPass 驼峰、samtools 全小写） |
| 数据库 | 首次出现给版本/访问日期："Ensembl release 110" / "WorldClim v2.1" |
| 参考基因组 | "ARS-UCD2.0" (cattle) / "ARS-UI_Ramb_v3.0" (sheep) — 给完整版本号 |
| 测序平台 | "Illumina NovaSeq 6000" / "PacBio Sequel II" — 给型号 |

### 单位
| 项目 | 规则 |
|---|---|
| 长度 | bp / kb / Mb / Gb（无空格："5 kb" 还是 "5kb" 看期刊；新趋势加空格） |
| 时间-进化 | year ago = ya；千年前 = kya；百万年前 = Mya |
| 样本量/读段 | "30×"（覆盖度，乘号是 ×，不是 x） |
| 化学量 | mol/L 而非 M（除非俗用） |
| 温度 | "25 °C"（数字与单位间空格，°C 不分开） |

---

## 引用宪法

### 引用密度
* **顶刊段落引用密度参考**：每段 2-5 个引用；每个 claim 至少 1 个；段尾综述性 claim 可集群引用。
* **引用过密信号**：一句话 5+ 个引用 = 像综述不像研究论文。
* **引用过疏信号**：整段无引用 = 让 reviewer 觉得 claim 没根据。

### 引用形式
| 期刊系 | 形式 |
|---|---|
| Nature 系 | 上标数字："adaptation¹⁻³" |
| Science 系 | 括号数字："adaptation (1-3)" |
| Cell 系 | "(Author, Year)" |
| BMC 系 | 数字加方括号 "[1, 2]" |
| PNAS | "(Author et al., Year)" |
| 投稿前确认期刊 instructions for authors | |

### 引用规则
* **绝不编造引用**。不确定就标 `[CITATION NEEDED]` 让用户填。
* **首次vs重复引用**：同一论文在文中重复引用，第二次开始可缩 "Chen et al."；首次必须给完整作者信息（按期刊规范）。
* **et al. 阈值**：作者 ≥ 3 通常用 et al.；具体几位作者后开始 et al. 看期刊。
* **集群引用排序**：通常按时间正序（旧→新）或按重要性排序（看期刊）。
* **avoid orphan citation**：每个引用都应该服务于具体 claim，不要"塞引用凑数"。
* **self-citation 度**：自引超过 20% 总引用会让 reviewer 警觉。

---

## 标点与排版宪法

| 项目 | 规则 |
|---|---|
| en-dash (–) | 范围："5–10 Mb"、"2010–2020"、"Wnt–β-catenin pathway" |
| em-dash (—) | 插入语，前后空格视期刊（Nature 系无空格："—"，部分期刊用空格"— —"） |
| hyphen (-) | 复合词："well-established"、"climate-driven"。**不用于范围** |
| Oxford comma | "A, B, and C"。**强烈推荐**（多数生命科学顶刊用），歧义最少 |
| 希腊字母 | Unicode 字符 "α"、"β"、"χ²"，不要 LaTeX 写 "\\alpha" 在正文里 |
| 上下标 | 化学式/同位素/统计："H₂O" / "¹⁴C" / "χ²" / "10⁻⁵" |
| 引号 | 双引号 "" 用于直接引用；单引号 '' 用于嵌套或专门术语；不用中文全角 |
| 缩写首次 | 全称（缩写）："genotype-environment association (GEA)"；之后只用缩写 |
| 缩写一致性 | 一旦定义缩写，全文坚持使用，不要时而 GEA 时而 genotype-environment association |

---

## 作者归属与致谢

* **作者顺序**：第一作者（共一）/ 通讯作者（co-corresponding） — 投稿前与所有作者确认。
* **贡献声明（CRediT taxonomy）**：现在多数期刊要求按 14 类贡献声明（Conceptualization / Data curation / Formal analysis / Funding acquisition / Investigation / Methodology / Project administration / Resources / Software / Supervision / Validation / Visualization / Writing - original draft / Writing - review & editing）。每位作者至少 1 类。
* **基金号**：精确到 grant number，不要写"国家自然基金"这种泛称。
* **数据可用性声明**：现在多数期刊强制要求；测序数据 → SRA / GSA / ENA；变异数据 → EVA / dbSNP；基因组组装 → GenBank。给 accession number。

---

## 红旗（违反宪法的常见信号）

写完一段后扫一遍：

- [ ] 时态有没有混用？尤其 Methods/Results 里有没有"is"、"are"、"shows"
- [ ] 数字格式是否统一（全文 P 值有效位数、CI 写法）
- [ ] 物种学名首次出现时是否完整 + 斜体
- [ ] 软件首次出现是否给版本号
- [ ] "significantly"、"substantially"、"considerably" 后面有没有数字
- [ ] 缩写定义后是否一直用缩写
- [ ] 引用是不是真的支持那个 claim（不是凑数）
- [ ] 数字在 abstract / results / figure / supplementary 一致
- [ ] 没有编造的引用、数字、参数

---

## 遇到冲突时的优先级

1. **目标期刊的 instructions for authors**（最高优先级，打破本宪法的任何条目）
2. **本宪法**（默认规则）
3. **用户原稿的风格**（如果不违反 1 和 2，保留用户的表达偏好）

例：本宪法说 "P 值用大写斜体"，但目标期刊明确用小写 "p"，则按期刊。
