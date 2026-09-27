# Hazardous Asteroid Detection with Machine Learning

Classifies potentially hazardous asteroids (PHAs) from orbital and physical parameters, and serves the model in an interactive Streamlit app.

Team project at Blekinge Institute of Technology (BTH), 2026.

## Results

Evaluated on a held-out test set. F2 score is the main metric because missing a hazardous asteroid costs far more than a false alarm.

| Model | F2 score | Recall (hazardous) |
|---|---|---|
| **Random Forest** | **0.988** | **99.0%** |
| Linear SVM (calibrated) | 0.705 | 100% |
| Logistic Regression | 0.703 | 100% |

## Approach

- **Data:** About 958,000 asteroid records with orbital elements (e, a, q, i, MOID and more), size, albedo and uncertainty values. Target: `pha` (Y/N).
- **Cleaning:** Dropped identifier and text columns and rows with missing values.
- **Class imbalance:** Hazardous asteroids are extremely rare. The training set is rebalanced with SMOTE (minority raised to 30% of the majority) followed by undersampling to a 3:1 ratio. The test set keeps the real distribution.
- **Models:** Logistic Regression, Random Forest and Linear SVM, all with class weighting, compared on F2, recall, precision and confusion matrices.
- **Exploration:** Correlation analysis, feature importance and PCA visualisation.
- **App:** Streamlit interface for exploring predictions.

## Run it

```bash
pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn plotly streamlit jupyter
jupyter notebook                 # run Asteroid-Detection.ipynb (Kernel > Restart & Run All, about 15 to 20 min)
python -m streamlit run app.py   # opens at http://localhost:8501
```

`dataset.csv` (about 436 MB) is not included because of GitHub size limits. Place it in the project root before running the notebook.

## Project structure

```
Asteroid-Detection.ipynb   Data cleaning, resampling, training and evaluation
app.py                     Streamlit app
dataset.csv                Asteroid data (not included)
```

## Tech

Python, scikit-learn, imbalanced-learn, pandas, NumPy, Matplotlib, Seaborn, Plotly, Streamlit.
