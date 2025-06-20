# Machine Learning Based Attack Detection in Structural Health Monitoring Wireless Sensor Networks
# 🚨 Intrusion Detection in Structural Health Monitoring (SHM) Wireless Sensor Networks (WSNs)

This project implements a machine learning-based Intrusion Detection System (IDS) tailored for SHM Wireless Sensor Networks. Using the **NSL-KDD** dataset, the system detects anomalies and potential cyber-attacks in real-time SHM deployments such as bridge monitoring, industrial control systems, and building health infrastructure.

---

## 📌 Project Overview

Structural Health Monitoring systems increasingly rely on wireless sensor networks, making them potential targets for cyber-attacks. This project addresses this challenge by developing a real-time IDS using supervised machine learning classifiers.

**Highlights:**
- Based on the NSL-KDD dataset (41 network features + attack labels)
- Multi-class attack detection
- Real-time monitoring with a dashboard
- Explainable AI features included
- Application-ready for SHM domains

---

## 📊 Dataset: NSL-KDD

- Enhanced version of the KDD Cup 1999 dataset
- Includes normal and attack traffic with 41 features
- Covers multiple attack types: DoS (e.g., neptune), Probe, R2L, U2R
- Preprocessed to handle class imbalance and improve training performance

---

## 🧠 Machine Learning Models Used

| Model                 | Accuracy | Notes                          |
|----------------------|----------|--------------------------------|
| ✅ Random Forest      | **Best** | Highest detection accuracy     |
| Decision Tree         | Moderate | Fast but less generalizable    |
| K-Nearest Neighbors   | Fair     | Slower on large datasets       |
| Logistic Regression   | Fair     | Works better for linear trends |

---

## ⚙️ Feature Engineering

- **Categorical Encoding** (e.g., protocol type)
- **Normalization** of continuous values
- **Custom Features**:
  - `bytes_ratio`: Ratio of source to destination bytes
  - `is_long_connection`: Flag for long duration connections

---

## 🚦 Real-Time Monitoring

A web-based dashboard enables:
- Live display of detected anomalies
- Visual representation of alerts by severity
- Explainable AI outputs (feature importance per prediction)

> *Stack used*: FastAPI, Plotly Dash, Bootstrap UI, Python backend

---

## 🔍 Exploratory Findings

- Department 72 showed seasonal peak sales—aligns with Thanksgiving spikes
- Store 20 and 4 had consistently high weekly traffic
- Top attack: **neptune** (a common DoS attack)
- Most important features: `src_bytes`, `bytes_ratio`, `logged_in`

---

## 📈 Model Performance

- Precision/Recall balanced on frequent attack types
- **Random Forest** delivered top F1-score
- Rare attack classes showed lower recall due to class imbalance

---

## 🚧 Limitations

- Class imbalance in dataset affects rare attack detection
- SARIMA models applied globally; not store/department specific
- Manual labeling limits scale of sentiment-driven features

---

## 🚀 Future Enhancements

- Implement LSTM / Transformer models for time-series intrusion prediction
- Add weather and promotion data as external inputs
- Improve real-time deployment using cloud (AWS/GCP) with autoscaling
- Semi-supervised learning for enhanced sentiment-based insights

---

## 📁 Project Structure

```bash
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   ├── EDA.ipynb
│   └── ModelTraining.ipynb
├── src/
│   ├── features.py
│   ├── train.py
│   └── predict.py
├── dashboard/
│   ├── app.py
│   └── utils.py
├── models/
├── requirements.txt
└── README.md
