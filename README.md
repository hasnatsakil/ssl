# SSL Project

This repository contains code and resources for the SSL (Self-Supervised Learning) project, focusing on medical imaging and natural language processing tasks related to chest X-ray analysis.

## Project Structure

- `create_mapping.py`: Script for creating mappings, likely for data preprocessing.
- `ssl.ipynb`: Jupyter notebook containing the main SSL implementation and experiments.
- `advice/`: Directory with advice and notes on labeling and data processing.
- `chexpert-labeler/`: Submodule for the CheXpert labeler tool from Stanford ML Group.
- `NegBio/`: Submodule for the NegBio library from NCBI for biomedical text processing.
- `mimic-cxr/`: Submodule for the MIMIC-CXR dataset resources.
- `error/`: Directory for error logs or debugging.
- `labeled/`: Directory for labeled data.

## Setup Instructions

### Prerequisites

- Python 3.7+
- Git
- Conda or virtualenv for environment management

### Cloning the Repository

Clone the repository with submodules:

```bash
git clone --recursive https://github.com/hasnatsakil/ssl.git
cd ssl
```

If you forgot to use `--recursive`, initialize submodules later:

```bash
git submodule update --init --recursive
```

### Environment Setup

1. Install Miniconda if not already installed (download from https://docs.conda.io/en/latest/miniconda.html).

2. Create and activate a conda environment:

```bash
conda env create -f environment.yml  # If available, or manually install dependencies
2. Install Python dependencies:

```bash
pip install -r requirements.txt
```

For conda packages like bioc, use:

```bash
conda install -c bioconda bioc
```
```

3. For specific submodules, follow their setup instructions:
   - CheXpert Labeler: See `chexpert-labeler/README.md`
   - NegBio: See `NegBio/README.rst`
   - MIMIC-CXR: See `mimic-cxr/README.md`

## Usage

1. Run the Jupyter notebook for experiments:
   ```bash
   jupyter notebook ssl.ipynb
   ```

2. Use `create_mapping.py` for data mapping as needed.

3. Refer to `advice/` for labeling guidelines.

## Contributing

Please follow standard Git practices. Ensure all changes are tested and documented.

## License

This project is for educational and research purposes. Check individual submodules for their licenses.

## Contact

For questions or issues, please open an issue on GitHub.