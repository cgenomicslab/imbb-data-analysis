# Setup Guide
## IMBB Data Analysis Course

Please complete these steps **before Day 1** so we can start coding right away.

Steps 1–5 set up Python for Week 1. Step 6 adds R for Week 2 — you can do this later if you prefer.

Choose your operating system and follow the instructions. Google Colab and the course JupyterHub are available as alternatives if you run into problems.

---

## Windows

### 1. Install Miniconda

Miniconda gives you Python and the `conda` package manager.

1. Download the installer from [https://docs.conda.io/en/latest/miniconda.html](https://docs.conda.io/en/latest/miniconda.html) — choose **Miniconda3 Windows 64-bit**.
2. Run the `.exe` file. Keep all the default settings (do **not** check "Add to PATH" — you don't need it).
3. When the installation finishes, open the Start menu and search for **"Anaconda Prompt (miniconda3)"**. Open it.

You should see a window like this:

```
(base) C:\Users\YourName>
```

Type the following and press Enter:

```
conda --version
```

If it prints a version number (e.g., `conda 24.x.x`), the installation worked.

**Important:** From now on, always use this **Anaconda Prompt** when working on the course — not the regular Command Prompt or PowerShell.

### 2. Create a course environment

In the Anaconda Prompt, run these commands one at a time (press Enter after each, and wait for it to finish before running the next):

```
conda create -n imbb python=3.11 -y
```

```
conda activate imbb
```

Your prompt should now start with `(imbb)` instead of `(base)`. Now install the packages:

```
conda install numpy pandas matplotlib seaborn scipy scikit-learn jupyter -y
```

```
pip install umap-learn
```

When everything finishes, verify:

```
python -c "import pandas; import seaborn; import sklearn; print('All good.')"
```

If it prints "All good." — the environment is ready.

**Remember:** Every time you open a new Anaconda Prompt to work on the course, you need to run `conda activate imbb` first.

### 3. Install VSCode

VSCode is a free code editor that can run Jupyter notebooks.

1. Download from [https://code.visualstudio.com](https://code.visualstudio.com) and install with default settings.
2. Open VSCode. Click the **Extensions** icon on the left sidebar (or press `Ctrl+Shift+X`).
3. Search for and install these two extensions:
   - **Python** (by Microsoft)
   - **Jupyter** (by Microsoft)

### 4. Test everything

1. Open VSCode.
2. Press `Ctrl+Shift+P`, type **"Jupyter: Create New Blank Notebook"** and select it.
3. In the top right corner of the notebook, click the kernel name. Select the **imbb** environment (it may appear as `Python 3.11 (imbb)`). If you don't see it, press `Ctrl+Shift+P`, type **"Python: Select Interpreter"**, and pick `imbb` from the list.
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

### 5. Download course materials

1. Go to [https://github.com/cgenomicslab/imbb-data-analysis](https://github.com/cgenomicslab/imbb-data-analysis)
2. Click the green **Code** button → **Download ZIP**
3. Extract the folder somewhere convenient (e.g., Desktop or Documents)
4. In VSCode: File → Open Folder → select the extracted folder

### 6. Install R (needed for Week 2)

Some Week 2 sessions use R. You can install R into the same conda environment so it works inside Jupyter — no separate software needed.

In the Anaconda Prompt, make sure your environment is active, then run:

```
conda activate imbb
```

```
conda install -c conda-forge r-base r-irkernel -y
```

This may take a few minutes. When it finishes, verify:

```
R --version
```

If it prints version information, R is ready. You will be able to switch between Python and R kernels inside Jupyter/VSCode.

**Alternative:** If you prefer a dedicated R environment, you can install [RStudio Desktop](https://posit.co/download/rstudio-desktop/) separately. The Week 2 instructors will provide specific R package installation instructions.

### Windows troubleshooting

**Anaconda Prompt not found in Start menu**
Search for "miniconda" instead. If nothing appears, re-run the Miniconda installer.

**`conda activate imbb` shows an error**
Make sure you are in Anaconda Prompt (not Command Prompt). You should see `(base)` in your prompt before activating.

**VSCode doesn't show the imbb kernel**
Press `Ctrl+Shift+P` → "Python: Select Interpreter" → look for `imbb`. If it's not listed, open Anaconda Prompt, run `conda activate imbb`, then `conda install jupyter -y`.

---

## macOS

### 1. Install Miniconda

Open **Terminal** (Applications → Utilities → Terminal, or press `Cmd+Space` and type "Terminal").

Copy and paste this command to download and run the Miniconda installer:

**Apple Silicon (M1/M2/M3/M4):**
```bash
curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh
bash Miniconda3-latest-MacOSX-arm64.sh
```

**Intel Mac:**
```bash
curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
bash Miniconda3-latest-MacOSX-x86_64.sh
```

Not sure which Mac you have? Click the Apple menu → About This Mac. If it says "Apple M1" or similar, it's Apple Silicon. If it says "Intel", it's Intel.

The installer will ask you a few questions:
- Press `Enter` to review the license, then type `yes` to accept
- Press `Enter` to confirm the default installation location
- Type `yes` when asked to initialize conda

When it finishes, **close and reopen Terminal**. You should now see `(base)` at the beginning of your prompt:

```
(base) yourname@mac ~ %
```

Verify:

```bash
conda --version
```

If it prints a version number, the installation worked. If it says "command not found", run:

```bash
~/miniconda3/bin/conda init zsh
```

Then close and reopen Terminal.

You can delete the installer file:

```bash
rm Miniconda3-latest-MacOSX-*.sh
```

### 2. Create a course environment

In Terminal, run:

```bash
conda create -n imbb python=3.11 -y
```

Wait for it to finish. Then:

```bash
conda activate imbb
```

Your prompt should now start with `(imbb)` instead of `(base)`. Install the packages:

```bash
conda install numpy pandas matplotlib seaborn scipy scikit-learn jupyter -y
```

```bash
pip install umap-learn
```

Verify:

```bash
python -c "import pandas; import seaborn; import sklearn; print('All good.')"
```

If it prints "All good." — the environment is ready.

**Remember:** Every time you open a new Terminal to work on the course, you need to run `conda activate imbb` first.

### 3. Install VSCode

Download from [https://code.visualstudio.com](https://code.visualstudio.com). Open the downloaded `.zip` file and drag **Visual Studio Code** to your Applications folder.

Alternatively, if you have [Homebrew](https://brew.sh) installed:

```bash
brew install --cask visual-studio-code
```

Open VSCode. Click the **Extensions** icon on the left sidebar (or press `Cmd+Shift+X`). Search for and install these two extensions:
- **Python** (by Microsoft)
- **Jupyter** (by Microsoft)

### 4. Test everything

1. Open VSCode.
2. Press `Cmd+Shift+P`, type **"Jupyter: Create New Blank Notebook"** and select it.
3. In the top right corner of the notebook, click the kernel name. Select the **imbb** environment (it may appear as `Python 3.11 (imbb)`). If you don't see it, press `Cmd+Shift+P`, type **"Python: Select Interpreter"**, and pick `imbb` from the list.
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

### 5. Download course materials

The simplest way is to clone the repository:

```bash
git clone https://github.com/cgenomicslab/imbb-data-analysis.git
```

macOS comes with git pre-installed. If for some reason it isn't available, you can instead:

1. Go to [https://github.com/cgenomicslab/imbb-data-analysis](https://github.com/cgenomicslab/imbb-data-analysis)
2. Click the green **Code** button → **Download ZIP**
3. Extract the folder

Then open VSCode: File → Open Folder → select the course folder.

### 6. Install R (needed for Week 2)

Some Week 2 sessions use R. You can install R into the same conda environment so it works inside Jupyter — no separate software needed.

In Terminal:

```bash
conda activate imbb
```

```bash
conda install -c conda-forge r-base r-irkernel -y
```

This may take a few minutes. When it finishes, verify:

```bash
R --version
```

If it prints version information, R is ready. You will be able to switch between Python and R kernels inside Jupyter/VSCode.

**Alternative:** If you prefer a dedicated R environment, you can install [RStudio Desktop](https://posit.co/download/rstudio-desktop/) separately. The Week 2 instructors will provide specific R package installation instructions.

### macOS troubleshooting

**"conda: command not found" after installing**
Run `~/miniconda3/bin/conda init zsh`, then close and reopen Terminal.

**"xcrun: error: invalid active developer path"**
macOS is asking you to install command-line tools. Run `xcode-select --install`, follow the prompt, then try again.

**VSCode doesn't show the imbb kernel**
Press `Cmd+Shift+P` → "Python: Select Interpreter" → look for `imbb`. If it's not listed, open Terminal, run `conda activate imbb`, then `conda install jupyter -y`.

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

We will provide access to a JupyterHub server with everything pre-installed (Python, R, and all required packages). Connection details will be shared before the course. This is a good fallback if your local setup has issues, but we encourage you to set up your own environment so you can keep using it after the course.

---

## Still stuck?

Email the course coordinator with a screenshot of the error. Or just use Google Colab for Day 1 — we can sort out installation issues during the break.
