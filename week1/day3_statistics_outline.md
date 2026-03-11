# Day 3: Statistics & P-value Logic
## Bioinformatics Course - IMBB-FORTH

**Lesson 3** Understanding hypothesis testing through permutation logic.

---

## Learning Objectives

By the end of this session, you will:
- Understand what a p-value means through permutation tests
- Compare distributions between groups
- Apply t-test and Mann-Whitney U test
- Test correlations for significance
- Interpret statistical results correctly

---

## Session Structure (2 hours)

### 1. Introduction: The Question We're Asking (10 min)

**Setup:**
- Cretan beaches dataset
- Observation: North coast beaches are warmer than South coast beaches
- Question: "Is this difference real, or could it be random chance?"

**Key concept:** Statistics helps us distinguish signal from noise

---

### 2. Understanding P-values via Permutation Test (40 min)

**The Core Logic:**

#### Step 1: Observe the real difference
- North beaches: mean temperature
- South beaches: mean temperature  
- Observed difference: X°C

#### Step 2: "What if location doesn't matter?"
- If compass direction is irrelevant, labels are arbitrary
- We can shuffle the labels and recalculate difference
- Do this 10,000 times

#### Step 3: Where does our real observation fall?
- Create histogram of 10,000 shuffled differences
- Mark where our real difference is
- P-value = proportion of shuffled results as extreme as real result

**Implementation:**
```python
# Pseudocode structure
real_diff = calculate_difference(north, south)

shuffled_diffs = []
for i in range(10000):
    shuffled_labels = shuffle(labels)
    diff = calculate_difference(shuffled_labels)
    shuffled_diffs.append(diff)

p_value = count(shuffled_diffs >= real_diff) / 10000
```

**Visualization:**
- Histogram of permuted differences
- Red line showing observed difference
- Shaded region showing p-value

**Interpretation:**
- p < 0.05: "Our observation is rare under randomness"
- p > 0.05: "Our observation could easily happen by chance"

---

### 3. Standard Statistical Tests (30 min)

**Now show that standard tests give similar answers:**

#### T-test (parametric)
- Assumes normal distributions
- Tests difference in means
- `scipy.stats.ttest_ind()`

#### Mann-Whitney U (non-parametric)
- Doesn't assume normality
- Tests if one group tends to be larger
- `scipy.stats.mannwhitneyu()`

**Compare all three:**
```
Method              | p-value
--------------------|--------
Permutation test    | 0.002
T-test              | 0.001
Mann-Whitney U      | 0.003
```

All agree: difference is significant!

**Exercise:** Test lionfish abundance (SE vs NW beaches)

---

### 4. Correlation Analysis (25 min)

**Visual + Statistical:**

#### Pearson Correlation
- Measures linear relationship strength
- r = -1 (perfect negative) to +1 (perfect positive)
- r = 0 (no linear relationship)

**Example: Temperature vs Tourism**
```python
r, p_value = scipy.stats.pearsonr(temperature, tourism)
```

**Interpretation:**
- r = 0.78: Strong positive correlation
- p < 0.001: Highly significant

**Multiple comparisons:**
- Test several variable pairs
- Create correlation matrix with p-values
- Which correlations are significant?

**Exercises:**
- Rainfall vs longitude (expect linear)
- Lionfish vs cornetfish (co-invasion)
- Wind speed vs longitude (U-shaped - correlation won't capture this well!)

---

### 5. Distribution Visualization (15 min)

**Before testing, always visualize:**

- Histograms with overlays (north vs south)
- Violin plots (show full distribution)
- Q-Q plots (check normality assumption)

**Key message:** Look at your data before testing!

---

### 6. Common Pitfalls & Best Practices (10 min)

**Pitfalls:**
- "p = 0.049 is significant, p = 0.051 is not" → arbitrary threshold
- Multiple testing without correction
- Testing after cherry-picking groups
- Correlation ≠ causation

**Best practices:**
- Report effect sizes (not just p-values)
- Visualize first, test second
- Consider biological significance
- Be transparent about multiple comparisons

---

## Key Datasets Used

1. **Cretan beaches** - primary dataset
   - North vs South temperature
   - SE vs NW invasive species
   - Temperature vs tourism correlation
   - Rainfall vs longitude

---

## Exercises Throughout

1. **Permutation test:** Wind speed (East vs West)
2. **T-test:** Tourist numbers (sand vs pebble beaches)
3. **Mann-Whitney:** Juniper density (lagoon vs non-lagoon)
4. **Correlation:** Phoenix palms vs rainfall
5. **Integration:** Find and test 3 interesting patterns in the data

---

## Key Takeaways

- **P-value = "How weird is our observation if nothing real is happening"**
- **Permutation tests build intuition** for what p-values mean
- **Standard tests are shortcuts** that give similar answers
- **Always visualize** before testing
- **Effect size matters** as much as significance
- **Statistical significance ≠ biological importance**

---

## Tomorrow Preview

Day 4: We'll use similar logic for enrichment analysis
- "Are purple balls over-represented in our subset?"
- Same permutation logic, different application
- Then: GO term enrichment and gene expression

---

## Required Libraries

```python
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
```

## Additional Resources

- Permutation tests explanation
- P-value interpretation guidelines
- Multiple testing corrections (Bonferroni, FDR)
