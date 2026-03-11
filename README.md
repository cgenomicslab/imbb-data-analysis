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
**Level:** Complete beginners..  
**Approach:** Mix of executable code and hands-on exercises

#### Daily Schedule

**Day 1: Python Fundamentals**
- Variables, data types, basic operations
- Lists, dictionaries, and slicing
- Loops, conditionals, and simple functions
- Understanding imports

**Day 2: Plotting & Data Operations**
- Seaborn visualization basics
- Arrays and pandas DataFrames
- Data filtering, selection, and groupby
- Boolean indexing

**Day 3: Statistics & Hypothesis Testing**
- Visualizing distributions
- Parametric tests (t-test)
- Non-parametric tests (Mann-Whitney U)
- Permutation tests (understanding the logic)

**Day 4: Expression Data & Visualization**
- PCA: toy example and interpretation
- Bulk RNA-seq data exploration
- UMAP introduction (visualization only)
- Interpreting dimensionality reduction plots

**Day 5: Differential Expression**
- Statistical basis of DE analysis
- Marker genes concept
- Comparing conditions
- Integrative project work

#### Week 1 Notebooks

| Day | Topic | Notebook |
|-----|-------|----------|
| Day 1 | Python Fundamentals | [day1_python_fundamentals.ipynb](week1/day1_python_fundamentals.ipynb) |
| Day 2 | Plotting & Data Operations | [day2_visualization_pandas.ipynb](week1/day2_visualization_pandas.ipynb) |
| Day 3 | Statistics & Hypothesis Testing | [day3_statistics_outline.md](week1/day3_statistics_outline.md) (outline) |
| Day 4 | Expression Data & Visualization | [day4_expression_pca_outline.md](week1/day4_expression_pca_outline.md) (outline) |
| Day 5 | Differential Expression | [day5_differential_expression_outline.md](week1/day5_differential_expression_outline.md) (outline) |

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
- **Required packages:** numpy, pandas, matplotlib, seaborn, scipy, scikit-learn

### Alternative Options
- **Google Colab:** Browser-based, no installation needed
- **IMBB JupyterHub:** Centralized server (access provided during course)

**Detailed instructions:** See [docs/SETUP.md](docs/SETUP.md)

---

## 📊 Datasets

### Dataset 1: Cretan Biodiversity
Cretan beaches' environmental and biodiversity measurements. Used for learning data manipulation and basic statistics.

**Variables:** Beach characteristics, wildlife sightings (Kri-kri, sea turtles, monk seals), vegetation, tourism, weather

### Dataset 2: Simulated Bulk RNA-seq
Gene expression dataset with 3 conditions. Used for learning expression analysis and differential expression concepts.

**Design:** 100 genes × 9 samples (3 conditions, 3 replicates each)

### Dataset 3: Simulated Single-cell RNA-seq  
Pre-processed single-cell data for visualization practice.

**Design:** ~1000 cells, 500 genes, 3-4 cell types with clear markers

---

## 🎓 Learning Objectives

By the end of Week 1, participants will be able to:

1. **Write basic Python code** to manipulate and analyze data
2. **Use pandas** to work with tabular biological data
3. **Create visualizations** to explore and communicate results
4. **Understand the statistical concepts** behind hypothesis testing
5. **Interpret PCA and UMAP plots** from expression data
6. **Grasp the logic of differential expression** analysis
7. **Feel confident** to continue learning independently

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
