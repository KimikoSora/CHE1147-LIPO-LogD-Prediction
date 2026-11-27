# CHE1147 Final Project — Molecular Lipophilicity Prediction

## Project Overview

We predict experimental logD at pH 7.4 from molecular structure. We compare
Ridge, Random Forest, and XGBoost using three descriptor sets: Full RDKit,
Reduced RDKit, and PhysChem11. All nine combinations use the same stratified
80/20 train/test split and the same five cross-validation folds within the
training set.

## Repository Contents

- `CHE1147_Final_project_code!!!!!.ipynb` — Data cleaning, descriptor calculation,
  model training, evaluation, and figure generation.
- `requirements.txt` — Python dependencies for reproducing the analysis.

## Dataset

We use the MoleculeNet Lipophilicity (LIPO) dataset. The notebook reads a local
copy of the CSV if available and otherwise downloads it from
[DeepChem](https://deepchemdata.s3-us-west-1.amazonaws.com/datasets/Lipophilicity.csv).

## How to Run

1. [Open the notebook in Google Colab](https://colab.research.google.com/github/KimikoSora/CHE1147-LIPO-LogD-Prediction/blob/main/CHE1147_Final_project_code%21%21%21%21%21.ipynb).
2. Select **Runtime → Run all**. The first cells install the pinned versions of
   RDKit, scikit-learn, and XGBoost. The remaining cells train and evaluate all
   nine configurations and generate the figures.
3. If the dataset download fails, upload `Lipophilicity.csv` through the
   Colab Files panel and rerun **Runtime → Run all**.

To install the project dependencies in a separate Python environment, run
`python -m pip install -r requirements.txt`.

## Outputs

The notebook saves tables and figures to `LIPO_Stratified_Results_Ipc_log1p/`.

- `LIPO_Model_Comparison_CV.csv` — Cross-validation results for all nine configurations.
- `LIPO_All_Models_CV_Test.csv` — Cross-validation and held-out test results.
- `LIPO_Three_Feature_Sets_Test_RMSE.png` — Test RMSE comparison across models and descriptor sets.
- `environment.json` — Python and package versions recorded by the notebook.
