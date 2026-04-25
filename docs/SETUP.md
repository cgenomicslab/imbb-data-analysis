# Setup Guide — IMBB Data Analysis Course

Complete steps 1–4 before Day 1. Step 5 (R) is for Week 2 — you can do it later.

---

# Windows

## 1. Install Python

Download and run the installer from: https://www.python.org/downloads/release/python-3119/


- ✓ Check **"Add Python to PATH"**
- Click **Install Now**

Verify in Command Prompt (`Win+R` —> type `cmd` —> Enter):

```
python --version
```

## 2. Download course materials

- Go to https://github.com/cgenomicslab/imbb-data-analysis
- Click the green **Code** button —> **Download ZIP**
- Extract the folder (e.g., in Documents)
- Open Command Prompt inside the **imbb-data-analysis** folder (type `cmd` in the address bar and press Enter)

## 3. Set up the environment

Run these commands one at a time inside the **imbb-data-analysis** folder:

```
python -m venv imbb
```

```
imbb\Scripts\activate
```

```
pip install -r requirements.txt
```

```
python -m ipykernel install --user --name=imbb --display-name "Python (imbb)"
```

## 4. Test

```
jupyter notebook
```

Open `docs/test_installation.ipynb` and run the cell. If it prints **"Everything works!"** — you're ready.

**Note:** Every time you reopen Command Prompt, activate the environment first: `imbb\Scripts\activate`

## 5. R (Week 2)

Download and install R from https://cran.r-project.org ("Download R for Windows" —> "base"), then install [RStudio Desktop](https://posit.co/download/rstudio-desktop/).

To also use R inside Jupyter, open R and run:

```
install.packages("IRkernel")
IRkernel::installspec()
```

## Visual Studio Code (VS Code)

You can also [install](https://code.visualstudio.com/download) and open notebooks in VSCode (with the Python and Jupyter extensions installed, easy) instead of the browser. Up to you though, the current setup works either way.

---

# macOS

## 1. Install Python

Download the macOS installer from: https://www.python.org/downloads/release/python-3119/

- **Apple Silicon (M1/M2/M3/M4):** universal2 installer
- **Intel Mac:** Intel installer

(Apple menu —> About This Mac to check.)

Verify in Terminal (`Cmd+Space` —> type "Terminal"):

```
python3 --version
```

## 2. Download course materials

- Go to https://github.com/cgenomicslab/imbb-data-analysis
- Click the green **Code** button → **Download ZIP**
- Extract the folder (e.g., in Documents)
- Open Terminal inside the **imbb-data-analysis** folder

## 3. Set up the environment

Run these commands one at a time inside the **imbb-data-analysis** folder:

```
python3 -m venv imbb
```

```
source imbb/bin/activate
```

```
pip install -r requirements.txt
```

```
python -m ipykernel install --user --name=imbb --display-name "Python (imbb)"
```

## 4. Test

```
jupyter notebook
```

Open `docs/test_installation.ipynb` and run the cell. If it prints **"Everything works!"** — you're ready.

**Note:** Every time you reopen Terminal, activate the environment first: `source imbb/bin/activate`

## 5. R (Week 2)

Download and install R from https://cran.r-project.org ("Download R for macOS"), then install [RStudio Desktop](https://posit.co/download/rstudio-desktop/).

To also use R inside Jupyter, open R and run:

```
install.packages("IRkernel")
IRkernel::installspec()
```

## Visual Studio Code (VS Code)

You can also [install](https://code.visualstudio.com/download) and open notebooks in VSCode (with the Python and Jupyter extensions installed, easy) instead of the browser. Up to you though, the current setup works either way.

---

# Alternatives

- **Google Colab** (no installation): Go to https://colab.research.google.com —> File —> Open Notebook —> GitHub tab —> paste `https://github.com/cgenomicslab/imbb-data-analysis`
- **Course [JupyterHub](https://jupyter.cgenomicslab.org/)**: Access details will be shared before the course — everything is pre-installed

---

## Problems?

Email the course coordinator with a screenshot of the error. Or just use Google Colab for Day 1 — we'll sort it out during the break.
