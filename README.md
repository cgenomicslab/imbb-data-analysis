# IMBB Data Analysis workshop
## **I**nstitute of **M**olecular **B**iology and **B**iotechnology - FORTH, Heraklion, Crete
- ## **April 27 – May 8, 2026**
### *Mentoring and Career Track Scheme (MCTS)*

A **hands-on** introduction to Python programming, data analysis, and computational biology for wet lab biologists.

<img src="./figures/logo.png" width="180"/>

---

## 🎯 Objectives

This workshop aims to:

- **Broaden data analysis understanding** in the institute
- **Demystify** computational methods  
- **Explain the logic** behind methods, not just how to run tools

This is an introductory boost — not a comprehensive training program. The goal is to get you started, familiarize you with code, and help you understand the concepts behind common analyses.

---

## 📚 Course Structure

### Week 1: Data Analysis Fundamentals ([CGLab](https://cgenomicslab.org/#members))
**Format:** 2-hour sessions daily, Monday–Thursday  
**Level:** Complete beginners  
**Dates:** April 27 – April 30  
**Time:** 10:00–12:00  

### Week 2: Specialized Topics in Genomics (IMBB bioinformatics/genomics experts)
**Format:** 2-hour sessions daily, Monday–Thursday  
**Level:** Complete beginners  
**Dates:** May 4 – May 8  
**Time:** 10:00–12:00  

---

## 🗓️ Week 1 Schedule

| Date | Room | Coordination | Topic | Notebook |
|------|------|---------------------|-------|----------|
| **Mon 27/4** — Day 1 | Orfanoudakis | Alexandros Pittis | Python Fundamentals | [day1.ipynb](week1/day1_python_fundamentals.ipynb) |
| **Tue 28/4** — Day 2 | Orfanoudakis | Alexandros Pittis | Plotting & Data Exploration | [day2.ipynb](week1/day2_plotting_data_exploration.ipynb) |
| **Wed 29/4** — Day 3 | Pagiatakis | Alexandros Pittis | Statistics & P-value Logic | [day3.ipynb](week1/day3_statistics_pvalue.ipynb) |
| **Thu 30/4** — Day 4 | Pagiatakis | Alexandros Pittis | Enrichment & Dimensionality Reduction | [day4.ipynb](week1/day4_enrichment_dimensionality.ipynb) |

🪵🔥 **Thursday, April 30** (after Day 4, time TBD): BBQ 🐙🦞🍤🦪🦐🦀 — everyone welcome!

---

## 🗓️ Week 2 Schedule

| Date | Room | Coordination (TBD) | Topic | Notebook |
|------|------|---------------------|-------|----------|
| **Mon 4/5** — Day 5 | Pagiatakis | Christos Andronis / Electra Tsaglioti (Bioinformatics Unit) | Bulk RNA-seq analysis | rna_seq.ipynb |
| **Tue 5/5** — Day 6 | TBD | Vaso Theodorou / Ethan Baird (Delidakis lab) | Single-cell RNA-seq analysis | scrna-seq.ipynb |
| **Wed 6/5** — Day 7 | Pagiatakis | Orsalia Hazapis (Talianidis lab) | ATAC-seq | atac_sec.ipynb |
| **Thu 7/5** — Day 8 | Pagiatakis | Instructors | Bring your data |  |
| **Fri 8/5** — Day 9 | Pagiatakis (TBC) | Instructors | Bring your data |  |

Materials for Week 2 will be provided by each contributing group. Links will be added here as they become available.

Final schedule to be confirmed with contributing labs/instructors.

---

## 🚀 Getting Started

> *Programming is learned at the keyboard, not in the classroom.*

### Prerequisites
- **No programming experience required**
- Laptop with admin rights for software installation

### Before Day 1
1. **Install Python and tools** — see [docs/SETUP.md](docs/SETUP.md)
2. **Go through the preparation notebooks** — see [precourse/](precourse/) (Python basics, and an R introduction for Week 2)

### Course Materials
All materials are in this repository:
- **week1/** — Jupyter notebooks for Week 1 (4 days)
- **precourse/** — Preparation notebooks (Python and R basics)
- **data/** — Datasets used throughout the course
- **docs/** — Setup instructions

---

## 💻 Technical Setup

**Recommended:** Miniconda + VSCode (see [docs/SETUP.md](docs/SETUP.md))

**Python packages (Week 1):** numpy, pandas, matplotlib, seaborn, scipy, scikit-learn, umap-learn

**R (Week 2):** Some Week 2 sessions use R. To add R to your conda environment:

```
conda install -c conda-forge r-base r-irkernel -y
```

This lets you run R notebooks in Jupyter. [RStudio](https://posit.co/download/rstudio-desktop/) is also an option if you prefer a dedicated R environment.

**Alternatives:** Google Colab (browser-based, no installation) or IMBB JupyterHub (access provided during course, Python and R pre-installed).

---

## 👥 Target Audience

- IMBB-FORTH lab members (MSc students, PhD students, postdocs, technicians) with **no programming experience**

**Expected participants:** Up to 40

---

## 🤝 Course Coordination & Contributing Groups

**Coordination:** [CGLab (Alexandros Pittis)](https://cgenomicslab.org/)

**Contributing labs (tentative):** 
- [Bioinformatics Unit](https://www.imbb.forth.gr/en/facilities/Bioinformatics-Unit.15/) (Andronis)
- [Genome Integrity](https://imbb.forth.gr/en/research/Matthieu-Lavigne.70/)/[Genomics Facility](https://www.imbb.forth.gr/en/facilities/Genomics-Facility.13/&tabid=Home.84) (Lavigne)
- [Stem Cells](https://www.imbb.forth.gr/en/research/Christos-Delidakis.58/) (Delidakis)
- [Chromatin & Cancer Epigenetics](https://www.imbb.forth.gr/en/research/Iannis-Talianidis.75/) (Talianidis)

---

## 🔗 Additional Resources

**Python**
- [Python Graph Gallery](https://python-graph-gallery.com/) — the biggest collection of Python chart examples
- [Python lessons (in Greek)](https://github.com/kantale/python_lessons) by Alexandros Kanterakis (ICS-FORTH)
- [Pandas getting started tutorials](https://pandas.pydata.org/docs/getting_started/intro_tutorials/) — official pandas introduction
- [Seaborn documentation](https://seaborn.pydata.org/)

**Genomics**
- [RNA-seq analysis with DESeq2](https://bioconductor.org/packages/release/bioc/vignettes/DESeq2/inst/doc/DESeq2.html) — the standard bulk RNA-seq tutorial
- [Scanpy tutorials](https://scanpy.readthedocs.io/en/stable/tutorials.html) — single-cell RNA-seq in Python
- [Single-cell best practices](https://www.sc-best-practices.org/) — comprehensive single-cell analysis guide

---

## 📧 Contact & Support

**Course Coordinator:** [Alexandros Pittis](https://cgenomicslab.org/#contact) `alexandros.pittis@gmail.com`

---

## 📝 Feedback

This is a living course that will improve with your input. After each session, we **welcome feedback on pace, clarity, and content**.
