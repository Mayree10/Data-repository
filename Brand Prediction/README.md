# Brand Prediction from Particle Image Data

This project focuses on identifying likely explosive brands from particle measurements collected in queries. We use clustering, classification, and similarity matching methods to assign unknown particles to known brands, distinguishing watchlist items from general background noise.

## Overview

We analyze particle data using:

- **Model-based clustering (Mclust)** to detect structure in the query datasets
- **Cluster-to-brand comparison** using Euclidean distances to known watchlist items
- **Downsampling strategies** to simulate realistic background distributions
- **Classification models** (Random Forest, LDA, kNN) to predict likely sources

The pipeline is applied to three query datasets (`query_1.csv`, `query_2.csv`, `query_6.csv`) and compared against:

- `unexploded_watchlist.csv` – labeled particles from known explosive brands
- `background_data.csv` – non-threatening environmental particles

---

## Key Steps

### 1. Clustering

Each query dataset is clustered using **Gaussian Mixture Models** via `mclust`. Cluster quality is assessed with silhouette scores. 

### 2. Cluster Comparison

Each cluster's average features (`Area`, `Perim.`, `Major`, `Minor`) are compared to known brand centers using Euclidean distance. This helps match unknown particles to the closest brand.

### 3. Background Downsampling

Two approaches are used to create a realistic non-watchlist training class:
- **Random sampling** across the entire background set
- **Brand-filtered sampling** based on background brands closest to query clusters

### 4. Classification

Classifiers are trained to distinguish watchlist brands from background:
- **Random Forest** (with cross-validation)
- **Linear Discriminant Analysis (LDA)** – with and without CV

Accuracy is measured through cross-validation and binomial testing.

---

## Results Summary

- Clustering revealed meaningful substructure in all three queries.
- Cluster-to-brand mapping provided interpretable insights into likely brand origins.
- The **filtered downsampling** method generally improved classifier precision over random sampling.
- The **Random Forest** model outperformed LDA in cross-validated accuracy.

---

## Technologies

- **R**
- `mclust`, `caret`, `ranger`, `MASS`
- Visualized using `ggplot2`, `cluster`

---

## Files

- /Brand Prediction/Project Code: Full analysis code
- Input: `.csv` files for query, watchlist, and background data

