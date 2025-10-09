# Reconstruction code
Reconstruction pipeline for deskewing, scaling, and rotating raw OPM data to conventional microscope coordinates.

## Description
Assumes a tilt angle of 45 degrees and camera pixel size of 0.08667 um.

Accepts as input the y-step size, slices per volume, camera binning, number of channels, as well as if all matrix operations are done together or separately.

To reconstruct raw data, select the folder in which the tiff files are located (files should be listed numerically, if more than one), and the GUI will process all of them and save them to a new folder tilted (reconstructed_data).

Processing involves interpolation and reconstructed data will have isotropic voxel dimensions, i.e. xyz = 0.08667 um.
