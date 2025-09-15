## 👨‍💻 Author  

Name : **Singara Harendra** 

Roll Number : DA25M028

# Fraud Detection with GMM-Based Synthetic Sampling and Cluster-Based Undersampling
📌 Project Overview

Credit card fraud detection is a highly imbalanced classification problem — fraudulent transactions make up less than 0.2% of the dataset. Traditional machine learning models often fail to detect these rare cases.

This project explores the use of Gaussian Mixture Models (GMM)-based synthetic oversampling and Cluster-Based Undersampling (CBU) to address class imbalance. The objective is to improve detection of fraudulent transactions while maintaining model stability.

📂 Repository Structure
├── fraud_detection_GMM_CBU.ipynb   # Main notebook with full pipeline
├── README.md                       # Project documentation
├── requirements.txt                # Dependencies (optional)
└── data/                           # (Dataset not included, due to size limit)

### ⚙️ Dataset

Source: Kaggle Credit Card Fraud Dataset

Features: 30 input features + 1 output label (Class)

Imbalance: Legitimate (≈ 284,000), Fraudulent (≈ 492)

### Preprocessing:

Standardized Time and Amount features

No missing values

🔎 Methodology
1. Baseline Model

Trained a classifier on the raw imbalanced dataset

Served as a benchmark for comparison

### 2. Resampling Strategies

GMM Oversampling: Generated synthetic minority samples by modeling fraud transactions as a Gaussian Mixture.

Cluster-Based Undersampling (CBU): Reduced the size of the majority class by clustering and sampling representative points.

Hybrid (GMM + CBU): Combined oversampling (minority) and undersampling (majority) to achieve balance.

### 3. Model Evaluation

Metrics calculated using sklearn classification report:

Accuracy

Precision

Recall

F1-score

### 📊 Results
Comparative Analysis (Fraud Class Only)
Model	Accuracy	Precision	Recall	F1-score
Baseline	0.9992	0.8585	0.6149	0.7165
GMM Oversampling	0.9750	0.0555	0.8378	0.1040
GMM + CBU	0.9843	0.0880	0.8581	0.1595
Key Insights:

Baseline: High precision but low recall → missed many fraud cases.

GMM Oversampling: Recall improved dramatically (0.62 → 0.83), but precision dropped sharply.

GMM + CBU Hybrid: Balanced resampling strategy achieved strong recall (0.85), though precision was still low.

✅ Conclusion

GMM-based oversampling improves recall, meaning the model catches more fraud cases.

CBU + GMM hybrid offers a balanced approach, reducing bias towards the majority class while preserving minority structure.

For fraud detection tasks, high recall is often preferred, since missing fraud cases is costlier than false alarms.
