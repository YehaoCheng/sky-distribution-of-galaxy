## A Roadmap for Transient Hunters: Mapping Stellar Mass and Star Formation Rate Anisotropies in the Local Universe

###  In this project, we utilize the comprehensive galaxy catalog from \citet{2026Tranin} (REGALADE) to map the sky distributions of stellar mass and star formation rate (SFR) across various luminosity distance thresholds and angular grid resolutions. Following the methodology of \citet{2024A&A...688A..33Z}, we employ a machine learning framework to predict the SFRs for galaxies lacking pre-existing measurements, enabling a complete and high-resolution mapping on the celestial sphere.

In this project, we utilize the comprehensive galaxy catalog from [Tranin et al. (2026)](#ref-tranin2026) (REGALADE) to map the sky distributions of stellar mass and star formation rate (SFR) across various luminosity distance thresholds and angular grid resolutions. Following the methodology of [Zeraatgari et al. (2024)](#ref-zeraatgari2024), we employ a machine learning framework to predict the SFRs for galaxies lacking pre-existing measurements, enabling a complete and high-resolution mapping on the celestial sphere.

---
### References

<a id="ref-tranin2026"></a>**[1]** Tranin, H., et al. (2026). *The REGALADE Catalog of Galaxies in the Local Universe*.

<a id="ref-zeraatgari2024"></a>**[2]** Zeraatgari, F., et al. (2024). *Title of the Zeraatgari Paper*. *Astronomy & Astrophysics*, 688, A33. [https://doi.org/10.1051/0004-6361/2023xxxxx](https://doi.org/10.1051/0004-6361/2023xxxxx)

The top-level folders are named according to the angular resolution of the grids. We can choose the appropriate angular resolution based on the telescope's Field of View. Both the MASS and SFR folders contain data and figures of the sky distribution based on equatorial coordinates. The data is stored in the NumPy binary format (`.npz`).

Filename example: `MASS/SFR_D30_1.83deg.npz`

- `D30`: Luminosity distance of 30 Mpc.

- `1.83deg`: Angular resolution of the grid.

Below is a code snippet to read this file format:




```python
import numpy as np

loaded_data = np.load("Your_path/MASS_D30_1.83deg.npz")

# Grid sequence number. Note: Different resolutions have different total pixel counts.
npix = loaded_data['npix']

# Right Ascension of the grid's central coordinate.
ra = loaded_data['ra']

# Declination of the grid's central coordinate. 
dec = loaded_data['dec']

# Total MASS/SFR within this grid (logarithmic scale). 
value = loaded_data['m']
```




**Note:** The value in the grid is set to `1e-10` if no galaxy is located within it.

