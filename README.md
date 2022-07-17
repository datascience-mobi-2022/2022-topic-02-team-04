# 2022-topic-02-team-04: Cancer Hallmark and Metabolic Pathways differ over Cancer types and in Prostate Adenocarcinoma patients

**Contributors:** Fabian Strobel, Lottida Phondeth, Laura Lange, Carla Welz <br>
**Supervisors:** Dr. Carl Herrmann, Wangjun Hu

## Abstract
The complexity of cancer cells has been broken down by the defined “Hallmarks of cancer”. In this project, it is the goal to further investigate these hallmarks of cancer as well as metabolic pathways via a pan-cancer analysis. In order to tackle these tasks, we make use of the given gene expression data stemming from various tumor samples. It is of great interest to find cancer-specific gene expression patterns with the help of so-called gene enrichment analysis such as the Gene Set Variance Analysis (GSVA) or the Gene Set Enrichment Analysis (GSEA) next to other methods we used along the way. Besides that, we took a closer look at prostate adenocarcinoma (PRAD). 
Prostate cancer itself is the second most common cancer type found in males worldwide – making up about 1.4 million cases of the 10.1 million new cases of all combined cancers diagnosed in males. While there are treatment options such as hormone deprivation therapy or radiation therapy, a specific cure has not been found yet. For this reason, it was important to find gene expression differences between normal prostate cells and cancerous prostate cells. Lastly, based on our generated pathway activity matrix, we wanted to predict the activity of a specific pathway.

## Data
During the project four given data sets were used: A list of gene sets for cancer hallmarks and a pan-cancer RNA-seq gene expression data frame for 9,741 patients of 33 various cancer types from “The Cancer Genome Atlas” Research Network: https://www.cancer.gov/tcga. Further, an R-object with 37 clinical annotations regarding the RNA-seq patients and for a focused analysis of PRAD, RNA-seq data of matched tumor and normal tissue of 52 PRAD patients were used. Additionally, 509 gene sets from the Molecular Signatures Database (MSigDB) (Liberzon et al. 2015; Subramanian et al. 2005) were gathered after literature review to get a large overlap with RNA-seq genes, resulting in 555 total gene sets. These include 50 hallmark gene sets (Liberzon et al. 2015), 186 curated gene sets from the KEGG pathway database (Kanehisa 2019; Kanehisa et al. 2021 ; Kanehisa and Goto 2000), 189 oncogenic signature gene sets (Liberzon et al. 2015; Subramanian et al. 2005) and the 84 largest ontology gene sets (Ashburner et al. 2000; GOC 2021; Köhler et al. 2020) as of June 2022.

## Folder structure

**data**: This folder contains the rds.files used during the project (.gitignore)

**descriptive_analysis**: This folder contains mainly plots for descriptive analysis of the given data sets.

**pan_cancer**: This folder contains the analysis of the large pan-cancer RNA-seq.

**prad_normal_vs_tumor**: This folder contains the complete focused analysis of prostate adenocarcinoma.

**preprocessing**: This folder contains the preprocessing files for the pan-cancer data frame.

**references**: This folder contains the .bib file for the citations and the r package citations.

**report_figures**: This folder contains the figures for our final report.
