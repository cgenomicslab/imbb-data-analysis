# Single-cell RNA-seq Dataset

## Description
Simulated single-cell RNA-seq data with 4 distinct cell types.

## Files
- `singlecell_expression.csv`: Expression matrix (subset of 200 cells)
- `singlecell_metadata.csv`: Cell metadata with UMAP coordinates

## Dataset Details
- **Full dataset:** 500 genes × 1000 cells
- **Saved subset:** 500 genes × 200 cells (for file size)
- **Cell types:** T_cells, B_cells, Monocytes, NK_cells
- **Cells per type:** 250

## Cell Type Markers
- **T_cells:** Genes 001-030
- **B_cells:** Genes 031-060
- **Monocytes:** Genes 061-090
- **NK_cells:** Genes 091-120
- **Other genes:** Low/variable expression

## Metadata Columns
- `cell_id`: Unique cell identifier
- `cell_type`: Cell type annotation
- `umap_1`, `umap_2`: Pre-computed UMAP coordinates
- `n_genes_expressed`: Number of genes with counts > 0
- `total_counts`: Total UMI counts per cell

## Usage
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load metadata
metadata = pd.read_csv('singlecell_metadata.csv')

# Plot UMAP
plt.figure(figsize=(8, 6))
for cell_type in metadata['cell_type'].unique():
    subset = metadata[metadata['cell_type'] == cell_type]
    plt.scatter(subset['umap_1'], subset['umap_2'], 
                label=cell_type, alpha=0.6, s=10)
plt.xlabel('UMAP 1')
plt.ylabel('UMAP 2')
plt.legend()
plt.title('Single-cell UMAP')
plt.show()
```

## Notes
- Simulated data for educational purposes
- Clear separation between cell types
- Realistic dropout patterns (scRNA-seq sparsity)
- Pre-computed UMAP for visualization practice
