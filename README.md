# HealthCare_Diabetes_Prediction_Using_ML
## 📌 Project Overview

This project predicts whether a patient is **diabetic or non-diabetic** using the
**Pima Indians Diabetes Dataset** (768 patient records, 9 features).

The project covers the **complete ML pipeline** — from raw data cleaning to model
evaluation — with a focus on real-world data problems like invalid zero values and
the importance of feature scaling.

---

## 📂 Project Structure

```
Healthcare-Diabetes-Prediction/
│
├── health care diabetes.csv          # Dataset (768 rows × 9 columns)
├── Diabetes_Analysis_Complete.ipynb  # Complete Jupyter Notebook
└── README.md                         # Project documentation
```

---

## 📊 Dataset Description

| Column | Description |
|---|---|
| Pregnancies | Number of times pregnant |
| Glucose | Plasma glucose concentration (2-hour oral glucose tolerance test) |
| BloodPressure | Diastolic blood pressure (mm Hg) |
| SkinThickness | Triceps skin fold thickness (mm) |
| Insulin | 2-hour serum insulin (mu U/ml) |
| BMI | Body mass index (weight in kg / height in m²) |
| DiabetesPedigreeFunction | Diabetes pedigree function (family history score) |
| Age | Age in years |
| Outcome | 1 = Diabetic, 0 = Non-Diabetic (Target Variable) |

- **Total Records:** 768 patients
- **Diabetic:** 268 (34.9%) &nbsp;|&nbsp; **Non-Diabetic:** 500 (65.1%)

---

## 🔧 Key Steps Performed

### 1. Data Cleaning
- Detected **261 medically invalid zero values** in `SkinThickness` (72 zeros) and `Insulin` (189 zeros)
- Zeros are medically impossible for these features — replaced with **column median**

### 2. Exploratory Data Analysis (EDA)
- Feature distribution histograms (Diabetic vs Non-Diabetic)
- Boxplots to visualize spread and outliers
- Correlation heatmap — **Glucose has the highest correlation (0.48)** with diabetes outcome

### 3. Key Insights from EDA

| Feature | Non-Diabetic Avg | Diabetic Avg | Difference |
|---|---|---|---|
| Glucose | 110.88 | 140.67 | **+27% higher** |
| BMI | 29.65 | 34.78 | **+17% higher** |
| Insulin | 111.10 | 145.81 | **+31% higher** |
| Age | 32 years | 37 years | **+5 years older** |
| Pregnancies | 3.03 | 4.46 | **+47% more** |

### 4. Feature Scaling
- Applied **StandardScaler** before model training
- Critical for distance-based models (SVM, KNN)
- SVM accuracy improved from **69.5% → 81.8%** after scaling

### 5. Machine Learning Models Trained

| Model | Train Accuracy | Test Accuracy | ROC-AUC |
|---|---|---|---|
| **SVM** ⭐ | 85.2% | **81.8%** | **0.889** |
| Logistic Regression | 81.1% | 80.5% | 0.878 |
| Random Forest | 100% | 79.9% | 0.862 |
| KNN | 82.6% | 77.9% | 0.808 |
| Decision Tree | 84.5% | 75.3% | 0.761 |

> ⭐ **SVM is the best model** — highest Test Accuracy (81.8%) and ROC-AUC (0.889)

### 6. Feature Importance (Random Forest)

| Rank | Feature | Importance |
|---|---|---|
| 1 | Glucose | 28.1% |
| 2 | BMI | 15.5% |
| 3 | DiabetesPedigreeFunction | 11.3% |
| 4 | Age | 10.2% |
| 5 | Insulin | 10.1% |

---

## 🏥 Business Insights & Recommendations

- **Glucose is the #1 predictor** — fasting glucose tests should be prioritized in routine checkups
- **Overweight patients (BMI > 30) above age 35** are at highest risk and should be screened first
- **SVM model (ROC-AUC = 0.889)** can correctly rank a diabetic patient above a non-diabetic patient **89% of the time**
- Hospitals can integrate this model into patient intake systems for **early diabetes detection**
- The model caught **64.8% of actual diabetic patients** (Recall) — further tuning can improve this

---

## 🛠️ Technologies Used

- **Python 3.10**
- **Pandas** — Data manipulation and analysis
- **NumPy** — Numerical operations
- **Matplotlib & Seaborn** — Data visualization
- **Scikit-learn** — Machine learning models, scaling, evaluation metrics

---

## ▶️ How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/koteshwarkatkuri/Healthcare-Diabetes-Prediction.git
   cd Healthcare-Diabetes-Prediction
   ```

2. Install required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```

3. Open the notebook:
   ```bash
   jupyter notebook Diabetes_Analysis_Complete.ipynb
   ```

4. Run all cells from top to bottom ✅

---

## 📈 Results Summary

- Cleaned invalid data, scaled features, trained 5 ML models
- **Best Model: SVM** with **81.8% accuracy** and **ROC-AUC of 0.889**
- **Top Predictors:** Glucose (28%), BMI (15%), Family History (11%)
- Actionable business insight: early flagging of high-risk patients using routine medical data

---

## 👤 Author

**Koteshwar Katkuri**
- 📧 koteshwarkatkuri@gmail.com
- 🔗 [LinkedIn](https://www.linkedin.com/in/koteshwar-katkuri)
- 💻 [GitHub](https://github.com/koteshwarkatkuri)
