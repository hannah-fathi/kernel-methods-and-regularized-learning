# Kernel Methods and Regularized Learning

**A Research-Oriented Implementation of Kernel Support Vector Machines, Kernel K-Means, and Regularized Linear Regression**

---

## Overview

This repository presents a comprehensive implementation and experimental evaluation of classical kernel-based machine learning algorithms and regularized linear regression models. The project investigates how kernel functions transform linear learning algorithms into powerful nonlinear learners while analyzing the impact of L1 and L2 regularization on predictive performance.

Rather than relying on high-level machine learning APIs, the core algorithms are implemented from scratch whenever possible, providing an educational and research-oriented framework for understanding optimization, kernel methods, and statistical learning.

The repository is organized as a reproducible experimental study consisting of three independent components:

* **Kernel Support Vector Classification**
* **Kernel K-Means Clustering**
* **Regularized Linear Regression**

Each component includes complete preprocessing, model implementation, hyperparameter tuning, quantitative evaluation, and visualization of experimental results.

---

## Highlights

* Research-oriented implementation of classical machine learning algorithms
* From-scratch implementation of Kernel Support Vector Machine using Quadratic Programming (CVXOPT)
* Kernel K-Means implementation with multiple kernel functions
* Ordinary Least Squares (OLS)
* Ridge Regression (L2)
* Lasso Regression using Coordinate Descent
* Hyperparameter optimization using 5-Fold Cross Validation
* Multiple evaluation metrics
* Comprehensive visualization of experimental results
* Fully reproducible experimental pipeline

---

## Repository Structure

```text
kernel-methods-and-regularized-learning
│
├── notebooks/
│   └── Kernels and Regularization in Linear Regression.ipynb
│
├── datasets/
│   ├── classification_datasets
│   ├── regression_datasets
│   └── SubsetMNIST
│
├── report/
│   └── Technical Report.pdf
│
├── results/
│   ├── decision_boundaries/
│   │   ├── decision_boundary_linear.png
│   │   ├── decision_boundary_poly_d1.png
│   │   ├── decision_boundary_poly_d2.png
│   │   ├── decision_boundary_poly_d3.png
│   │   └── decision_boundary_rbf.png
│   │
│   ├── clustering/
│   │   ├── True_class_label_XOR.png
│   │   ├── clustering_standard.png
│   │   ├── clustering_linear.png
│   │   ├── clustering_rbf.png
│   │   ├── clustering_poly_d1.png
│   │   ├── clustering_poly_d2.png
│   │   └── clustering_poly_d3.png
│   │
│   ├── clustering_test/
│   │   ├── clustering_test_standard.png
│   │   ├── clustering_test_linear.png
│   │   ├── clustering_test_rbf.png
│   │   ├── clustering_test_poly_d1.png
│   │   ├── clustering_test_poly_d2.png
│   │   └── clustering_test_poly_d3.png
│   │
│   ├── regression/
│   │   ├── Predicted vs True Value.png
│   │   ├── Lasso Coefficients.png
│   │   ├── comparison_MSE_between_models.png
│   │   └── comparison_R2_between_models.png
│   │
│   └── performance/
│       ├── performance_comparison_part1.png
│       └── F1_score_test_part2.png
│
├── requirements.txt
├── LICENSE
└── README.md
```

---

# Research Objectives

The primary objective of this repository is to investigate the effectiveness of kernel methods and regularization techniques across different machine learning paradigms.

Specifically, this study aims to

* investigate nonlinear classification using Kernel Support Vector Machines,
* evaluate kernel-based clustering on nonlinearly separable data,
* compare different kernel functions,
* analyze the influence of feature standardization,
* study the effect of L1 and L2 regularization,
* provide reproducible implementations suitable for educational and research purposes.

---

# Methodology

---

## Part I — Kernel Support Vector Machine

Kernel Support Vector Machine is implemented by solving the dual optimization problem using **CVXOPT**.

Unlike conventional linear SVMs, kernel functions implicitly project data into higher-dimensional feature spaces, enabling nonlinear decision boundaries without explicitly computing transformed features.

### Implemented Kernels

* Linear Kernel
* Radial Basis Function (RBF)
* Polynomial Kernel (Degree 1)
* Polynomial Kernel (Degree 2)
* Polynomial Kernel (Degree 3)

### Experimental Pipeline

```text
Dataset Loading
        │
        ▼
Feature Standardization
        │
        ▼
Kernel Matrix Computation
        │
        ▼
5-Fold Cross Validation
        │
        ▼
Hyperparameter Selection
        │
        ▼
Dual Quadratic Programming
        │
        ▼
Support Vector Extraction
        │
        ▼
Prediction
        │
        ▼
Performance Evaluation
        │
        ▼
Decision Boundary Visualization
```

### Evaluation Metrics

* Accuracy
* Precision
* Recall
* F1-score
* Computational Runtime

---

## Part II — Kernel K-Means

Kernel K-Means extends conventional K-Means clustering by replacing Euclidean distances with kernel-induced distances in a reproducing kernel Hilbert space (RKHS).

The implementation evaluates the clustering capability of different kernels on the XOR dataset.

### Implemented Methods

* Standard K-Means
* Linear Kernel
* RBF Kernel
* Polynomial Kernel (Degree 1)
* Polynomial Kernel (Degree 2)
* Polynomial Kernel (Degree 3)

### Experimental Procedure

* Data preprocessing
* Kernel matrix computation
* Gamma tuning for RBF kernel
* Multiple clustering runs
* Majority-vote cluster alignment
* Quantitative evaluation
* Training visualization
* Test visualization

### Evaluation Metrics

* Accuracy
* Precision
* Recall
* F1-score

---

## Part III — Regularized Linear Regression

The regression section compares classical linear regression models under different regularization strategies.

### Implemented Models

* Ordinary Least Squares (OLS)
* Ridge Regression (L2 Regularization)
* Lasso Regression (L1 Regularization)

### Optimization Methods

| Model | Optimization         |
| ----- | -------------------- |
| OLS   | Closed-form solution |
| Ridge | Closed-form solution |
| Lasso | Coordinate Descent   |

### Experimental Pipeline

```text
Dataset
      │
      ▼
Train/Test Split
      │
      ▼
Feature Standardization
      │
      ▼
5-Fold Cross Validation
      │
      ▼
Lambda Selection
      │
      ▼
Model Training
      │
      ▼
Prediction
      │
      ▼
Performance Evaluation
```

### Evaluation Metrics

* Mean Squared Error (MSE)
* R² Score
* Runtime

---

# Datasets

Three datasets are included in this repository.

| Dataset                 | Purpose                                                                         |
| ----------------------- | ------------------------------------------------------------------------------- |
| classification_datasets | Kernel Support Vector Machine experiments                                       |
| regression_datasets     | Linear regression experiments                                                   |
| SubsetMNIST             | Additional machine learning dataset included for coursework and experimentation |

---

# Experimental Results

The repository contains comprehensive visualizations generated during the experiments.

## Kernel SVM

* Decision boundaries for all kernels
* Support vector visualization
* Kernel performance comparison

## Kernel K-Means

* Ground-truth XOR visualization
* Training clustering results
* Test clustering results
* Kernel comparison using F1-score

## Regularized Regression

* Predicted versus True values
* Lasso coefficient visualization
* MSE comparison
* R² comparison

---

# Implemented Algorithms

## Classification

* Kernel Support Vector Machine
* Linear Kernel
* Polynomial Kernel
* Radial Basis Function Kernel

## Clustering

* Standard K-Means
* Kernel K-Means

## Regression

* Ordinary Least Squares
* Ridge Regression
* Lasso Regression

---

# Software Stack

* Python
* NumPy
* SciPy
* Matplotlib
* Scikit-learn
* CVXOPT
* Jupyter Notebook

---

# Reproducibility

Clone the repository

```bash
git clone https://github.com/hannah-fathi/kernel-methods-and-regularized-learning.git
```

Move to the project directory

```bash
cd kernel-methods-and-regularized-learning
```

Install dependencies

```bash
pip install -r requirements.txt
```

Launch the notebook

```bash
jupyter notebook notebooks/"Kernels and Regularization in Linear Regression.ipynb"
```

---

# Technical Report

A complete technical report describing the mathematical background, implementation details, experimental methodology, optimization procedures, and quantitative analysis is available in

```text
report/Technical Report.pdf
```

---

# Future Work

Possible future extensions include

* Support Vector Regression (SVR)
* Kernel Principal Component Analysis
* Spectral Clustering
* Gaussian Process Regression
* Multiple Kernel Learning
* Random Fourier Features
* Nyström Approximation
* Large-scale kernel optimization
* Multi-class Kernel SVM
* Sparse kernel methods


---

# Author

**Hannah Fathi**

M.Sc. Student in Artificial Intelligence  

**Research Interests**

- Computer Vision
- Medical AI
- Remote Sensing
- Machine Learning
- Kernel Methods
- Explainable Artificial Intelligence (XAI)
- Large Language Models (LLMs)

---

## Research Timeline

| Item | Description |
|------|-------------|
| Project Type | Research-Oriented Machine Learning Implementation |
| Development Period | Spring 2025 |
| Language | Python |
| Environment | Google Colab / Jupyter Notebook |

---

## Citation

If you use this repository in your research or teaching, please cite it as

```bibtex
@misc{kernel_methods_regularized_learning,
  title        = {Kernel Methods and Regularized Learning},
  author       = {Hannah Fathi},
  year         = {2025},
  note         = {Research-oriented implementation of kernel methods and regularized machine learning},
  url          = {https://github.com/hannah-fathi/kernel-methods-and-regularized-learning}
}
```

---

## License

This project is released under the MIT License.

---

## Keywords

Kernel Methods • Kernel SVM • Kernel K-Means • Support Vector Machines • Regularized Learning • Ridge Regression • Lasso Regression • Ordinary Least Squares • Machine Learning • Cross Validation • Nonlinear Classification • Clustering • Python
