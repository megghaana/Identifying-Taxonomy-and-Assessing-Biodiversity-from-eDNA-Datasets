# Identifying Taxonomy and Assessing Biodiversity from eDNA Datasets

## Project Overview

This project leverages **DNABERT embeddings**, **HDBSCAN clustering**, and **UMAP dimensionality reduction** to identify taxonomic structure and assess biodiversity patterns from environmental DNA (eDNA) datasets.

Using deep learning-based DNA sequence embeddings, we perform unsupervised clustering to explore biological relationships and evaluate cluster quality using standard metrics.

---

## Objectives

- Extract SSU rRNA sequences from NCBI (Cnidaria dataset)
- Generate k-mer features and DNABERT embeddings
- Perform unsupervised clustering using HDBSCAN
- Visualize biodiversity structure using 2D & 3D UMAP
- Evaluate clustering performance using:
  - Silhouette Score
  - Davies–Bouldin Index
  - Calinski–Harabasz Score

---

## Methodology

### 1️. Data Acquisition
- Retrieved nucleotide sequences from NCBI using Biopython's Entrez API
- Extracted sequence and taxonomic metadata
- Stored sequences in FASTA format

### 2️. Feature Engineering
Two feature representations were explored:
- 4-mer frequency vectors
- DNABERT embeddings (`zhihan1996/DNA_bert_6`)

DNABERT embeddings were used for final clustering due to superior representation power.

### 3️. Clustering
- Algorithm: **HDBSCAN**
- Handles noise points automatically
- No need to predefine number of clusters

### 4️. Dimensionality Reduction
- UMAP (2D & 3D)
- Euclidean metric
- Used for biological structure visualization

### 5️. Evaluation Metrics
Clustering performance was evaluated excluding noise samples:

- **Silhouette Score**
- **Davies–Bouldin Index**
- **Calinski–Harabasz Score**

---

## Results

The clustering successfully grouped sequences according to taxonomic similarity, with distinct biodiversity patterns emerging in 3D UMAP space.

Interactive 3D visualization available in: umap_3d_clusters.html


Download and open in browser for full interactivity.

---

## Visualizations

- 2D UMAP (Cluster-based)
- 3D UMAP (Cluster-based)
- 3D UMAP (Organism-based)

Interactive visualization is included as an HTML file.

---

## Tech Stack

- Python
- Biopython
- HuggingFace Transformers
- PyTorch
- HDBSCAN
- UMAP
- Scikit-learn
- Plotly
- Seaborn
- Matplotlib

---

## Repository Structure
├── eDNA.ipynb

├── umap_3d_clusters.html

├── .gitignore

├── README.md

---

## Installation

```bash
pip install biopython pandas numpy torch transformers hdbscan umap-learn scikit-learn matplotlib seaborn plotly
