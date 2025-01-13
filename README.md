# vinci_conda

A GitHub Actions workflow for building and managing Conda environments on Windows machines.

## Features

- Creates/updates Conda environments from environment.yml files
- Supports multiple environment configurations in different folders
- Downloads and caches dependencies including:
  - Python packages via pip/conda
  - Spark NLP jars (optional)
  - Spacy language models (optional)
- Compresses environments into 7z archives for easy uploading
- Creates GitHub releases with built environments

## Usage

1. Place your environment.yml file in a subfolder (e.g., win_dev, win_pip) or make a new folder
2. Trigger the workflow manually through GitHub Actions
3. Configure the build parameters:
   - `build_folder`: Folder containing the environment.yml (e.g., win_dev)
   - `target_folder`: Destination path for the Conda environment
   - `download_jars`: Enable Spark NLP jar downloads
   - `sparknlp_version`: Specify Spark NLP version
   - `download_spacy_model`: Download Spacy language models
   - `zip_vol_size`: Control archive volume size
   - `retention_days`: Artifact retention period

## Available Environments

- `win_dev`: Basic Python development environment with Jupyter
- `win_pip`: Python environment with pytest support

## Installation

1. Download the 7z archives from the latest release
2. Extract to your specified target folder
3. Activate the environment using Conda