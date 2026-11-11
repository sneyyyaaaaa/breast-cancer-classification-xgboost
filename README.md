# Breast Cancer Classification Using XGBoost

## Overview
An educational machine-learning project that trains an XGBoost classifier on the Wisconsin Diagnostic Breast Cancer dataset available through scikit-learn.

The notebook uses ten mean tumour measurements and predicts the dataset's benign or malignant class label. It is a learning project, not a clinical tool.

## Dataset
- Dataset: Wisconsin Diagnostic Breast Cancer
- Source: `sklearn.datasets.load_breast_cancer`
- Records: 569 (212 malignant, 357 benign)
- Input features: 10 mean tumour measurements (the columns whose names contain "mean")
- Target mapping in this notebook: `1` = malignant, `0` = benign

The dataset is loaded directly from scikit-learn; a separate CSV file is not required.

## Methods
1. Load the built-in dataset.
2. Select the ten mean measurement features by column name.
3. Explore class balance and feature correlations.
4. Split the data into stratified training and test sets (80:20, random seed 42).
5. Train an XGBoost classifier (200 trees, maximum depth 3, learning rate 0.05, subsample 0.9, column subsample 0.9).
6. Evaluate with accuracy, precision, recall, F1-score, ROC-AUC, a confusion matrix, and five-fold cross-validation accuracy.
7. Visualize feature importance.
8. Demonstrate interactive and manual-input predictions.

## Evaluation design
- **Split:** stratified 80:20 with random seed 42, performed before any model fitting. This gives 455 training and 114 test samples.
- **Preprocessing:** no preprocessing is learned from the data. There is no scaling or imputation (not needed for tree-based models) and no data-driven feature selection. The ten features are chosen by column name only.
- **Hyperparameters:** fixed in the code and not tuned on the test set. The test set is used once, to evaluate a single model.
- **Cross-validation:** five-fold cross-validation is run on the full dataset, so it is a separate estimate and is not independent of the test set. No preprocessing is performed inside the folds, so there is no fold-to-fold leakage from preprocessing.
- **Leakage checks:** the split precedes all fitting, the test set is not used for tuning or model selection, and the dataset contains no exact duplicate rows.
- **Repeated patients:** the scikit-learn copy of the dataset does not include patient identifiers, so patient-level repeats cannot be checked in this notebook.

## Recorded evaluation results
The saved notebook output reports the following results:

| Metric | Result |
|---|---:|
| Accuracy | 95.6% |
| Precision | 95.1% |
| Recall | 92.9% |
| F1-score | 94.0% |
| ROC-AUC | 97.6% |
| 5-fold cross-validation accuracy | 94.6% |

These are results from the notebook's recorded run and evaluation setup. They are not a guarantee of performance on new data.

## Errors and limitations
- The test set has 114 samples. The model misclassified 5 of them (2 false positives and 3 false negatives), so the metrics are uncertain by several percentage points.
- Missing a malignant case is the costly error. Recall is 92.9%, and the default 0.5 decision threshold was used with no threshold or calibration analysis.
- The dataset is small and comes from a single source. There is no external validation.
- Only the ten mean features are used, so the model ignores the other measurements in the dataset.
- The interactive demo accepts any slider combination, including biologically implausible inputs, and will still return a prediction.

## Technologies
Python, Jupyter Notebook, Pandas, NumPy, Matplotlib, Seaborn, scikit-learn, XGBoost, and ipywidgets.

## Run locally
```bash
git clone https://github.com/sneyyyaaaaa/breast-cancer-classification-xgboost.git
cd breast-cancer-classification-xgboost
python -m pip install -r requirements.txt
jupyter notebook
```
Open `Breast_Cancer_XGBoost.ipynb` and run all cells. The interactive controls require a Jupyter environment that supports ipywidgets. Results may differ slightly with other package versions.

## Repository contents
- `Breast_Cancer_XGBoost.ipynb` — data exploration, model training, evaluation, and prediction demo.
- `requirements.txt` — Python dependencies.
- `.gitignore` — common generated/local files excluded from version control.

## Limitations and responsible use
This is an academic demonstration using a public benchmark dataset. It is not a clinically validated diagnostic system and must not be used to diagnose cancer, guide treatment, or replace assessment by qualified healthcare professionals.

## Reference
The notebook introduction cites: Singh, Ansari & Jha (2026), *Cloud based Breast Cancer Detection using Machine Learning by XGBoost Method*, IJSRAIML, 2(3), 179–196. Please verify the publication details against the original paper before relying on or citing this reference in formal academic work.

## Author
**Sneha Theertha A D**
M.Tech Computer Science and Information Systems

## License
No license is currently specified. All rights in the notebook remain with their respective authors unless a license is added.
