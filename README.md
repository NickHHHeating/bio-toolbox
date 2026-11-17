# 生信资源索引

个人用的收藏页。记录常去的仓库、数据入口和检索方法，省得每次重新搜。
建立于 2026-11-17，持续补充。

---

## 一、教程

### [jmzeng1314/GEO](https://github.com/jmzeng1314/GEO) · 896 ★ · R

中文的 GEO 芯片分析全流程教程。limma 差异分析、火山图、热图、GO/KEGG 富集都在里面，代码可以直接跑。作者是国内做生信培训的曾健明，教程的写法和国内视频课是一个路子，适合跟着复现。

对着学的时候重点看这几块：

- 芯片数据的读取和注释（GPL 探针到基因的映射，这一步最容易出错）
- limma 的三段式：`lmFit` → `eBayes` → `topTable`
- 差异结果的筛选阈值怎么定，logFC 和 adj.P.Val 各管什么
- pheatmap 的参数，行聚类和列聚类什么时候该关掉

### [nf-core/differentialabundance](https://github.com/nf-core/differentialabundance) · 98 ★ · Nextflow

差异丰度分析的标准流程，limma、DESeq2 都在里面。不用真的去跑 Nextflow，看它的文档能知道一个规范的分析应该包含哪些步骤和哪些质控。

---

## 二、工具目录

### [danielecook/Awesome-Bioinformatics](https://github.com/danielecook/Awesome-Bioinformatics) · 4370 ★

生信工具总目录，按用途分类。找工具从这里进比直接搜快，因为已经筛过一轮。

### [seandavi/awesome-single-cell](https://github.com/seandavi/awesome-single-cell) · 3894 ★

单细胞工具和数据集的清单。做单细胞再分析时先在这里看有没有现成的。

---

## 三、绘图

### [loukesio/ggvolc](https://github.com/loukesio/ggvolc) · 73 ★ · R

火山图。直接读 DESeq2、edgeR、limma 的结果，不用自己从 `topTable` 的表格重新拼数据框。还能标记感兴趣的基因，并把基因列表用 gt 排成表格。

---

## 四、搜索方法

GitHub 的搜索框在页面顶部，写着 "Search or jump to"。任意页面按 `/` 也能打开。

真正管用的是限定符，比关键词重要：

```
limma language:R stars:>50 pushed:>2026-01-01
```

| 限定符 | 作用 |
| --- | --- |
| `language:R` | 只要某个语言 |
| `stars:>50` | 星数下限，筛掉没人用的 |
| `pushed:>2026-01-01` | 最近还在更新，筛掉弃坑的 |
| `in:readme` | 在说明文档里搜，比只搜名字准 |
| `topic:rna-seq` | 按标签搜，同类项目排在一起 |

按标签浏览更整齐：`github.com/topics/rna-seq`、`github.com/topics/single-cell`。

看一个仓库值不值得用，先看最后一次提交时间。三年没动的，依赖基本装不上。

---

## 五、数据去哪找

GitHub 上基本没有骨关节炎的分析代码，搜 `osteoarthritis bioinformatics` 只有零星几个论文附属脚本，星数都是个位数。数据和原始代码在别处：

- **GEO**（`ncbi.nlm.nih.gov/geo`）：搜 `osteoarthritis cartilage`，公开的芯片和测序数据都在这里
- **论文 supplementary**：很多期刊要求作者上传分析代码，GitHub 上没有不代表不存在
- **Europe PMC**：查文献和补充材料

---

## 六、待补

- [ ] 单细胞 OA 数据集的整理（GSE172500、GSE220243、GSE255460 这几套先看）
- [ ] 富集分析常用包对比（clusterProfiler 和 fgsea 的分工）
- [ ] 论文配图的规范（字号、配色、导出格式）
