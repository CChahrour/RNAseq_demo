# RNAseq_demo

This repository contains a fully worked example of an RNA-seq differential expression analysis in R, including:

- Experimental design with replicates and genotype
- Count matrix loading from featureCounts
- DESeq2 likelihood ratio test (LRT) modeling
- DESeq2 Wald test modeling
- Data normalization, PCA, RLE, clustering, and volcano plots
- Visual summaries and downstream exploration

RNA-seq data from:

> Meaker GA, Nicholls M, Chahrour C, et al. A genome-wide screen identifies *Runx2* as a novel regulator of hematopoietic stem cell expansion and T-cell commitment. *Blood*. 2025;146(26):3188-3200. doi:[10.1182/blood.2025029115](https://doi.org/10.1182/blood.2025029115). PMID:[40961240](https://pubmed.ncbi.nlm.nih.gov/40961240/).

---

## 📁 Contents

- [`pairwise_example.Rmd`](pairwise_example.Rmd) - R Markdown containing a DESeq2 Wald-test workflow for the pairwise `het` vs `wt` genotype comparison, with the rendered report in [`pairwise_example.html`](pairwise_example.html).
- [`LRT_timepoint_example.Rmd`](LRT_timepoint_example.Rmd) - R Markdown containing a DESeq2 LRT workflow across the `hom`, `het`, and `wt` genotypes, with the rendered report in [`LRT_timepoint_example.html`](LRT_timepoint_example.html).

---

## 🔧 Requirements

You'll need the following R packages:

```r
library(DESeq2)
library(ComplexHeatmap)
library(ggplot2)
library(dplyr)
library(tidyverse)
library(reshape2)
library(ggrepel)
library(RColorBrewer)
library(limma)
library(qvalue)
library(circlize)
```

---

## 🚀 Getting Started

1. Clone this repo:

   ```bash
   git clone https://github.com/CChahrour/RNAseq_demo.git
   cd RNAseq_demo
   ```

2. Open either `LRT_timepoint_example.Rmd` or `pairwise_example.Rmd` in RStudio or VS Code.

3. Adjust the `setwd()` path at the top to match your working environment.

4. Render the report to HTML.

---

## 🧪 Analysis Overview

- **Design**: Wald testing for `het` vs `wt`, plus LRT comparing the full `~ genotype` model against the reduced `~ 1` model across `hom`, `het`, and `wt`
- **Transformations**: VST, RLE, PCA
- **Visualizations**: Boxplots, heatmaps, volcano plots, Venn diagrams
- **Interpretation**: P-value distributions, fold change summaries, DE gene overlaps

---

## 📄 Example Output

Once rendered, each HTML report contains:

- Summary of your sample metadata
- Quality control plots (RLE, PCA)
- Differential expression statistics and visualizations
- Overlapping DE genes across genotype comparisons


## Citation
DESeq2 method reference:

> Love MI, Huber W, Anders S. Moderated estimation of fold change and dispersion for RNA-seq data with DESeq2. *Genome Biology*. 2014;15(12):550. doi:[10.1186/s13059-014-0550-8](https://doi.org/10.1186/s13059-014-0550-8). PMID:[25516281](https://pubmed.ncbi.nlm.nih.gov/25516281/).