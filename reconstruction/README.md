# Reconstruction (2P- and 1P-OPM)
Deskews, rescales, and rotates raw OPM data into conventional microscope coordinates (GPU-accelerated).

## Defaults
- Tilt angle: **45°**
- Camera pixel size (x,y): **0.08667 µm** (adjusted by **bin**)
- Output voxel size (x,y,z): **isotropic = 0.08667 µm × bin**

## Inputs (GUI)
- **Y-step size** (µm)
- **Slices per volume**: enter an integer, or **`z`** to use all z-slices per volume
- **Binning**: 1/2/4 (sets effective pixel size)
- **# of channels**: **1 or 2** (more requires code edits)
- **Matrix ops**: `"together"` (faster) or `"seperate"` (lower GPU RAM)

## Quick start
1. `python reconstruct.py`
2. Click **Choose folder** and select the directory with raw **.tif** files (numerically sorted).
3. Set parameters → **Transform**.
4. Outputs are written to **`reconstructed_data/`** (e.g., `recon_0.tif`, `recon_1.tif`, …).

## Output
- Deskewed+rotated volumes with isotropic voxels (= effective pixel size).
- Interpolation is applied during resampling.

## Requirements
- Python 3.9+; **CUDA-capable GPU**
- `cupy`, `cupyx.scipy.ndimage`, `tifffile`, `numpy`, `matplotlib`, `tkinter` (stdlib), `napari` (optional for viewing)


License: BSD-3-Clause (see root [LICENSE](../LICENSE))
