
# 🕵️‍♂️ Fraud Detection Data Analysis 🧠📊

Welcome to a complete exploratory data analysis (EDA) project aimed at uncovering fraud patterns from financial transaction data. This work focuses on behavioral, temporal, and technical factors that correlate with fraudulent activity.

---

## 🗂️ Dataset Overview

- 📁 **File**: `SOI_2025_Dataset.csv`
- 🎯 **Target column**: `fraud_bool` (0 = Legit, 1 = Fraud)
- 📊 **Features analyzed**:
  - `credit_risk_score`
  - `bank_branch_count_8w`
  - `device_distinct_emails_8w`
  - `foreign_request`, `month`, `session_length_in_minutes`, `payment_type`
  - `prev_address_months_count`, `current_address_months_count`
  - `total_relationship_count`, `income`

---

## 🔍 Key Insights & Findings

### 📈 Credit Risk Score
- 🚩 Fraudsters had **unexpectedly higher credit scores**, possibly indicating **synthetic identity fraud** or stolen identities with good credit history.

### 🏦 Bank Branch Usage (Last 8 Weeks)
- Fraudulent users typically had access to **fewer bank branches**, suggesting **online-only behavior** or **temporary accounts**.

### 💻 Device–Email Mapping
- Devices associated with **multiple distinct emails** were more likely linked to fraud — indicating **account farming** or **shared device abuse**.

### 🌐 Foreign Requests
- A clear fraud spike was observed in transactions with `foreign_request = 1`, supporting **geolocation-based risk** profiling.

### 🗓️ Monthly Trend
- 📆 Fraud incidents peaked in **Month 7 (July)** — likely due to seasonal or quarter-end fraud trends.

### ⌛ Session Length
- Most fraudulent sessions were **short-lived** (low session length), hinting at **scripted** or **bot-like** behavior.

### 💻 Device OS
- Fraud was disproportionately higher on **Windows OS**, likely due to ease of use for fraud tools and botnets.

### 🔌 Keep-Alive Sessions
- Fraudsters often had `keep_alive_session = 0`, suggesting **non-persistent activity** to avoid detection.

### 🏠 Address Stability
- Fraudulent users often had **very short** or **missing previous address durations**, indicating a lack of verifiable residential history.

### 💰 Income Trends
- Users with **missing or low income values** were slightly more fraud-prone.
- Could also indicate **fake identity data entries**.

### 🧾 Total Relationships
- Lower `total_relationship_count` suggests **new, potentially fake accounts** used solely for fraud.

### 💳 Payment Types
- Certain `payment_type` values (like prepaid cards) saw **higher fraud rates**, indicating misuse of anonymous or quick-transfer payment methods.

---

## 📊 Visualizations Included

- 📦 Boxplots for feature distributions
- 📉 Fraud rate bar charts by:
  - Month
  - Device type
  - Bank branch access
- 📍 Countplots of fraud vs foreign access, OS, and payment type

🖼️ All charts are embedded in [`data_analysis.ipynb`](./data_analysis.ipynb)

---

## 📁 Project Structure

```
fraud-detection-project/
├── data/                      # Sample CSVs or ignored original data
├── plots/                     # Saved figures from EDA
├── data_analysis.ipynb        # Main notebook
├── README.md                  # You’re reading this
├── requirements.txt           # Dependencies
└── .gitignore                 # Files to exclude
```

---

## ⚙️ Technologies Used

- 🐍 Python 3.x
- 📊 Pandas, NumPy
- 🎨 Matplotlib, Seaborn
- 🧠 Jupyter Notebook

---

## 🚀 How to Run This Project

1. 📥 Clone the repository:
   ```bash
   git clone https://github.com/Anj2307/SOI_project.git
   cd fraud_detect
   ```

2. 🔧 Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. ▶️ Launch the notebook:
   ```bash
   jupyter notebook data_analysis.ipynb
   ```

---

## 📌 Next Steps

- 🏗️ Feature engineering (e.g., recency-weighted risk scores)
- 🤖 Build fraud classification models: Logistic Regression, XGBoost, etc.
- 📈 Evaluate metrics: Precision, Recall, AUC-ROC
- 🌐 Deploy via API or real-time scoring service

---

## 🤝 Contributions

🧑‍💻 Pull requests and forks are welcome!  
If you have new analysis ideas or want to improve modeling, feel free to contribute.

---

## 👤 Author

Developed by: **Anubhav Goyal**  
🎓 B.Tech (Mathematics and Computing) @ IIT Dharwad  
📬 GitHub: [@Anj2307](https://github.com/Anj2307)

---

> 📎 *This project is part of a learning journey in AI, Finance, and Machine Learning applied to fraud detection.*
