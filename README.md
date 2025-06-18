# 💳 Credit Risk Analysis – AI-Driven Data Analytics by TATA iQ

This repository documents **Task 1** of my Virtual Internship in **AI-Driven Data Analytics**, offered by **Tata iQ**. This project is centered on understanding and predicting **credit card delinquency** using real-world data, assisted by AI and data science tools.

---

## 🔎 Understanding the Basics

### 🧾 What is a Credit Card?

A **credit card** allows a customer to borrow money up to a set limit to pay for goods or services. The amount borrowed must be repaid later, usually with interest. Responsible usage helps build credit scores; irresponsible usage can lead to **debt accumulation**.

---

### ⚠️ What is Credit Card Delinquency?

**Credit card delinquency** occurs when a customer **fails to make the minimum required payment** by the due date. It typically goes through stages:
- **30+ Days Late** → Mild delinquency
- **60+ Days Late** → Medium risk
- **90+ Days Late** → Severe default risk

Delinquency can damage the customer’s credit score and cost lenders **significant financial loss**.

---

### 💡 Why Analyze Delinquency Risk?

Understanding which customers are likely to miss payments allows financial institutions to:
- Predict **who is at risk**
- **Intervene early** with reminders or flexible plans
- **Reduce loan defaults and losses**
- Maintain **regulatory compliance** and fairness

---

## 🧠 Project Overview

### 💼 Client: Geldium

**Geldium** is a digital financial services provider focused on **credit cards and consumer loans**. They have seen a rise in customers **missing payments** beyond 30 days.

### 🧩 The Challenge

Geldium currently uses **manual methods** and simple historical trends to track risk. They want Tata iQ to develop an **AI-powered model** that can:
- Accurately predict delinquency
- Recommend personalized outreach
- Maintain **transparency, fairness, and auditability**

---

## 🎯 Internship Task 1: Exploratory Data Analysis (EDA)

As an **AI Transformation Consultant**, my job was to perform a full EDA on Geldium’s customer dataset before building predictive models.

### 📌 Task Objectives:
- Understand dataset structure and completeness
- Handle missing values and detect anomalies
- Identify variables most relevant to delinquency
- Use GenAI (like ChatGPT) to support imputation and insight generation
- Document all findings in a detailed report

---

## 🧾 Dataset Summary

- **Records**: 500 customers
- **Columns**: 19
- **Target**: `Delinquent_Account` (Binary: 1 = Missed payments, 0 = No issues)

### 🔑 Key Features

| Column | Description |
|--------|-------------|
| `Age`, `Income`, `Credit_Score` | Customer profile |
| `Credit_Utilization`, `Loan_Balance` | Credit behavior |
| `Debt_to_Income_Ratio` | Financial stress |
| `Missed_Payments`, `Account_Tenure` | Payment history |
| `Employment_Status`, `Location`, `Credit_Card_Type` | Categorical info |
| `Month_1` to `Month_6` | Past 6-month payment behavior |

---

## 📉Task 1: Exploratory Data Analysis (EDA) Process – Step by Step

### ✅ Step 1: Review and Insight Generation

- Verified column types and descriptions using the **Dataset Description Guide**
- Used **GenAI** to summarize patterns, detect outliers, and suggest questions
- Checked for:
  - Duplicates → None
  - Age anomalies → All values valid
  - Credit utilization > 100% → None

### ✅ Step 2: Missing Data Analysis

| Feature         | Missing Count | Strategy                    |
|-----------------|----------------|-----------------------------|
| `Income`        | 39             | Regression-based Imputation |
| `Credit_Score`  | 2              | Median Imputation           |
| `Loan_Balance`  | 29             | Predictive Imputation       |

⚠️ No columns were dropped. All imputations were guided by **AI recommendations + domain logic**.

### ✅ Step 3: Detecting Risk Indicators

Used correlation analysis + trend mapping to identify top delinquency predictors:

- **High Credit Utilization** → Signs of financial stress
- **High Debt-to-Income (DTI) Ratio** → Over-borrowing
- **Short Account Tenure** → Limited trust and repayment history
- **Low Credit Score** → Legacy of missed payments
- **Recent missed payments (Months 5 & 6)** → Near-future risk

---

## 🤖 Using GenAI in EDA

To accelerate and enrich the EDA, I used **Generative AI** tools such as ChatGPT.

### 🛠️ AI Usage Included:
- Summarizing dataset structure
- Identifying missing data handling strategies
- Generating synthetic data to test imputation assumptions
- Highlighting feature relationships in natural language

### 💬 Example Prompts Used:
- “Summarize key patterns in this dataset and list high-risk features.”
- “What is the best way to handle missing income values?”
- “Which variables most influence credit card delinquency risk?”

All AI outputs were **validated by statistical methods** to ensure reliability.

---

## 📄 Final Deliverable

I compiled all findings, charts, decisions, and insights into a formal document titled:

**EDA_Summary_Report_Geldium_Final.docx**

Contents include:
- Dataset overview and types
- Missing data analysis
- Risk indicators and correlations
- GenAI tools and prompts
- Next steps toward model building

---

## 📚 Key Learnings from Task 1

- Gained deep experience in real-world **Exploratory Data Analysis**
- Applied **industry best practices** for imputation and anomaly handling
- Learned how to **extract business insight from raw data**
- Practiced using **GenAI for data automation and summarization**
- Documented results in a professional and explainable format

---

# 🔍 Task 2: Predictive Modeling  

In this **Task 2** of my virtual internship project with **Tata iQ**, where I moved beyond data exploration (Task 1) and outlined a predictive modeling approach to forecast **credit card delinquency risk** among customers of Geldium.

Building on the insights gathered in the Exploratory Data Analysis phase, I used **GenAI tools** to define model logic, select an appropriate algorithm, justify the approach, and create a fair and interpretable evaluation plan.

---

## 🧠 Objective

To design a conceptual AI model that:
- Predicts whether a customer is likely to become delinquent (miss payments)
- Assists the Collections team in identifying high-risk customers
- Maintains fairness, transparency, and regulatory alignment
- Leverages insights from customer financial and behavioral attributes

---

## 🔧 1. Model Logic (Generated with GenAI)

The predictive model uses key financial indicators to classify customers as either **at risk of delinquency (1)** or **not delinquent (0)**. The GenAI-generated model workflow includes:

### 🔄 Modeling Steps:
1. **Load Dataset**: Use Geldium’s cleaned dataset
2. **Feature Selection**: Focus on influential attributes like:
   - Credit_Utilization
   - Debt_to_Income_Ratio
   - Missed_Payments
   - Credit_Score
   - Account_Tenure
3. **Data Preprocessing**: 
   - Handle missing values (e.g., impute Income)
   - Encode categorical variables (Employment_Status, Credit_Card_Type)
4. **Model Training**:
   - Apply Logistic Regression for binary classification
   - Calculate delinquency probability for each customer
5. **Classification Threshold**:
   - If probability > 0.5 → classify as delinquent
6. **Output**: 
   - Provide label (0 or 1) + explanation using SHAP or similar techniques
7. **Model Evaluation**:
   - Accuracy, Precision, Recall, F1 Score, AUC-ROC

This logic was generated with the help of ChatGPT to accelerate model planning and summarization.

---

## 📌 2. Justification for Model Choice

I selected **Logistic Regression** for the following reasons:

- 🧾 **Interpretability**: Ideal for explaining how each feature influences the prediction
- 🎯 **Binary Outcome Alignment**: Perfect match for the target variable (`Delinquent_Account`)
- 🛡️ **Regulatory Compliance**: Trusted by financial institutions due to transparency
- ⚡ **Efficient Deployment**: Lightweight, easy to implement and maintain
- 🤝 **Business Alignment**: Supports Geldium’s need for traceable, fair, and ethical AI

Though alternatives like Random Forest or Neural Networks offer higher complexity and potential accuracy, their lack of transparency would not align well with Geldium’s operational and compliance requirements.

---

## 📈 3. Evaluation Strategy

To ensure both **accuracy** and **fairness**, I developed a multi-dimensional evaluation strategy:

### 📊 Key Metrics:
- **Accuracy**: Overall correctness of predictions
- **Precision**: Percentage of true delinquents among those predicted at-risk
- **Recall**: Percentage of all actual delinquents the model correctly identified
- **F1 Score**: Harmonic mean of precision and recall—ideal for imbalanced data
- **AUC-ROC**: Measures the model’s ability to distinguish between classes
- **Confusion Matrix**: Visual breakdown of prediction performance

### ⚖️ Fairness & Bias Mitigation:
- Use **disparate impact analysis** to detect bias across income, employment, and location groups
- Apply **SHAP values** to understand which features influence individual predictions
- Test for **demographic parity** and **equal opportunity** across customer segments
- Avoid proxy variables (e.g., ZIP code) that may unintentionally embed bias

### 🧭 Ethical Considerations:
- Maintain **human-in-the-loop** review before action on high-risk predictions
- Keep all explanations traceable and auditable
- Respect data privacy and transparency in all model outputs

---

## 🧠 Learnings from Task 2

- Used **GenAI** tools effectively to generate model logic and justification
- Learned to balance **performance, explainability, and fairness** in model design
- Developed a complete conceptual pipeline suitable for **real-world deployment**
- Designed a responsible evaluation framework aligned with industry standards

---

This modeling plan sets the foundation for building a responsible and effective AI-powered credit risk solution. The next step would involve implementation, validation, and real-time deployment support.

---


