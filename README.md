Distributed SMOTE for Scalable Fraud Detection
Overview
This project explores the impact of distributed oversampling techniques on the performance, scalability, and computational efficiency of fraud detection models applied to large-scale, highly imbalanced datasets. Specifically, it evaluates and compares implementations of SMOTE (Synthetic Minority Oversampling Technique) in distributed environments.

The core problem addressed is the challenge of scaling nearest-neighbor-based SMOTE algorithms in distributed systems—an important concern when dealing with massive datasets like those used in credit card fraud detection.

Problem Statement
Fraud detection datasets are typically extremely imbalanced, with fraudulent transactions often representing less than 0.2% of total entries. This imbalance can bias classifiers, making them ineffective at identifying rare but critical cases.

The Credit Card Fraud Detection dataset used in this study includes 284,807 transactions over two days, of which only 492 are fraudulent. Standard classification algorithms struggle to detect these minority instances without oversampling.

Goal
To evaluate and compare different distributed SMOTE strategies in terms of:

Classification performance

Execution (wall-clock) time

Scalability in distributed systems

Methods and Techniques
Three distributed SMOTE variants are analyzed:

Global SMOTE
Traditional SMOTE applied globally across the entire dataset.

Partition-Based Local SMOTE
SMOTE applied within clusters generated using:

K-Means

Bisecting K-Means

Approximate SMOTE using Locality Sensitive Hashing (LSH)
A faster, memory-efficient method that approximates nearest neighbors without full distance calculations.

Each method is tested in conjunction with ensemble classifiers (e.g., Random Forest, XGBoost) to assess classification performance on distributed data.

Key Findings
Partition-based SMOTE methods offer a significant improvement in classification accuracy for fraudulent transactions while maintaining fast execution times.

LSH-based approximate SMOTE reduces computational cost, providing an efficient balance between speed and accuracy.

These findings highlight critical trade-offs between computational resources and model effectiveness for real-time or large-scale fraud detection systems.

Technologies Used
Apache Spark / PySpark (for distributed data processing)

Scikit-learn, XGBoost (for model training and evaluation)

Pandas, NumPy (for preprocessing and analysis)

Matplotlib / Seaborn (for visualizations)
