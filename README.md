# MDD-SingleChannel-EEG

Implementation of the machine learning framework for detecting **Major Depressive Disorder (MDD)** from **single-channel resting-state EEG** using nested Leave-One-Subject-Out (LOSO) cross-validation and Bayesian hyperparameter optimization.


## Overview

The framework evaluates single-channel EEG recordings using three classical machine learning models:

- Random Forest (RF)
- Support Vector Machine (SVM)
- Gradient Boosting (GB)

Each model is evaluated using:

- Nested Leave-One-Subject-Out (LOSO) cross-validation
- Bayesian hyperparameter optimization
- Subject-level threshold optimization
- Subject-level classification based on segment predictions


## Dataset

Each script expects one feature file for a single EEG channel (e.g., `Feat_C3_final.csv`) with the following columns:

- Segment
- Subject_ID
- Subject
- Label
- Feature columns


## Running the Code

Select the desired EEG channel inside the script, for example:

CHANNEL = "C3"

Run the corresponding model


## Outputs

Each implementation generates:

- Bayesian optimization logs
- Threshold optimization logs
- Subject-level prediction logs
- Segment-level prediction logs
- Confusion matrix
- Final subject-level performance metrics

The Random Forest implementation additionally generates:
- Average feature ranking across folds

## Requirements

The code was developed using Python 3.


