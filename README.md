# 2022-topic-02-team-04: Cancer Hallmark and Metabolic Pathways differ over Cancer types and in Prostate Adenocarcinoma patients

**Contributors:** Fabian Strobel, Lottida Phondeth, Laura Lange, Carla Welz <br>
**Supervisors:** Dr. Carl Herrmann, Wangjun Hu

## Abstract
The complexity of cancer cells has been broken down into certain “hallmarks of cancer” by Hanahan and Weinberg in 2000 and 2011. In this project, it was the goal to further investigate these hallmarks as well as metabolic pathways via a pan-cancer analysis. To tackle these tasks, RNA-seq expression data from “The Cancer Genome Atlas” for various tumor samples was investigated. For a greater understanding of RNA’s impact on a cell, not only genes but also the pathways they are part of were studied. To summarize the gene expression data into pathway activity, Gene Set Variation Analysis dealt as a tool for pathway or gene set scoring. Through dimensionality reduction and clustering, two clusters of cancers that differed in up- and downregulated pathways were identified. The main concern with this analysis is the loss of information, since not every RNA transcript is yet assigned to a known pathway. However, it was possible to predict pathway activity using a multivariate linear regression model.
Besides that, paired RNA-seq data of prostate adenocarcinoma and normal tissue was examined. Prostate cancer itself is the second most common cancer type found in males worldwide. After Gene Set Variation Analysis sixteen pathways showed a significantly, differentially expression within the cancer compared to normal samples. Analyzing the gene ontology of differentially expressed genes illustrated the ubiquitous effects of cancer in cells. Future studies will show how this knowledge can be expanded with epigenetic information or be used to improve diagnosis and therapy.

## Data
During the project four given data sets were used: A list of gene sets for cancer hallmarks and a pan-cancer RNA-seq gene expression data frame for 9,741 patients of 33 various cancer types from “The Cancer Genome Atlas” Research Network: https://www.cancer.gov/tcga. Further, an R-object with 37 clinical annotations regarding the RNA-seq patients and for a focused analysis of PRAD, RNA-seq data of matched tumor and normal tissue of 52 PRAD patients were used. Additionally, 509 gene sets from the Molecular Signatures Database (MSigDB) (Liberzon et al. 2015; Subramanian et al. 2005) were gathered after literature review to get a large overlap with RNA-seq genes, resulting in 555 total gene sets. These include 50 hallmark gene sets (Liberzon et al. 2015), 186 curated gene sets from the KEGG pathway database (Kanehisa 2019; Kanehisa et al. 2021 ; Kanehisa and Goto 2000), 189 oncogenic signature gene sets (Liberzon et al. 2015; Subramanian et al. 2005) and the 84 largest ontology gene sets (Ashburner et al. 2000; GOC 2021; Köhler et al. 2020) as of June 2022.

## Folder structure

**data**: This folder contains the rds.files used during the project (.gitignore).

**descriptive_analysis**: This folder contains mainly plots for descriptive analysis of the given data sets.

**pan_cancer**: This folder contains the analysis of the large pan-cancer RNA-seq.

**prad_normal_vs_tumor**: This folder contains the complete focused analysis of prostate adenocarcinoma.

**preprocessing**: This folder contains the preprocessing files for the pan-cancer data frame.

**references**: This folder contains the .bib file for the citations and the r package citations.

**report_figures**: This folder contains the figures for our final report.
