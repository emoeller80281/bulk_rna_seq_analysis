# Bulk RNA-seq Analysis

This repository contains scripts for analyzing `filtered_feature_bc_matrix.h5` output files from CellRanger. The `notebooks` directory contains Jupyter notebooks for preprocessing and analyzing a knockout sample and a wild-type sample. 

## Installation:

### 1) Create conda environment

```bash
conda create --file environment.yml
conda activate rna_seq
```

### 2) Register the Jupyter kernel

```bash
python -m ipykernel install --user --name rna_seq
```

### 3) Start a Jupyter server

**Note:** If you are on an HPC, make sure that you *do not start the Jupyter sever on the head node*. Create a new interactive session. For our HPC, the command is:

```bash
salloc -p compute -c 12 --mem=32G bash
srun --pty bash
```

Next, start the Jupyter lab server:

```bash
jupyter lab --no-browser --ip=0.0.0.0 --port=8885 --ServerApp.log_level=ERROR
```

Use this server to run the Jupyter notebooks in `notebooks`.