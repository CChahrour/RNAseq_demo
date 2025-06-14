# RNAseq_demo

This repository contains a fully worked example of an RNA-seq differential expression analysis in R, including:

- 🧪 Experimental design with replicates and time points  
- 🧬 Count matrix loading from featureCounts  
- 📊 DESeq2 Likelihood Ratio Test (LRT) modeling  
- 🧠 Data normalization, PCA, RLE, clustering, and volcano plots  
- 📈 Visual summaries and downstream exploration  

---

## 📁 Contents

- `LRT_timepoint_example.Rmd` — Quarto report containing the full DE analysis pipeline  
- `full_design.csv` — Metadata file with sample annotations (treatment, time, replicate, etc.)  
- `seqnado_output/` — Expected directory for count matrix input from [SeqNado](https://github.com/CChahrour/SeqNado)  

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

4. Adjust the sample_info to match the experimental design

5. Render the report to HTML

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
