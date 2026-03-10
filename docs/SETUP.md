# Installation & Setup Guide
## IMBB Data Analysis Course - IMBB-FORTH

This guide will help you set up Python and the necessary tools for the course. Choose the method that works best for you.

---

## 🎯 Quick Decision Guide

**Choose your setup method:**

- **Windows users:** → Native Python (Option 1) or Google Colab (Option 3)
- **Mac users:** → Native Python (Option 2) or Google Colab (Option 3)  
- **Linux users:** → Native Python (similar to Mac) or Google Colab (Option 3)
- **Installation problems?** → Google Colab (Option 3)
- **Want centralized access?** → IMBB JupyterHub (Option 4, if available)

**Recommended:** Try native installation first (Options 1-2), keep Google Colab as backup.

---

## Option 1: Windows Native Installation

### Step 1: Install Python via Anaconda

1. **Download Anaconda:**
   - Go to [https://www.anaconda.com/download](https://www.anaconda.com/download)
   - Download the Windows installer (Python 3.11 or newer)
   - File size: ~600 MB

2. **Install Anaconda:**
   - Run the downloaded `.exe` file
   - Click "Next" through the installer
   - **Important:** Check "Add Anaconda to my PATH environment variable" (even if not recommended)
   - Install for "Just Me"
   - Complete installation (~5-10 minutes)

3. **Verify installation:**
   - Open "Anaconda Prompt" from Start Menu
   - Type: `python --version`
   - Should show: `Python 3.11.x` or newer
   - Type: `conda --version`
   - Should show conda version

### Step 2: Install Required Packages

Open "Anaconda Prompt" and run these commands one by one:

```bash
conda install numpy pandas matplotlib seaborn scipy scikit-learn -y
conda install jupyter notebook -y
```

**Wait** for each command to finish (may take 2-5 minutes).

### Step 3: Install VSCode

1. **Download VSCode:**
   - Go to [https://code.visualstudio.com](https://code.visualstudio.com)
   - Download Windows installer
   - Run installer with default settings

2. **Install Python Extension:**
   - Open VSCode
   - Click Extensions icon (left sidebar, or Ctrl+Shift+X)
   - Search for "Python" (by Microsoft)
   - Click "Install"
   - Search for "Jupyter" (by Microsoft)
   - Click "Install"

3. **Test setup:**
   - Open VSCode
   - Press Ctrl+Shift+P
   - Type "Jupyter: Create New Blank Notebook"
   - In the notebook, type: `import pandas as pd; print(pd.__version__)`
   - Press Shift+Enter to run
   - Should print pandas version (e.g., `2.2.0`)

### Common Windows Issues

**Problem:** "python is not recognized"
- **Solution:** Add Python to PATH manually:
  - Search "Environment Variables" in Windows
  - Edit "Path" variable
  - Add: `C:\Users\YourUsername\anaconda3`
  - Add: `C:\Users\YourUsername\anaconda3\Scripts`
  - Restart terminal

**Problem:** Permission errors during installation
- **Solution:** Run Anaconda Prompt as Administrator (right-click → Run as administrator)

**Note on WSL:** We **do NOT recommend** using WSL (Windows Subsystem for Linux) for this course. Native Windows installation is simpler and sufficient.

---

## Option 2: macOS Native Installation

### Step 1: Install Python via Anaconda

1. **Download Anaconda:**
   - Go to [https://www.anaconda.com/download](https://www.anaconda.com/download)
   - Download macOS installer (Intel or Apple Silicon)
   - File size: ~600 MB

2. **Install Anaconda:**
   - Open the downloaded `.pkg` file
   - Follow installation wizard
   - Use default settings
   - Complete installation

3. **Verify installation:**
   - Open "Terminal" (Applications → Utilities → Terminal)
   - Type: `python --version`
   - Should show: `Python 3.11.x` or newer
   - Type: `conda --version`
   - Should show conda version

### Step 2: Install Required Packages

Open Terminal and run:

```bash
conda install numpy pandas matplotlib seaborn scipy scikit-learn -y
conda install jupyter notebook -y
```

### Step 3: Install VSCode

1. **Download VSCode:**
   - Go to [https://code.visualstudio.com](https://code.visualstudio.com)
   - Download macOS installer
   - Open `.zip` file and drag VSCode to Applications

2. **Install Extensions:**
   - Open VSCode
   - Click Extensions icon (Cmd+Shift+X)
   - Install "Python" (by Microsoft)
   - Install "Jupyter" (by Microsoft)

3. **Test setup:**
   - Open VSCode
   - Press Cmd+Shift+P
   - Type "Jupyter: Create New Blank Notebook"
   - Test with: `import pandas as pd; print(pd.__version__)`

---

## Option 3: Google Colab (No Installation)

**Best for:** Anyone with installation problems, or as a backup option.

### Setup Steps

1. **Create Google Account:**
   - If you don't have one: [https://accounts.google.com](https://accounts.google.com)

2. **Access Google Colab:**
   - Go to [https://colab.research.google.com](https://colab.research.google.com)
   - Sign in with Google account

3. **Test Colab:**
   - Click "New Notebook"
   - In a cell, type: `import pandas as pd; print(pd.__version__)`
   - Press Shift+Enter
   - Should print pandas version

4. **Using Course Materials:**
   - Download `.ipynb` files from our GitHub
   - In Colab: File → Upload Notebook → Choose file
   - OR: File → Open Notebook → GitHub tab → Enter repo URL: `https://github.com/cgenomicslab/imbb-data-analysis`

### Colab Advantages
✅ No installation needed  
✅ Works on any computer with internet  
✅ Pre-installed packages  
✅ Free GPU access (not needed for this course)

### Colab Limitations
⚠️ Files don't persist (save to Google Drive)  
⚠️ Sessions timeout after inactivity  
⚠️ Requires internet connection

### Saving Your Work in Colab
- **Option 1:** File → Save a copy in Drive
- **Option 2:** File → Download → Download .ipynb
- **Recommended:** Save regularly during sessions!

---

## Option 4: IMBB JupyterHub (If Available)

**Status:** To be confirmed with institute administration.

If we set up a centralized JupyterHub:

### Advantages
✅ Pre-configured environment  
✅ No installation needed  
✅ Accessible from any computer  
✅ Shared computing resources

### Access Instructions (TBD)
- Server URL will be provided
- Username/password will be sent via email
- Login and start coding!

---

## Linux Installation (Brief)

Most Linux users can follow similar steps to macOS:

1. **Install Anaconda:**
   - Download from anaconda.com
   - Run: `bash Anaconda3-*.sh`
   - Follow prompts

2. **Install packages:**
   ```bash
   conda install numpy pandas matplotlib seaborn scipy scikit-learn jupyter -y
   ```

3. **Install VSCode:**
   - Download `.deb` or `.rpm` from code.visualstudio.com
   - Install Python and Jupyter extensions

---

## 📦 Required Packages Summary

All methods should have these packages:

| Package | Purpose |
|---------|---------|
| `numpy` | Numerical arrays and operations |
| `pandas` | DataFrames and data manipulation |
| `matplotlib` | Basic plotting |
| `seaborn` | Statistical visualizations |
| `scipy` | Scientific computing and statistics |
| `scikit-learn` | Machine learning (PCA, etc.) |
| `jupyter` | Notebook interface |

**Versions:** Any recent version is fine. Course tested with Python 3.10+.

---

## ✅ Test Your Installation

Before Day 1, test that everything works:

### Test 1: Launch Jupyter

**Windows:**
- Open Anaconda Prompt
- Type: `jupyter notebook`
- Should open browser with Jupyter

**Mac/Linux:**
- Open Terminal
- Type: `jupyter notebook`

**All platforms:**
- Browser should open showing file navigator
- Create new Python 3 notebook
- You're ready!

### Test 2: Import Packages

In a Jupyter notebook or VSCode, run this cell:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from scipy import stats
from sklearn.decomposition import PCA

print("✅ All packages imported successfully!")
print(f"NumPy version: {np.__version__}")
print(f"Pandas version: {pd.__version__}")
```

If this runs without errors, you're all set!

### Test 3: Simple Plot

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Load example data
tips = sns.load_dataset('tips')

# Create plot
sns.scatterplot(data=tips, x='total_bill', y='tip')
plt.title('Test Plot')
plt.show()
```

If you see a scatter plot, everything works!

---

## 🆘 Troubleshooting

### General Issues

**Problem:** Package import errors
- **Solution:** Reinstall package: `conda install package_name -y`

**Problem:** Jupyter doesn't start
- **Solution:** Try: `conda install jupyter -y --force-reinstall`

**Problem:** VSCode can't find Python
- **Solution:** In VSCode, press Ctrl/Cmd+Shift+P → "Python: Select Interpreter" → Choose Anaconda Python

### Getting Help

1. **Before Day 1:**
   - Email course coordinator with screenshot of error
   - Try Google Colab as backup

2. **During Day 1:**
   - Helpers will circulate to assist
   - Use Google Colab if installation fails

3. **General Resources:**
   - [Anaconda Documentation](https://docs.anaconda.com)
   - [VSCode Python Tutorial](https://code.visualstudio.com/docs/python/python-tutorial)
   - [Google Colab FAQ](https://research.google.com/colaboratory/faq.html)

---

## 📚 Downloading Course Materials

### Method 1: Download ZIP (Easiest)

1. Go to https://github.com/cgenomicslab/imbb-data-analysis
2. Click green "Code" button
3. Click "Download ZIP"
4. Extract to your Documents folder
5. Open in VSCode or Jupyter

### Method 2: Git Clone (Advanced)

If you have git installed:

```bash
git clone https://github.com/cgenomicslab/imbb-data-analysis.git
cd imbb-data-analysis
jupyter notebook
```

### Method 3: Individual Files

- Download specific `.ipynb` notebooks as needed
- Download datasets from `data/` folder
- Save to a dedicated course folder

---

## 🎓 Ready for Day 1!

Once you can:
- ✅ Open Jupyter notebooks (any method)
- ✅ Import numpy, pandas, matplotlib, seaborn
- ✅ Create a simple plot

**You're ready to start!**

See you on Day 1. Don't worry if you encounter issues—we'll have help available.

---

## 💡 Tips for Success

1. **Create a dedicated folder** for course materials
2. **Organize by day:** `day1/`, `day2/`, etc.
3. **Save your work frequently**
4. **Keep notes** in the notebooks (add markdown cells)
5. **Don't be afraid to experiment** and break things!

Remember: **Everyone was a beginner once.** It's okay to ask for help!

---

*Questions? Contact the course coordinator or ask during Day 1.*
