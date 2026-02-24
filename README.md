# 💳 customer-transaction-prediction

This project predicts whether a **bank customer will make a future transaction** using an anonymized dataset containing 200 numerical features.

It demonstrates a complete **end-to-end machine learning workflow**, including data loading, preprocessing, model training, evaluation, and model comparison.

The goal is to classify customers into:

**0 → No Transaction**
**1 → Transaction**

---

## 📌 Project Overview

* **Problem Type:** Binary Classification
* **Domain:** Banking / Financial Analytics
* **Target Variable:** `target`
* **Dataset Size:** 200,000 records
* **Features:** 200 anonymized numerical variables
* **Models Used:** Logistic Regression, Random Forest, Gradient Boosting

---

## 📊 Dataset

* Fully anonymized dataset
* Columns:

  * `ID_code` → Customer identifier
  * `target` → Binary output (0 or 1)
  * 200 numerical feature columns

✔ No missing values
✔ High-dimensional tabular dataset
✔ Realistic financial prediction task

Dataset Source:
[https://d3ilbtxij3aepc.cloudfront.net/projects/CDS-Capstone-Projects/PRCP-1003-CustTransPred.zip](https://d3ilbtxij3aepc.cloudfront.net/projects/CDS-Capstone-Projects/PRCP-1003-CustTransPred.zip)

---

## 🔍 Data Loading

The dataset was downloaded dynamically from a zipped source using:

* `requests`
* `zipfile`
* `pandas`

This ensures reproducibility without manual downloads.

---

## 🔧 Data Preprocessing

* Removed `ID_code`
* Verified absence of missing values
* Split dataset into:

  * **Training:** 20%
  * **Testing:** 80% (used to speed up model training)
* Stratified sampling to preserve class distribution

---

## 🧠 Model Selection & Training

Three machine learning models were implemented:

### Models

* Logistic Regression (`max_iter=1000`)
* Random Forest Classifier
* Gradient Boosting Classifier

Training was performed on the reduced training subset to improve computational efficiency.

---

## 📈 Model Evaluation

### Metrics Used

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC

---

### ✅ Logistic Regression

* Accuracy: **0.9130**
* Precision: **0.6688**
* Recall: **0.2658**
* F1-score: **0.3804**
* ROC-AUC: **0.8547**

---

### ⚠️ Random Forest

* Accuracy: **0.8995**
* Precision: **1.0000**
* Recall: **0.0000**
* F1-score: **0.0000**
* ROC-AUC: **0.8074**

(Random Forest predicted no positive samples)

---

### ⚡ Gradient Boosting

* Accuracy: **0.9025**
* Precision: **0.8185**
* Recall: **0.0384**
* F1-score: **0.0734**
* ROC-AUC: **0.8267**

---

## 🏆 Best Model

**Logistic Regression** performed best overall due to:

* Highest ROC-AUC
* Better precision–recall balance
* Stable performance across evaluation metrics

---

## ⚠️ Challenges Faced

### 1️⃣ Anonymized Features

* No feature interpretation possible
  **Solution:** Focused on modeling rather than domain-driven feature engineering

### 2️⃣ Large Dataset Size

* Long training time
  **Solution:** Reduced training size using 80% test split

### 3️⃣ Logistic Regression Convergence Warning

**Solution:** Increased `max_iter` to 1000

### 4️⃣ Random Forest Metric Warning

* No positive predictions
  **Solution:** Used `zero_division=1` in evaluation metrics

---

## 🛠️ Tech Stack

| Tool             | Purpose            |
| ---------------- | ------------------ |
| Python           | Programming        |
| Pandas / NumPy   | Data processing    |
| Scikit-learn     | ML modeling        |
| Requests         | Data retrieval     |
| Zipfile          | Dataset extraction |
| Jupyter Notebook | Experimentation    |

---

## 🚀 How to Run

```bash
git clone https://github.com/SyedHussain23/customer-transaction-prediction
cd customer-transaction-prediction
pip install pandas numpy scikit-learn requests
jupyter notebook customer-transaction-prediction.ipynb
```

---

## 🔮 Future Improvements

* Hyperparameter tuning
* Cross-validation enhancement
* Feature selection techniques
* Advanced ensemble models
* Explainable AI (SHAP, LIME)
* Deep learning experimentation

---

## 👨‍💻 Author

**Syed Hussain Abdul Hakeem**

* LinkedIn: [https://www.linkedin.com/in/syed-hussain-abdul-hakeem](https://www.linkedin.com/in/syed-hussain-abdul-hakeem)
* GitHub: [https://github.com/SyedHussain23](https://github.com/SyedHussain23)

---

## ⭐ Show Your Support

If you found this project useful, consider giving it a ⭐.
