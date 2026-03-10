# Course Datasets

This folder contains all datasets used throughout the IMBB data analysis course.

## 📊 Available Datasets

### 1. Cretan Beaches (`cretan_beaches.csv`)
**Used in:** Days 1-3  
**Purpose:** Learning data manipulation, statistics, and hypothesis testing

A fun dataset featuring 25 Cretan beaches with environmental and biodiversity measurements.

**Variables (17 columns):**
- `beach_name`: Beach identifier
- `region`: Chania, Rethymnon, Heraklion, or Lassithi
- `beach_type`: Sand, Pebbles, or Mixed
- `beach_length_m`: Beach length in meters
- `kri_kri_sightings`: Cretan wild goat sightings
- `caretta_nests`: Loggerhead sea turtle nests
- `monk_seal_sightings`: Mediterranean monk seal observations
- `lizard_species`: Number of lizard species
- `cretan_palms`: Cretan date palm trees count
- `thyme_coverage_pct`: Thyme vegetation coverage (%)
- `sea_urchin_density`: Low/Medium/High
- `lionfish_spotted`: Invasive lionfish presence (0/1)
- `water_temp_celsius`: Average water temperature
- `wind_speed_kmh`: Average wind speed
- `annual_rainfall_mm`: Annual rainfall
- `avg_tourists_per_day`: Average daily tourists
- `blue_flag`: Blue Flag certification (0/1)

**Sample size:** 25 beaches

---

### 2. Bulk RNA-seq (`bulk_rnaseq_counts.csv` + `bulk_rnaseq_metadata.csv`)
**Used in:** Days 4-5  
**Purpose:** Expression data analysis, PCA, differential expression

Simulated gene expression data for 3 experimental conditions.

**Count Matrix:**
- **Dimensions:** 100 genes × 9 samples
- **Conditions:** Normal, Treatment_A, Treatment_B
- **Replicates:** 3 per condition
- **Format:** Raw integer counts

**Differential Expression Pattern:**
- Genes 001-015: Upregulated in Treatment_A
- Genes 016-030: Downregulated in Treatment_A
- Genes 031-045: Upregulated in Treatment_B
- Genes 046-060: Downregulated in Treatment_B
- Genes 061-100: Not differentially expressed

**Metadata columns:**
- `sample_name`: Sample identifier
- `condition`: Experimental condition
- `replicate`: Biological replicate number

See `README_rnaseq.md` for details.

---

### 3. Single-cell RNA-seq (`singlecell_expression.csv` + `singlecell_metadata.csv`)
**Used in:** Day 4  
**Purpose:** UMAP visualization, cell type identification

Simulated single-cell RNA-seq data with 4 distinct cell populations.

**Expression Matrix:**
- **Dimensions:** 500 genes × 200 cells (subset provided)
- **Full dataset:** 500 genes × 1000 cells
- **Cell types:** T_cells, B_cells, Monocytes, NK_cells
- **Format:** Integer UMI counts (sparse)

**Metadata columns:**
- `cell_id`: Unique cell identifier
- `cell_type`: Cell type annotation
- `umap_1`, `umap_2`: Pre-computed UMAP coordinates
- `n_genes_expressed`: Genes with counts > 0
- `total_counts`: Total UMI counts per cell

**Cell Type Markers:**
- T_cells: Genes 001-030
- B_cells: Genes 031-060
- Monocytes: Genes 061-090
- NK_cells: Genes 091-120

See `README_singlecell.md` for details.

---

## 📥 Loading Data

### Python (pandas)
```python
import pandas as pd

# Cretan beaches
beaches = pd.read_csv('data/cretan_beaches.csv')

# Bulk RNA-seq
counts = pd.read_csv('data/bulk_rnaseq_counts.csv', index_col=0)
metadata = pd.read_csv('data/bulk_rnaseq_metadata.csv')

# Single-cell
sc_expression = pd.read_csv('data/singlecell_expression.csv', index_col=0)
sc_metadata = pd.read_csv('data/singlecell_metadata.csv')
```

### Google Colab
```python
import pandas as pd

# If uploaded to Colab
beaches = pd.read_csv('cretan_beaches.csv')

# OR from GitHub (once repo is public)
url = 'https://raw.githubusercontent.com/cgenomicslab/imbb-data-analysis/main/data/cretan_beaches.csv'
beaches = pd.read_csv(url)
```

---

## 🔍 Quick Data Exploration

### Beaches Dataset
```python
import pandas as pd

beaches = pd.read_csv('data/cretan_beaches.csv')

# Basic info
print(beaches.shape)  # (25, 17)
print(beaches.columns)

# Summary statistics
print(beaches.describe())

# Count by region
print(beaches['region'].value_counts())
```

### Bulk RNA-seq
```python
import pandas as pd

counts = pd.read_csv('data/bulk_rnaseq_counts.csv', index_col=0)
metadata = pd.read_csv('data/bulk_rnaseq_metadata.csv')

# Check dimensions
print(f"Genes: {counts.shape[0]}, Samples: {counts.shape[1]}")

# View first few genes
print(counts.head())

# Samples per condition
print(metadata['condition'].value_counts())
```

### Single-cell
```python
import pandas as pd
import matplotlib.pyplot as plt

metadata = pd.read_csv('data/singlecell_metadata.csv')

# Plot UMAP
for cell_type in metadata['cell_type'].unique():
    subset = metadata[metadata['cell_type'] == cell_type]
    plt.scatter(subset['umap_1'], subset['umap_2'], 
                label=cell_type, alpha=0.6, s=20)
plt.xlabel('UMAP 1')
plt.ylabel('UMAP 2')
plt.legend()
plt.title('Single-cell UMAP')
plt.show()
```

---

## 📝 Data Notes

### Cretan Beaches
- Real beach names from Crete
- Simulated measurements for educational purposes
- Some realistic correlations (e.g., tourists vs monk seals)
- Intentional patterns for hypothesis testing practice

### RNA-seq Datasets
- **Simulated data** following biological distributions
- Clear differential expression patterns for learning
- Realistic count distributions (negative binomial)
- Biological and technical variation included
- Designed for easy interpretation

### File Formats
- All CSV files for easy reading
- Compatible with Excel, R, Python
- UTF-8 encoding
- No missing values

---

## 🎯 Learning Objectives by Dataset

### Cretan Beaches → Learn:
- Data loading and inspection
- Filtering and selecting data
- Grouping and aggregation
- Basic statistics
- Hypothesis testing
- Correlation analysis

### Bulk RNA-seq → Learn:
- Expression matrices
- Normalization concepts
- PCA and dimensionality reduction
- Differential expression
- Statistical testing on high-dimensional data

### Single-cell → Learn:
- Sparse data (many zeros)
- UMAP visualization
- Cell type identification
- Marker genes
- Interpretation of clustering

---

## 📚 Additional Information

For detailed information about each dataset, see:
- `README_rnaseq.md` - Bulk RNA-seq details
- `README_singlecell.md` - Single-cell details

---

## 🤝 Contributing

If you find issues with the datasets or have suggestions for improvement:
1. Note the issue clearly
2. Describe what you expected vs what you found
3. Report to the course coordinator

---

*These datasets are educational simulations designed specifically for this course. They demonstrate real analytical concepts with manageable data sizes.*
