# 🩺 Diabetes Prediction using K-Nearest Neighbours (KNN)

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.5.0-orange?logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

A complete end-to-end machine learning project that predicts whether a patient is diabetic using the **Pima Indians Diabetes Dataset** and the **K-Nearest Neighbours (KNN)** algorithm.

---

## 📌 Project Overview

This project walks through the full ML pipeline:

- Exploratory Data Analysis (EDA)
- Data Preprocessing & Missing Value Treatment
- Feature Scaling (StandardScaler)
- Finding Optimal K via Cross-Validation
- Model Training & Evaluation
- Model Comparison: KNN vs Logistic Regression vs Decision Tree
- ROC Curve & Confusion Matrix Visualization

---

## 📁 Project Structure

```
diabetes-knn-classifier/
│
├── notebook/
│   └── diabetes_knn_classifier.ipynb   ← Full Jupyter notebook
│
├── src/
│   └── knn_diabetes.py                 ← Clean Python script
│
├── images/                             ← Saved plots (auto-generated)
│   ├── class_distribution.png
│   ├── correlation_heatmap.png
│   ├── best_k_plot.png
│   ├── confusion_matrix.png
│   ├── roc_curve.png
│   └── model_comparison.png
│
├── data/                               ← Data loads from URL automatically
│   └── .gitkeep
│
├── requirements.txt                    ← Python dependencies
└── README.md
```

---

## 📊 Dataset

| Property | Value |
|---|---|
| Name | Pima Indians Diabetes Dataset |
| Source | [Jason Brownlee's GitHub](https://raw.githubusercontent.com/jbrownlee/Datasets/master/pima-indians-diabetes.data.csv) |
| Samples | 768 |
| Features | 8 (Glucose, BMI, Age, etc.) |
| Target | `Outcome` — 0 = No Diabetes, 1 = Diabetes |
| Class Balance | 500 (No Diabetes) / 268 (Diabetes) |

---

## 🔑 Features Used

| Feature | Description |
|---|---|
| Pregnancies | Number of times pregnant |
| Glucose | Plasma glucose concentration |
| BloodPressure | Diastolic blood pressure (mm Hg) |
| SkinThickness | Triceps skinfold thickness (mm) |
| Insulin | 2-Hour serum insulin (mu U/ml) |
| BMI | Body Mass Index |
| DiabetesPedigree | Diabetes pedigree function |
| Age | Age in years |

---

## ⚙️ Setup & Installation

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/diabetes-knn-classifier.git
cd diabetes-knn-classifier

# 2. Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch Jupyter Notebook
jupyter notebook notebook/diabetes_knn_classifier.ipynb

# OR run the Python script directly
python src/knn_diabetes.py
```

---

## 🧪 Methodology

### 1. Data Cleaning
- Replaced biologically impossible zero values in `Glucose`, `BloodPressure`, `SkinThickness`, `Insulin`, `BMI` with column **medians**

### 2. Preprocessing
- 80/20 train-test split with stratification
- Applied `StandardScaler` — critical for KNN since it uses distance

### 3. Hyperparameter Tuning
- Tested K from 1 to 20 using 5-fold cross-validation
- Selected K with the highest mean CV accuracy

### 4. Evaluation Metrics
- Accuracy, Precision, Recall, F1-Score
- Confusion Matrix
- ROC-AUC Score & Curve

---

## 📈 Results

| Metric | Score |
|---|---|
| Test Accuracy | ~78% |
| ROC-AUC | ~0.84 |
| Best K | ~11 |

### Key Insight
> Scaling is critical for KNN. Without `StandardScaler`, accuracy drops by ~5-8% because features like `Insulin` (range 0–800) dominate distance calculations over `BMI` (range 15–65).

---

## 📉 Model Comparison

| Model | Accuracy | ROC-AUC |
|---|---|---|
| KNN (tuned) | ~78% | ~0.84 |
| Logistic Regression | ~80% | ~0.86 |
| Decision Tree | ~75% | ~0.79 |

---

## 🧠 Concepts Demonstrated

- `KNeighborsClassifier` from scikit-learn
- Cross-validation with `cross_val_score`
- Feature scaling with `StandardScaler`
- Evaluation with `classification_report`, `ConfusionMatrixDisplay`
- ROC curve & AUC score
- Train vs CV accuracy (overfitting detection)

---

## 📚 References

- [Scikit-learn KNN Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html)
- [Pima Indians Diabetes Dataset — UCI ML Repository](https://archive.ics.uci.edu/ml/datasets/Pima+Indians+Diabetes)
- [Jason Brownlee — Machine Learning Mastery](https://machinelearningmastery.com/)

---

## 👤 Author

**Aryan Mishra**
- GitHub: [@ARYAN MISHRA]([https://github.com/YOUR_USERNAME](https://github.com/aryan2026-mishra))
- LinkedIn: [LinkedIn]([https://linkedin.com/in/your-profile](https://www.linkedin.com/in/aryan-mishra-61561b298/))

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use it for learning!
