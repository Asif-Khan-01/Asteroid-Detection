================================================================================
ASTEROID DETECTION USING MACHINE LEARNING
================================================================================

1. Install Required Packages:

   pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn plotly streamlit jupyter

2. Verify Installation:

   python -c "import pandas, sklearn, imblearn; print('Ready!')"

================================================================================
EXECUTION STEPS
================================================================================

STEP 1: Train Models
---------------------
Open terminal in project directory and run:

   jupyter notebook

Open "asteroid_detection.ipynb" and click:
   Kernel → Restart & Run All

Wait 15-20 minutes for training to complete.

STEP 2: Run Streamlit App
--------------------------
In terminal, run:

   python -m streamlit run app.py

App opens at http://localhost:8501
Press Ctrl+C to stop.

================================================================================
FILE STRUCTURE
================================================================================

Asteroid Detection/
├── dataset.csv                     (Dataset - Required)
├── asteroid_detection.ipynb        (Main notebook)
├── app.py                          (Streamlit app)
└── README.md                       (This file)

================================================================================
EXPECTED RESULTS
================================================================================

Model Performance:
- Random Forest:    F2-Score: 0.9879, Recall: 99.03%
- SVM:              F2-Score: 0.7048, Recall: 100%
- Logistic Reg:     F2-Score: 0.7033, Recall: 100%

Total Execution Time: 15-20 minutes

================================================================================
TROUBLESHOOTING
================================================================================

Error: "Module not found"
Fix: pip install [missing_package]

Error: "File not found: dataset.csv"
Fix: Place dataset.csv in project root directory

Error: Memory issues
Fix: Close other applications, restart Jupyter kernel

================================================================================
QUICK START
================================================================================

1. pip install [packages]
2. jupyter notebook
3. Run asteroid_detection.ipynb (Kernel → Restart & Run All)
4. Save models (run code from Step 2)
5. python -m streamlit run app.py

Done!