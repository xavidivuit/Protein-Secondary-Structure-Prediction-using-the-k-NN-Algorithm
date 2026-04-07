# Protein-Secondary-Structure-Prediction-using-the-k-NN-Algorithm
Prediction of protein secondary structure (α-helix, β-sheet, coil) from amino acid sequences using the k-Nearest Neighbors algorithm.

# Overview
Each sample consists of a sliding window of 17 consecutive amino acids extracted from known proteins. The goal is to predict the secondary structure of the central residue (position 9) based on its local sequence context. Amino acids are encoded using one-hot encoding, resulting in a 340-dimensional feature vector per sample.

# Requirements
Python ≥ 3.8
Packages: scikit-learn, numpy, pandas, matplotlib, seaborn

# Dataset
**Source:** [UCI Machine Learning Repository — Molecular Biology (Protein Secondary Structure)](https://archive.ics.uci.edu/ml/datasets/Molecular+Biology+(Protein+Secondary+Structure))

**File:** `data4.csv` — 10,000 samples, semicolon-separated

**Classes:** α-helix (`h`), β-sheet (`e`), coil (`_`)

**Class distribution:** coil 55.6% · α-helix 25.1% · β-sheet 19.4%

# Methods
**Algorithm:** k-Nearest Neighbors (k-NN) with Euclidean distance

**Feature encoding:** one-hot (17 positions × 20 amino acids = 340 features)

**Train/test split:** 80/20 with stratified sampling (`random_state = 42`)

**Values of k evaluated:** {1, 3, 5, 7, 9, 11, 15, 21}

**Metrics:** accuracy, Cohen's kappa, precision, recall, F1-score, ROC/AUC (one-vs-rest)

# Results

Best model: **k = 1**

| k  | Accuracy | Cohen's Kappa |
|----|----------|---------------|
| 1  | 0.770    | 0.612         |
| 3  | 0.727    | 0.522         |
| 5  | 0.697    | 0.458         |
| 7  | 0.680    | 0.424         |
| 9  | 0.664    | 0.382         |
| 11 | 0.640    | 0.328         |
| 15 | 0.636    | 0.307         |
| 21 | 0.619    | 0.256         |

Per-class performance at k = 1:

| Class       | Precision | Recall | F1   | AUC   |
|-------------|-----------|--------|------|-------|
| α-helix (h) | 0.72      | 0.75   | 0.74 | 0.827 |
| β-sheet (e) | 0.68      | 0.66   | 0.67 | 0.793 |
| Coil (\_)   | 0.83      | 0.82   | 0.82 | 0.800 |
| Macro avg   | 0.74      | 0.74   | 0.74 | 0.807 |

# Usage

Open the notebook and run all cells:

```bash
jupyter notebook "Protein Secondary Structure Prediction using the k-NN Algorithm.ipynb"
```

Make sure `data4.csv` is in the same directory as the notebook.
# Project Structure

| File | Description |
|------|-------------|
| `.gitattributes` | Python |
| `data4.csv` | Dataset (10,000 samples) |
| `Protein Secondary Structure Prediction using the k-NN Algorithm.ipynb` | Main notebook |
| `README.md` | Project documentation |
