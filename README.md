# Functional-S-persulfidation-Exploration_Figures
Code and data for reproducing Figures 1 and 2 in our manuscript "Functional S-persulfidation Exploration Reveals a Novel Regulatory Mechanism of HNF1α"
# Multi-Omics Data Analysis and Visualization

This repository contains R scripts for comprehensive multi-omics data analysis, including GO enrichment, proteomics PaxDb mapping, pie chart visualization, chord diagram, and word cloud generation. All analyses use input data stored in the `data/` folder and produce outputs in the `results/` folder.

---

## Table of Contents

1. [Environment Requirements](#environment-requirements)  
2. [Directory Structure](#directory-structure)  
3. [Data Preparation](#data-preparation)  
4. [Analysis Scripts](#analysis-scripts)  
5. [Outputs](#outputs)  
6. [Citation / References](#citation--references)

---

## Environment Requirements

The analyses require R ≥ 4.3 and the following R packages:

```r
# Core packages
install.packages(c("readxl", "openxlsx", "dplyr", "tidyr", "ggplot2", "RColorBrewer", "wordcloud", "tm", "biomaRt"))

# Bioconductor packages
if (!require("clusterProfiler")) BiocManager::install("clusterProfiler")
if (!require("org.Hs.eg.db")) BiocManager::install("org.Hs.eg.db")
if (!require("org.Mm.eg.db")) BiocManager::install("org.Mm.eg.db")
if (!require("org.At.tair.db")) BiocManager::install("org.At.tair.db")
if (!require("AnnotationDbi")) BiocManager::install("AnnotationDbi")
if (!require("circlize")) BiocManager::install("circlize")

---

## Directory Structure
├── data/                # Input data files
│   ├── Human_protein.xlsx
│   ├── Mouse_protein.xlsx
│   ├── Arabidopsis_protein.xlsx
├── results/             # Output files (Excel, PDF, figures)
│   ├── Human_GO_CC_MF_result.xlsx
│   ├── Mouse_GO_BP_result.xlsx
│   ├── Arabidopsis_GO_CC_MF_result.xlsx
├── scripts/             # R scripts or Rmd files
├── README.md            # This file

---

## Data Preparation
Place all input Excel files in the data/ folder.

Ensure column names match those expected in each script:

GO enrichment: uniprot_id (Human/Mouse) or TAIR (Arabidopsis)

PaxDb mapping: uniprot_id for proteins

Chord diagram: first column is AC_site, subsequent columns are organs

Word cloud: column elements containing text strings

Example datasets are provided in the supplementary materials corresponding to each figure.
Analysis Scripts

---

## Analysis Scripts
GO Enrichment Analysis (Human, Mouse, Arabidopsis):

Uses clusterProfiler and organism-specific annotation packages.

Supports Cellular Component (CC), Molecular Function (MF), and Biological Process (BP).

Produces Excel tables and PDF barplots/dotplots.

PaxDb Protein Abundance Mapping:

Maps UniProt IDs to Ensembl peptide IDs and PaxDb IDs.

Merges with PaxDb abundance data.

Outputs matched protein abundance tables in Excel.

Pie Chart Visualization:

Computes element contributions across subsets.

Plots pie chart of subset contribution using ggplot2.

Chord Diagram of Organ Differences:

Computes pairwise differences for AC sites across organs.

Plots chord diagram using circlize.

Word Cloud Generation:

Generates word cloud from GO terms or text elements.

Can highlight specific keywords.

Outputs PDF figure.

All scripts are designed to read input from data/ and save outputs in results/.
Outputs

---

## Outputs

Excel summary files (results/*.xlsx)

PDF figures for GO enrichment, pie charts, chord diagrams, and word clouds (results/*.pdf)

---

## References

Yu, G., Wang, L.G., Han, Y., et al. (2012). clusterProfiler: An R Package for Comparing Biological Themes among Gene Clusters. OMICS: A Journal of Integrative Biology, 16(5), 284-287. DOI: 10.1089/omi.2011.0118

Wang, M., Herrmann, C.J., Simonovic, M., et al. (2015). Version 4.0 of PaxDb: Protein Abundance Data, Integrated Across Model Organisms, Tissues, and Cell-Lines. Proteomics, 15(18), 3163-3168. DOI: 10.1002/pmic.201400441

Gu, Z., et al. (2014). circlize Implements and Enhances Circular Visualization in R. Bioinformatics, 30(19), 2811-2812. DOI: 10.1093/bioinformatics/btu393

Fellows, I. (2018). wordcloud: Word Clouds. R package version 2.6. CRAN: wordcloud

Notes

Ensure R working directory is set to the repository root.

All scripts assume input data in data/ and will automatically save results to results/.
