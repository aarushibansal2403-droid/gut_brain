# Gut–Brain Axis Analysis: Microbiota, Stress & Adrenal Gene Expression

A computational analysis exploring how **psychological stress** and **gut microbiota composition** influence the **adrenal response** in mice.

**Author:** Aarushi Bansal  
**Date:** 15 November 2025  
**Project Duration:** ~2 months  

---

## Overview

This repository contains a Jupyter Notebook (`main.ipynb`) that performs a comparative gene expression analysis using **microarray datasets** from the NCBI Gene Expression Omnibus (GEO).  
It is designed for **biologists, bioinformaticians, and computational scientists** investigating host–microbiome interactions, stress biology, or adrenal signaling pathways.

---

## Datasets Used

### **1. GSE122754**  
*“Absence of gut microbial colonization attenuates the sympathoadrenal response to hypoglycemia in mice”*  
**Authors:** Giri P. et al.

### **2. GSE253827**  
*“Psychological Stress-Induced Systemic Corticosterone Directly Sabotages Intestinal Stem Cell Activity”*  
**Authors:** Sheng X. et al.

These datasets enable parallel investigation of:

- Effects of **germ-free (GF)** status on adrenal gene expression  
- Effects of **psychological stress** on adrenal and intestinal pathways  


## Aim of the Project

To determine how:

1. **Absence of gut microbiota** affects adrenal gene expression  
2. **Psychological stress** downregulates key adrenal or systemic regulatory genes  
3. Identify **common pathways** disrupted in both conditions to gain insight into the **gut–brain axis**


## Background

The gut microbiome influences:

- Neuroendocrine signaling  
- Sympathoadrenal response  
- Immune regulation  
- Metabolic homeostasis  
- Stress adaptation  

Germ-free mice—a model lacking all microbial exposure—provide a clean system to isolate microbe-driven transcriptional changes.

Psychological stress triggers corticosterone release and impacts peripheral tissues, including adrenal and intestinal cells.

This study integrates both aspects to highlight **microbiome–stress interactions**.


## Data Description

The notebook processes microarray probe-level expression data from biological replicates, including:

- **Germ-free mice**
- **Conventional controls**
- **Stressed mice**

Preprocessing steps include:

- Organizing probe tables into a pandas DataFrame  
- Removing:
  - QC probes  
  - Non-coding transcripts  
  - Unannotated probes  


## Analysis Workflow

### **1. Loading GEO Data**

- Reads GSM expression tables  
- Merges probes into a consistent matrix  
- Assigns sample metadata manually  

### **2. Differential Expression**

For each probe:

- Mean expression in GF mice  
- Mean expression in controls  
- Fold change calculated as:  
  \[
  \text{Fold Change} = \frac{\text{Mean}_\text{GF}}{\text{Mean}_\text{CV}}
  \]

Interpretation:

- **Fold change > 1.0:** Upregulated in GF  
- **Fold change < 1.0:** Downregulated in GF  

### **3. Output Summary**

- Top upregulated genes  
- Top downregulated genes  
- Full DataFrame of fold-change values  

### **4. Functional Enrichment**

Performed using **DAVID**, including:

- Gene Ontology (GO)  
- KEGG Pathways  
- Reactome Pathways  

Visualization of results is done in the notebook.


## Main Findings

### **1. Germ-Free vs Control Mice**
- Enrichment in **cellular response to calcium ions**  
- Enrichment in **GTPase activity**, suggesting altered signaling  
- Several genes involved in neuroendocrine function appear microbially regulated  

### **2. Control vs Stressed Mice**
- Enrichment in **circadian rhythm processes**, suggesting stress-induced chronobiology disruption  
- Altered expression in genes associated with adrenal and metabolic regulation  

### **3. Common Pathways**
Shared/overlapping pathways from both datasets:

- **Regulation of lipolysis in adipocytes (KEGG)**  
- **G alpha signaling events (Reactome)**  
- **Clathrin-mediated endocytosis (Reactome)**  

These may represent nodes connecting microbiome cues to stress physiology.


## Limitations

- Small dataset size  
- Microarray (not RNA-seq), lower dynamic range  
- Fold-change only (no statistical testing like limma or adjusted p-values)  

Despite limitations, the results offer **hypothesis-generating insights**.

## Files in This Repository

- `main.ipynb` — analysis notebook  
- `README.md` — this documentation  

## How to Run

### Install dependencies:
```bash
pip install pandas numpy
```

### Open the notebook:
```bash
jupyter notebook main.ipynb
```

### Run all cells
to reproduce the workflow and generate figures and enrichment plots.

## Future Improvements

- limma-based differential expression  
- Principal Component Analysis (PCA)  
- Integration with cortisol/corticosterone measurements  
- Expanding to RNA-seq datasets  

## Final Note

This project provides a foundational computational framework for exploring connections between **microbiota**, **stress**, and **adrenal signaling**—a key axis in gut–brain research.

