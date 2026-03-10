# IMBB Data Analysis Course - First Draft Summary
## What's Been Created

### 📁 Repository Structure

```
imbb-data-analysis/
├── README.md                          # Main course overview
├── data/                              # All datasets
│   ├── README.md                      # Dataset documentation
│   ├── cretan_beaches.csv             # Fun dataset (25 beaches, 17 variables)
│   ├── bulk_rnaseq_counts.csv         # RNA-seq counts (100 genes × 9 samples)
│   ├── bulk_rnaseq_metadata.csv       # Sample information
│   ├── singlecell_expression.csv      # scRNA-seq (500 genes × 200 cells subset)
│   ├── singlecell_metadata.csv        # Cell annotations + UMAP coords
│   ├── README_rnaseq.md               # Bulk RNA-seq details
│   └── README_singlecell.md           # Single-cell details
├── docs/                              # Documentation
│   ├── SETUP.md                       # Installation guide (Win/Mac/Linux/Colab)
│   └── WEEK2_SCHEDULE.md              # Week 2 tentative schedule
└── week1/                             # Week 1 materials
    ├── day1_python_fundamentals.ipynb          # ✅ Complete notebook
    ├── day2_visualization_pandas.ipynb         # ✅ Complete notebook
    ├── day3_statistics_outline.md              # 📝 Detailed outline
    ├── day4_expression_pca_outline.md          # 📝 Detailed outline
    └── day5_differential_expression_outline.md # 📝 Detailed outline
```

---

## ✅ Completed Components

### 1. Main README.md
- Course philosophy and goals
- Week 1 & 2 structure
- Learning objectives
- Installation info
- Target audience
- Contributing labs

### 2. SETUP.md
- Windows native installation (Anaconda + VSCode)
- macOS installation
- Linux brief guide
- Google Colab backup option
- JupyterHub discussion (if available)
- Troubleshooting section
- Installation testing instructions

### 3. Week 2 Schedule
- Tentative sessions from different labs:
  - Phylogenetics (CGLab)
  - DE analysis (Bioinformatics Unit)
  - ATAC-seq (Talianidis Lab)
  - Single-cell (Lavigne/Delidakis Labs)
  - Proteomics (Gkouridis Lab)
  - Additional sessions (Ntini Lab, imaging)
- Format guidelines for contributors
- Bring-your-own-data sessions

### 4. Datasets (All Simulated)

#### Cretan Beaches (25 beaches)
**Variables:**
- Geographic: beach_name, region, beach_type, beach_length_m
- Wildlife: kri_kri_sightings, caretta_nests, monk_seal_sightings, lizard_species
- Vegetation: cretan_palms, thyme_coverage_pct
- Marine: sea_urchin_density, lionfish_spotted
- Environmental: water_temp_celsius, wind_speed_kmh, annual_rainfall_mm
- Tourism: avg_tourists_per_day, blue_flag

**Purpose:** Fun, relatable dataset for learning pandas, statistics, hypothesis testing

#### Bulk RNA-seq
- 100 genes × 9 samples (3 conditions, 3 replicates each)
- Clear DE patterns programmed in
- Negative binomial distribution
- Includes metadata file

#### Single-cell RNA-seq
- 500 genes × 1000 cells (200 subset provided)
- 4 cell types with distinct markers
- Pre-computed UMAP coordinates
- Realistic dropout patterns

### 5. Week 1 Notebooks

#### Day 1: Python Fundamentals (✅ COMPLETE)
**Sections:**
1. Variables and data types
2. Lists (indexing, slicing, **append**)
3. Dictionaries
4. Conditionals
5. Loops
6. Functions
7. **Imports explained**

**Features:**
- Multiple small exercises throughout
- Final integrative exercise
- Clear explanations for beginners
- Biological examples

#### Day 2: Visualization & Pandas (✅ COMPLETE)
**Sections:**
1. Seaborn plotting (scatter, histogram, box plot)
2. Pandas basics (loading data, selecting)
3. **Boolean indexing** (emphasized)
4. Groupby and aggregation
5. Plotting pandas data

**Features:**
- Uses Cretan beaches dataset
- Exercises throughout
- Comprehensive final exercise
- Focus on interpretation

#### Day 3: Statistics & Hypothesis Testing (📝 OUTLINE)
**Planned sections:**
1. Visualizing distributions
2. Basic statistics
3. t-test (parametric)
4. Mann-Whitney U (non-parametric)
5. **Permutation test** (emphasis on understanding)

**To develop:** Full notebook from outline

#### Day 4: Expression Data & PCA/UMAP (📝 OUTLINE)
**Planned sections:**
1. **Toy PCA example** (small matrix, visual explanation)
2. Understanding expression data
3. PCA on bulk RNA-seq
4. UMAP brief introduction (pre-computed)

**To develop:** Full notebook from outline

#### Day 5: Differential Expression (📝 OUTLINE)
**Planned structure:**
- **Hour 1:** Guided demo of DE analysis
  - Statistical basis
  - Testing genes
  - FDR correction
  - Visualization
- **Hour 2:** Project work with helpers

**To develop:** Full notebook from outline

---

## 📋 Instructions for GitHub Upload

### Repository Information
- **GitHub Organization:** https://github.com/cgenomicslab
- **Repository Name:** `imbb-data-analysis`
- **Full URL:** https://github.com/cgenomicslab/imbb-data-analysis

### Steps to Upload

1. **Download all materials from Claude**
2. **Create local directory structure** in `~/Documents/courses/imbb-data-analysis/`
3. **Initialize git repository**
4. **Create GitHub repo** in cgenomicslab organization
5. **Push to GitHub**

Detailed instructions are in the separate guide provided.

---

## 📋 Next Steps

### To Complete the Course

1. **Expand Day 3-5 Notebooks**
   - Convert outlines to full Jupyter notebooks
   - Add executable code cells
   - Include exercises
   - Add explanatory text

2. **Test Everything**
   - Run all notebooks end-to-end
   - Verify data paths work
   - Test exercises have clear instructions
   - Ensure plots render correctly

3. **Week 2 Coordination**
   - Contact contributing labs
   - Confirm availability
   - Share format guidelines
   - Collect their materials

4. **Setup Logistics**
   - Decide on native installation vs JupyterHub
   - Test installation instructions on Windows/Mac
   - Prepare backup Colab versions
   - Set up communication channel

5. **Pilot Test**
   - Run through materials yourself
   - Time each section
   - Identify difficult parts
   - Adjust pacing

---

## 💡 Course Strengths

1. **Relatable First Dataset**
   - Cretan beaches are fun and local
   - Easy to understand variables
   - Real-world feel

2. **Progressive Difficulty**
   - Starts very basic (Day 1)
   - Builds systematically
   - Clear learning path

3. **Emphasis on Concepts**
   - Explanation over tools
   - "Why" not just "how"
   - Statistical intuition (permutation test)

4. **Manageable Data Sizes**
   - Won't overwhelm beginners
   - Fast to process
   - Can understand full dataset

5. **Week 2 Diversity**
   - Exposure to many techniques
   - Learn from experts
   - See applications

---

## 🔧 Potential Improvements

### Before Launch

1. **Add visual aids**
   - Diagrams for complex concepts
   - Screenshots of expected outputs
   - Workflow illustrations

2. **More exercises**
   - Add optional challenge problems
   - Include solutions
   - Vary difficulty levels

3. **Cheat sheets**
   - Common pandas operations
   - Plotting quick reference
   - Statistical tests decision tree

4. **Troubleshooting guide**
   - Common errors
   - How to ask for help
   - Debugging tips

### During Course

1. **Collect feedback**
   - Daily quick surveys
   - Pace check-ins
   - Difficulty ratings

2. **Adapt as needed**
   - Skip/expand based on time
   - Add examples if needed
   - Adjust exercises

---

## 📧 Sharing with Colleagues

### For Review, Share:
1. Main README.md - get feedback on scope
2. SETUP.md - have someone test installations
3. Week 2 schedule - confirm with labs
4. Day 1-2 notebooks - pilot with a colleague

### For Week 2 Contributors:
- Send Week 2 schedule document
- Request their notebook/materials
- Share format guidelines
- Set deadlines

---

## 🎯 Key Decisions Needed

1. **Installation approach**
   - Native only vs JupyterHub
   - Windows: native or WSL?

2. **Week 1 dataset final choice**
   - Keep Cretan beaches?
   - Or use something more traditional?

3. **Day 3-5 depth**
   - How deep into statistics?
   - PCA theory vs just usage?
   - DE: show code or just interpret?

4. **Final Day 5 format**
   - More guided vs more independent?
   - Prepared examples vs exploration?

---

## ✨ What Makes This Course Special

1. **Demystifying approach** - "not for weirdos"
2. **Local flavor** - Cretan beaches
3. **Concept-first** - understanding over tools
4. **Week 2 diversity** - see many applications
5. **Manageable scope** - realistic for 2 weeks

---

**All files updated with "IMBB Data Analysis Course" naming. Ready for GitHub upload to cgenomicslab organization!**
