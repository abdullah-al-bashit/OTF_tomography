# OTF-Tomography

[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Linux-lightgrey.svg)]()

**On-the-Fly Cryo-Electron Tomography Automation**

A Python-based graphical interface for automating cryo-electron tomography (cryo-ET) data acquisition and processing workflows. Developed at Harvard Medical School to streamline multi-stage refinement pipelines for structural biology research.

<p align="center">
  <img src="OTF-tomo.png" alt="OTF-Tomography GUI" width="700"/>
</p>

## Overview

Cryo-ET generates nanometer-resolution 3D reconstructions of biological specimens but requires complex multi-stage refinement including drift correction, motion correction, and tilt-series alignment. This GUI automates key steps in the workflow:

- **Microscope configuration** — Set acquisition parameters
- **Motion correction** — Automated drift correction for tilt series
- **Tilt-series alignment** — Integration with IMOD/AreTomo
- **Particle picking** — crYOLO integration for automated detection
- **RELION preprocessing** — Prepare data for subtomogram averaging

## Features

- Real-time monitoring of data acquisition
- Automated pipeline execution with configurable parameters
- Integration with standard cryo-ET software (RELION, crYOLO, IMOD)
- Batch processing for high-throughput data collection
- Logging and progress tracking

## Installation

### Prerequisites

- Python ≥ 3.8
- RELION (for subtomogram averaging)
- crYOLO (for particle picking)
- IMOD or AreTomo (for alignment)

### Setup

```bash
git clone https://github.com/abdullah-al-bashit/OTF_tomography.git
cd OTF_tomography

# Install Python dependencies
pip install numpy scipy tkinter

# Ensure external tools are in PATH
which relion_refine  # RELION
which cryolo_predict.py  # crYOLO
```

## Usage

### Launch GUI

```bash
python OTF-tomo.py
```

### Pipeline Components

| Module | Description |
|--------|-------------|
| `OTF-tomo.py` | Main GUI application |
| `backend_master.py` | Pipeline orchestration and job management |
| `alignment.py` | Tilt-series alignment routines |
| `prep_functions.py` | Data preprocessing utilities |
| `run_cryolo.py` | crYOLO particle picking integration |
| `rln_helpers.py` | RELION helper functions |
| `transfer_data.py` | Data transfer and organization |
| `check_run_pipeline.py` | Pipeline status monitoring |

### Configuration

Configure paths and parameters in the GUI or edit the configuration section in `backend_master.py`:

```python
# Example configuration
DATA_DIR = "/path/to/raw/data"
OUTPUT_DIR = "/path/to/processed"
RELION_PATH = "/software/relion/bin"
```

## Project Structure

```
OTF_tomography/
├── OTF-tomo.py           # Main GUI application
├── OTF-tomo.png          # GUI screenshot
├── backend_master.py     # Pipeline orchestration
├── alignment.py          # Alignment routines
├── prep_functions.py     # Preprocessing utilities
├── run_cryolo.py         # crYOLO integration
├── rln_helpers.py        # RELION helpers
├── transfer_data.py      # Data transfer
├── check_run_pipeline.py # Pipeline monitoring
├── test.py               # Test suite
├── program_commands.log  # Command logging
└── README.md
```

## Users

This tool has been used for cryo-ET data collection and structure determination by researchers at:

- **Boston Children's Hospital**
- **Dana-Farber Cancer Institute**
- **Massachusetts General Hospital**
- **Harvard Medical School**

## Author

**Abdullah Al Bashit, PhD**  
Developed as a Visiting Researcher at Harvard Medical School

- Email: [a.bashit@northeastern.edu](mailto:a.bashit@northeastern.edu)
- Website: [abdullah-al-bashit.github.io](https://abdullah-al-bashit.github.io)
- Google Scholar: [Profile](https://scholar.google.com/citations?user=w3KyQbkAAAAJ)

## License

This project is licensed under the MIT License - see [LICENSE](LICENSE) for details.

## Acknowledgments

- Harvard Medical School Cryo-ET Facility
- Boston-area structural biology community

## Citation

If you use this software in your research, please acknowledge:

```
OTF-Tomography: On-the-Fly Cryo-ET Automation
Abdullah Al Bashit
Harvard Medical School, 2024
https://github.com/abdullah-al-bashit/OTF_tomography
```
