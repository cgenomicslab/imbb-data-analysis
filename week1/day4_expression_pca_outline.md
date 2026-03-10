# Day 4: Expression Data & Dimensionality Reduction
## Notebook Outline

### Section 1: Toy PCA Example (20 min)
- Create simple 5x3 matrix
- Show what PCA does geometrically
- Variance explained concept
- Manually compute PC1, PC2
- Plot toy example
- Exercise: Interpret toy PCA

### Section 2: Understanding Expression Data (30 min)
- Load bulk RNA-seq counts
- What is a count matrix? (genes × samples)
- Why normalize? Library size effects
- Log transformation - why?
- Basic QC: library sizes, distributions
- Exercise: Calculate basic statistics on counts

### Section 3: PCA on Real Data (40 min)
- from sklearn.decomposition import PCA
- Normalize counts (simple scaling)
- Run PCA on bulk RNA-seq
- Plot PC1 vs PC2, color by condition
- Variance explained bar plot
- Interpret: what does separation mean?
- Exercise: Identify which PCs separate conditions

### Section 4: UMAP Introduction (20 min)
- Load single-cell metadata (pre-computed UMAP)
- Plot UMAP colored by cell type
- UMAP vs PCA: when to use which?
- Link to resources for learning more
- **Brief explanation** - not deep dive
- Exercise: Color UMAP by gene expression level

### Final Exercise (10 min)
- Compare PCA and grouping for your bulk data
- Interpret biological meaning
- Discuss with neighbors
