# MDD-SingleChannel-EEG

Implementation of the machine learning framework for detecting **Major Depressive Disorder (MDD)** from **single-channel resting-state EEG** using nested Leave-One-Subject-Out (LOSO) cross-validation and Bayesian hyperparameter optimization.

---

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


## Repository Structure


MDD-SingleChannel-EEG/

├── RF/
│   └── Nested_LOSO_Bayesian_RF_SingleChannel.py
│
├── SVM/
│   └── Nested_LOSO_Bayesian_SVM_SingleChannel.py
│
├── GB/
│   └── Nested_LOSO_Bayesian_GB_SingleChannel.py
│
├── requirements.txt
├── LICENSE
└── README.md
```

---

## Machine Learning Models

The repository includes implementations of:

- Random Forest (RF)
- Support Vector Machine (SVM)
- Gradient Boosting (GB)

The Random Forest implementation additionally provides feature importance ranking across LOSO folds.

---

## Dataset

The feature datasets used in this study are **not included** in this repository.

The experiments were conducted using a publicly available resting-state EEG dataset. Please obtain the original EEG dataset from the source referenced in the manuscript and generate the required feature matrices following the methodology described in the paper.

Each script expects one feature file for a single EEG channel (e.g., `Feat_C3_final.csv`) with the following columns:

- Segment
- Subject_ID
- Subject
- Label
- Feature columns

---

## Running the Code

Select the desired EEG channel inside the script, for example:

```python
CHANNEL = "C3"
```

Run the corresponding model:

### Random Forest

```bash
python Nested_LOSO_Bayesian_RF_SingleChannel.py
```

### Support Vector Machine

```bash
python Nested_LOSO_Bayesian_SVM_SingleChannel.py
```

### Gradient Boosting

```bash
python Nested_LOSO_Bayesian_GB_SingleChannel.py
```

---

## Outputs

Each implementation generates:

- Bayesian optimization logs
- Threshold optimization logs
- Subject-level prediction logs
- Segment-level prediction logs
- Confusion matrix
- Final subject-level performance metrics

The Random Forest implementation additionally generates:

- Feature importance for each LOSO fold
- Average feature ranking across folds

---

## Requirements

The code was developed using Python 3.

Install the required packages using:

```bash
pip install -r requirements.txt
```

The required packages are listed in `requirements.txt`.

---

## Citation

If you use this code in your research, please cite the associated publication:

> Shruthi Narayanan Vaniya, Ahsan Habib, Maia Angelova, Sheikh Mohammed Shariful Islam, and Chandan Karmakar. *Towards Practical Mental Health Assessment: Detection of Major Depressive Disorder Using Minimal EEG Sensing.* *(Update with the final journal citation after publication.)*

---

## License

This project is released under the MIT License.
