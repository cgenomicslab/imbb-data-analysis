# Day 4: Enrichment & Expression Analysis
## Bioinformatics Course - IMBB-FORTH

**Lesson 4** Understanding enrichment logic and applying it to gene expression.

---

## Learning Objectives

By the end of this session, you will:
- Understand enrichment analysis through a simple example
- Apply permutation and hypergeometric tests to enrichment
- Transition to GO term enrichment
- Compare gene expression between conditions
- Visualize expression data with heatmaps and volcano plots

---

## Session Structure (2 hours)

### Part 1: Enrichment - The Colored Balls Example (40 min)

**The Setup:**

Total population: 100 balls
- 20 purple
- 30 red
- 25 blue
- 15 green
- 10 yellow

You select a subset of 15 balls for a "special experiment"
Observed counts in your subset:
- 8 purple
- 3 red
- 2 blue
- 1 green
- 1 yellow

**The Question:** Are purple balls enriched in your subset?

---

#### Step 1: Calculate Expected vs Observed

**Expected (if random):**
- 20% of population is purple
- In 15 balls, expect: 15 × 0.20 = 3 purple balls
- But we observed: 8 purple balls

**Fold enrichment:**
```
Fold enrichment = Observed / Expected
                = 8 / 3 
                = 2.67x
```

Purple balls are 2.67× more common in our subset than expected!

---

#### Step 2: Is This Significant? (Permutation Test)

**Logic (same as yesterday!):**

1. Observed: 8 purple balls in subset of 15
2. Shuffle: Randomly pick 15 balls from population 10,000 times
3. Count: How often do we get ≥8 purple balls?
4. P-value: proportion of shuffles with ≥8 purple

**Implementation:**
```python
population = create_population()  # 100 balls with colors
observed = 8  # purple balls in subset

counts = []
for i in range(10000):
    random_subset = random.sample(population, 15)
    purple_count = count_purple(random_subset)
    counts.append(purple_count)

p_value = sum(counts >= 8) / 10000
```

**Result:** p < 0.01 → Significant enrichment!

---

#### Step 3: Hypergeometric Test (Exact Calculation)

**Instead of simulation, use exact probability:**

```python
from scipy.stats import hypergeom

# Parameters:
# M = total population (100)
# n = items of interest in population (20 purple)
# N = sample size (15)
# k = items of interest in sample (8 purple)

p_value = hypergeom.sf(k=7, M=100, n=20, N=15)
```

**Both methods agree:** purple balls are significantly enriched!

---

#### Exercise: Test All Colors

Calculate enrichment for all 5 colors:
- Which colors are enriched?
- Which are depleted?
- Which show no enrichment?

Create summary table:
```
Color   | Observed | Expected | Fold Enr. | P-value | Significant?
--------|----------|----------|-----------|---------|-------------
Purple  |    8     |   3.0    |   2.67    | 0.003   | Yes
Red     |    3     |   4.5    |   0.67    | 0.42    | No
...
```

---

### Part 2: GO Term Enrichment (30 min)

**The Transition:**

Same logic, different application!

**Biological scenario:**
- Total genome: 20,000 genes
- GO term "cell cycle": 500 genes
- Your gene list (differentially expressed): 100 genes
- Overlap: 15 genes in "cell cycle"

**Question:** Is "cell cycle" enriched in your gene list?

---

#### Simple GO Example

**Population:**
- 50 total genes
- GO1 (metabolism): 20 genes
- GO2 (cell cycle): 10 genes
- GO3 (immune): 8 genes
- (others): 12 genes

**Your gene list:** 10 genes
- 6 from GO1
- 2 from GO2
- 1 from GO3
- 1 other

**Test each GO term:**

```python
# GO1 (metabolism)
observed = 6
expected = 10 × (20/50) = 4
fold_enr = 6/4 = 1.5

# Hypergeometric test
p_value = test_enrichment(observed=6, category_size=20, 
                         list_size=10, total_genes=50)
```

**Exercise:** Calculate enrichment for all three GO terms

---

#### Visualization: Bar Plot

```python
# Show fold enrichment with significance stars
GO terms with fold enrichment
* = p < 0.05
** = p < 0.01
```

**Key message:** Same math as colored balls, applied to biology!

---

### Part 3: Expression Analysis (50 min)

**Now apply to real gene expression data**

---

#### Load Bulk RNA-seq Data

```python
expression = pd.read_csv('bulk_rnaseq_counts.csv')
metadata = pd.read_csv('bulk_rnaseq_metadata.csv')
```

**Design:**
- 3 conditions: Normal, Treatment_A, Treatment_B
- 3 replicates each
- 100 genes

---

#### Visualize: Heatmap

```python
# Log-transform
log_expr = np.log2(expression + 1)

# Heatmap of all genes
sns.heatmap(log_expr, cmap='viridis')
```

**Observation:** Some genes differ between conditions

---

#### Compare Single Gene Across Conditions

**Example: Gene_005**

```python
# Get expression for Gene_005
gene_data = expression.loc['Gene_005']

# Split by condition
normal = gene_data[metadata['condition'] == 'Normal']
treatment_a = gene_data[metadata['condition'] == 'Treatment_A']
treatment_b = gene_data[metadata['condition'] == 'Treatment_B']

# Visualize
sns.boxplot with three boxes

# Test: Normal vs Treatment_A
t_stat, p_value = stats.ttest_ind(normal, treatment_a)
```

**Question:** Is this gene significantly different between conditions?

---

#### Compare All Genes: Loop Approach

```python
results = []
for gene in genes:
    normal_expr = get_expression(gene, 'Normal')
    treatment_expr = get_expression(gene, 'Treatment_A')
    
    # T-test
    stat, p = ttest_ind(normal_expr, treatment_expr)
    
    # Fold change
    fc = mean(treatment_expr) / mean(normal_expr)
    
    results.append({
        'gene': gene,
        'fold_change': fc,
        'p_value': p
    })

results_df = pd.DataFrame(results)
```

---

#### Volcano Plot

**Visualize all genes at once:**

X-axis: log2(fold change)
Y-axis: -log10(p-value)

```python
results_df['log2_fc'] = np.log2(results_df['fold_change'])
results_df['-log10_p'] = -np.log10(results_df['p_value'])

sns.scatterplot(x='log2_fc', y='-log10_p', data=results_df)

# Add significance threshold lines
# Horizontal: p = 0.05
# Vertical: fc = 2x
```

**Quadrants:**
- Top right: Upregulated & significant
- Top left: Downregulated & significant
- Bottom: Not significant

---

#### Exercise: Find Top Differential Genes

1. Filter for p < 0.05
2. Filter for |log2_fc| > 1 (2-fold change)
3. How many genes pass both filters?
4. What are the top 5 most significant genes?

---

## Key Datasets Used

1. **Colored balls** - toy enrichment example
2. **Simple GO terms** - 50 genes, 3 GO categories
3. **Bulk RNA-seq** - 100 genes, 3 conditions

---

## Exercises Throughout

1. Test all 5 colors for enrichment
2. Calculate GO term enrichment for all categories
3. Compare gene expression (Normal vs Treatment_A)
4. Create volcano plot
5. Identify differentially expressed genes

---

## Key Takeaways

- **Enrichment = observed vs expected**
- **Same statistical logic** as yesterday (permutation/hypergeometric)
- **Fold enrichment** shows magnitude of effect
- **P-value** shows statistical significance
- **GO enrichment** applies this to gene sets
- **Volcano plots** summarize thousands of tests
- **Effect size + significance** both matter

---

## Tomorrow Preview

Day 5: Dimensionality reduction
- PCA on simple toy example
- PCA on expression data (3 conditions)
- UMAP visualization
- Understanding what these plots show

---

## Required Libraries

```python
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
from scipy.stats import hypergeom
```

## Additional Resources

- Hypergeometric distribution explanation
- GO term databases (KEGG, Reactome)
- Multiple testing correction (FDR)
- Volcano plot interpretation
