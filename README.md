# Cybersecurity Threat Detection – Suspicious Web Threat Interactions 🔒

## 📌 Project Summary
The “Cybersecurity: Suspicious Web Threat Interactions” project focuses on detecting and classifying malicious web sessions using a hybrid of **machine learning**, **anomaly detection**, and **feature engineering**. By analyzing network session logs (e.g., AWS CloudWatch), this project aims to automate threat detection to support real-time cybersecurity decision-making.

---

## 🎯 Problem Statement
Cyber threats mimic legitimate user behavior, making detection difficult in high-volume data environments. This project addresses challenges like:
- Imbalanced datasets
- Feature sparsity
- Evolving attack patterns

The solution applies:
- **Anomaly detection** (Isolation Forest)
- **Supervised learning** (Random Forest Classifier)
- **Advanced feature engineering**
to proactively flag suspicious traffic and reduce false positives.

---

## 🧠 Business Objective
> Improve the early detection of cyber threats using machine learning on historical traffic logs.

This enables:
- Faster response to incidents
- Smarter security rule design
- Reduced risk of data leaks and operational disruptions

---

## 🧾 Dataset Overview
Source: Web traffic logs (likely from AWS CloudWatch)  
Features include:
- `bytes_in`, `bytes_out`, `packet_count`, `session_duration`
- Engineered metrics like `byte_ratio`, `packets_per_sec`
- Binary label: `is_suspicious` derived from `detection_types`

---

## ⚙️ Methodology

### 🧹 Data Cleaning & Preprocessing
- Parsed datetime fields
- Removed inconsistencies
- Normalized for model input

### 🧪 Feature Engineering
- Extracted behavioral patterns:
  - `byte_ratio`, `packets_per_sec`, `dst_port`, `session_duration`
- Enhanced model interpretability using SHAP

### 🚨 Anomaly Detection
- **Isolation Forest** highlighted statistical outliers in sessions
- Focus on fixed session durations with high byte transfers

### 🤖 Classification Model
- **Random Forest Classifier** used for binary classification
- Evaluation metrics:
  - **Precision**: 0.91
  - **Recall**: 0.88
  - **F1-Score**: 0.89
  - **ROC AUC**: 0.94

### 📊 Model Interpretation
- **SHAP** values explained model behavior
- Most important features:
  - `bytes_out`, `packets_per_sec`, `byte_ratio`, `dst_port`

---

## 📈 Key Visual Insights

- **Traffic Time Patterns**: Spikes between 00:00–02:00 & 08:00–10:00
- **Country Risk**: US (40.1%) and Canada (25.5%) dominate suspicious traffic
- **Top Threat IPs**: 4 IPs flagged with 28+ detections
- **Bytes Anomalies**: Outliers exceed 25MB in a 600-second session
- **Session Duration**: Uniform and non-discriminatory
- **Detection Source**: All detections flagged by WAF (`waf_rule`)

---

## ✅ Results
- Achieved high detection performance with low false positives
- Built a SOC-ready, scalable threat detection pipeline
- Delivered a robust end-to-end solution with explainable AI

---

## 🔍 Recommendations
- Monitor high-byte sessions with fixed durations
- Investigate top contributing IPs and countries
- Complement WAF rules with ML-based anomaly detection
- Drop or re-engineer non-informative features (e.g., fixed session duration)

---

## 📂 Project Structure (PPT)
| Slide | Title | Description |
|-------|-------|-------------|
| 1     | Project Summary | Problem, Dataset, and Business Goal |
| 2–5   | EDA & Anomaly Insights | Session duration, Bytes transferred, Time patterns |
| 6–9   | Country & IP Analysis | Donut, Bar, and Heatmaps of threat origins |
| 10–13 | Model Evaluation | Confusion matrix, ROC curve, SHAP, Feature Importance |
| 14    | Conclusion | Final summary and next steps |

---

## 👤 Author
**Niket Talikoti**  
[LinkedIn](https://www.linkedin.com/in/nikettalikoti/) • [GitHub](https://github.com/niketgtalikoti)

---


