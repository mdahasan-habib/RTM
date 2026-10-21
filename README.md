# RTM

## Dependencies

This notebook drives the **DENISE Black Edition** finite-difference code for acoustic RTM.
DENISE is **not included** in this repository; install it separately:

- Code: https://github.com/daniel-koehn/DENISE-Black-Edition (by Daniel Koehn, GPL licence)

### Build DENISE (macOS / Linux)
```bash
git clone --depth=1 https://github.com/daniel-koehn/DENISE-Black-Edition
cd DENISE-Black-Edition/libcseife && make
cd ../src && make denise          # needs an MPI compiler (OpenMPI) and FFTW
```
On macOS: `brew install open-mpi fftw`, and pass the Homebrew include/library paths to `make`.

### Python packages
```bash
pip install numpy scipy matplotlib segyio
```

### Configure the notebook
Edit the paths in the first cell:
- `DENISE_ROOT` – your DENISE-Black-Edition folder (the notebook imports its `pyapi_denise.py`)
- `MPIRUN` – the `mpirun` matching the MPI DENISE was built with
- `SEGY` – path to the Viking Graben data

## Data
Mobil AVO Viking Graben Line 12 (2D marine streamer, North Sea), public dataset released by
Mobil through the SEG. The SEG-Y file (~750 MB) is not included in this repository.
