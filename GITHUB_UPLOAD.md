# Quick Start: Upload to GitHub

## Step-by-Step Commands

Open Terminal and run these commands **exactly as shown**:

### 1. Navigate and Initialize

```bash
# Go to your courses directory
cd ~/Documents/courses

# Download the folder from Claude and place it here as "imbb-data-analysis"
# Then navigate into it
cd imbb-data-analysis

# Initialize git
git init

# Check what files you have
ls -la
```

### 2. Add All Files and Commit

```bash
# Add all files
git add .

# Verify what will be committed
git status

# Commit with message
git commit -m "Initial commit: IMBB data analysis course materials"
```

### 3. Create GitHub Repository

**In your browser:**
1. Go to https://github.com/cgenomicslab
2. Click **"New"** button (green button)
3. Repository name: `imbb-data-analysis`
4. Description: "Hands-on data analysis course for IMBB-FORTH - Python, statistics, and expression data"
5. Choose **Public** or **Private**
6. **DO NOT** check "Initialize with README"
7. Click **"Create repository"**

### 4. Connect and Push

```bash
# Add the remote (replace with your actual org if different)
git remote add origin https://github.com/cgenomicslab/imbb-data-analysis.git

# Rename branch to main
git branch -M main

# Push to GitHub
git push -u origin main
```

### 5. Verify

Go to: https://github.com/cgenomicslab/imbb-data-analysis

Check that all files are there!

---

## Repository Structure You Should See

```
imbb-data-analysis/
├── .gitignore
├── README.md
├── DRAFT_SUMMARY.md
├── data/
│   ├── README.md
│   ├── README_rnaseq.md
│   ├── README_singlecell.md
│   ├── cretan_beaches.csv
│   ├── bulk_rnaseq_counts.csv
│   ├── bulk_rnaseq_metadata.csv
│   ├── singlecell_expression.csv
│   └── singlecell_metadata.csv
├── docs/
│   ├── SETUP.md
│   └── WEEK2_SCHEDULE.md
└── week1/
    ├── day1_python_fundamentals.ipynb
    ├── day2_visualization_pandas.ipynb
    ├── day3_statistics_outline.md
    ├── day4_expression_pca_outline.md
    └── day5_differential_expression_outline.md
```

---

## Future Updates

To make changes and push them:

```bash
# Make your changes, then:
git add .
git commit -m "Description of what you changed"
git push
```

---

## Share with Students

**Repository URL:**
```
https://github.com/cgenomicslab/imbb-data-analysis
```

**Clone command for students:**
```bash
git clone https://github.com/cgenomicslab/imbb-data-analysis.git
```

**Or download ZIP:**
- Go to repository URL
- Click green "Code" button
- Click "Download ZIP"

---

## Troubleshooting

**If push is rejected:**
```bash
git pull origin main --allow-unrelated-histories
git push
```

**If authentication fails:**
- You may need a Personal Access Token
- GitHub Settings → Developer settings → Personal access tokens

---

## All Set!

Your course materials are now on GitHub at:
**https://github.com/cgenomicslab/imbb-data-analysis**

Share this URL with colleagues for feedback!
