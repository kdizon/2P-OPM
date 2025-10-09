# FastMC — Fast multi-camera acquisition for 2P-OPM

FastMC provides NI-DAQ–driven timing for one to three PCO Edge cameras, the OPM galvo, and optional LED control, with Micro-Manager used as the **viewer only**. The hardware timing and limits come from `FastMC_core.py`; `FastMC.py` is the user-editable runner/config.

---

## Files
- **`FastMC_core.py`** — core NI-DAQ functions and timing logic (galvo AO, LED DO, camera triggers, limits). _Do not modify._
- **`FastMC.py`** — edit parameters here (2D/3D, exposure, ROI, z-range, LED mode) and run.

## Requirements
- Windows with **NI-DAQmx** and a compatible NI device (e.g., Dev1).
- **PCO Edge** cameras (CL) with SDK/driver accessible to Python.
- Python packages: `nidaqmx`, `numpy`, `scipy`, `matplotlib`, `tkinter` (stdlib), and your PCO camera Python module (`pco`).  
- Micro-Manager (as a viewer only).

---

## Quick start
1. Open **`FastMC.py`** and set parameters (see inline comments):  
   - `multi_d=False` for **2D** (stacks = frames) **or** `True` for **3D** (stacks = volumes).  
   - `num_stacks`, `stack_delay_time`, `exposure_time`, `readout_mode="fast"|"slow"`.  
   - For 3D: set `z_start`, `z_end`, `z_step`.  
   - Optional LED control via `led_trigger="hardware"|"software_fraction"|"software_time"`, plus `led_stack_fraction_on` or `led_time_on`/`led_frequency`.
2. Run:
   ```bash
   python FastMC.py
