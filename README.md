# Functional-S-persulfidation-Exploration_Figures
Code and data for reproducing Figures 1 and 2 in our manuscript "Functional S-persulfidation Exploration Reveals a Novel Regulatory Mechanism of HNF1α"
Multi-Omics Data Analysis and Visualization

# Multi-Omics Data Analysis and Visualization

This repository contains R scripts for comprehensive multi-omics data analysis, including GO enrichment, proteomics PaxDb mapping, pie chart visualization, chord diagram, and word cloud generation.  
All analyses use input data stored in the `data/` folder and produce outputs in the `results/` folder.

---

## Table of Contents

- [Environment Requirements](#environment-requirements)  
- [Directory Structure](#directory-structure)  
- [Data Preparation](#data-preparation)  
- [Analysis Scripts](#analysis-scripts)  
- [Outputs](#outputs)  
- [Citations and References](#citations-and-references)  

---

## Environment Requirements

The analyses require **R ≥ 4.3** and the following R packages:

# Core packages
install.packages(c("readxl", "openxlsx", "dplyr", "tidyr", "ggplot2", 
                   "RColorBrewer", "wordcloud", "tm", "biomaRt"))

# Bioconductor packages
if (!require("BiocManager")) install.packages("BiocManager")
BiocManager::install(c("clusterProfiler", "org.Hs.eg.db", "org.Mm.eg.db", 
                       "org.At.tair.db", "AnnotationDbi", "circlize"))

---

## Directory Structure

The repository is organized as follows:

├── data/             # Input data files (Excel, CSV, etc.)
├── results/          # Output results (PDFs, plots, tables)
├── scripts/          # R Markdown (.Rmd) analysis scripts
├── README.md         # Project documentation

---

## Data Preparation

- All input data must be placed in the `data/` folder.  
- Example datasets are provided in supplementary materials for each figure.  
- Ensure that column names match the expected format in the scripts (see comments in each `.Rmd`).  

---

## Analysis Scripts

The main analysis scripts are provided as `.Rmd` files under `scripts/`:

1. GO Enrichment Analysis  
   Performs GO enrichment for human, mouse, and Arabidopsis datasets using *clusterProfiler*.  

2. Proteomics PaxDb Mapping  
   Maps protein abundance information from PaxDb and visualizes distributions.  

3. Pie Chart Visualization  
   Summarizes functional categories as proportions.  

4. Chord Diagram  
   Compares organ-specific protein oxidation differences and visualizes using `circlize`.  

5. Word Cloud Generation  
   Extracts enriched GO terms and generates keyword clouds with highlighted biological processes.  

Each script outputs figures or tables into the `results/` folder.

---

## Outputs

- All results (PDFs, PNGs, tables) are saved in the `results/` directory.  
- File names correspond to the figure or analysis type (e.g., `Figure1A_GO_BP.pdf`, `organ_chord_diagram.pdf`).  

---

## Citations and References

If you use this repository, please cite the following tools:

- Yu G, Wang LG, Han Y, He QY. (2012). **clusterProfiler: an R package for comparing biological themes among gene clusters.** *OMICS: A Journal of Integrative Biology*, 16(5), 284–287.  
- Wang M, Herrmann CJ, Simonovic M, Szklarczyk D, von Mering C. (2015). **PaxDb, a database of protein abundance averages across all three domains of life.** *Nature Biotechnology*, 33(1), 117–118.  
- Gu Z, Gu L, Eils R, Schlesner M, Brors B. (2014). **circlize implements and enhances circular visualization in R.** *Bioinformatics*, 30(19), 2811–2812.  
- Fellows I. (2018). **wordcloud: Word Clouds.** R package version 2.6, CRAN.  
