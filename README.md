The first folders are named in angular resolutions of grids. We could chose the proper angular resolution according to the FoV of telescope.
Both the MASS and SFR folders contain data and figures of sky distribution based on equatorial coordinate. The format of data is the numpy binary format.

MASS/SFR_D30_1.83deg.npz

D30: luminosity distance: 30Mpc.
1.83deg: angular resolution of grid.

We provide a piece of code for reading this format file below:

#------------------------------------------------------
import numpy as np

loaded_data = np.load("MASS_D30_1.83deg.npz")

npix = loaded_data['npix']    # sequence number of gird, different angular resolution has different total number pixel.
ra = loaded_data['ra']        # right ascension of central coordinate of grid.
dec = loaded_data['dec']      # declination of central coodinate of grid.
value = loaded_data['value']  # total mass/SFR within this grid (logarithmic form).
#------------------------------------------------------


Note: the value in grid be 1e-10 if no galaxy located at the grid.

