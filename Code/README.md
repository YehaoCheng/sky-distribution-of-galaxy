# Stellar Mass & SFR Pipeline
A complete open-source Python pipeline for calculating integrated stellar mass and star formation rate (SFR) HEALPix maps, plus machine learning-based SFR prediction and visualization tools, built for the REGALADE galaxy survey.

---

## Overview
This repository contains all scripts to process galaxy catalog data, including:
1.  **Machine learning SFR prediction**: A CatBoost regression pipeline to predict `log(SFR)` from galaxy photometry, redshift and stellar mass
2.  **Batch HEALPix map calculation**: All-sky maps of total stellar mass (MASS) and SFR, across multiple resolutions and luminosity distance thresholds
3.  **Publication-ready visualization**: Tools to plot Mollweide-projection sky maps of derived quantities

---

## Repository Structure
- Code
  - README.md           # This file (project overview)
  - requirements.txt    # Python dependency list
  - healpy_MASS.ipynb   # Batch HEALPix stellar mass map calculation
  - healpy_SFR.ipynb    # Batch HEALPix SFR map calculation
  - ML_predict.ipynb    # CatBoost-based SFR prediction pipeline
  - Ploting.ipynb       # Batch visualization for MASS/SFR HEALPix maps

## Pipeline Workflow
The pipeline runs in 3 sequential stages, ordered by data dependency:

### Stage 1: Machine Learning SFR Prediction
Use `ML_predict.ipynb` to train and validate a CatBoost regression model, and predict `log(SFR)` for galaxies lacking pre-existing measurements.
- **Input**: Cleaned galaxy catalog with photometry, redshift, stellar mass, and observed `logSFR` labels
- **Workflow**: Data cleaning → feature engineering → train/validation split → 10-fold cross-validation → blind test evaluation → prediction for unlabeled galaxies
- **Output**: Complete galaxy catalog with predicted `logSFR` values, ready for map calculation

### Stage 2: Batch HEALPix Map Calculation
Use `healpy_MASS.ipynb` and `healpy_SFR.ipynb` to compute all-sky maps of integrated stellar mass and SFR, using the full catalog from Stage 1.
- **Input**: Full galaxy catalog (required columns: `ra`, `dec`, `dL/Mpc`, `logM`, `logSFR` (observed + predicted))
- **Customizable parameters**:
  - `TARGET_NSIDES`: List of HEALPix resolutions to compute (e.g. `[4, 8, 16]`)
  - `DISTANCE_RANGE`: Luminosity distance thresholds (Mpc) to process (default: 10–200 Mpc, step 10)
  - File paths: Update input/output directories to match your environment
- **Output**: HEALPix maps saved to `mapdate/MASS/` and `mapdate/SFR/` (NPZ binary format)

### Stage 3: Publication-Ready Visualization
Use `Ploting.ipynb` to generate high-resolution all-sky plots from the HEALPix maps produced in Stage 2.
- **Input**: NPZ map files from Stage 2
- **Output**: Mollweide-projection sky maps saved to `results/figure/` (PDF format)

---

## Requirements
All dependencies are listed in `requirements.txt`. Install them with:
```bash
pip install -r requirements.txt
