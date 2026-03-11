# IMBB Data Analysis Course
## Institute of Molecular Biology and Biotechnology - FORTH, Heraklion, Crete

A hands-on introduction to Python programming, data analysis, and computational biology for wet lab biologists.

---

## 🎯 Objectives

**Data analysis is for every scientist.** Every biologist should understand basic computational concepts and feel comfortable working with data. This course aims to:

- **Broaden data analysis understanding** across the institute
- **Build confidence** in computational approaches
- **Explain the logic** behind methods, not just how to run tools
- **Cultural shift** - thinking about the data is part of every researcher's approach

This is an introductory boost — not a comprehensive training program. The goal is to get you started, familiarize you with code, and help you understand the concepts behind common analyses.

---

## 📚 Course Structure

### Week 1: Fundamentals
**Format:** 2-hour sessions daily, Monday-Friday  
**Level:** Complete beginners  
**Approach:** Mix of executable code and hands-on exercises

#### Daily Schedule

**Day 1: Python Fundamentals**
- Variables, data types, basic operations
- Lists, dictionaries, and slicing
- Loops, conditionals, and simple functions
- Understanding imports

**Day 2: Plotting & Data Exploration**
- Seaborn visualization with Cretan beaches data
- Pandas DataFrames: filtering, selection, groupby
- Correlation visualization (heatmaps)
- Expression data preview

**Day 3: Statistics & P-value Logic**
- Understanding p-values through permutation tests
- T-test and Mann-Whitney U test
- Correlation significance testing
- Visualizing distributions and testing differences

**Day 4: Enrichment & Expression Analysis**
- Enrichment logic with colored balls example
- Hypergeometric and permutation tests
- GO term enrichment
- Differential expression and volcano plots

**Day 5: Dimensionality Reduction**
- PCA on toy dataset and expression data
- Variance explained and loadings interpretation
- UMAP visualization
- Integration: complete analysis workflow

#### Week 1 Notebooks

| Day | Topic | Notebook |
|-----|-------|----------|
| Day 1 | Python Fundamentals | [day1_python_fundamentals.ipynb](week1/day1_python_fundamentals.ipynb) |
| Day 2 | Plotting & Data Exploration | [day2_plotting_data_exploration.ipynb](week1/day2_plotting_data_exploration.ipynb) |
| Day 3 | Statistics & P-value Logic | [day3_statistics_outline.md](week1/day3_statistics_outline.md) (outline) |
| Day 4 | Enrichment & Expression | [day4_enrichment_expression_outline.md](week1/day4_enrichment_expression_outline.md) (outline) |
| Day 5 | Dimensionality Reduction | [day5_dimensionality_reduction_outline.md](week1/day5_dimensionality_reduction_outline.md) (outline) |

### Week 2: Specialized Topics
**Format:** 2-hour sessions per topic  
**Led by:** Institute Groups

#### Tentative Topics

| Topic |
|-------|
| Phylogenetics & Orthology/Paralogy |
| Differential Gene Expression Analysis |
| ATAC-seq Analysis |
| Single-cell RNA-seq |
| Proteomics Analysis |
| Neurophysiology Data Analysis |
| Behavioral Data Analysis |
| Imaging Analysis |

*Note: Final schedule to be confirmed with contributing labs*

---

## 🚀 Getting Started

### Prerequisites
- **No programming experience required**
- Laptop with admin rights for software installation
- Willingness to learn and experiment
- Basic familiarity with biological concepts

### Before Day 1
1. **Install Python and tools** (see [SETUP.md](docs/SETUP.md))
   - Recommended: Native Python installation with VSCode
   - Backup: Google Colab account (free)
   - Alternative: Institute JupyterHub (access to be provided)

2. **Optional preparation:**
   - Review basic Python syntax: [Python for beginners tutorial by Alexandros Kanterakis](https://github.com/kantale/python_lessons) (colleague's repo)
   - Test your setup with a simple Jupyter notebook

### Course Materials
All materials are available in this repository:
- **week1/**: Jupyter notebooks for Week 1 (5 days)
- **data/**: Datasets used throughout the course
- **docs/**: Setup instructions and additional resources

---

## 💻 Technical Setup

### Recommended Setup (Native Installation)
- **Python 3.10+** via Anaconda or Miniconda
- **VSCode** with Python and Jupyter extensions
- **Required packages:** numpy, pandas, matplotlib, seaborn, scipy, scikit-learn, umap-learn

### Alternative Options
- **Google Colab:** Browser-based, no installation needed
- **IMBB JupyterHub:** Centralized server (access provided during course)

**Detailed instructions:** See [docs/SETUP.md](docs/SETUP.md)

---

## 📊 Datasets

### Cretan Beaches Dataset
Environmental and ecological data from 27 beaches across Crete and Gavdos. Used for data exploration, visualization, statistical testing, and correlation analysis.

**Variables:** Beach characteristics, compass direction, invasive species abundance, sea temperature, tourism, wind speed, rainfall, vegetation (phoenix palms, juniper)

**Applications:** 
- Day 2: Plotting and data exploration
- Day 3: Statistical hypothesis testing, permutation tests, correlation analysis

### Colored Balls Dataset
Toy enrichment example for teaching statistical logic.

**Setup:** 100 balls (5 colors), subset of 15 balls with known composition

**Applications:**
- Day 4: Enrichment analysis, permutation tests, hypergeometric tests

### Bulk RNA-seq Dataset
Simulated gene expression data with realistic differential expression patterns.

**Design:** 100 genes × 9 samples (3 conditions, 3 replicates each)

**Applications:**
- Day 2: Expression data preview and heatmaps
- Day 4: Differential expression analysis, volcano plots
- Day 5: PCA and dimensionality reduction

### Single-cell RNA-seq Dataset (Optional)
Pre-processed single-cell data for visualization demonstration.

**Design:** 500 genes × 200 cells, 4 cell types with distinct markers

**Applications:**
- Day 5: UMAP visualization preview

---

## 🎓 Learning Objectives

By the end of Week 1, participants will be able to:

1. **Write basic Python code** to manipulate and analyze data
2. **Load and explore datasets** with pandas
3. **Create informative visualizations** with seaborn
4. **Understand p-value logic** through permutation tests
5. **Apply statistical tests** (t-test, Mann-Whitney U, correlation)
6. **Grasp enrichment analysis** concepts through concrete examples
7. **Analyze gene expression data** and identify differential expression
8. **Interpret dimensionality reduction** plots (PCA, UMAP)
9. **Execute a complete analysis workflow** from data to interpretation
10. **Feel confident** to continue learning independently

---

## 👥 Target Audience

- IMBB-FORTH lab members (postdocs, PhD students, MSc students, wet lab biologists)
- Researchers with **no programming experience**
- Scientists interested in understanding computational approaches
- Anyone who wants to **demystify data analysis**

**Expected participants:** Up to 40 people

---

## 🤝 Course Coordination & Contributing Groups

### Coordination
- **CGLab (Pittis)**

### Contributing Labs?
- **CGLab (Pittis)**
- **Bioinformatics Unit (Andronis)**
- **Epigenetics, RNA Biology & Gene Regulation Lab (Ntini)**
- **Genome Integrity & Gene Control Mechanisms Lab (Lavigne)**
- **Biology of Stem Cells (Delidakis)**
- **Chromatin & Cancer Epigenetics Lab (Talianidis)**
- **Dynamic Structural Biology (Gkouridis)**
- **Dendrites (Poirazi)**
- **Systems Neuroscience Lab (Froudarakis)**
- **Developmental Morphogenesis Lab (Pavlopoulos)**

---

## 📖 Additional Resources

### Recommended Learning Paths
- [Python lessons repository](https://github.com/kantale/python_lessons) (in Greek/English)
- [Python Data Science Handbook](https://jakevdp.github.io/PythonDataScienceHandbook/)
- [Scanpy tutorials](https://scanpy.readthedocs.io/en/stable/tutorials.html) (single-cell)
- [Seaborn documentation](https://seaborn.pydata.org/)

### IMBB Resources
- IMBB Bioinformatics Unit
- IMBB-FORTH computing infrastructure
- Collaboration with University of Crete

---

## 🔗 Quick Links

- **Course Repository:** https://github.com/cgenomicslab/imbb-data-analysis
- **Installation Help:** [docs/SETUP.md](docs/SETUP.md)
- **Week 1 Materials:** [week1/](week1/)
- **Datasets:** [data/](data/)
- **IMBB Website:** [https://www.imbb.forth.gr](https://www.imbb.forth.gr)

---

## 📧 Contact & Support

**Course Coordinator:** Alexandros Pittis (alexandros.pittis@gmail.com)

**During the course:**
- Ask questions during sessions
- Request help from circulating instructors
- Use the course communication channel (to be announced)

---

## 📝 Feedback

This is a living course that will improve with your input. After each session, we welcome feedback on:
- Pace and difficulty
- Content clarity
- Technical issues
- Suggestions for improvement

**Remember:** There are no stupid questions. We are trying to learn also.

---
