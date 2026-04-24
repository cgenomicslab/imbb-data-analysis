# Preparation Course material + Python Virtual Environment + Jupyter Setup

This guide shows the simplest way to set up a Python virtual environment and Jupyter Notebook on **Windows** and **macOS** and access the course material

# Working with a Git Repository

You should **clone or download course material first** in your Documents folder (or in a dedicated folder of your choice), then create the virtual environment *inside that folder*.

## Option 1 — Clone with Git

If you have Git installed:

```bash
git clone https://github.com/cgenomicslab/imbb-data-analysis
cd imbb-data-analysis
```

## Option 2 — Download ZIP

- Click **Download ZIP** on the repository page
- Extract it
- Open Terminal / Command Prompt in that folder **imbb-data-analysis**

---

## Then create the environment inside the **imbb-data-analysis** folder

# Windows Setup

## 1. Install Python

- Download the Windows installer from: https://www.python.org/downloads/release/python-3110rc2/
- Run the installer
- ✅ Check **"Add Python to PATH"**
- Click **Install Now**

Verify installation:

```bash
python --version
```

---

## 2. Create a Virtual Environment



```bash
python -m venv imbb_env
```

---

## 3. Activate the Environment

**Command Prompt:**

```bash
imbb_env\Scripts\activate
```

**PowerShell:**

```bash
imbb_env\Scripts\Activate.ps1
```

## 4. Install required packages

```bash
pip install -r requirements.txt
```

---

## 5. Add Environment to Jupyter

```bash
python -m ipykernel install --user --name=imbb_env
```

---

## 6. Run Jupyter

```bash
jupyter notebook
```

---

## 7. Test installation

Open the `test_installation.ipynb` notebook and run the cell! Everything should be working!

---



# macOS Setup

## 1. Install Python

- Download macOS installer from: https://www.python.org/downloads/release/python-3110rc2/
- Install normally

Verify installation:

```bash
python3 --version
```

---

## 2. Create a Virtual Environment

```bash
python3 -m venv imbb_env
```

---

## 3. Activate the Environment

```bash
source imbb_env/bin/activate
```

---

## 4. Install required packages

```bash
pip install -r requirements.txt
```

---

## 5. Add Environment to Jupyter

```bash
python3 -m ipykernel install --user --name=imbb_env
```

---

## 6. Run Jupyter

```bash
jupyter notebook
```

---

## 7. Test installation

Open the `test_installation.ipynb` notebook and run the cell! Everything should be working!

---

# Alternatives

There are many ways to work with Python environments and notebooks. Feel free to use whichever tool you prefer:

- **VS Code** (with the Python & Jupyter extensions)
- **Google Colab** (runs in the browser, no local setup needed)
- **PyCharm**
- **Anaconda / Miniconda**

All of these can run Jupyter notebooks or Python scripts, and most can manage virtual environments for you.

👉 The setup in this guide uses the standard `venv` + Jupyter approach because it is lightweight and works everywhere.
