---
layout: page
title: Yuchen Yang's feature researches
---

### Aggregated Clustering Method for Single-cell RNA-seq Data

I developed SAFE-clustering and SAME-clustering, a flexible, accurate and robust method for single-cell aggregated (From Ensemble) clustering. 
SAFE and SAME both build a consensus clustering solution from solutions of multiple types of individual clustering methods, 
including SC3, CIDR, Seurat and t-SNE + k-means. SAFE performs ensemble clustering using three hypergraph-based partitioning 
algorithms, and SAME applies EM algorithm in ensemble step.

Our analyses revealed that both SAFE and SAME provided the most accurate or closest match to the most accurate clustering solutions across 
benchmarking datasets with varying technologies, number of single cells and level of heterogeneity across single cells. SAME also allows additional flexibility, 
enjoys statistical rigor by employing a mixture model framework and demonstrates superior performance over 15 benchmark datasets [4].

### Batch Effect Correction for scRNA-seq data via Supervised Mutual Nearest Neighbor (SMNN) Detection

An ever-increasing deluge of scRNA-seq data has been generated, often involving different time points, laboratories or sequencing protocols. Batch effect correction has been recognized to be indispensable when integrating scRNA-seq data from multiple batches. A recent study proposed an effective batch effect correction method based on mutual nearest neighbors (MNN) across batches [5]. However, the original MNN method is unsupervised in that it ignores cluster label information of single cells, which has the potential to further improve effectiveness of batch effect correction, particularly under realistic scenarios where true biological differences are not orthogonal to batch effect. Therefore, I propose SMNN for batch effect correction of scRNA-seq data via supervised mutual nearest neighbor detection. SMNN either takes cluster/cell-type label information as input or infers cell types using scRNA-seq clustering. It then detects mutual nearest neighbors within matched cell types and corrects batch effect accordingly. Compared to MNN, SMNN provides improved merging within the corresponding cell types across batches. The cells from the same cell type across the two batches are closer (2.8 - 8.2%; measured by Euclidean distance) after SMNN correction than MNN. Moreover, in all three benchmarking real datasets attempted so far, SMNN retains more cell type specific features after correction.
