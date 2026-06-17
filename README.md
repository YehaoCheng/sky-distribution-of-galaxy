# A Roadmap for Transient Hunters: Mapping Stellar Mass and Star Formation Rate Anisotropies in the Local Universe


## Description: 
In this project, we utilize the comprehensive galaxy catalog from [Tranin et al. (2026)](#ref-tranin2026) (REGALADE) to map the sky distributions of stellar mass and star formation rate (SFR) across various luminosity distance thresholds and angular grid resolutions. Following the methodology of [Zeraatgari et al. (2024)](#ref-zeraatgari2024), we employ a machine learning framework to predict the SFRs for galaxies lacking pre-existing measurements, enabling a complete and high-resolution mapping on the celestial sphere.

## Data Availability
To ensure long-term preservation and accommodate large file sizes, the materials for this project are distributed between GitHub and Zenodo:

- **GitHub (This Repository)**: Contains the machine learning source code (Jupyter Notebooks), the aggregated sky distribution data (`.npz` files), and the corresponding sky map figures.
- **Zenodo Archive**: Contains the large tabular datasets, including the filtered REGALADE base catalog, the machine learning training/validation sets (cross-matched with GSWLC-2), and the final catalog with our predicted SFRs. 
  - **Download the full tabular datasets here:** [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20695048.svg)](https://doi.org/10.5281/zenodo.20695048)

## Repository Structure
- xx deg / arcmin
    - MASS / SFR
      - data / figures
      
The data in each "data" folder represents the sky distribution of stellar mass and SFR. The corresponding sky distribution maps are located in the "figures" folder.

The data is stored in the NumPy binary format (`.npz`).

Filename example: `MASS/SFR_D30_1.83deg.npz`

- `D30`: Luminosity distance of 30 Mpc.

- `1.83deg`: Angular resolution of the grid.

Below is a code snippet to read this file format:

**Note:** The value in the grid is set to `1e-10` if no galaxy is located within it.

  


## License
This project is open-sourced under the MIT License. See the LICENSE file for details.


## References

<a id="ref-tranin2026"></a>**[1]** Tranin et al., (2026). *A catalog to unite them all: REGALADE, a revised galaxy  compilation for the advanced detector era*. [	https://doi.org/10.1051/0004-6361/202556896](	https://doi.org/10.1051/0004-6361/202556896).

<a id="ref-zeraatgari2024"></a>**[2]** Zeraatgari et al., (2024). *Exploring galactic properties with machine learning Predicting star formation, stellar mass, and metallicity from photometric data*. [https://doi.org/10.1051/0004-6361/202348714](https://doi.org/10.1051/0004-6361/202348714)


