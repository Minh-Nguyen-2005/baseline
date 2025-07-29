# Data Science for Optimization of Healthcare Operations: Improving Real-time Appointment-matching System

The pandemic has had a considerable impact on elective care and currently, the waiting list is at its highest on record, with over 6.6 million people waiting for consultant-led elective care. It is estimated that around 6M fewer people completed elective pathways between January 2020 and July 2021. Operational performance, defined by the proportion of those seen within 18 weeks (target of 92%) has dropped significantly. The proportion seen within 18 weeks has dropped to below 65%.

As such, in this project, we propose to develop a real-time appointment-matching simulation program with constrained resources using SimPy environment, where patient assignments to healthcare providers in the Upper Valley area are simulated and monitored such that patients always go to the provider with the shortest line. Thus, this research project aims to utilize the power of Data and AI to optimize Hitchcock Hospital’s healthcare system by minimizing patients’ wait time and speeding up the process of arranging appointments, hence supporting patients’ access to prioritized medical care services.

## Baseline

A collection of baseline implementations for biomedical classification tasks, covering Inflammatory Bowel Disease (IBD), Liver, Gastrointestinal Motility, and Pancreas datasets. This repository provides a single “baseline” script that trains and evaluates simple models across each domain, plus per‐task folders containing data preprocessing, training notebooks, and result summaries.

## Table of Contents

- [Features](#features)  
- [Requirements](#requirements)  
- [Installation](#installation)  
- [Usage](#usage)  
- [Directory Structure](#directory-structure)  
- [Subfolder Details](#subfolder-details)  
  - [IBD](#ibd)  
  - [Liver](#liver)  
  - [Motility](#motility)  
  - [Pancreas](#pancreas)  
- [Contributing](#contributing)  
- [License](#license)

## Features

- **Unified Baseline**  
  A single entrypoint that can run a simple model (e.g. logistic regression) across multiple biomedical tasks.  
- **Per‐task Notebooks**  
  Each subfolder walks through data loading, preprocessing, model training, and evaluation for that specific domain.  
- **Modular Design**  
  Shared helper functions in `baseline/baseline.py` make it easy to add new tasks or swap in more sophisticated models later.  

## Requirements

- Python 3.8+  
- `numpy`  
- `pandas`  
- `scikit-learn`  
- `matplotlib`  
- Any other dependencies listed in `requirements.txt`  

## Installation

```bash
# 1. Clone the repo
git clone https://github.com/Minh-Nguyen-2005/baseline.git
cd baseline

# 2. (Optional) create a virtual environment
python3 -m venv venv
source venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

## Usage

The main baseline script lives at: baseline/baseline.py

It can be invoked from the project root:
python baseline/baseline.py \
    --task IBD \
    --data-path ./IBD \
    --model logistic_regression \
    --output-dir ./results/IBD
```

**Arguments**:

* --task
One of IBD, Liver, Motility, or Pancreas.

* --data-path
Path to the folder containing that task’s raw data.

* --model
Which baseline model to train (e.g. logistic_regression, decision_tree).

* --output-dir
Directory to save trained model and evaluation metrics.

Run python ```baseline/baseline.py``` --help for full options.

## Directory Structure

```bash
baseline/
├── baseline.py           # core training & evaluation logic
├── IBD/                  # IBD AnyLogic Simulation and Excel data 
├── Liver/                # Liver AnyLogic Simulation and Excel data
├── Motility/             # Motility AnyLogic Simulation and Excel data
├── Pancreas/             # Pancreas AnyLogic Simulation and Excel data
├── requirements.txt      # Python dependencies
└── README.md             # this file
```

## IBD

- ```data/``` – raw CSVs or image folders for IBD samples

- ```notebook.ipynb``` – step‐by‐step data exploration, preprocessing, baseline model training, and performance plots

- ```results/``` – saved metrics (accuracy, ROC AUC), confusion matrices, and model pickle files

## Liver

- ```data/``` – liver ultrasound or clinical feature tables

- ```train_liver.ipynb``` – code to load features, normalize, train a baseline classifier, and visualize ROC curves

- ```figures/``` – diagnostic plots, feature importance bar charts

## Motility

- ```data/``` – time‐series recordings of GI motility signals (e.g. sensor CSVs)

- ```motility_baseline.py``` – a standalone script that extracts simple time‐domain features (mean, variance) and trains a tree-based model

- ```outputs/``` – model predictions vs. ground truth overlaid on raw signals

## Pancreas

- ```data/``` – CT scan slices or tabular biomarkers for pancreas lesions

- ```pancreas_notebook.ipynb``` – deep dive on data augmentation, CNN baseline training, and test‐set evaluation

- ```models/``` – saved Keras/TensorFlow .h5 files and performance summary tables

## Contributing

Fork the repo

Create your feature branch (git checkout -b feature/XYZ)

Commit your changes (git commit -m "Add XYZ")

Push to your branch (git push origin feature/XYZ)

Open a Pull Request

Please adhere to PEP8 style and include notebook cleanups before submitting.

## License

By Minh Nguyen for Dartmouth E.E. Just Summer Internship and FYREE research programs
