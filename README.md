# RNAseq_demo

This repository contains a fully worked example of an RNA-seq differential expression analysis in R, including:

- 🧪 Experimental design with replicates and time points  
- 🧬 Count matrix loading from featureCounts  
- 📊 DESeq2 Likelihood Ratio Test (LRT) modeling  
- 📊 DESeq2 Wald test modeling 
- 🧠 Data normalization, PCA, RLE, clustering, and volcano plots  
- 📈 Visual summaries and downstream exploration  

RNA-seq Data from:

```
Meaker GA, Nicholls M, Chahrour C, Hsu I, Smith A, Bozhilov Y, Leung M, Vassort H, Olender L, Beaven O, Huang X, Brown EJ, Vanden Bempt M, Khoo HM, Bhadury J, Milne TA, Wilkinson AC. A genome-wide screen identifies Runx2 as a novel regulator of hematopoietic stem cell expansion and T-cell commitment. Blood. 2025 Dec 25;146(26):3188-3200. doi: 10.1182/blood.2025029115. PubMed PMID: 40961240.
```
---

## 📁 Contents

- `pairwise_example.Rmd` - R markdown containing the full DE analysis pipeline using a Wald pairwise comparison for 2 genotypes with the rendered report `pairwise_example.html`.
- `LRT_timepoint_example.Rmd` — R markdown containing the full DE analysis pipeline using a LRT on 3 genotypes with the rendered report `LRT_timepoint_example.html`.

---

## 🔧 Requirements

You'll need the following R packages (installed via `BiocManager::install()`):

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

2. Open `LRT_timepoint_example.Rmd` in RStudio or VS Code.

3. Adjust the `setwd()` path at the top to match your working environment.

4. Render the report to HTML

---

## 🧪 Analysis Overview

- **Design**: LRT comparing full vs reduced models
- **Transformations**: VST, RLE, PCA
- **Visualizations**: Boxplots, heatmaps, volcano plots, Venn diagrams
- **Interpretation**: P-value distributions, fold change summaries, DE gene overlaps

---

## 📄 Example Output

Once rendered, the HTML report contains:

- Summary of your sample metadata
- Quality control plots (RLE, PCA)
- Differential expression statistics and visualizations
- Overlapping DE genes across time points or conditions
