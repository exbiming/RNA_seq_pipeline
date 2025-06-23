# 分享我的 RNA_seq_pipeline

## 以下简述本代码流程：

##### 001 创建环境，准备参考文件

##### 002 数据导入 → 质控(fastp) → 比对（hisat2） → 排序(samtools) → 定量(featureCounts or Stringtie) → 计算FPKM（推荐用normalized_counts.csv）

##### 003 差异分析：DESeq2 → 用Excel对.csv结果文件进行筛选。

##### 003.x 差异分析变体：DESeq2-双因素差异分析， DESeq2-Likelihood Ratio Test，EdgeR-无重复样本差异分析，EdgeR-重复样本差异分析



## pipeline结果文件一览：

##### fastp质控报告：.fastp.log，.fastp.html，.fastp.json
##### hisat2比对率：.maprate.txt
##### samtools结果：.sorted.bam（排序），.sorted.bam.bai（索引）
##### featureCounts结果：expression_matrix.txt (表达量.原始), expression.txt (表达量.纯净)，expression_matrix.txt.summary (报告)
##### Deseq2结果：.csv (差异基因)，normalized_counts.csv (标准化表达量)，rlog_counts.csv (rlog变换后的表达量，用于热图、PCA等)，MA_.pdf，PCA_.pdf


#### ------------------------------------------
#### Usage：
The pipeline was adapted from https://github.com/exbiming/RNA_seq_pipeline.git.

推动科学进步，促进技术交流。
