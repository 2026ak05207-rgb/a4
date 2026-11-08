# BITS Pilani M.Tech (AIML) - Machine Learning Assignment 2

## 1. Project Overview
This project presents an end-to-end Machine Learning pipeline developed as part of the Machine Learning Assignment - 2 (WILP Division). It features synthetic dataset generation, competitive offline evaluation of five classification algorithms, model serialization, and interactive web deployment using Streamlit Community Cloud.

### Core Deliverables:
- **GitHub Repository** with complete source code (`app.py`), package dependencies (`requirements.txt`), comprehensive documentation (`README.md`), and test data (`test_data.csv`).
- **Live Web Application** deployed on Streamlit Community Cloud.
- **Zero-Downtime Design:** Built with a smart dynamic fallback mechanism that re-trains models on-the-fly if pre-trained binaries are absent from the host environment.

---

## 2. Dataset Characteristics
To perform robust binary classification, we generated a high-dimensional synthetic dataset matching assignment specifications:
- **Total Instances:** 1,000
- **Total Features:** 12 (8 informative features, 4 redundant features for complexity)
- **Test Split:** 20% stratified split (200 instances) saved as `test_data.csv`
- **Target Class:** Binary (0 or 1)

---

## 3. Machine Learning Models & Evaluation Comparison
We trained and validated 5 distinct classification models. Each model's final testing performance is summarized below:

| ML Model Name | Accuracy | AUC Score | Precision | Recall | F1 Score | MCC Score |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Logistic Regression** | 0.6750 | 0.7810 | 0.6733 | 0.6800 | 0.6766 | 0.3500 |
| **Decision Tree** | 0.7500 | 0.7500 | 0.7232 | 0.8100 | 0.7642 | 0.5036 |
| **KNN (Winner)** | **0.9100** | **0.9515** | **0.8796** | **0.9500** | **0.9135** | **0.8226** |
| **Naive Bayes** | 0.7100 | 0.7807 | 0.7143 | 0.7000 | 0.7071 | 0.4201 |
| **Support Vector Machine** | 0.9050 | 0.9453 | 0.8716 | 0.9500 | 0.9091 | 0.8133 |

### Model Performance Insights:
- **K-Nearest Neighbors (KNN)** achieved the highest performance overall with an **Accuracy of 91.0%** and an **MCC of 0.8226**.
- **Support Vector Machine (SVM)** achieved highly competitive results (90.5% Accuracy) and shared the highest **Recall (95.0%)** with KNN.

---

## 4. Web Application Features
The deployed Streamlit application incorporates the following interactive features:
1. **Dynamic File Upload (.csv):** Accepts user-uploaded test dataset for model evaluation.
2. **Model Selector Dropdown:** Allows the evaluator to toggle between any of the 5 trained models.
3. **Metrics Panel:** Displays dynamically computed metrics (Accuracy, AUC, Precision, Recall, F1, and MCC).
4. **Visual Interpretations:** Renders a Confusion Matrix heatmap and raw Classification Report on the uploaded test CSV data.

---

## 5. Deployment Instructions (Streamlit Community Cloud)
1. Fork or upload this flat directory directly to a public GitHub repository.
2. Ensure all files (`app.py`, `requirements.txt`, etc.) are placed at the **root** folder level (no nesting directories).
3. Go to [Streamlit Community Cloud](https://share.streamlit.io/) and click **New app**.
4. Select your Repository, Branch (`main`), and set the main file path to `app.py`.
5. Click **Deploy** to publish the interactive dashboard!
