# A Lightweight Contrastive Embedding Approach for Retail E-Commerce Clustering

## Project Description
This project proposes a two-stage, lightweight clustering framework designed for retail e-commerce data. Traditional clustering methods such as K-Means are widely used due to their simplicity and efficiency but often struggle with mixed feature distributions, varying feature magnitudes, and overlapping clusters, which are common in retail datasets.

To address these limitations, the project introduces a contrastive embedding approach using Linear Discriminant Analysis (LDA) with pseudo-labels generated from an initial K-Means clustering. By learning a discriminative embedding that maximizes between-cluster variance and minimizes within-cluster variance, the proposed method improves cluster separability while remaining computationally inexpensive and interpretable.

The approach is evaluated across four diverse retail datasets representing customer-level, product-level, and store-level analytics.

---

## Environment Setup and Requirements

### Software Requirements
- Python 3.8 or higher
- Jupyter Notebook or any Python IDE

### Required Libraries
- numpy
- pandas
- scikit-learn
- matplotlib
- seaborn (optional)

Install dependencies:
```bash
pip install numpy pandas scikit-learn matplotlib seaborn
```

### Hardware Requirements
- CPU-only environment
- No GPU required

---

## Instructions to Reproduce Results

1. Load one of the retail datasets (Mall, Amazon, Flipkart, or Walmart).
2. Select numerical features and apply standardization.
3. Apply K-Means clustering and determine k using the Elbow Method.
4. Compute the baseline silhouette score.
5. (Optional) Apply PCA for 2D visualization.
6. Use K-Means labels as pseudo-labels and train an LDA model.
7. Transform data using LDA and reapply K-Means.
8. Evaluate clustering quality using silhouette score.

---

## Steps to Train Your Own Model

1. Prepare a numerical retail dataset.
2. Standardize features.
3. Apply K-Means to generate initial clusters.
4. Use these clusters as pseudo-labels.
5. Train LDA to learn a contrastive embedding.
6. Re-cluster data in the LDA space.
7. Evaluate performance with silhouette score.

---

## Results Summary

| Dataset          | k | Baseline K-Means | K-Means + LDA |
|------------------|---|------------------|---------------|
| Mall Customers   | 5 | 0.42             | 0.44          |
| Amazon Products  | 4 | 0.29             | 0.47          |
| Flipkart Laptops | 3 | 0.21             | 0.41          |
| Walmart Sales    | 3 | 0.20             | 0.53          |

Key findings:
- Consistent improvement across all datasets
- Largest gains in high-dimensional data (Walmart)
- Modest improvement for low-dimensional data (Mall Customers)

---

## Notes and Limitations

- Performance depends on initial K-Means pseudo-label quality
- LDA is a linear method and may not capture non-linear structures
- PCA is used only for visualization
- Only numerical features are considered

---

## Future Work
- Explore kernel or non-linear LDA
- Compare with GMM and DBSCAN
- Incorporate text and temporal retail data

---

Instructor: Prof. Qazi  
Group: Group 1  
Date: December 24
