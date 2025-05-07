#  Distributed SMOTE for Scalable Fraud Detection

## Overview

This project investigates the **impact of distributed oversampling techniques** on the performance, scalability, and computational efficiency of fraud detection models on large-scale, imbalanced datasets.

The focus is on improving fraud detection performance using different variants of **SMOTE (Synthetic Minority Oversampling Technique)**, which is known for mitigating class imbalance issues. However, its nearest-neighbor search poses scalability challenges in distributed systems.

## Problem Statement

Fraud detection datasets are highly imbalanced. For example, the **Credit Card Fraud Detection** dataset used in this study contains:

-  **284,807 transactions**
- **Only 492 (0.172%) are fraudulent**

Without proper handling, machine learning classifiers tend to become **biased toward the majority class**, rendering them ineffective for real fraud detection tasks.

##  Objective

Evaluate the **trade-offs** between **classification accuracy**, **computational cost**, and **scalability** of various distributed SMOTE implementations, including:

-  Global SMOTE
-  Partition-Based SMOTE (K-Means, Bisecting K-Means)
-  Approximate SMOTE using Locality-Sensitive Hashing (LSH)

##  Methods

Three distributed SMOTE strategies were analyzed:

### 1. Global SMOTE
> Applies SMOTE across the full dataset (baseline method).

### 2. Partition-Based Local SMOTE
> Partitions the minority class using:
- **K-Means clustering**
- **Bisecting K-Means clustering**

SMOTE is applied locally within each cluster to enhance both **efficiency** and **cluster fidelity**.

### 3. LSH-Based Approximate SMOTE
> Uses **Locality Sensitive Hashing** to approximate nearest neighbors quickly, minimizing computational overhead in distributed environments.

## Key Findings

- **Partition-Based SMOTE** yields **higher accuracy** for fraudulent transaction detection and **lower execution time**.
- **LSH-based SMOTE** reduces computational cost while maintaining competitive accuracy.
- These results reveal **important trade-offs** between runtime performance and model effectiveness in big data fraud detection.

##  Research Question

> _What is the impact of traditional distributed oversampling techniques in combination with ensemble classifiers on the performance, scalability, and computational efficiency of fraud detection models in big data environments?_



