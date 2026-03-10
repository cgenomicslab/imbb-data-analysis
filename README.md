# IMBB Data Analysis Course
## Institute of Molecular Biology and Biotechnology - FORTH, Heraklion, Crete

A hands-on introduction to Python programming, data analysis, and computational biology for wet lab biologists.

---

## 🎯 Course Philosophy

**Data analysis is not for weirdos.** Every biologist should understand basic computational concepts and feel comfortable working with data. This course aims to:

- **Democratize data analysis knowledge** across the institute
- **Build confidence** in computational approaches, not just technical mastery
- **Explain the logic** behind methods, not just how to run tools
- **Create a cultural shift** where computational thinking is part of every researcher's toolkit

This is an introductory boost—not a comprehensive training program. The goal is to get you started, familiarize you with code, and help you understand the concepts behind common analyses.

---

## 📚 Course Structure

### Week 1: Fundamentals (Led by CGLab & Collaborators)
**Format:** 2-hour sessions daily, Monday-Friday  
**Level:** Complete beginners welcome  
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

### Week 2: Specialized Topics (Led by Institute Labs)
**Format:** 2-hour sessions per topic  
**Leaders:** Various IMBB-FORTH groups

#### Tentative Schedule

| Day | Topic | Led by |
|-----|-------|--------|
| Mon | Phylogenetics & Orthology/Paralogy | CGLab (Pavlopoulos group) |
| Tue | Differential Gene Expression Analysis | Bioinformatics Unit |
| Wed | ATAC-seq Analysis | Talianidis Lab |
| Thu | Single-cell RNA-seq | Lavigne/Delidakis Labs |
| Fri | Proteomics Analysis | Gkouridis Lab |
| *Additional* | Differential RNA-binding Interactions | Ntini Lab |
| *Additional* | Imaging Analysis | Pavlopoulos Lab |

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
   - Review basic Python syntax: [Python for beginners tutorial](https://github.com/kantale/python_lessons) (colleague's repo)
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
A fun, biology-themed dataset featuring Cretan beaches with environmental and biodiversity measurements. Used for learning data manipulation and basic statistics.

**Variables:** Beach characteristics, wildlife sightings (Kri-kri, sea turtles, monk seals), vegetation, tourism, weather

### Dataset 2: Simulated Bulk RNA-seq
A small, manageable gene expression dataset with 3 conditions. Used for learning expression analysis and differential expression concepts.

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

- IMBB-FORTH lab members (wet lab biologists, postdocs, PhD students)
- Researchers with **no programming experience**
- Scientists interested in understanding computational approaches
- Anyone who wants to **demystify data analysis**

**Expected participants:** Up to 40 people

---

## 🤝 Contributing Labs & Instructors

### Week 1 Coordination
- **CGLab (Pavlopoulos group):** Course design and Week 1 instruction
- **Supporting labs:** Additional helpers and troubleshooting

### Week 2 Contributors
- **Bioinformatics Unit:** Differential expression
- **Talianidis Lab:** ATAC-seq
- **Lavigne/Delidakis Labs:** Single-cell RNA-seq
- **Ntini Lab:** RNA-binding protein interactions
- **Gkouridis Lab:** Proteomics
- **Pavlopoulos Lab:** Imaging analysis

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

**Course Coordinator:** CGLab, IMBB-FORTH  
**Lab:** CGLab (Pavlopoulos group)
**Location:** Nikolaou Plastira 100, GR-70013, Heraklion, Crete, Greece

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

**Remember:** There are no stupid questions. We're all learning together!

---

## 🌟 Acknowledgments

This course was developed by the IMBB-FORTH community to promote computational literacy across the institute. Special thanks to all contributing labs and the Bioinformatics Unit for their support.

**Institute of Molecular Biology and Biotechnology (IMBB)**  
Foundation for Research and Technology - Hellas (FORTH)  
Heraklion, Crete, Greece

---

*"In 2026, every biologist should feel comfortable with code and data. Let's make that a reality."*
