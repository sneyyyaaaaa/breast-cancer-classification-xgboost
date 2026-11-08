# Breast Cancer Classification Using XGBoost

## Overview
An educational machine-learning project that trains an XGBoost classifier on the Wisconsin Diagnostic Breast Cancer dataset available through scikit-learn.

The notebook uses ten mean tumour measurements and predicts the dataset's benign or malignant class label.

## Dataset
- Dataset: Wisconsin Diagnostic Breast Cancer
- Source: `sklearn.datasets.load_breast_cancer`
- Records: 569
- Input features: 10 mean tumour measurements
- Target mapping in this notebook: `1` = malignant, `0` = benign

The dataset is loaded directly from scikit-learn; a separate CSV file is not required.

## Methods
1. Load the built-in dataset.
2. Select the ten mean measurement features.
3. Explore class balance and feature correlations.
4. Split the data into stratified training and test sets (80:20).
5. Train an XGBoost classifier.
6. Evaluate with accuracy, precision, recall, F1-score, ROC-AUC, a confusion matrix, and five-fold cross-validation accuracy.
7. Visualize feature importance.
8. Demonstrate interactive and manual-input predictions.

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

## Technologies
Python, Jupyter Notebook, Pandas, NumPy, Matplotlib, Seaborn, scikit-learn, XGBoost, and ipywidgets.

## Run locally
```bash
git clone https://github.com/USERNAME/breast-cancer-classification-xgboost.git
cd breast-cancer-classification-xgboost
python -m pip install -r requirements.txt
jupyter notebook
```
Open `Breast_Cancer_XGBoost.ipynb` and run the cells. The interactive controls require a Jupyter environment that supports ipywidgets.

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
