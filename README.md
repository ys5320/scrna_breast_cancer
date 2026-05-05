# scRNA-seq Analysis of Breast Cancer Bioelectrical Phenotypes

## Overview
End-to-end single-cell RNA sequencing analysis connecting transcriptional signatures to bioelectrical phenotypes in breast cancer cell lines and primary tumours.

## Projects

### Project 1: Primary Tumour Analysis (Wu et al. 2021)
- **Dataset:** GSE176078 — 98,593 cells from 26 primary breast tumours
- **Pipeline:** QC, normalisation, Harmony batch correction, Leiden clustering, DEG, GSEA
- **Key finding:** TNBC vs ER+ comparison reveals consistent metabolic (glycolysis, OXPHOS) and inflammatory pathway enrichment — independently validating PhD bulk omics findings

### Project 2: Cell Line Integration (Gardner 2024 + Gambardella 2022)
- **Datasets:** GSE268249 (10x Genomics) + GSE173634 (Drop-seq) — 13,057 cells, 6 breast cancer cell lines
- **Pipeline:** Cross-technology integration using scVI, DEG, GSEA
- **Comparisons:** Blinker vs Waver electrical phenotype; High vs Mid electrical activity
- **Key finding:** Blinker/waver grouping reveals inflammatory and proliferative pathway differences, with important caveat that grouping is partially confounded by molecular subtype

## Cell Lines
| Cell Line | Subtype | Electrical Phenotype | Activity Level |
|-----------|---------|---------------------|----------------|
| MDA-MB-231 | TNBC/Basal | Blinker | Mid |
| MDA-MB-468 | TNBC/Basal | Blinker | High |
| BT474 | Luminal B/HER2+ | Waver | High |
| T47D | Luminal A | Waver | Mid |
| CAL51 | TNBC/Basal | Waver | Mid |
| Hs578T | Claudin-low | Waver | Mid |

## Technical Stack
- Python 3.11, Scanpy 1.11, scVI-tools, Harmony, GSEApy
- Imperial College London HPC (PBS scheduler)

## Repository Structure
scrna_project/
├── notebooks/
│   ├── 01_load_explore.ipynb        # Wu 2021 primary tumour analysis
│   └── 02_celllines_analysis.ipynb  # Cell line integration analysis
├── data/                            # Raw data (not tracked)
├── results/                         # Analysis outputs (not tracked)
└── figures/                         # Generated plots (not tracked)
## Requirements
scanpy
scvi-tools
harmonypy
gseapy
pybiomart
anndata
