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
value = loaded_data['value']
```




**Note:** The value in the grid is set to `1e-10` if no galaxy is located within it.

