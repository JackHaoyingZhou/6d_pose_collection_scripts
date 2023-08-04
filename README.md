# 6D pose dataset collection scripts

The following repository contains scripts to automatically generate 6d pose datasets from the SurgicalRoboticsAssets.


# Getting started

## Installation

First install `ambf6dpose` package with:
```bash
pip install -e .
```

## Scripts
Scripts to collect and read data are found in `scripts/` folder.

**Collection script**
```bash
collect_data.py --help
```

```bash
Usage: collect_data.py [OPTIONS]

  6D pose data collection script. Instructions: (1) Run ambf simulation (2)
  run recorded motions (3) run collection script.

Options:
  --path TEXT          Path to save dataset  [required]
  --sample_time FLOAT  Sample every n seconds
  --help               Show this message and exit.
```

Do adapt this script, make sure to check the `DatasetSample` class that is return by the `DatasetReader` class.

**Projecting script**
```bash
python generate_blended.py --help
```

```bash
Usage: generate_blended.py [OPTIONS]

  Generate test images by project needle 3d point to the image plane. This
  script can be used to visualy inspect the correctness of the intrinsic and
  extrinsic matrices

Options:
  --path TEXT  Path to save dataset  [required]
  --help       Show this message and exit.
```

## Known issues:

* Ros topic for images are hardcoded on the `SimulationInterface.py`. If you are using a different topic, the resulting images will be empty.