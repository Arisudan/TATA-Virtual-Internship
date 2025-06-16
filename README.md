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

## 📁 Project Directory Structure

Task-1-EDA-Geldium/
├── Delinquency_prediction_dataset.xlsx # Raw dataset from Geldium
├── Updated_Dataset_Description_Guide.pdf # Field explanation
├── EDA_Summary_Report_Geldium_Final.docx # Final report (output)
├── README.md # Documentation
