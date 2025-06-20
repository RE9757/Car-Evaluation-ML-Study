# 🚗 Car Evaluation Classification — Naïve Bayes vs Logistic Regression

This project presents an empirical comparison between **Logistic Regression** and **Naïve Bayes (GaussianNB)** models using the [UCI Car Evaluation dataset](https://archive.ics.uci.edu/ml/datasets/Car+Evaluation). The goal is to build predictive models that can classify car acceptability based on multiple categorical attributes. The implementation includes preprocessing, training, cross-validation, and performance analysis.

---

## 📌 Overview

- **Problem Type**: Multiclass classification
- **Dataset**: Car Evaluation Dataset from the UCI Machine Learning Repository
- **Target**: `class_val` — Car acceptability category (`unacc`, `acc`, `good`, `vgood`)
- **Features**:
  - Buying price
  - Maintenance cost
  - Number of doors
  - Seating capacity
  - Luggage boot size
  - Safety level

---

## 🔧 Implementation Highlights

- **Data Processing**:
  - Removed duplicate entries and validated missing values
  - One-hot encoded categorical attributes
  - Visualized feature and class distributions using interactive pie charts

- **Modeling**:
  - Compared baseline and tuned versions of two classifiers:
    - Logistic Regression with various solvers and regularization values
    - Gaussian Naïve Bayes with different smoothing parameters

- **Evaluation**:
  - 4-fold cross-validation
  - Micro and macro averages for precision and recall
  - Classification reports for detailed performance insights

---

## 📊 Summary of Results

| Model                                | Cross-Validation Accuracy |
|-------------------------------------|----------------------------|
| Logistic Regression (default)       | ~78.2%                     |
| Logistic Regression (sag, C=0.5)    | ~77.3%                     |
| Logistic Regression (newton-cg, C=2)| **~78.5%**                 |
| GaussianNB (default)                | ~47.3%                     |
| GaussianNB (var_smoothing=1e-2)     | ~48.8%                     |
| GaussianNB (var_smoothing=1e-4)     | ~47.0%                     |

Key takeaways:
- Logistic Regression consistently outperforms Naïve Bayes in both accuracy and precision.
- Naïve Bayes yields better recall on some minority classes but with high false positives.
- The dataset is class-imbalanced, which leads to discrepancies between micro and macro metrics.

---

## 🛠️ Tools & Libraries

- Python 3
- pandas, numpy
- scikit-learn
- matplotlib, seaborn, plotly
- Jupyter / Google Colab

---

## 📁 Folder Structure
Car-Evaluation-Classification/
├── notebooks/
│ └── car_evaluation_study.ipynb # Jupyter/Colab notebook
├── src/ # Optional Python scripts
├── figures/ # Optional output plots
├── README.md
└── requirements.txt


---

## 📎 Dataset Source

- [Car Evaluation Dataset - UCI ML Repository](https://archive.ics.uci.edu/ml/datasets/Car+Evaluation)

---

## 💡 Notes

This project demonstrates a typical supervised learning workflow, including data preprocessing, model selection, and result interpretation. It can be extended by exploring additional classifiers such as decision trees, random forests, or ensemble methods.
