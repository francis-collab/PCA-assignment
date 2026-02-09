# Principal Component Analysis (PCA) from Scratch  
**Mathematics for Machine Learning – Formative Assignment: Advanced Linear Algebra**

This repository contains a complete, from-scratch implementation of **Principal Component Analysis (PCA)** using only NumPy (as strictly required by the assignment template). The project follows the exact Google Colab template structure (Steps 1, 3–8) and meets all rubric criteria.

## Project Summary

**Goal**  
Implement PCA manually to reduce dimensionality while preserving as much variance as possible, demonstrating core linear algebra concepts:

- Manual standardization: `z = (x - μ) / σ` (mean = 0, std = 1) using only NumPy
- Covariance matrix computation
- Eigendecomposition
- Sorting principal components by descending eigenvalues
- Explained variance ratios and cumulative variance
- Dynamic selection of principal components (≥95% explained variance)
- Projection onto selected components
- Before vs After PCA visualization (scatter plots with proper labeling)

**Strict constraints followed**  
- No scikit-learn for standardization, covariance, eigendecomposition, or projection  
- Only NumPy allowed for core PCA steps  
- Real African dataset with missing values (NaNs) and non-numeric columns (categorical strings)  
- Proper handling: one-hot encoding + mean imputation  
- All required cell outputs displayed (arrays, shapes, plots)

## Dataset

**ACLED African Conflicts, 1997–2017** (Kaggle)  
- **Source**: https://www.kaggle.com/datasets/jboysen/african-conflicts  
- **Description**: Comprehensive dataset of over 165,000 political violence, protest, and armed conflict events across all African countries (including Rwanda 🇷🇼, Uganda, DR Congo, and many others). Includes event types, actors, locations, fatalities, timestamps, and more.  
- **Why chosen**:
  - Fully African-focused and impactful (used for humanitarian analysis, peacebuilding research, and understanding regional instability)  
  - 28 original columns (exceeds 10-column requirement)  
  - Non-numeric columns: many categorical strings (e.g., `EVENT_TYPE`, `ADMIN1`, `SOURCE`, `NOTES`)  
  - Missing values: Significant NaNs (e.g., 15–83% in actor/alliance columns)  
  - Not generic/common (specific to African conflict dynamics, sourced from media/reports)

**File used**: `african_conflicts.csv` (download from the Kaggle link above)

## Features Implemented

- Data preprocessing: one-hot encoding of categoricals, mean imputation for missing values, dropping high-cardinality columns to manage dimensionality  
- Manual standardization with NumPy only  
- Covariance matrix calculation  
- Eigendecomposition with NumPy  
- Explained variance ratio + cumulative variance computation  
- Automatic selection of optimal number of principal components (95% threshold)  
- Data projection onto selected components  
- Side-by-side scatter plots: original standardized features vs PC1–PC2  
- Insightful explanation of PCA effects (centering, rotation, variance maximization)

## Repository Contents
```
├── PCA_Assignment.ipynb # Completed notebook exactly matching the assignment template
├── african_conflicts.csv # (optional – usually not uploaded due to size; download from Kaggle)
└── README.md # This file
```
## How to Run

1. **Clone or download this repository**

    git clone https://github.com/YOUR-USERNAME/pca-assignment.git
    cd pca-assignment

2. **Open in Google Colab**

    # Open Colab
    Go to: https://colab.research.google.com

    # Open notebook from GitHub
    File → Open notebook → GitHub tab
    Paste: https://github.com/YOUR-USERNAME/pca-assignment/blob/main/PCA_Assignment.ipynb

3. **Upload the dataset**

    # Download dataset
    Download: african_conflicts.csv from
    https://www.kaggle.com/datasets/jboysen/african-conflicts

    # Upload in Colab
    Left sidebar → Files → Upload → select the CSV file

4. **Run all cells**

    Runtime → Run all

    Expected outputs include:
        - Dataset shape, missing values report, non-numeric columns
        - Standardization verification (mean ≈ 0, std = 1)
        - Covariance matrix
        - Eigenvalues & sorted eigenvectors
        - Explained variance plot
        - Number of selected components + cumulative variance
        - Reduced data sample
        - Before vs After PCA scatter plots with labels and explanation

# Note: Dataset is large (~165k rows)
# If Colab runs slowly or hits memory limits after one-hot encoding, use a subset:

    df = df.sample(20000, random_state=42)

# This uses a representative 20,000-row subset for faster execution 
# while preserving the assignment goals.


## Rubric Alignment
```
+----------------------------------------+----------------------------------------------------------+
| Criterion                               | How it is met                                           |
+----------------------------------------+----------------------------------------------------------+
| Data with missing values & non-numeric  | Yes – NaNs imputed, categorical strings one-hot encoded |
| Explained variance calculation          | Yes – ratios computed, sorted descending, dynamic selection ≥95% cumulative |
| Visualization before & after            | Yes – scatter of first two original features vs PC1 vs PC2, labeled axes, preserved structure |
| Insightful explanation                  | Yes – printed explanation of centering, rotation, variance maximization, and African context |
| From-scratch implementation             | Yes – NumPy only for all core PCA operations (standardization, cov, eig, projection) |
+----------------------------------------+----------------------------------------------------------+
```

## Acknowledgments

Dataset: Armed Conflict Location & Event Data Project (ACLED) via Kaggle  
Course: Mathematics for Machine Learning  
Reference: Built In – Step-by-Step Explanation of Principal Component Analysis  


Francis  
Kigali, Rwanda  
February 2026