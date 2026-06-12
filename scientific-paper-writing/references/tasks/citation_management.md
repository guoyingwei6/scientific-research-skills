---
created: 2026-06-02 21:45
updated: 2026-06-02 21:45
---
# Task: Citation management / 引用管理

> Citation management 要回答的问题：**引用是不是对的 + 格式是不是符合期刊 + 没编造**。
> 服务的 reviewer 决策：作者读没读原文 + 引用是否支持 claim。

## ⚓ 元层锚点

- `meta/constitution.md`：引用宪法
- `meta/reviewer_psychology.md`：第 3 大怀疑信号 = 引用支持力度不够
- `meta/user_tools.md`：用户用 Zotero,Claude 不要用 web_search 找文章

---

## 任务本质

引用管理是**最容易出 integrity 问题**的环节。Claude 编造引用 = 学术不端。

写得好的标志：每个引用都**真实存在 + 支持具体 claim + 格式统一**。

---

## 三条铁律

### 铁律 1: 绝不编造
**Claude 不知道某篇论文存在 / 不确定作者年份 → 标 `[CITATION NEEDED]`**

不要说 "这大概是 Smith et al. 2020"。LLM 编造引用是经典学术不端事件。

### 铁律 2: 引用对应 claim
- 一个引用支持一个具体 claim
- 不要"塞引用凑数"（一句话末尾 5 个引用都没具体支持）
- 引用的论文**结论必须真的支持**你的 claim（不是相反）

### 铁律 3: 一致性
- 全文引用格式一致（按期刊 instructions）
- 同一论文每次引用形式一致
- 缩写名 vs 全称名一致

---

## 引用形式（按期刊）

| 期刊系 | 形式 | 例 |
|---|---|---|
| Nature 系 | 上标数字 | "adaptation¹⁻³" |
| Science | 括号数字 | "adaptation (1–3)" |
| Cell 系 | (Author, Year) | "(Smith et al., 2020)" |
| BMC 系 | 数字加方括号 | "[1, 2]" |
| PNAS | (Author et al., Year) | "(Smith et al., 2020)" |
| MBE / GBE | (Author Year) 无逗号 | "(Smith et al. 2020)" |
| 投稿前查 instructions for authors | | |

---

## 引用密度

| 段落类型 | 密度 |
|---|---|
| Introduction §1 (大背景) | 1-3 个 / 段（不要太多） |
| Introduction §2-3 (已知 / gap) | 3-5 个 / 段 |
| Introduction §4 (本研究) | 0-2 个（自己研究不需要太多引用） |
| Methods | 关键软件每个引用一次（首次出现） |
| Results | 0-2 个 / 段（result 本身的引用主要是已知功能注释） |
| Discussion | 3-7 个 / 段（密度最高） |

---

## et al. 阈值

按期刊：
- ≥ 3 作者用 et al.（最常见）
- ≥ 4 / ≥ 6 作者用 et al.（部分期刊）
- 看 instructions

参考文献列表里：
- 通常列前 5-10 位作者后 et al.
- 某些期刊要求**全部列出**（注意篇幅）

---

## 集群引用排序

按时间正序（旧→新）= 默认  
按重要性 = 期刊允许时

例：
- "Multiple studies have addressed this question (Smith 2010; Jones 2015; Wang 2020)."

---

## 自引比例

> 自引超过 20% 总引用数 = reviewer 警觉 / editor 红旗

- 适度自引正常（你的 prior work 支持本研究）
- **过度自引** = 论文 inflation 怀疑
- 自引时要诚实标注（同期刊可能查 PI）

---

## 元层雷区

### 1. 编造引用（最严重）
- LLM 编造的论文常常作者真实但 title 不存在 / 作者真实但年份错 / 期刊错
- **任何不确定**的引用都标 `[CITATION NEEDED]`
- 用户用 Zotero 自己填

### 2. 引用与 claim 错位
- 你说"X 是 Y" 引 [Smith 2020]
- Smith 2020 实际结论是"X 不是 Y"
- reviewer 翻原文一看，立即怀疑诚信

### 3. Orphan citation
- 引用没服务于具体 claim
- 一句话末尾"(Smith 2020; Jones 2021; Wang 2022)" 但段落没明确说这三篇在说什么
- → 引用应该有"用处"，不是装饰

### 4. 引用过度依赖综述
- 综述是补充，不是替代
- 关键 claim 引用**原始研究**
- 综述只在 introduction §2 大背景或快速 fill in 时用

### 5. 引用过老
- 全文引用都 5+ 年前 → reviewer 怀疑你没跟最新文献
- 关键 claim 应该有近 3-5 年的引用
- 经典奠基论文（Hardy-Weinberg / Wright / Kimura 等）当然可以引老的

### 6. 引用单一团队
- 全文 30 个引用，20 个来自同一 group → 不平衡
- 平衡多团队 / 多机构 / 多国

### 7. 引用列表与正文不一致
- 列表里有论文正文不出现 = 删
- 正文 cite 但列表里没 = 加
- 投稿前 sanity check

### 8. 格式不统一
- 同篇论文一处 "(Smith et al., 2020)" 一处 "(Smith et al. 2020)" / "(Smith 2020)" / "Smith and Jones 2020" 混用
- 用 Zotero / EndNote 自动管理避免手工错乱

---

## BibTeX / EndNote / Zotero 配合

按 `user_tools.md`：用户用 Zotero。

### Claude 的角色
- 在论文里引用时**用 placeholder 或自然语言形式**，让用户自己拷 .bib 或 .ris 进来
- 不要伪造 BibTeX 条目
- 用户给 Zotero key（如 [@Smith2020]）就用 [@Smith2020] 格式
- 用户给具体引用就保留具体引用

### 模板：用户没给具体引用时
```
"Local adaptation has been characterized in multiple cattle breeds [CITATION NEEDED: prior cattle GEA studies, e.g., Sun 2026 iMeta or similar]."
```

→ 用户根据 placeholder 自己填 Zotero key。

---

## 跨方向 illustration

> 不同方向引用密度 / 偏好略有不同：

### 景观基因组学 / GEA
- Methods 部分必引 software paper：
  - RDA: vegan package — Oksanen et al.
  - LFMM: Caye et al. 2019 (LEA package)
  - BayPass: Gautier 2015
  - WorldClim: Fick & Hijmans 2017
- Discussion 必引 climate adaptation 经典：Aitken 2008 / Hereford 2009 / Savolainen 2013
- 跨物种 convergent evolution：每讨论候选基因都引该基因在其他物种的研究

### 选择信号
- Methods 必引 statistic paper：
  - iHS: Voight et al. 2006
  - XP-EHH: Sabeti et al. 2007
  - selscan software: Szpiech & Hernandez 2014
- Discussion 跨物种比较：每候选基因引其他物种的同基因研究

### 群体结构 / 系统地理学
- Methods 必引：PLINK (Chang 2015) / ADMIXTURE (Alexander 2009) / smartpca (Patterson 2006)
- Discussion 跨物种比较 + 古 DNA 文献

### Imputation panel
- Methods 必引：Beagle / IMPUTE / GLIMPSE
- Discussion 与已发表 panel 对比

---

## 自查清单（投稿前）

- [ ] 全文搜 `[CITATION NEEDED]` 残留 → 0
- [ ] 全文搜 `[Author Year]` 占位符残留 → 0
- [ ] 引用列表 vs. 正文一致（列表无正文外的；正文每个 cite 在列表）
- [ ] 引用格式统一（按期刊 instructions）
- [ ] et al. 阈值统一
- [ ] 自引比例 < 20%
- [ ] 关键 claim 有近 3-5 年原始研究支持（不只是综述）
- [ ] 没有引用与 claim 实际相反
- [ ] 同一论文每次引用形式一致
- [ ] DOI / PMID 在 BibTeX 里齐
