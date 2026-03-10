# Bulk RNA-seq Dataset

## Description
Simulated bulk RNA-seq count data for a simple 3-condition experiment.

## Files
- `bulk_rnaseq_counts.csv`: Gene expression count matrix
- `bulk_rnaseq_metadata.csv`: Sample information

## Experimental Design
- **Conditions:** Normal, Treatment_A, Treatment_B
- **Replicates:** 3 biological replicates per condition
- **Total samples:** 9
- **Genes:** 100

## Differential Expression Pattern
- **Genes 001-015:** Upregulated in Treatment_A vs Normal
- **Genes 016-030:** Downregulated in Treatment_A vs Normal
- **Genes 031-045:** Upregulated in Treatment_B vs Normal
- **Genes 046-060:** Downregulated in Treatment_B vs Normal
- **Genes 061-100:** No differential expression (noise only)

## Data Format
- Rows = Genes
- Columns = Samples
- Values = Raw read counts (integers)

## Usage
```python
import pandas as pd

# Load count data
counts = pd.read_csv('bulk_rnaseq_counts.csv', index_col=0)

# Load metadata
metadata = pd.read_csv('bulk_rnaseq_metadata.csv')
```

## Notes
- This is simulated data for educational purposes
- Counts follow negative binomial distribution
- Biological and technical variation included
- Clear DE patterns for easy interpretation
