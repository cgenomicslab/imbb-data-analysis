# Setup Guide

## IMBB Data Analysis Course

Please complete these steps **before Day 1** so we can start coding right away.

Steps 1–4 set up Python for Week 1. Step 5 adds R for Week 2 — you can do this later.

Choose your operating system and follow the instructions below.

---

## Windows

### Step 1 — Install Python

Download the latest **Python 3.11** installer from: https://www.python.org/downloads/release/python-31111/

Run the installer:

- ✅ Check **"Add Python to PATH"** (important!)
- Click **Install Now**

Open **Command Prompt** (press `Win+R`, type `cmd`, press Enter) and verify:

```
python --version
```

If it prints `Python 3.11.x` — Python is installed.

### Step 2 — Download course materials

**Option A — Download ZIP:**

1. Go to https://github.com/cgenomicslab/imbb-data-analysis
2. Click the green **Code** button → **Download ZIP**
3. Extract the folder somewhere convenient (e.g., Documents)
4. Open Command Prompt in that folder (type `cmd` in the address bar and press Enter)

**Option B — Clone with Git** (if you have Git installed):

```
git clone https://github.com/cgenomicslab/imbb-data-analysis.git
cd imbb-data-analysis
```

### Step 3 — Create environment and install packages

Make sure you are inside the `imbb-data-analysis` folder in your Command Prompt. Then run these three commands, one at a time:

```
python -m venv imbb
```

```
imbb\Scripts\activate
```

Your prompt should now start with `(imbb)`. Now install everything:

```
pip install -r requirements.txt
```

When it finishes, register the environment as a Jupyter kernel:

```
python -m ipykernel install --user --name=imbb --display-name "Python (imbb)"
```

### Step 4 — Test your setup

Start Jupyter:

```
jupyter notebook
```

This will open your browser. Navigate to `docs/test_installation.ipynb` and run the cell. If you see **"Everything works!"** — you are ready for Day 1.

**Remember:** Every time you open a new Command Prompt to work on the course, navigate to the course folder and activate the environment first:

```
imbb\Scripts\activate
```

### Step 5 — Install R (needed for Week 2)

Some Week 2 sessions use R. You can do this later.

**Option A — RStudio Desktop (recommended)**

1. Download and install R from https://cran.r-project.org (choose "Download R for Windows" → "base").
2. Download and install [RStudio Desktop](https://posit.co/download/rstudio-desktop/).
3. Open RStudio. If it opens without errors, R is ready.

**Option B — R inside Jupyter (via conda)**

If you prefer to run R notebooks inside Jupyter, install [Miniconda](https://docs.conda.io/en/latest/miniconda.html), then:

```
conda install -c conda-forge r-base r-irkernel -y
R -e "IRkernel::installspec()"
```

### Windows troubleshooting

**`python` opens the Microsoft Store or is not recognized:**
Re-run the Python installer and make sure "Add Python to PATH" is checked. Alternatively, try `python3` instead of `python`.

**`pip install` fails with permission errors:**
Make sure the `(imbb)` environment is activated — you should see `(imbb)` at the start of your prompt.

---

## macOS

### Step 1 — Install Python

macOS comes with an older Python. Install Python 3.11:

Download the macOS installer from: https://www.python.org/downloads/release/python-31111/

Choose the correct installer for your Mac:
- **Apple Silicon (M1/M2/M3/M4):** macOS 64-bit universal2 installer
- **Intel Mac:** macOS 64-bit Intel installer

Not sure which Mac you have? Click the Apple menu → About This Mac. If it says "Apple M1" or similar, it's Apple Silicon.

Install normally. Then open **Terminal** (Cmd+Space, type "Terminal") and verify:

```
python3 --version
```

If it prints `Python 3.11.x` — Python is installed.

### Step 2 — Download course materials

**Option A — Clone with Git** (macOS comes with Git pre-installed):

```
git clone https://github.com/cgenomicslab/imbb-data-analysis.git
cd imbb-data-analysis
```

**Option B — Download ZIP:**

1. Go to https://github.com/cgenomicslab/imbb-data-analysis
2. Click the green **Code** button → **Download ZIP**
3. Extract the folder somewhere convenient (e.g., Documents)
4. Open Terminal in that folder (right-click the folder → "Open Terminal" or drag the folder onto the Terminal icon)


### Step 3 — Create environment and install packages

Make sure you are inside the `imbb-data-analysis` folder in Terminal. Then run:

```
python3 -m venv imbb
```

```
source imbb/bin/activate
```

Your prompt should now start with `(imbb)`. Now install everything:

```
pip install -r requirements.txt
```

When it finishes, register the environment as a Jupyter kernel:

```
python -m ipykernel install --user --name=imbb --display-name "Python (imbb)"
```

### Step 4 — Test your setup

Start Jupyter:

```
jupyter notebook
```

This will open your browser. Navigate to `docs/test_installation.ipynb` and run the cell. If you see **"Everything works!"** — you are ready for Day 1.

**Remember:** Every time you open a new Terminal to work on the course, navigate to the course folder and activate the environment first:

```
source imbb/bin/activate
```

### Step 5 — Install R (needed for Week 2)

Some Week 2 sessions use R. You can do this later.

**Option A — RStudio Desktop (recommended)**

1. Download and install R from https://cran.r-project.org (choose "Download R for macOS" and pick the installer matching your Mac).
2. Download and install [RStudio Desktop](https://posit.co/download/rstudio-desktop/).
3. Open RStudio. If it opens without errors, R is ready.

**Option B — R inside Jupyter (via conda)**

If you prefer to run R notebooks inside Jupyter, install [Miniconda](https://docs.conda.io/en/latest/miniconda.html), then:

```
conda install -c conda-forge r-base r-irkernel -y
R -e "IRkernel::installspec()"
```

### macOS troubleshooting

**"xcrun: error: invalid active developer path":**
Run `xcode-select --install`, follow the prompt, then try again.

**"python3: command not found" after installing:**
Close and reopen Terminal, then try again.

---

## Alternatives

### Google Colab (no installation needed)

If you run into problems with the local setup, you can use Google Colab as a backup.

1. Go to https://colab.research.google.com and sign in with a Google account.
2. File → Open Notebook → GitHub tab → paste `https://github.com/cgenomicslab/imbb-data-analysis`.
3. Select the notebook you want to open.

Colab has most packages pre-installed. For any missing ones, add a cell at the top:

```
!pip install umap-learn
```

Keep in mind that Colab sessions are temporary — save your work to Google Drive or download the notebook when you're done.

### Course JupyterHub

We will provide access to a JupyterHub server with everything pre-installed (Python, R, and all packages). Connection details will be shared before the course. This is a good fallback if your local setup has issues, but we encourage you to set up your own environment so you can keep using it after the course.

### VSCode

If you prefer a code editor over Jupyter in the browser, [VSCode](https://code.visualstudio.com) with the **Python** and **Jupyter** extensions (both by Microsoft) can also run the notebooks. After installing, select the `imbb` kernel from the top-right corner of any notebook.

---

## Still stuck?

Email the course coordinator with a screenshot of the error. Or just use Google Colab for Day 1 — we can sort out installation issues during the break.
