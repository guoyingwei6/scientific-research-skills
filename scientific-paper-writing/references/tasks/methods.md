---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Task: Methods

> Methods 要回答的问题：**reviewer 能不能复现 + 方法选择是不是合理**。
> 服务的 reviewer 决策：data 可不可信 + 方法严不严谨。

## ⚓ 元层锚点

- `meta/constitution.md`：**绝对过去时** + 软件版本 + 数字格式
- `meta/reviewer_psychology.md`：第 2 大怀疑信号 = "方法关键参数缺失"
- `meta/over_claim_guard.md`：方法选择不要 "we use the most accurate method"——基于场景说明合理性即可
- `meta/workflow.md`：Frame → Outline → Draft → Self-review

---

## 任务本质

Methods 是 **可重复性合同**。每个参数、每个版本号、每个阈值都是合同条款。

Methods 写得好的标志：**一个 method-expert reviewer 看完后能在自己机器上复现你的关键步骤**——他可能数据拿不到，但流程清楚得像 cookbook。

---

## 通用工作流

### Frame
- 我的**关键创新方法**是什么？(常规方法可缩写，关键方法详写)
- 哪些参数选择是**有争议的**？(需要多说一句为什么这么选)
- 哪些步骤是**项目specific**？(需要给具体阈值/版本号)

### Outline
按"数据生产 → 数据处理 → 数据分析"顺序列小节：

```
§1 Sample / Data
§2 Sequencing / Genotyping (如适用)
§3 Read mapping / Alignment
§4 Variant calling / QC
§5 [核心分析模块 1]
§6 [核心分析模块 2]
§N Statistical analysis / Software summary
```

每小节列：用了什么软件 + 版本 + 关键参数 + 阈值 + 输出。

### Draft
**全部过去时**。被动语态可保留（强调对象时），但近年顶刊更倾向主动。

### Self-review
- 关键参数都给了吗（version + threshold + multiple testing）？
- 缩写首次出现给全称了吗？
- 软件版本号都齐吗？
- 数据可用性 / 代码可用性写了吗？

---

## 通用骨架

每个小节内部三件套：**目标 → 流程 → 参数**。

```
[Section: 干什么 + 为什么用这方法]
[流程: 从 input 到 output 1-3 句话]
[参数: 软件 vX.Y, threshold = X, 关键设置]
```

例：

> Variant calling. Variant calling was performed using GATK v4.4.0.0 following the GATK Best Practices pipeline. We applied HaplotypeCaller in GVCF mode for each sample, followed by joint genotyping with GenotypeGVCFs. Variants were filtered with VariantFiltration using the following thresholds: QD < 2.0, FS > 60.0, MQ < 40.0, MQRankSum < −12.5, ReadPosRankSum < −8.0, SOR > 3.0. Indels were filtered with QD < 2.0, FS > 200.0, ReadPosRankSum < −20.0, SOR > 10.0.

注意：每个数字背后都是项目decision，能说清就说，不能说清就引前人。

---

## 关键参数披露清单（按高频小节）

下面是**绝大多数生命科学组学论文都会涉及**的小节及其关键参数。**不必每篇都有，但有的话就要披露完整**。

### Sample / Data
- 来源（自测序 / 公共数据库 + accession）
- 物种 + 品种 + 个体数
- 地理来源 / 表型描述（如适用）
- IRB / IACUC / 伦理批文（动物实验或人类研究）

### Sequencing / Library prep
- 平台 + 型号（"Illumina NovaSeq 6000"）
- Library prep kit
- Read length（150 bp PE 等）
- Mean coverage / 总数据量

### Read mapping
- 参考基因组（带版本：ARS-UCD2.0 / ARS-UI_Ramb_v3.0 等）
- 比对软件 + 版本（BWA-MEM v0.7.17）
- 关键参数（默认就说 default）
- Duplicate marking（Picard / samtools markdup）

### Variant calling
- caller + 版本（GATK / bcftools / DeepVariant）
- Joint vs. single-sample
- Filter thresholds

### QC / Filtering
- MAF 阈值
- Missing rate 阈值
- HWE 阈值
- 个体 missing rate
- LD pruning（如做）参数：window / step / r²

### 群体遗传分析（如有）
- PCA：PLINK / smartpca + 用了什么 SNP 集
- ADMIXTURE：K 范围 + CV error 选 K
- Tree：方法（NJ / ML）+ 软件 + bootstrap
- FST：估计方法（Weir & Cockerham 1984）+ 窗口大小

### 选择信号（如有）
- 统计量：iHS / XP-EHH / FST / CLR / nSL / Tajima's D
- 软件：selscan / VCFtools / SweepFinder
- 窗口 / 阈值（top X% / 经验 P 值 < X）
- 多重检验校正

### GEA / Landscape genomics（如有）
- 环境数据来源：WorldClim vX.X / CHELSA / NCEP 等
- 环境变量数（n=X）+ 时间窗（1981-2010 等）
- 共线性处理：VIF threshold / 相关性 > X 的剔除
- GEA 方法：RDA / LFMM / BayPass + 软件版本
- 多方法整合标准（Venn 交集 / 多方法都显著）

### Imputation（如有）
- Reference panel
- Software（Beagle / IMPUTE / GLIMPSE）+ 版本
- Concordance / r² 评估方法

### 多组学整合（如有）
- 各 omic 数据来源 + 处理流程（链接到 single-omic methods 章节）
- 整合方法（cis-eQTL / co-localization / partial correlation 等）

### Statistical analysis
- 多重检验校正方法（Bonferroni / FDR / qvalue）
- 显著性阈值
- R / Python 主要 package + 版本

### Data and code availability
- 测序数据：SRA / GSA / ENA accession
- 基因型数据：dbSNP / EVA accession
- 基因组组装：GenBank / DDBJ accession
- 代码：GitHub URL（建议带 DOI via Zenodo）
- Supplementary：列出 Tables / Figures 编号

---

## 元层雷区（跨方向通用）

### 1. 缺版本号
❌ "Reads were aligned with BWA."  
✅ "Reads were aligned with BWA-MEM v0.7.17."

每个软件**首次出现必须带版本号**。版本不记得 → 标 `[VERSION NEEDED]` 让用户填。

### 2. 缺阈值
❌ "Variants were filtered for quality."  
✅ "Variants were retained if MAF > 0.01, missing rate < 0.10, and HWE P > 1 × 10⁻⁶."

阈值缺失 = reviewer 立刻质疑过滤合理性。

### 3. 时态错乱
❌ "We use BWA to align reads."  
✅ "We aligned reads using BWA-MEM v0.7.17."

Methods **绝对过去时**。例外：描述软件本身特性（"PLINK supports ..."），但不推荐。

### 4. 多重检验缺失
- 任何 GWAS / GEA / selection scan 都要说**多重检验如何处理**
- "P < 0.05" + 100 万 SNP 而没说 Bonferroni / FDR = 立即被怀疑

### 5. "Best practices" 不是免死金牌
❌ "We followed GATK Best Practices."（仅此一句）  
✅ 即使 follow Best Practices 也要列出**关键参数**——因为 Best Practices 本身在演化，不同版本不一样

### 6. 引用代替描述
❌ "We performed PCA following Smith et al. 2020."  
✅ "We performed PCA using PLINK v1.9 [Chang et al. 2015]. The analysis used X SNPs after LD pruning (window = 50 kb, step = 5, r² < 0.2)."

引用前人是补充，不是替代。

### 7. 软件名拼写
- 看官方文档：PLINK 全大写、samtools 全小写、BayPass 驼峰、bcftools 全小写
- 不要"plink" / "PlinK" / "PLink"（软件名是 brand name，要尊重官方拼写）

### 8. 不要写"我们用了 X 因为它最准"
❌ "We used method X because it is the most accurate."  
✅ "We chose method X because it is suitable for [specific data property of our study]."

理由要 specific，不要 general。

### 9. 数据/代码可用性缺失
- 现在多数期刊**强制要求**
- 测序数据没 accession 是 reject 直接原因
- 代码至少有 GitHub URL；正式 release 加 Zenodo DOI 更佳

### 10. 序列不连贯
Methods 章节顺序应该跟数据流顺序一致：
- ❌ Read mapping 之前先讲 GEA 分析
- ✅ Sample → Sequencing → Mapping → Variant calling → QC → Downstream analyses

---

## 跨方向 illustration

> 元规则的演示，不是范式模板。

### 群体结构 / 驯化
关键披露：参考基因组版本 / variant filter 阈值 / PCA 用的 SNP 集 / ADMIXTURE 选 K 的 CV error / 系统树方法 + bootstrap

### 选择信号
关键披露：每个统计量的窗口大小 / 阈值取法（empirical P 还是 fixed cutoff）/ 多统计量交集规则 / 多重检验校正

### 景观基因组学（GEA）
关键披露：
- 环境变量来源（WorldClim v2.1 等）+ 时间窗（如 1981-2010）+ 提取方式（site-level vs. mean within X km buffer）
- 环境变量数 + VIF 阈值（典型 10）+ 剔除流程
- RDA：constrained vs. unconstrained / variation partitioning（pure climate vs. pure geography vs. shared）
- LFMM：是 LFMM 还是 LFMM2？K 怎么选的？是否 genomic.control？
- BayPass：core model + AUX/IS model / 几个独立 run / 多重 run 的合并方式（median BF）/ XtX threshold
- 多方法整合：Venn 交集还是某种 union？候选 SNP 阈值（典型 3 SD 或 top X%）

### 渗入 / 杂交
关键披露：D-statistic 用什么 outgroup / TreeMix migration edge 数选择 / RFMix 参考 panel / IBDMix / qpAdm 模型

### SV / 泛基因组
关键披露：长读长测序平台 + coverage / 组装软件（hifiasm / Verkko）+ 版本 / SV caller（pbsv / Sniffles / svim）/ pangenome graph 软件（minigraph / pggb）

### Imputation panel
关键披露：reference panel sample size + composition / software + 版本 / phasing 流程 / r² 评估

### 多组学整合
关键披露：每个 omic 数据的 QC 流程（链接到对应 single-omic methods）/ 整合方法（cis-eQTL: FastQTL? eQTL: tensorQTL? co-localization: coloc?）

---

## 篇幅与组织

* **顶刊**：Methods 通常移到正文末尾或 Online Methods，篇幅 5-10 页
* **专业刊**：Methods 在 IMRAD 顺序中，篇幅 2-5 页
* **二区**：Methods 详细，可以非常长

无论哪种，关键参数披露完整度**一样**。差异在文字风格和详略层次。

---

## 自查清单（写完 Methods 后）

- [ ] 全部**过去时**？（搜索 "is" / "are" / "shows" 在 Methods 里出现次数）
- [ ] 每个软件首次出现都有**版本号**？
- [ ] 每个 filter 都有**阈值**？
- [ ] 多重检验校正方法**明确**？
- [ ] 关键参数选择有**理由**（不是 "best" 这种空话）？
- [ ] 缩写首次出现都有**全称**？
- [ ] 软件名拼写跟**官方文档**一致？
- [ ] 章节顺序跟**数据流**一致？
- [ ] **数据可用性 + 代码可用性**写了？
- [ ] 项目specific的伦理批文 / IRB 写了（如适用）？
- [ ] 没有"we use X because it is the most accurate"这种 general 表述？
