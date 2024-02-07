# Synthetic data generation of surgical instruments' 6D pose datasets​ 

Package to generate 6D pose datasets of surgical instruments. The package is based on the [Surgical Robotic challenge][1] simulation environment and the [BOP toolkit][2].

<p align="center">
<img src="./docs/imgs/main_fig.png" width="700">
</p>

[1]: https://github.com/surgical-robotics-ai/surgical_robotics_challenge
[2]: https://github.com/thodan/bop_toolkit 

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

To load data into a neural network I would start from this script. `DatasetReader` behaves similarly to a torch `Dataset`, i.e., it is an iterable object and the data can be accessed via the `[]` operator. Make sure to check the `DatasetSample` and `DatasetReader` classes for more info.

## Known issues:

* Ros topic for images are hardcoded on the `SimulationInterface.py`. If you are using a different topic, the resulting images will be empty.

# Citation
If you find this work useful, please cite it as:

```bibtex

```
