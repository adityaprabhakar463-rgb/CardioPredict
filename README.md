# 🫀 CardioPredict

> A machine learning project for predicting heart disease using the UCI Heart Disease dataset.

![Python](https://img.shields.io/badge/Python-3.12+-blue?style=flat-square&logo=python)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange?style=flat-square&logo=scikit-learn)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat-square&logo=jupyter)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

---

## 📖 Overview

**CardioPredict** is a supervised machine learning project that trains and evaluates multiple classification models to predict the presence of heart disease in patients. It uses the [UCI Heart Disease dataset](https://www.kaggle.com/datasets/redwankarimsony/heart-disease-data), which aggregates clinical data from four institutions worldwide.

The goal is to classify patients as having heart disease (`num > 0`) or not (`num = 0`), based on 13 clinical features.

---

## 📁 Project Structure

```
CardioPredict/
├── CardioPredict.ipynb   # Main Jupyter Notebook (EDA + Model Training)
├── requirements.txt      # Python dependencies
├── .gitignore            # Git ignore rules
└── README.md             # Project documentation
```

---

## 🔬 Dataset

| Property | Details |
|---|---|
| **Source** | UCI Heart Disease Dataset (via Kaggle) |
| **File** | `heart_disease_uci.csv` |
| **Instances** | 920 rows |
| **Features** | 13 clinical features + 1 target |
| **Target** | `num` — 0 (No Disease) / 1–4 (Disease Present) |

### Key Features

| Feature | Description |
|---|---|
| `age` | Age of the patient (years) |
| `sex` | Sex (Male / Female) |
| `cp` | Chest pain type (Typical Angina, Atypical Angina, Non-anginal, Asymptomatic) |
| `trestbps` | Resting blood pressure (mm Hg) |
| `chol` | Serum cholesterol (mg/dl) |
| `fbs` | Fasting blood sugar > 120 mg/dl |
| `restecg` | Resting ECG results |
| `thalch` | Maximum heart rate achieved |
| `exang` | Exercise-induced angina |
| `oldpeak` | ST depression induced by exercise |
| `slope` | Slope of peak exercise ST segment |
| `ca` | Number of major vessels (0–3) |
| `thal` | Thalassemia type |

---

## ⚙️ Methodology

### 1. Exploratory Data Analysis (EDA)
- Distribution of target classes
- Age, max heart rate, chest pain type, and sex distributions vs. target
- Correlation heatmap of numerical features

### 2. Preprocessing
- **Numerical features**: Median/mean imputation → Standard scaling
- **Categorical features**: Most-frequent imputation → One-hot encoding (`drop='first'`)
- Built using `sklearn.pipeline.Pipeline` and `ColumnTransformer`

### 3. Models Trained

| # | Model | Library |
|---|---|---|
| 1 | Logistic Regression | `sklearn.linear_model` |
| 2 | Random Forest Classifier | `sklearn.ensemble` |
| 3 | Support Vector Machine (SVM) | `sklearn.svm` |
| 4 | K-Nearest Neighbors (KNN) | `sklearn.neighbors` |

### 4. Evaluation
Each model is evaluated using:
- Precision, Recall, F1-Score
- `classification_report` (per-class breakdown)
- 80/20 stratified train-test split (`random_state=42`)

---

## 🚀 Getting Started

### Prerequisites
- Python 3.12+
- A Kaggle account (for dataset download via `kagglehub`)

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/your-username/CardioPredict.git
cd CardioPredict
```

**2. Create a virtual environment (recommended)**
```bash
python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Launch the notebook**
```bash
jupyter notebook CardioPredict.ipynb
```

> **Note:** On first run, `kagglehub` will automatically download the dataset. Make sure your Kaggle API credentials are configured (`~/.kaggle/kaggle.json`).

---

## 📦 Dependencies

```
pandas
numpy
matplotlib
seaborn
scikit-learn
kagglehub
```

---

## 📊 Results

Run all cells in `CardioPredict.ipynb` to view the full classification report for each model, including per-class precision, recall, and F1-score.

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

---

## 📄 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

---

## 🙏 Acknowledgements

- Dataset: [Redwan Karim Sony — Heart Disease Data (Kaggle)](https://www.kaggle.com/datasets/redwankarimsony/heart-disease-data)
- Original source: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/45/heart+disease)
- Built with [scikit-learn](https://scikit-learn.org/)
