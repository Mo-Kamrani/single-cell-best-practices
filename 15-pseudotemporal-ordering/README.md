# Pseudotemporal Ordering

[Open the notebook](01-pseudotemporal-ordering.ipynb)

Diffusion Pseudotime (DPT) analysis of adult human bone-marrow single-cell RNA-seq data, compared with the **precomputed Palantir pseudotime** supplied in the dataset. This notebook does not rerun Palantir.

## Workflow

1. Load the dataset: 5,780 cells and 27,876 genes before preprocessing.
2. Filter genes, normalize counts, log-transform expression, and annotate highly variable genes.
3. Compute PCA and a nearest-neighbor graph using 10 principal components.
4. Inspect cell types on the supplied t-SNE embedding.
5. Compute a diffusion map and select a putative root cell using `X_diffmap[:, 3].argmin()`.
6. Calculate DPT and compare it with Palantir using t-SNE and cell-type violin plots.

## Data and execution

Input: `data/pseudotemporal.h5ad`

If the file is missing, the notebook downloads it from its [Figshare backup](https://ndownloader.figshare.com/files/35826944). An internet connection is required for that first download.

Paths are relative to the notebook kernel's working directory. Run all cells in order in an environment containing **Scanpy** and a Jupyter interface. The saved Python metadata reports **3.11.15**; the notebook does not record a complete pinned dependency environment.

## Outputs

- Cell-type t-SNE plot
- Diffusion-map plot
- Side-by-side DPT and Palantir t-SNE plots
- Cell-type pseudotime distributions

The notebook retains its saved outputs and figures. It stores computed DPT values in `adata.obs["dpt_pseudotime"]` in memory; there is no dataset-export step.

## Interpretation

The recorded analysis reports elevated DPT values in CLP and some HSC populations, while the supplied Palantir ordering better matches the developmental hierarchy discussed in the notebook. This is a dataset-specific comparison, not a general ranking of the methods. Root selection affects interpretation, and pseudotime is a relative ordering rather than elapsed time.

## Publication checks

All **20 cells** (9 code and 11 Markdown) and their saved outputs are preserved from the supplied notebook. Publication checks cover notebook structure, Python syntax, PNG integrity, and the published file hash; the analysis was not rerun for publication.

