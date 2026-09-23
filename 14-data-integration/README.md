# Data Integration

This section benchmarks multiple single-cell data-integration methods on selected batches from the Open Problems BMMC multiome dataset.

## Workflow

[`01-data-integration.ipynb`](01-data-integration.ipynb) performs:

- selection and preprocessing of GEX features
- construction of an unintegrated baseline
- batch-aware highly variable gene selection
- integration with scVI and scANVI
- graph-based integration with BBKNN
- expression-space integration with Seurat
- benchmarking with scIB metrics
- comparison of batch correction and biological conservation

## Input

```text
data/openproblems_bmmc_multiome_genes_filtered.h5ad
```

## Methods compared

- Unintegrated HVG baseline
- scVI
- scANVI
- BBKNN
- Seurat

## Result

In the completed run, scANVI achieved the highest overall benchmark score (`0.974`) using a weighted score of 40% batch correction and 60% biological conservation.

## Requirements

- Python 3
- Scanpy and AnnData
- scvi-tools
- BBKNN
- scIB
- rpy2 and anndata2ri
- R with Seurat
- pandas, NumPy and Matplotlib

The dataset is referenced through a repository-relative path and is not included in the repository.
