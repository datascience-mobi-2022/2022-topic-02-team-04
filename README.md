# 2022-topic-02-team-04: prostate adenocarcinoma (PRAD)

# Abstract
The complexity of cancer cells has been broken down by the defined “Hallmarks of cancer”. In this project, it is the goal to further investigate these hallmarks of cancer as well as metabolic pathways via a pan-cancer analysis. In order to tackle these tasks, we make use of the given gene expression data stemming from various tumor samples. It is of great interest to find cancer-specific gene expression patterns with the help of so-called gene enrichment analysis such as the Gene Set Variance Analysis (GSVA) or the Gene Set Enrichment Analysis (GSEA) next to other methods we used along the way. Besides that, we took a closer look at prostate adenocarcinoma (PRAD). 
Prostate cancer itself is the second most common cancer type found in males worldwide – making up about 1.4 million cases of the 10.1 million new cases of all combined cancers diagnosed in males. While there are treatment options such as hormone deprivation therapy or radiation therapy, a specific cure has not been found yet. For this reason, it was important to find gene expression differences between normal prostate cells and cancerous prostate cells. Lastly, based on our generated pathway activity matrix, we wanted to predict the activity of a specific pathway.

## Folder structure

**data**: This folder contains the rds.files used during the project (.gitignore)

**descriptive_analysis**: This folder contains mainly plots for descriptive analysis of the given data sets.

**pan_cancer**: This folder contains the analysis of the large pan-cancer RNAseq

**prad_normal_vs_tumor**: This folder contains the complete focused analysis of prostate adenocarcinoma.

**preprocessing**: This folder contains the preprocessing files for the pan-cancer data frame.

**refrences**: This folder contains the .bib file for the citations and the r package citations
