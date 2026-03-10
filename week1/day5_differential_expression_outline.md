# Day 5: Differential Expression & Integration
## Notebook Outline

### Hour 1: Guided Demo (60 min)

#### Part 1: What is Differential Expression? (15 min)
- The biological question: which genes change?
- Fold change vs statistical significance
- Concept of marker genes (one-vs-rest)
- Multiple testing problem (FDR)

#### Part 2: Statistical Basis (20 min)
- Apply Day 3 concepts to expression data
- Test one gene: Normal vs Treatment_A
- Use t-test on log-transformed counts
- Calculate fold change
- Exercise: Test 3 genes manually

#### Part 3: Scale Up (15 min)
- Loop through all genes
- Store p-values and fold changes
- Apply FDR correction (Benjamini-Hochberg)
- Identify DE genes (p < 0.05, |FC| > 2)
- Exercise: Count DE genes

#### Part 4: Visualization (10 min)
- Volcano plot (log2FC vs -log10(p-value))
- Bar plots of top DE genes
- Heatmap of DE genes across samples
- Exercise: Create your own visualization

### Hour 2: Project Work (60 min)

#### Independent Analysis
- Choose a comparison (TreatmentA vs Normal OR TreatmentB vs Normal)
- Perform full DE analysis
- Create visualizations
- Interpret results

#### Helpers Circulate
- Troubleshoot code issues
- Help interpret results
- Answer questions
- Discuss biological meaning

#### Wrap-up (10 min)
- Share findings (volunteers)
- Discuss challenges
- Preview Week 2
- Course feedback

### Summary
- Recap all Week 1 concepts
- Path forward for learning
- Resources for continued practice
