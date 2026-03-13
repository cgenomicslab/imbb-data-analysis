# Setup Guide
## IMBB Data Analysis Course

Please complete these steps **before Day 1** so we can start coding right away.

The recommended setup is **Miniconda + VSCode**. Google Colab and the course JupyterHub are available as alternatives.

---

## Step 1: Install Miniconda

Miniconda is a small installer that gives you Python and the `conda` package manager.

### Windows

1. Download the installer from [https://docs.conda.io/en/latest/miniconda.html](https://docs.conda.io/en/latest/miniconda.html) — choose **Miniconda3 Windows 64-bit**.
2. Run the `.exe` file. Accept the defaults, but **check** "Add Miniconda3 to my PATH environment variable" (ignore the warning).
3. Open **Command Prompt** (search "cmd" in the Start menu) and verify:

```
conda --version
python --version
```

Both should print a version number. If `conda` is not recognized, close and reopen the terminal.

### macOS

1. Download from [https://docs.conda.io/en/latest/miniconda.html](https://docs.conda.io/en/latest/miniconda.html).
   - Apple Silicon (M1/M2/M3): choose **Miniconda3 macOS Apple M1 64-bit pkg**
   - Intel Mac: choose **Miniconda3 macOS Intel x86 64-bit pkg**
2. Open the `.pkg` file and follow the installer.
3. Open **Terminal** (Applications → Utilities → Terminal) and verify:

```
conda --version
python --version
```

If `conda` is not found, run `source ~/.zshrc` (or `source ~/.bashrc`) and try again.

---

## Step 2: Create a Course Environment

Open a terminal (Command Prompt on Windows, Terminal on macOS) and run:

```bash
conda create -n imbb python=3.11 -y
conda activate imbb
```

You should see `(imbb)` at the beginning of your prompt. Then install the packages:

```bash
pip install numpy pandas matplotlib seaborn scipy scikit-learn umap-learn jupyter
```

This takes a few minutes. When it finishes, verify:

```bash
python -c "import pandas; import seaborn; import sklearn; print('All good.')"
```

---

## Step 3: Install VSCode

VSCode is a free code editor that runs Jupyter notebooks.

1. Download from [https://code.visualstudio.com](https://code.visualstudio.com) and install.
2. Open VSCode, click the **Extensions** icon on the left sidebar (or press `Ctrl+Shift+X` on Windows, `Cmd+Shift+X` on macOS).
3. Search for and install two extensions:
   - **Python** (by Microsoft)
   - **Jupyter** (by Microsoft)

### Connect VSCode to your environment

1. Press `Ctrl+Shift+P` (Windows) or `Cmd+Shift+P` (macOS).
2. Type **"Python: Select Interpreter"** and select the one that says `imbb`.
3. If it doesn't appear, click "Enter interpreter path" and paste the path from running `which python` (macOS) or `where python` (Windows) with the `imbb` environment activated.

---

## Step 4: Test Your Setup

1. Open VSCode.
2. Press `Ctrl+Shift+P` / `Cmd+Shift+P` → type **"Jupyter: Create New Blank Notebook"**.
3. Make sure the kernel in the top right says **imbb**. If not, click it and select the `imbb` environment.
4. Paste this into the first cell and press `Shift+Enter`:

```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from scipy import stats
from sklearn.decomposition import PCA

print("Everything works!")
```

If you see "Everything works!" — you are ready for Day 1.

---

## Step 5: Download Course Materials

### Option A: Download ZIP (simplest)

1. Go to [https://github.com/cgenomicslab/imbb-data-analysis](https://github.com/cgenomicslab/imbb-data-analysis)
2. Click the green **Code** button → **Download ZIP**
3. Extract the folder somewhere convenient (e.g., Desktop or Documents)
4. In VSCode: File → Open Folder → select the extracted folder

### Option B: Git clone

If you have git installed:

```bash
git clone https://github.com/cgenomicslab/imbb-data-analysis.git
```

---

## Alternatives

### Google Colab (no installation)

If you run into problems with the local setup, you can use Google Colab as a backup.

1. Go to [https://colab.research.google.com](https://colab.research.google.com) and sign in with a Google account.
2. File → Open Notebook → GitHub tab → paste `https://github.com/cgenomicslab/imbb-data-analysis`.
3. Select the notebook you want to open.

Colab has most packages pre-installed. For packages it doesn't have (like `umap-learn`), add a cell at the top:

```python
!pip install umap-learn
```

Keep in mind that Colab sessions are temporary — save your work to Google Drive or download the notebook when you're done.

### Course JupyterHub

We will provide access to a JupyterHub server with everything pre-installed. Connection details will be shared before the course. This is a good fallback if your local setup has issues, but we encourage you to set up your own environment so you can keep using it after the course.

---

## Troubleshooting

**"conda is not recognized" (Windows)**
Close and reopen Command Prompt. If it still doesn't work, search "Environment Variables" in Windows settings, edit the `Path` variable, and add the path to your Miniconda installation (typically `C:\Users\YourName\miniconda3` and `C:\Users\YourName\miniconda3\Scripts`). Restart the terminal.

**"conda: command not found" (macOS)**
Run `source ~/.zshrc` in Terminal. If that doesn't help, open `~/.zshrc` in a text editor and check that a line like `eval "$(/Users/YourName/miniconda3/bin/conda shell.zsh hook)"` exists. If not, run `~/miniconda3/bin/conda init zsh` and restart Terminal.

**VSCode doesn't show the imbb kernel**
Make sure you activated the environment (`conda activate imbb`) and installed `jupyter` inside it. Then in VSCode, press `Ctrl+Shift+P` → "Python: Select Interpreter" and look for the `imbb` environment.

**Package import errors**
Activate the environment first (`conda activate imbb`), then reinstall: `pip install package_name`.

**Still stuck?**
Email the course coordinator with a screenshot of the error. Or just use Google Colab for Day 1 — we can sort out installation issues during the break.
