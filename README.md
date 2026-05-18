# 💘 Tying the (Data) Knot: Love, Life & Likes

**WIA1006/WID3006 Machine Learning — Sem 2, Session 2025/2026**

> Predicting Match Outcomes in Dating App Behavior Using Machine Learning

---

## 👥 Group Members

| No. | Name | Matric No. | Role |
|-----|------|-----------|------|
| 1 | [Member 1 Name] | [Matric No.] | **Project Lead** — EDA & Data Preprocessing |
| 2 | [Member 2 Name] | [Matric No.] | **Model Builder A** — Models 1, 2 & 3 |
| 3 | [Member 3 Name] | [Matric No.] | **Model Builder B** — Models 4, 5 & Auto-sklearn |
| 4 | [Member 4 Name] | [Matric No.] | **Evaluator & Visualizer** — Evaluation, Comparison & Dashboard |
| 5 | [Member 5 Name] | [Matric No.] | **Report Writer & Presenter** — Report, Slides & Video |

---

## 📁 Repository Structure

```
├── README.md                  ← You are here
├── data/
│   └── dating_app_data.csv    ← Dataset from Kaggle (download instructions below)
├── notebooks/
│   ├── 01_EDA_Preprocessing.ipynb
│   ├── 02_Feature_Engineering.ipynb
│   ├── 03_Model_Training.ipynb
│   ├── 04_Model_Evaluation.ipynb
│   └── 05_Dashboard_App.ipynb
├── src/
│   ├── preprocessing.py       ← Shared preprocessing functions
│   ├── models.py              ← Model training utilities
│   └── evaluation.py          ← Evaluation & plotting helpers
├── reports/
│   ├── Group_Project_Report.docx
│   └── figures/               ← Saved plots for the report
├── slides/
│   └── Presentation_Slides.pptx
├── video/
│   └── README.md              ← Video link only (DO NOT upload video file)
└── requirements.txt
```

---

## 🚀 Getting Started

### Step 1: Clone the Repository

```bash
git clone https://github.com/[your-username]/[repo-name].git
cd [repo-name]
```

### Step 2: Download the Dataset

1. Go to: https://www.kaggle.com/datasets/keyushnisar/dating-app-behavior-dataset
2. Click **Download** and extract the CSV file.
3. Place it inside the `data/` folder as `dating_app_data.csv`.

### Step 3: Set Up Your Environment

```bash
# Option A: Using pip
pip install -r requirements.txt

# Option B: Using conda
conda create -n ml-project python=3.10
conda activate ml-project
pip install -r requirements.txt
```

### Step 4: Open the Notebooks

```bash
# Local Jupyter
jupyter notebook notebooks/

# OR use Google Colab / Kaggle Notebook (recommended)
# Upload the notebooks and dataset to your platform of choice
```

---

## 📋 Task Breakdown by Member

### 🟦 Member 1 — Project Lead: EDA & Data Preprocessing

**Deadline: Week 8 (27 April 2026)**

- [ ] Download & load the dataset
- [ ] Complete `01_EDA_Preprocessing.ipynb`:
  - [ ] Dataset overview (shape, dtypes, head, describe)
  - [ ] Missing value analysis & handling
  - [ ] Outlier detection (boxplots, IQR)
  - [ ] Distribution plots for all numerical features
  - [ ] Categorical feature bar charts
  - [ ] Correlation heatmap
  - [ ] Key insights summary (minimum 5 observations)
- [ ] Complete `02_Feature_Engineering.ipynb`:
  - [ ] Label encoding / One-hot encoding for categoricals
  - [ ] Feature scaling (StandardScaler / MinMaxScaler)
  - [ ] Feature selection using correlation analysis
  - [ ] PCA (if applicable) — explain variance retained
  - [ ] Train/test split (80/20 with stratification)
  - [ ] Save cleaned data as `data/processed_data.csv`
- [ ] Write shared functions in `src/preprocessing.py`
- [ ] Coordinate with all members on data format

**Deliverables:** `01_EDA_Preprocessing.ipynb`, `02_Feature_Engineering.ipynb`, `src/preprocessing.py`

---

### 🟩 Member 2 — Model Builder A: Models 1, 2 & 3

**Deadline: Week 10 (11 May 2026)**

- [ ] Use the cleaned data from Member 1
- [ ] In `03_Model_Training.ipynb`, train these 3 models:
  - [ ] **Model 1: Logistic Regression**
    - Baseline model
    - Hyperparameter tuning (C, solver, penalty) via GridSearchCV
  - [ ] **Model 2: Random Forest Classifier**
    - Hyperparameter tuning (n_estimators, max_depth, min_samples_split)
    - Feature importance plot
  - [ ] **Model 3: Support Vector Machine (SVM)**
    - Hyperparameter tuning (C, kernel, gamma)
    - Note: Scale features first
- [ ] For each model:
  - [ ] Train with default params → record baseline score
  - [ ] Tune with GridSearchCV or RandomizedSearchCV
  - [ ] Record best params and best score
  - [ ] Save trained model using `joblib`
- [ ] Document everything with markdown cells

**Deliverables:** `03_Model_Training.ipynb` (Models 1-3 section), saved models in `models/`

---

### 🟨 Member 3 — Model Builder B: Models 4, 5 & Auto-sklearn

**Deadline: Week 10 (11 May 2026)**

- [ ] Use the cleaned data from Member 1
- [ ] In `03_Model_Training.ipynb`, train these models:
  - [ ] **Model 4: Gradient Boosting (XGBoost or LightGBM)**
    - Hyperparameter tuning (learning_rate, n_estimators, max_depth)
    - Feature importance plot
  - [ ] **Model 5: K-Nearest Neighbors (KNN)**
    - Hyperparameter tuning (n_neighbors, weights, metric)
    - Elbow plot for optimal K
  - [ ] **Auto-sklearn Baseline**
    - Run auto-sklearn on same train/test split
    - Record best pipeline and score
    - Compare with your 5 manual models
- [ ] For each model: same process as Member 2
- [ ] Save all trained models

**Deliverables:** `03_Model_Training.ipynb` (Models 4-5 & Auto-sklearn section), saved models

---

### 🟧 Member 4 — Evaluator & Visualizer: Evaluation, Comparison & Dashboard

**Deadline: Week 11 (18 May 2026)**

- [ ] Complete `04_Model_Evaluation.ipynb`:
  - [ ] Load all 5 trained models + auto-sklearn results
  - [ ] For each model, generate:
    - [ ] Confusion matrix (heatmap)
    - [ ] Classification report (precision, recall, F1)
    - [ ] ROC curve + AUC score
    - [ ] Precision-Recall curve
  - [ ] Comparison table: all models side by side
  - [ ] Bar chart: accuracy / F1 / AUC comparison
  - [ ] Statistical analysis of results
  - [ ] Best model selection with justification
- [ ] *(Optional but highly recommended)* Complete `05_Dashboard_App.ipynb`:
  - [ ] Build a simple Streamlit / Gradio app
  - [ ] User inputs profile → model predicts match outcome
  - [ ] Show prediction probabilities
  - [ ] Display feature importance
- [ ] Save all plots to `reports/figures/`

**Deliverables:** `04_Model_Evaluation.ipynb`, `05_Dashboard_App.ipynb`, `reports/figures/`

---

### 🟥 Member 5 — Report Writer & Presenter: Report, Slides & Video

**Deadline: Week 12 (25 May 2026) for drafts, Week 13 (8 June 2026) for final**

- [ ] Write `reports/Group_Project_Report.docx`:
  - [ ] **Section 1: Problem & Objective** (What are we predicting? Why?)
  - [ ] **Section 2: Methodology & Model Explanation** (Pipeline, each model explained)
  - [ ] **Section 3: Results & Visualization** (Tables, plots from Member 4)
  - [ ] **Section 4: Insights & Interpretation** (What did we learn?)
  - [ ] **Section 5: Conclusion** (Best model, limitations, future work)
- [ ] Prepare `slides/Presentation_Slides.pptx`:
  - [ ] Slide 1: Title slide with all members' names
  - [ ] Slides 2-3: Problem statement & dataset overview
  - [ ] Slides 4-5: Methodology & preprocessing
  - [ ] Slides 6-8: Model results & comparison
  - [ ] Slide 9: Dashboard demo (screenshot)
  - [ ] Slide 10: Conclusion & key takeaways
  - [ ] **Include in slides:** Video link + Notebook link
- [ ] Record 5-minute video presentation:
  - [ ] Each member presents their section (~1 min each)
  - [ ] Upload to YouTube/Google Drive (unlisted)
  - [ ] Put the link in `video/README.md` AND in the slides
- [ ] Final QA: all member names on every file

**Deliverables:** `Group_Project_Report.docx`, `Presentation_Slides.pptx`, video link

---

## ⏰ Timeline

| Week | Date | Milestone | Owner |
|------|------|-----------|-------|
| 5 | 6 Apr 2026 | Project kickoff, repo setup | All |
| 6 | 13 Apr 2026 | Dataset downloaded, initial EDA started | Member 1 |
| 8 | 27 Apr 2026 | **EDA & Preprocessing DONE** | Member 1 |
| 9 | 4 May 2026 | Model training in progress | Members 2 & 3 |
| 10 | 11 May 2026 | **All 5 models + Auto-sklearn DONE** | Members 2 & 3 |
| 11 | 18 May 2026 | **Evaluation & Dashboard DONE** | Member 4 |
| 12 | 25 May 2026 | Report draft & slides draft ready | Member 5 |
| 12 | 1 Jun 2026 | Video recorded, all files reviewed | All |
| **13** | **8 Jun 2026** | **🚨 FINAL SUBMISSION (12:00 PM)** | **All** |

---

## 📦 Submission Checklist

Before submitting to SPECTRUM, verify **ALL** of the following:

- [ ] **All group members' names** appear on:
  - [ ] Presentation slides (title slide)
  - [ ] Report (cover page)
  - [ ] Notebook (first cell)
  - [ ] Video (intro slide)
- [ ] **Presentation Slides (.pptx)** contain:
  - [ ] Link to 5-minute video presentation
  - [ ] Link to Google Colab / Kaggle notebook
  - [ ] *(If local notebook: also submit .ipynb + .pdf)*
- [ ] **Report (.docx)** is complete with all 5 sections
- [ ] **Video** is uploaded online (NOT submitted as a file)
- [ ] **No video file** in the submission
- [ ] Submitted before **8 June 2026, 12:00 PM** (late = 0%)

---

## 🛠 Tech Stack

- **Python 3.10+**
- **Libraries:** pandas, numpy, scikit-learn, xgboost/lightgbm, matplotlib, seaborn, auto-sklearn
- **Notebook:** Jupyter / Google Colab / Kaggle
- **Optional:** Streamlit or Gradio (for dashboard)

---

## ⚠️ Important Rules

1. **DO NOT** submit the video file — only the link.
2. **DO NOT** miss the deadline — late submissions get **0%**.
3. **DO** put all member names on every submission file.
4. **DO** use the provided Kaggle dataset as your primary data source.
5. **DO** train a minimum of 5 models and compare with auto-sklearn.

---

## 📞 Need Help?

If you're stuck on your task:
1. Post in the group chat with a clear description of the problem.
2. Include error messages or screenshots.
3. Tag the relevant member if it depends on their work.
4. Don't wait until the last minute — ask early!

---

*Made with ❤️ by our ML group — WIA1006/WID3006 Sem 2, 2025/2026*
