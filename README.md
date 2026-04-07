# Protein-Secondary-Structure-Prediction-using-the-k-NN-Algorithm
Prediction of protein secondary structure (α-helix, β-sheet, coil) from amino acid sequences using the k-Nearest Neighbors algorithm.

# Overview
Each sample consists of a sliding window of 17 consecutive amino acids extracted from known proteins. The goal is to predict the secondary structure of the central residue (position 9) based on its local sequence context. Amino acids are encoded using one-hot encoding, resulting in a 340-dimensional feature vector per sample.

# Dataset
Source: UCI Machine Learning Repository — Molecular Biology (Protein Secondary Structure)
Preprocessed file: data4.csv (10,000 samples)
Classes: α-helix (h), β-sheet (e), coil (_)
Class distribution: coil 55.6%, α-helix 25.1%, β-sheet 19.4%

# Methods
Algorithm: k-Nearest Neighbors (k-NN) with Euclidean distance
Feature encoding: one-hot (17 positions × 20 amino acids = 340 features)
Train/test split: 80/20 with stratified sampling (random_state = 42)
Values of k evaluated: {1, 3, 5, 7, 9, 11, 15, 21}
Metrics: accuracy, Cohen's kappa, precision, recall, F1-score, ROC/AUC (one-vs-rest)

# Requirements
Python ≥ 3.8
Packages: scikit-learn, numpy, pandas, matplotlib, seaborn

# Project Structure

| File | Description |
|------|-------------|
| `data4.csv` | Dataset (10,000 samples) |
| `Protein Secondary Structure Prediction using the k-NN Algorithm.ipynb` | Main notebook |
| `README.md` | Project documentation |
