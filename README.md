# gut_brain
A study on to determine the effects of psychological stress and gut-microbiota on adrenal response.

# Author - Aarushi Bansal
# Date - 15 November 2025
# Time taken to complete the project - Approximately 2 months

The notebook is structured for biologists, bioinformaticians, and computational scientists who work with microarray expression data, particularly from the NCBI Gene Expression Omnibus (GEO).

# Datasets used: 
## 1. GSE122754 - Absence of gut microbial colonization attenuates the sympathoadrenal response to hypoglycemia in mice by Giri P. et al.
## 2. GSE253827 - Psychological Stress-Induced Systemic Corticosterone Directly Sabotages Intestinal Stem Cells Activity by Sheng X. et al.

# Aim: To determine the effects of psychological stress and gut-microbiota on adrenal response.

This repository contains a Jupyter Notebook (`main.ipynb`) that performs differential gene expression analysis comparing **germ-free** and **control** mice using microarray expression data.

# Background
The gut microbiome modulates numerous physiological processes, including immune system maturation, metabolic homeostasis, stress response, and neuroendocrine signaling. Germ-free mice (raised without any microbial exposure) offer a powerful model to study how host gene expression is reshaped in the absence of microbial cues.
This analysis aims to:
- Identify genes in germ-free mice and their effects on adrenal response 
- Identify genes downregulated in stressed mice and their effect on adrenal response
- To narrow down common pathways these genes affect which can provide clues towards the working of gut-mind axis.

# Data Description
The analysis uses microarray expression data from a set of GSM samples retrieved from GEO. The dataset consists of biological replicates from:
1. Germ-free mice from GSE122754 data set
2. Conventional control mice
3. Stressed Mice from GSE253827 data set
The notebook extracts probe-level expression data and organizes it into a structured pandas DataFrame. Sample names are explicitly categorized into experimental groups.

# Overview of the Analysis

The analysis includes:

1. Loading GEO Data
   - Imports expression data from GSM samples.
   - Organizes probes and sample IDs into a pandas DataFrame.

2. Sample Selection - Filtered to remove quality controls, non-coding RNA transcripts, undetermined genes from the analysis

3. Differential Expression Calculation
- For each gene/probe:
  Compute mean expression in GF mice
  Compute mean expression in CV mice
- Calculate fold change
  Fold change = Mean_GF / Mean_CV
  Values >1 indicate upregulation in GF
  Values <1 indicate downregulation in GF

5. Output
   - Prints ranked tables for the most significantly regulated genes.
     
6. Gene Ontology, KEGG Ananlysis and Reactome analysis was done on DAVID profiler by using the genes found. The raw data was downloaded and plotted in the Jupyter notebook

# Main findings 
1. Cellular response to calcium ions and GTPase activity has been enriched in the absence of gut microbiota. 
2. Circadian rhythm processes in the adrenal cells have been enriched in presence of stress which may indicate sleep disturbances.
3. The common enriched KEGG pathway from the affected genes is regulation of lipolysis in adipocytes. The reactome pathways affected - G alpha signalling events and clathrin mediated endocytosis.
   # Please note - These results are not as statistically significant as they should be however, these provide clues as to how this project can be expanded. Due to limited data available this project could not be expanded.


# Files

- `main.ipynb` — Full analysis notebook.
- `README.md` — This documentation file.

# How to Run

1. Install dependencies:
   ```bash
   pip install pandas numpy
   ```
2. Open the notebook:
   ```bash
   jupyter notebook main.ipynb
   ```
3. Run all cells to reproduce the results.


---

Feel free to extend the notebook with visualizations, volcano plots, or pathway enrichment!

