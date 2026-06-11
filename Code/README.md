# Stellar Mass & SFR Pipeline
A complete open-source Python pipeline for calculating integrated stellar mass and star formation rate (SFR) HEALPix maps, plus machine learning-based SFR prediction and visualization tools, built for the REGALADE galaxy survey.

---

## Overview
This repository contains all scripts to process galaxy catalog data, including:
1.  **Batch HEALPix map calculation**: All-sky maps of total stellar mass (MASS) and SFR, across multiple resolutions and luminosity distance thresholds
2.  **Machine learning SFR prediction**: A CatBoost regression pipeline to predict `log(SFR)` from galaxy photometry, redshift and stellar mass
3.  **Publication-ready visualization**: Tools to plot Mollweide-projection sky maps of derived quantities

---

## Repository Structure
Code/
├── README.md # This file (project overview)
├── requirements.txt # Python dependency list
├── healpy_MASS.ipynb # Batch HEALPix stellar mass map calculation
├── healpy_SFR.ipynb # Batch HEALPix star formation rate (SFR) map calculation
├── ML_predict.ipynb # CatBoost-based SFR prediction pipeline
└── Ploting.ipynb # Batch visualization for MASS/SFR HEALPix maps


---

## Requirements
All dependencies are listed in `requirements.txt`. Install them with:
```bash
pip install -r requirements.txt
