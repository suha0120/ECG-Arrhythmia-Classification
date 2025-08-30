# ECG-Arrhythmia-Classification

# Arrhythmia Classification Using ECG and Machine Learning

## 📌 Project Overview
This project focuses on **multiclass classification of cardiac arrhythmias** using ECG signals. The primary goal is to build a robust machine learning framework capable of detecting different arrhythmia types efficiently, while addressing challenges such as **signal noise**, **high dimensionality**, and **class imbalance**.

The project uses the **MIT-BIH Arrhythmia Database** as the primary dataset and employs advanced preprocessing, feature engineering, and machine learning techniques to improve diagnostic accuracy.

---

## ⚙️ Workflow

### 1. Data Collection & Preprocessing
- Dataset: MIT-BIH Arrhythmia Database  
- ECG signal preprocessing:
  - Baseline wander removal (high-pass filtering)  
  - Powerline interference removal (notch filter at 60 Hz)  
  - High-frequency noise reduction (low-pass filtering)  
- Normalization using **Z-score**  
- Heartbeat segmentation around **R-peaks** (250 samples per beat)  

### 2. Feature Extraction & Dimensionality Reduction
- Extracted **32 features** (temporal + morphological):
  - Intervals (RR, QRS, QT, ST, PQ)  
  - Wave amplitudes (P, Q, R, S, T)  
  - QRS shape descriptors  
- Applied **PCA (Principal Component Analysis)** to reduce feature space while retaining 95% of variance.  

### 3. Handling Class Imbalance
- Problem: Normal beats dominate the dataset, minority classes underrepresented.  
- Applied:
  - **SMOTE** – Synthetic Minority Oversampling  
  - **ADASYN** – Adaptive Synthetic Sampling  
- Balanced dataset for fair training and evaluation.  

### 4. Classification Models
Evaluated multiple machine learning classifiers:
- **CatBoost**  
- **XGBoost**  
- **LightGBM**

### 5. Evaluation Metrics
- Accuracy  
- Precision, Recall, F1-Score (Macro)  
- AUC-ROC  
- 10-fold cross-validation for reliable assessment  

---

## 📊 Results
- **Without balancing:** High accuracy but poor recall on minority classes.  
- **With SMOTE/ADASYN:** Significant improvements in macro F1-score.  
- **Best Result:**  
  - **CatBoost + SMOTE** → Macro F1 ≈ **0.924**  
- SMOTE slightly outperformed ADASYN across classifiers.  

---

## 🚀 Future Work
- Test framework on multi-center ECG datasets.  
- Explore **deep learning models** (CNNs, RNNs, GAN-based augmentation).  
- Implement explainable AI tools (e.g., SHAP, LIME) for clinical interpretability.  
- Optimize hyperparameters with **Bayesian optimization**.  

---

## 📂 Repository Structure
