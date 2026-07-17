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
