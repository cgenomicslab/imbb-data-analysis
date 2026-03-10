# Day 3: Statistics & Hypothesis Testing
## Notebook Outline

### Section 1: Visualizing Distributions (20 min)
- Normal distribution concept
- Histogram + KDE plots with seaborn
- Understanding mean, median, std
- Exercise: Plot beach rainfall distribution

### Section 2: Basic Statistics (20 min)
- Descriptive statistics (mean, median, variance, std)
- Why log-transform biological data?
- Correlation: Pearson vs Spearman
- Exercise: Calculate correlation between tourists and monk seals

### Section 3: Hypothesis Testing - t-test (25 min)
- What is a p-value? (explain intuitively)
- Parametric test: t-test
- scipy.stats.ttest_ind()
- Example: Compare water temperature between two regions
- Exercise: Compare beach length between Sand vs Pebbles

### Section 4: Non-parametric - Mann-Whitney U (25 min)
- When to use non-parametric tests
- Mann-Whitney U test
- scipy.stats.mannwhitneyu()
- Example: Compare tourist counts
- Exercise: Test if Chania has different rainfall than Lassithi

### Section 5: Permutation Test (25 min) - EMPHASIZE THIS
- **The key concept: random sampling logic**
- What does a p-value really mean?
- Code permutation test from scratch
- Show observed difference vs random differences
- Plot distribution of random differences
- Exercise: Permutation test for your own question

### Final Exercise (15 min)
- Choose two groups from beaches dataset
- Run all three tests (t-test, U-test, permutation)
- Compare results
- Interpret findings
