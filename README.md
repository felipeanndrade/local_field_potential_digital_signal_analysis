# Summary 

This notebook analyzes Local Field Potential (LFP) signals in two frequency bands: HG (High Gamma) and HFO (High-Frequency Oscillation). The main workflow is:

1. **Reading MATLAB (.mat) file**
   - Uses a helper function with `h5py` to read `.mat` files in version 7.3 (not supported by `scipy.io.loadmat`).
   - Loads variables `lfpHG` and `lfpHFO` and converts them to NumPy arrays.

2. **Data Preparation**
   - Sets the sampling rate (`srate = 1000 Hz`) and calculates time vectors.
   - Prepares signals for analysis and plotting.

3. **Signal Visualization**
   - Plots both frequency band signals in the interval from 10 to 15 seconds.
   - Creates plots with offset and calibration bars for easier interpretation.

4. **Spectral Analysis (Welch PSD)**
   - Uses Welch's method (`scipy.signal.welch`) to calculate the Power Spectral Density (PSD) of the signals.
   - Plots PSDs for each band separately and together for comparison.

5. **Theta Band Power Calculation (5–10 Hz)**
   - Calculates the mean power in the theta band for each channel.

6. **Theta Power Visualization**
   - Plots a bar chart comparing theta power between HG and HFO.

7. **Scale Comparison in PSD**
   - Plots the PSD of both channels on a linear scale (0–200 Hz) and a logarithmic scale.

8. **Detailed Band Analysis**
   - PSD of HG in the range 0–15 Hz and HFO in the range 100–150 Hz, using different window sizes (full signal vs 1s window).
   - Interpolates results for comparative visualization.

## Main techniques and libraries used
- **h5py** for reading `.mat` files (version 7.3).
- **NumPy** for data manipulation.
- **Matplotlib** for signal and spectral visualization.
- **SciPy (welch)** for spectral analysis.

## Purpose
The notebook is designed for the analysis and visualization of local field potentials in different frequency bands, enabling comparison between bands, identification of spectral patterns, and calculation of power in specific ranges (such as the theta band).
