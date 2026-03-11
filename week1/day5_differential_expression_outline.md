# Day 5: Dimensionality Reduction & Integration
## Bioinformatics Course - IMBB-FORTH

**Lesson 5** Understanding PCA, UMAP, and bringing it all together.

---

## Learning Objectives

By the end of this session, you will:
- Understand what dimensionality reduction does
- Interpret PCA plots and variance explained
- Apply PCA to expression data
- Understand UMAP for visualization
- Compare different dimensionality reduction methods
- Integrate concepts from the entire week

---

## Session Structure (2 hours)

### Part 1: Introduction - Why Reduce Dimensions? (15 min)

**The Problem:**

Imagine describing a person:
- Height, weight, age, income, education years, shoe size, etc.
- 10+ variables!

**Can we summarize in fewer dimensions?**
- Dimension 1: "Body size" (combines height, weight, shoe size)
- Dimension 2: "Socioeconomic status" (combines income, education)

Now we have 2 dimensions instead of 10!

**In biology:**
- 100 genes → Too many to plot
- PCA → 2-3 principal components → Easy to visualize
- **Goal:** Preserve important patterns while reducing complexity

---

### Part 2: PCA on Toy Dataset (35 min)

**Simple Dataset: Student Exam Scores**

20 students, 3 subjects:
- Math scores
- Physics scores  
- History scores

**Question:** Can we reduce to 2 dimensions and still capture main patterns?

---

#### Step 1: Load and Visualize

```python
students = pd.DataFrame({
    'student': ['S1', 'S2', ..., 'S20'],
    'math': [85, 92, 78, ...],
    'physics': [88, 90, 75, ...],
    'history': [65, 70, 85, ...]
})

# Math and Physics are highly correlated (same students good at both)
# History less correlated
```

**Scatter plot matrix:**
- Math vs Physics: strong correlation
- Math vs History: weaker correlation
- Physics vs History: weaker correlation

---

#### Step 2: Run PCA

```python
from sklearn.decomposition import PCA

# Prepare data (exclude student names)
X = students[['math', 'physics', 'history']]

# Standardize (important!)
from sklearn.preprocessing import StandardScaler
X_scaled = StandardScaler().fit_transform(X)

# Run PCA
pca = PCA(n_components=2)
X_pca = pca.fit_transform(X_scaled)

# Create DataFrame with results
pca_df = pd.DataFrame(X_pca, columns=['PC1', 'PC2'])
pca_df['student'] = students['student']
```

---

#### Step 3: Interpret Results

**Variance explained:**
```python
print(pca.explained_variance_ratio_)
# Output: [0.75, 0.20]  (example values)
```

- PC1 explains 75% of variance → "general academic ability"
- PC2 explains 20% of variance → "STEM vs humanities"
- Together: 95% of original information!

**Component loadings:**
```python
loadings = pd.DataFrame(
    pca.components_.T,
    columns=['PC1', 'PC2'],
    index=['math', 'physics', 'history']
)
print(loadings)
```

Interpretation:
- PC1: All subjects load similarly → overall performance
- PC2: Math/Physics positive, History negative → STEM vs humanities

---

#### Step 4: Visualize PCA Plot

```python
sns.scatterplot(data=pca_df, x='PC1', y='PC2', s=100)

# Add student labels
for i, student in enumerate(pca_df['student']):
    plt.text(pca_df.iloc[i]['PC1'], pca_df.iloc[i]['PC2'], student)
```

**Observations:**
- Students spread along PC1 (overall ability)
- Students separate along PC2 (STEM vs humanities preference)
- We reduced 3D to 2D and still see patterns!

---

### Part 3: PCA on Expression Data (40 min)

**Now apply to real biological data**

---

#### Load RNA-seq Data

```python
expression = pd.read_csv('bulk_rnaseq_counts.csv', index_col=0)
metadata = pd.read_csv('bulk_rnaseq_metadata.csv')

# Shape: 100 genes × 9 samples
# 3 conditions × 3 replicates
```

**Problem:** 100 dimensions (genes) - can't visualize!

---

#### Prepare Data

```python
# Transpose: samples as rows, genes as columns
X = expression.T

# Log-transform
X_log = np.log2(X + 1)

# Standardize
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X_log)
```

---

#### Run PCA

```python
pca = PCA(n_components=5)
X_pca = pca.fit_transform(X_scaled)

# Create results DataFrame
pca_results = pd.DataFrame(
    X_pca[:, :2],  # First 2 components
    columns=['PC1', 'PC2']
)
pca_results['condition'] = metadata['condition'].values
pca_results['replicate'] = metadata['replicate'].values
```

---

#### Visualize: PCA Scatter

```python
sns.scatterplot(data=pca_results, 
                x='PC1', y='PC2',
                hue='condition',
                style='replicate',
                s=200)
```

**Expected pattern:**
- Samples cluster by condition
- Replicates close together
- Different conditions separate

---

#### Scree Plot: Variance Explained

```python
variance = pca.explained_variance_ratio_

# Bar plot
plt.bar(range(1, 6), variance)
plt.xlabel('Principal Component')
plt.ylabel('Variance Explained')
```

**Interpretation:**
- PC1: 60% → biggest source of variation (likely condition effect)
- PC2: 25% → second source (maybe batch effect or second treatment)
- PC3-5: <10% each → noise or minor effects

**Rule of thumb:** First 2-3 PCs usually capture main biology

---

#### Exercise: Loadings Analysis

Which genes contribute most to PC1?

```python
# Get loadings for PC1
pc1_loadings = pd.DataFrame({
    'gene': expression.index,
    'loading': pca.components_[0]
})

# Sort by absolute loading
pc1_loadings['abs_loading'] = np.abs(pc1_loadings['loading'])
top_genes = pc1_loadings.sort_values('abs_loading', ascending=False).head(10)
```

These genes drive the separation between conditions!

---

### Part 4: UMAP - Alternative Visualization (20 min)

**What is UMAP?**

- Another dimensionality reduction method
- Better at preserving local structure
- Often used for single-cell data
- Non-linear (unlike PCA)

---

#### Run UMAP

```python
from umap import UMAP

# Same data as PCA
umap_model = UMAP(n_components=2, random_state=42)
X_umap = umap_model.fit_transform(X_scaled)

# Create results
umap_results = pd.DataFrame(
    X_umap,
    columns=['UMAP1', 'UMAP2']
)
umap_results['condition'] = metadata['condition'].values
```

---

#### Compare PCA vs UMAP

```python
# Side-by-side plots
fig, axes = plt.subplots(1, 2, figsize=(12, 5))

# PCA
sns.scatterplot(data=pca_results, x='PC1', y='PC2', 
                hue='condition', ax=axes[0], s=200)
axes[0].set_title('PCA')

# UMAP
sns.scatterplot(data=umap_results, x='UMAP1', y='UMAP2',
                hue='condition', ax=axes[1], s=200)
axes[1].set_title('UMAP')
```

**Observations:**
- Both separate conditions
- UMAP might show tighter clusters
- PCA preserves global distances better
- UMAP preserves local neighborhoods better

---

#### When to Use Each?

**PCA:**
- Understand variance sources
- Linear relationships
- Interpretable components
- Fast, deterministic

**UMAP:**
- Complex, non-linear data
- Visualization emphasis
- Better local structure
- Single-cell RNA-seq

---

### Part 5: Single-Cell Preview (15 min)

**Optional: Brief look at scRNA-seq**

```python
# Load pre-clustered single-cell data
sc_expr = pd.read_csv('singlecell_expression.csv', index_col=0)
sc_meta = pd.read_csv('singlecell_metadata.csv')

# Already has UMAP coordinates and cell type labels
# Shape: 500 genes × 200 cells

# Visualize
sns.scatterplot(data=sc_meta, x='UMAP_1', y='UMAP_2',
                hue='cell_type', s=50, alpha=0.7)
```

**What you see:**
- Cells cluster by type
- T cells separate from B cells
- Clear cell type boundaries

**Key message:** Same principles, different scale
- Bulk RNA-seq: 9 samples → simple PCA
- scRNA-seq: 1000s of cells → UMAP for visualization

---

### Part 6: Integration Exercise (20 min)

**Bring together the week's concepts:**

**Scenario:** You have new RNA-seq data
- 4 conditions
- 4 replicates each
- 200 genes

**Tasks:**

1. **Explore (Day 1-2):**
   - Load data
   - Check structure
   - Calculate summary statistics

2. **Visualize (Day 2):**
   - Heatmap of top variable genes
   - Sample correlation matrix

3. **Test (Day 3):**
   - PCA to check for separation
   - If conditions separate, test specific genes
   - Calculate p-values for condition differences

4. **Analyze (Day 4):**
   - Find differentially expressed genes
   - Create volcano plot
   - If gene lists available: enrichment analysis

5. **Interpret (Day 5):**
   - PCA plot to visualize overall patterns
   - Identify which genes drive PC1
   - Biological interpretation

**This is the workflow you'll use in real research!**

---

## Key Datasets Used

1. **Student scores** - toy PCA example (3 variables)
2. **Bulk RNA-seq** - 100 genes, 9 samples
3. **Single-cell** (preview) - 500 genes, 200 cells

---

## Exercises Throughout

1. Interpret PC loadings on toy data
2. Run PCA on expression data
3. Create scree plot
4. Identify top genes for PC1
5. Compare PCA vs UMAP
6. Integration exercise (full workflow)

---

## Key Takeaways

- **Dimensionality reduction** = summarize many variables in few dimensions
- **PCA** finds directions of maximum variance
- **Variance explained** tells you how much information each PC captures
- **Loadings** show which variables contribute to each PC
- **PCA vs UMAP** - different strengths, choose based on goal
- **First 2-3 PCs** usually capture main biological signal
- **Always combine** with statistical testing (from Day 3)

---

## Week 1 Summary

We learned:
1. **Python basics** - variables, lists, loops, functions
2. **Data exploration** - pandas, filtering, grouping, visualization
3. **Statistics** - p-values via permutation, t-tests, correlation
4. **Enrichment** - same logic applied to gene sets
5. **Dimensionality reduction** - visualize complex data

**You now have a foundation** to:
- Load and explore biological data
- Visualize patterns
- Test hypotheses statistically
- Interpret expression data
- Understand common analysis plots

---

## Week 2 Preview

Next week:
- **Specialized topics** from different labs
- **Real datasets** from actual research
- **Advanced methods** building on this foundation
- **Your own data** - bring it and get help!

---

## Required Libraries

```python
import pandas as pd
import seaborn as sns
import numpy as np
from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler
from umap import UMAP  # pip install umap-learn
```

## Additional Resources

- PCA explained visually
- UMAP documentation
- Single-cell analysis workflows (Scanpy tutorials)
- Dimensionality reduction comparison
