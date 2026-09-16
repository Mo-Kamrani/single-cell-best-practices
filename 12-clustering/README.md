# Clustering

This section applies graph-based clustering to the low-dimensional representation generated in the previous workflow.

## Leiden clustering

[`01-leiden-clustering.ipynb`](01-leiden-clustering.ipynb) performs:

- K-nearest-neighbor graph construction from the first 30 principal components
- UMAP recomputation
- Leiden clustering
- comparison of clustering resolutions (0.25, 0.5, and 1.0)
- export of the clustered `AnnData` object

### Input

```text
data/s4d8_dimensionality_reduction.h5ad
```

### Output

```text
results/s4d8_clustered.h5ad
```

## Requirements

- Python 3
- Scanpy
- AnnData
- igraph / Leiden clustering support through Scanpy
