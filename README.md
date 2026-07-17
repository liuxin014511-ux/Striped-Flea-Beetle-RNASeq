# Striped-Flea-Beetle-UVB-RNASeq
Screening for specific gene
Transcriptome Analysis Pipeline for Developmental Stages
Introduction
This repository contains a comprehensive R-based bioinformatics pipeline designed for RNA-seq data analysis across different experimental groups or developmental stages (e.g., in Phyllotreta striolata).

The script automates the downstream analysis of transcriptomic data, starting from a normalized expression matrix (TPM/FPKM). It is specifically tailored to identify stage-specific or sex-specific expressed genes using stringent filtering criteria, while also providing high-quality, publication-ready visualizations.

Key Features
Automated Data Parsing: Automatically aligns expression matrices with sample metadata and maps experimental groups.

Stage-Specific Gene Identification: Implements strict fold-change and expression threshold rules to isolate genes uniquely expressed in specific developmental stages.

Hierarchical Clustering Heatmaps: Utilizes ComplexHeatmap to visualize specific gene expression patterns with robust clustering (Euclidean distance + Complete linkage).

Principal Component Analysis (PCA): Performs PCA on log-transformed data to assess sample variance and group clustering.

Pairwise Differential Expression (DEG): Calculates custom pairwise fold-changes and p-values, visualizing results through highly customized, combined volcano plots using patchwork.

Sample Correlation Assessment: Generates Pearson correlation matrices and annotates heatmaps via pheatmap to validate biological replicates.
Operation Workflow & Usage
1. Prerequisites
Ensure you have R (version >= 4.0) installed. The script includes an automated environment preparation chunk that will check for and install any missing required packages (from CRAN and Bioconductor), including:
dplyr, tidyr, matrixStats, ggplot2, patchwork, pheatmap, ComplexHeatmap, circlize, RColorBrewer, and EnhancedVolcano.

2. Input Data Preparation
Place the following two CSV files in your working directory:

gene_tpm_matrix.csv: A numeric expression matrix (e.g., TPM).

Row names: Gene IDs.

Column names: Sample IDs.

all_samples_metadata.csv: The sample metadata file.

Must contain at least two columns named exactly: id (matching matrix column names) and group (developmental stage/treatment).

3. Running the Pipeline
Clone or download this repository.

Open the R script Transcriptome_Analysis_Pipeline.R.

Modify the working directory path in Section 1 to point to your data folder:

R


setwd("path/to/your/working_directory")
Run the entire script. The pipeline will automatically loop through your designated groups and comparisons.

4. Expected Outputs
Upon successful execution, the script will generate and save the following files into your working directory:

Data Tables (.csv):

[Group]_FC_strict_stage_specific_genes.csv: Gene lists for each specific stage.

All_Stage_Specific_Genes_Summary.csv: A combined summary of all stage-specific genes.

DEG_Result_[GroupA]_vs_[GroupB].csv: Pairwise differential expression results.

Publication-Ready Figures (.pdf / .png):

Stage_Specific_Genes_ComplexHeatmap.pdf: Clustering heatmap of identified specific genes.

Sample_PCA_Plot.pdf: PCA plot of all samples.

Volcano_Style2_[GroupA]_vs_[GroupB].pdf: Individual customized volcano plots.

All_Volcano_Combined.pdf / .png: A compiled grid of all pairwise volcano plots.

Sample_Correlation_Heatmap.pdf: Pearson correlation heatmap across biological replicates.
