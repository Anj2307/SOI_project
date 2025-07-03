
# 🕵️‍♂️ Fraud Detection Model 🧠📊

Welcome to a complete exploratory data analysis (EDA) project aimed at uncovering fraud patterns from financial transaction data. This works on differnet parameters of fraud person. In this project I create Machine learning model to predict fraud automatically

---
# 📊 Data Analysis

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
## 🧱 Feature Engineering

We enhanced the dataset to better represent risk factors:

### 1: 🏠 Address Stability

- Replaced `-1` in `prev_address_months_count` and `current_address_months_count`  with median of respective columns

### 2: 💳 Encoded Categorical Features

- Label-encoded: `payment_type`, `employment_type`, `device_os`,`housing_status` etc.
- Saved mappings to `mappings.json`

### 3: 🚀 Velocity Risk Features

- Standardized and log-transformed: `velocity_6h`, `velocity_8h`, `velocity_1w`
- Created `velocity_risk_score` with `weights` saved to `weight_map(2).json`.

### 4: 📍 Standerdize the data

- Transformed: `Data is transformed or scaled in all categories`
### 5: 📐 Create test and train datasets for model creation

- `Have created train_test_split data`
---
All feature engineering code are embedded in [`feature engineering`](./feature_engineering.ipynb)
## 📁 Project Structure

```
fraud_detect/
├── data/
│   └── SOI_2025_Dataset.csv
├── notebooks/
│   ├── 01_data_analysis.ipynb
│   ├── 02_feature_engineering.ipynb
├── mappings/
│   ├── mappings.json
│   └── weight_map(2).json
├── plots/
├── requirements.txt
├── README.md
└── .gitignore
```


---

## ⚙️ Technologies Used

- 🐍 Python 3.x, json
- 📊 Pandas, NumPy,sckitlearn
- 🎨 Matplotlib, Seaborn
- 🧠 Jupyter Notebook
  

---

## 🚀 How to Run This Project

1. 📥 Clone the repository:
   ```bash
   git clone https://github.com/Anj2307/fraud_detect.git
   cd fraud_detect
   ```

2. 🔧 Install dependencies:
   ```bash
   pip install -r requirements.txt
   pip install json
   ```

3. ▶️ Launch the notebook:
   ```bash
   jupyter notebook data_analysis.ipynb
   jupyter notebook feature_engineering.ipynb
   ```
---

## 📌 Next Steps

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
