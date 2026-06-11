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

### Usage: 
In the document, we have provided sky distribution maps and corresponding data of stellar mass and SFR for multiple angular resolutions at each luminosity distance. The top-level folders are named according to the angular resolution of the grids. We can choose the appropriate angular resolution based on the telescope's Field of View. Both the MASS and SFR folders contain data and figures of the sky distribution based on equatorial coordinates. The data is stored in the NumPy binary format (`.npz`).

Filename example: `MASS/SFR_D30_1.83deg.npz`

- `D30`: Luminosity distance of 30 Mpc.

- `1.83deg`: Angular resolution of the grid.

Below is a code snippet to read this file format:



---

## Requirements
All dependencies are listed in `requirements.txt`. Install them with:
```bash
pip install -r requirements.txt
