# RADAR: RFI Aware Detection of Anomalous Radio-Technosignatures Pipeline

## 1. Scientific Goal and Motivation

With access to large-scale commensal datasets from COSMIC, manual inspection is no longer feasible. RADAR was developed to automate the reduction of millions of signals into a tractable set of scientifically meaningful candidates.

RADAR is a modular data analysis pipeline designed to reduce large-scale radio astronomy datasets (VLA and MeerKAT) into a small set of candidate technosignature signals by systematically removing radio-frequency interference (RFI).

The scientific goal is to improve the efficiency of technosignature searches by combining:
- frequency-domain filtering
- signal-to-noise heuristics
- beam geometry constraints
- temporal consistency checks

---

## 2. Code Interface / How to Run

The pipeline is implemented in Python using a combination of notebooks and scripts.

Typical workflow:

- Run preprocessing notebooks to reformat data:
  - MeerKAT_pre_processing
  - VLA_COSMIC_pre_processing

- Execute filtering stages:
  - RFI_anomoly_analysis
    - frequency-based RFI removal
    - SNR and drift filtering
    - beam multiplicity analysis

- Output is generated as:
  - cleaned `.csv` / `.pkl` catalogs
  - filtered candidate datasets
  - diagnostic plots  (`.png`)
  
- Further data cleaning stats:
  - view cleaning results with data_visualization 

Users interact with the pipeline by modifying filtering parameters directly in notebooks.

---

## 3. Pipeline Overview

RADAR processes data through the following stages:

1. Data ingestion (SETICORE / BLUSE outputs)
2. Schema normalization (MeerKAT → VLA format)
3. Known RFI frequency excision
4. Adaptive SNR and drift filtering
5. Beam multiplicity and spatial overlap analysis
6. Temporal consistency checks across observations
7. Final classification:
   - Clean candidate
   - Possible RFI
   - Strong RFI

---

## 4. Outputs

The pipeline produces:

- Cleaned hit catalogs (`.csv`, `.pkl`)
- Intermediate filtered datasets
- RFI classification tables
- Diagnostic plots:
  - beam overlap visualizations
  - waterfall plots
  - signal distribution histograms

---

## 5. Testing and Validation

The pipeline includes multiple non-trivial validation tests:

1. Beam Multiplicity Validation  
   Ensures known RFI sources are correctly identified through multi-beam detection patterns.

2. RFI Reduction Efficiency  
   Tracks dataset reduction at each filtering stage to quantify algorithm performance.

---

## Notes

This project is intentionally designed as a modular scientific codebase rather than a single script. Each stage of processing can be modified or replaced independently, allowing extension to other telescopes or datasets.

---

## Author
Ella Bishop
