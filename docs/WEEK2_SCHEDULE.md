# Week 2: Specialized Topics
## IMBB Data Analysis Course

Week 2 builds on Week 1 fundamentals by showcasing specialized analyses from different IMBB-FORTH labs. Each 2-hour session is led by experts in their respective fields.

---

## 📅 Tentative Schedule

### Session Format
- **Duration:** 2 hours per session
- **Format:** Demo + hands-on practice with real/example data
- **Level:** Assumes (maybe) Week 1 knowledge
- **Goal:** Exposure to different analysis types, not mastery

---

## Monday: Phylogenetics & Orthology/Paralogy

**Led by:** CGLab (Pittis group)  
**Time:** [TBD]

### Topics Covered
- Introduction to evolutionary relationships
- Phylogenetic tree construction and interpretation
- Orthology vs paralogy: what's the difference?
- Gene family evolution
- Practical applications in comparative genomics

### What You'll Learn
- Read and interpret phylogenetic trees
- Identify orthologs and paralogs
- Use basic phylogenetic tools

### Example Analysis
- Build a phylogenetic tree from protein sequences
- Identify orthologous genes across species
- Interpret evolutionary relationships

**Prerequisites:** Week 1 (basic Python and data manipulation)

---

## Tuesday: Differential Gene Expression Analysis

**Led by:** IMBB Bioinformatics Unit  
**Time:** [TBD]

### Topics Covered
- In-depth differential expression (DE) analysis
- Batch effects and normalization
- GO term enrichment (detailed)

### What You'll Learn
- Run complete DE pipelines
- Interpret DE results critically
- Understand statistical assumptions
- Visualize results effectively

### Example Analysis
- Real RNA-seq dataset analysis
- From counts to biological insights
- Publication-quality visualizations

**Prerequisites:** Week 1 Day 5 (basic DE concepts)

---

## Wednesday: ATAC-seq Analysis

**Led by:** Talianidis Lab  
**Time:** [TBD]

### Topics Covered
- Introduction to chromatin accessibility
- ATAC-seq principles and workflow
- Peak calling and annotation
- Differential accessibility analysis
- Motif enrichment
- Integration with RNA-seq data

### What You'll Learn
- Understand chromatin accessibility data
- Interpret ATAC-seq peaks
- Link accessibility to gene expression
- Identify transcription factor binding sites

### Example Analysis
- Peak calling from ATAC-seq data
- Differential accessibility between conditions
- Motif analysis in accessible regions

**Prerequisites:** Week 1 (basic statistics and expression concepts)

---

## Thursday: Single-cell RNA-seq Analysis

**Led by:** Lavigne/Delidakis Labs  
**Time:** [TBD]

### Topics Covered
- Single-cell vs bulk RNA-seq
- scRNA-seq workflow: QC, normalization, clustering
- Cell type identification
- Marker gene discovery
- Trajectory analysis
- Integration of multiple datasets

### What You'll Learn
- Process scRNA-seq data
- Identify cell types and states
- Find marker genes
- Visualize single-cell data (UMAP, t-SNE)
- Interpret clustering results

### Example Analysis
- Complete scRNA-seq pipeline
- From raw counts to annotated cell types
- Biological interpretation

**Prerequisites:** Week 1 Day 4-5 (dimensionality reduction and DE basics)

---

## Friday: Proteomics Analysis

**Led by:** Gouridis Lab  
**Time:** [TBD]

### Topics Covered
- Introduction to mass spectrometry proteomics
- Protein identification and quantification
- Differential protein expression
- Post-translational modifications
- Proteomics data visualization
- Integration with transcriptomics

### What You'll Learn
- Understand proteomics data structure
- Analyze protein abundance
- Identify differentially expressed proteins
- Correlate protein and RNA levels
- Pathway analysis for proteomics

### Example Analysis
- Proteomics dataset analysis
- Differential expression
- Functional enrichment
- Multi-omics integration

**Prerequisites:** Week 1 (basic statistics and expression analysis)

---

## Additional Sessions (Optional/TBD)

### Session A: Differential RNA-binding Protein Interactions

**Led by:** Ntini Lab  
**Time:** [TBD]

### Topics
- RNA-binding proteins (RBPs)
- CLIP-seq and related methods
- Identifying RBP binding sites
- Differential binding analysis
- Integration with RNA-seq

---

### Session B: Imaging Analysis & Quantification

**Led by:** Pavlopoulos Lab  
**Time:** [TBD]

### Topics
- Image analysis fundamentals
- Cell segmentation and tracking
- Fluorescence quantification
- High-throughput imaging
- Python tools for microscopy (scikit-image, napari)

---

### Session C: ChIP-seq Analysis (If available)

**Led by:** [TBD]  
**Time:** [TBD]

### Topics
- ChIP-seq principles
- Peak calling
- Differential binding
- Motif analysis
- Integration with other datasets

---

## 🎯 Session Format

Each session will follow this structure:

### Part 1: Introduction (30 min)
- Biological background
- Method overview
- Data types and structure
- Common applications

### Part 2: Live Demo (45 min)
- Analysis walkthrough
- Code explanation
- Interpretation of results
- Common pitfalls

### Part 3: Hands-on Practice (45 min)
- Participants work on similar data
- Apply learned concepts
- Helpers circulate for support
- Q&A and troubleshooting

---

## 🔧 Bring Your Own Data

After Week 2 sessions, participants are encouraged to:

### Supervised Work Sessions
- **When:** [TBD - potentially 2 additional sessions]
- **Format:** Open lab format with helpers
- **Bring:** Your own datasets
- **Get help with:**
  - Applying course concepts to your data
  - Troubleshooting analysis issues
  - Interpreting your specific results
  - Planning analysis strategies

### Guidelines for Own Data
1. **Come prepared:** Have data organized and accessible
2. **Know your question:** What do you want to analyze?
3. **Start simple:** Don't try to do everything at once
4. **Ask for help!**

**Ideal Own-Data Questions:**
- "I have RNA-seq data from 2 conditions, help me find DE genes"
- "Can you help me interpret my PCA plot?"
- "How do I visualize my proteomics results?"
- "I have single-cell data, how do I identify cell types?"

---

## 📚 Additional Resources Per Topic

### Phylogenetics
- [Phylogenetic tree basics](https://en.wikipedia.org/wiki/Phylogenetic_tree)
- MEGA software documentation
- ETE toolkit for Python

### Differential Expression
- [DESeq2 vignette](https://bioconductor.org/packages/release/bioc/vignettes/DESeq2/inst/doc/DESeq2.html)
- [edgeR user guide](https://bioconductor.org/packages/release/bioc/html/edgeR.html)
- pyDESeq2 documentation

### ATAC-seq
- [ATAC-seq guidelines](https://www.encodeproject.org/atac-seq/)
- ATACseqQC R package
- MACS2 peak calling

### Single-cell RNA-seq
- [Scanpy tutorials](https://scanpy.readthedocs.io/en/stable/tutorials.html)
- [Seurat vignettes](https://satijalab.org/seurat/)
- [Single-cell best practices](https://www.sc-best-practices.org/)

### Proteomics
- [MaxQuant documentation](https://www.maxquant.org/)
- [MSstats](https://www.bioconductor.org/packages/release/bioc/html/MSstats.html)
- [Perseus software](https://maxquant.net/perseus/)


---

## 📝 Notes

### For Participants

**To get the most from Week 2:**

1. **Complete Week 1 first** - Week 2 assumes this foundation
2. **Install additional tools** as requested by session leaders
3. **Review biological background** for each technique
4. **Bring questions** about your own research
5. **Take notes** and save example code

---

## 🔄 Schedule Updates

This schedule is **tentative** and will be finalized based on:
- Lab availability
- Participant feedback after Week 1
- Logistical considerations

**Final schedule will be announced:** [Date TBD]

Check this document regularly for updates!

---

## 📧 Contact

**Week 2 Coordination:** [Contact TBD]

**Lab-specific questions:**
- Contact individual lab leaders directly
- OR contact course coordinator for referral

---

## 🌟 Philosophy for Week 2

Week 2 is about **exposure and inspiration**, not mastery. Goals:

- **See the diversity** of computational approaches
- **Understand when** different methods are appropriate
- **Know what's possible** for your own research
- **Connect with experts** who can help later
- **Get excited** about data analysis!

You won't become an expert in any single technique, but you'll gain:
- Conceptual understanding
- Basic vocabulary
- Starting points for further learning
- Connections to IMBB experts

**Most importantly:** You'll think of how computational approaches can be valuable for your research..
