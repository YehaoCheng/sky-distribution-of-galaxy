The first folders are named in angular resolutions. We chose the proper angular resolution according to the FoV of telescope.
Both the Mass and SFR folders contain data based on equatorial and galactic coordinates. Because there are difference for the division of celestrial sphere based on the equatorial and galactic coordinates but the difference is small and don't affect the main results.

MASS/SFR_D30_1.83deg_gal.txt
D30: luminosity distance: 30Mpc;
1.83deg: angular resolution;
gal: galaxies in Galactic coordinates (no gal means equatorial coordinates).

In the text file, there are four column: 
pix_num : sequence number of pixel, different pixel size (angular resolution) has different total number pixel.
ra/l: right ascension/galactic longitude.
dec/b: declination/galactic latitude.
Mass/SFR: total mass/SFR within this pixel (logarithmic form).

Note: ra/l and dec/b represents the coordinates at the center of each pixel.

