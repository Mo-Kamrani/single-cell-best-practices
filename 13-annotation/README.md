# Cell Type Annotation

This section annotates the clustered `s4d8` single-cell RNA-seq dataset using complementary manual and reference-based strategies.

## Workflow

[`01-cell-type-annotation.ipynb`](01-cell-type-annotation.ipynb) performs:

- marker-based inspection and manual annotation
- differential-expression-assisted cluster interpretation
- coarse- and fine-grained annotation with CellTypist
- scArches reference mapping into a pretrained scVI latent space
- weighted KNN label transfer with uncertainty estimates
- marker-based validation of transferred labels
- export of the annotated `AnnData` object

## Input

```text
data/s4d8_clustered.h5ad
```

## Reference files

```text
reference/annotation_reference_features.csv
reference/annotation_reference_model.pt
reference/annotation_reference_embedding.h5ad
```

## Output

```text
results/s4d8_annotated.h5ad
```

## Requirements

- Python 3
- Scanpy
- CellTypist
- scArches
- pandas, NumPy, SciPy
- Matplotlib and Seaborn

Large datasets and pretrained model files are intentionally referenced through repository-relative paths and are not included in the repository.
