RADAR: RFI Aware Detection of Anomalous Radio-Technosignatures Pipeline

1. Scientific Goal

RADAR is a modular data analysis pipeline designed to reduce large-scale radio astronomy datasets (VLA and MeerKAT) into a small set of candidate technosignature signals by systematically removing radio-frequency interference (RFI).

The scientific goal is to improve the efficiency of technosignature searches by combining:
- frequency-domain filtering
- signal-to-noise heuristics
- beam geometry constraints
- temporal consistency checks

2. Code Interface / How to Run

The pipeline is implemented in Python using a combination of notebooks and scripts.

Typical workflow:

1. Run preprocessing notebooks to reformat data:
   - MeerKAT_pre_processing
   - VLA_COSMIC_pre_processing 

2. Execute filtering stages:
   - frequency-based RFI removal
   - SNR and drift filtering
   - beam multiplicity analysis

3. Output is generated as:
   - cleaned `.csv` / `.pkl` catalogs
   - filtered candidate datasets
   - diagnostic plots (`.png`)

Users can modify:
- SNR thresholds
- drift rate cuts
- beam overlap criteria

directly inside the notebooks.
