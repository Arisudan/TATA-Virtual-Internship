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

# 💡 Task 3: Turning Insights into Actionable Business Strategy

## 🎯 Objective
To translate predictive analytics into clear, actionable recommendations for Geldium’s Collections team. This phase focuses on leveraging the predictive model developed in Task 2 to:

- Identify high‑risk customer segments
- Propose feasible interventions
- Ensure recommendations are fair, ethical, and aligned with Geldium’s objectives

---

## 🔑 1. Summary of Predictive Insights
- Customers with **2+ missed payments** and a **Debt‑to‑Income Ratio > 50%** are roughly **3× more likely** to miss future payments.  
- Customers **under 30** with **credit utilization > 80%** have a **3.4× higher risk** of delinquency.  
- New account holders (**account tenure < 1 year**) with rising credit utilization demonstrate early warning signs for future risk.

---

## ✅ 2. Recommendation Framework (SMART)

**Restated Insight**  
Customers under 30 with high credit utilization and 2 or more missed payments are at the highest risk of future delinquency.

**Proposed Recommendation**  
Launch a **6‑week targeted SMS and financial coaching campaign** for this segment.

- **Specific:** Target customers under 30 with credit utilization > 80% and ≥ 2 missed payments.
- **Measurable:** Reduce 30‑day delinquency in this segment by **12%** over the pilot period.
- **Actionable:** Leverage existing CRM and SMS platforms for campaign execution.
- **Relevant:** Supports Geldium’s objectives of reducing delinquency and building long‑term trust.
- **Time‑bound:** Pilot campaign over 6 weeks, review results, and scale if successful.

**Why This Works for Geldium**  
- Enables targeted intervention for the highest‑risk segment.  
- Leverages existing digital platforms for cost‑effective outreach.  
- Supports long‑term customer relationships and promotes financial literacy.

---

## ⚖️ 3. Ethical and Responsible AI Considerations

**Fairness and Bias**  
- **Risk:** Model may over‑penalize younger customers or lower‑income groups due to data imbalances.  
- **Mitigation:** Perform regular reviews across demographics (age, income, location) and adjust thresholds as needed.

**Explainability**  
- **Risk:** Stakeholders may struggle to understand why certain customers are flagged as high risk.  
- **Solution:** Incorporate SHAP or LIME explanations into the workflow, making risk assessments clear and actionable.

**Responsible Decision‑Making**  
- Ensure AI‑driven recommendations enable early support and recovery, not punitive measures.  
- Maintain a human‑in‑the‑loop review process for critical decisions.  
- Establish accountability policies and review contested risk classifications.

**Other Ethical Considerations**  
- Maintain data privacy and adhere to applicable regulations.  
- Align AI interventions with Geldium’s long‑term objectives of customer trust, transparency, and inclusive financial services.

---

## 🏁 Final Outcome
With Task 3, this project demonstrates how AI‑driven insights can:

✅ Support Geldium in reducing delinquency by focusing resources where they matter most.  
✅ Maintain a strong commitment to ethical, fair, and responsible AI practices.  
✅ Provide a foundation for future AI‑enhanced risk assessments and customer support interventions.

---

## 🔥 Key Learnings from Task 3
- Developed actionable recommendations that balance business feasibility and customer trust.  
- Understood the role of ethics, fairness, and accountability in AI‑driven risk modeling.  
- Created a seamless link between data insights and business action, making AI a tool for inclusive and trustworthy financial services.

--

# 🤖 Task 4: AI-Powered Collections System — Design & Strategy

In **Task 4** of my virtual internship with **Tata iQ**, I translated the predictive analytics insights from earlier tasks into a **high‑level, actionable design** for an **AI‑Powered Collections System**. This phase focuses on creating an autonomous, responsible, and scalable approach for collections that is both effective for the business and fair to customers.

---

## 🎯 Objective
Develop a **next‑generation collections system** that:
- Automates and personalizes outreach based on delinquency risk  
- Balances automation with human oversight  
- Ensures fairness, transparency, and compliance with regulations  
- Enables continuous learning and improvement from outcomes  

---

## 🛠️ System Overview — How It Works
The proposed system operates through a **4‑Step Cycle**:
1️⃣ **Inputs** — Ingest customer data (demographics, repayment history, credit utilization, loan balances)  
2️⃣ **Decision Logic** — Combine predictive model outputs with business rules to determine the best action  
3️⃣ **Actions** — Trigger interventions such as payment reminders, hardship support, or case escalations  
4️⃣ **Learning** — Continuously monitor outcomes, refine strategies, and adapt the model for better results  

---

## ⚡️ Role of Agentic AI — Autonomy vs Oversight

| ⚡ **Fully Automated**                           | 👥 **Human Oversight**                           |
|-----------------------------|-----------------------------|
| Sending routine payment reminders | Approving personalized hardship or repayment plans |
| Prioritizing accounts by risk       | Managing contested or sensitive cases |
| Adjusting outreach cadence based on behavior | Final review for fairness and compliance |

---

## 🛡️ Responsible AI Guardrails
To ensure trust, accountability, and ethical behavior:

✅ **Fairness Checks** — Regular audits to detect and mitigate bias across customer demographics  
✅ **Explainability** — Clear, interpretable decisions making it easy for staff and customers to understand outcomes  
✅ **Compliance** — Strict alignment with regulations (ECOA, GDPR, FCA, FCRA) and built‑in controls for auditing and review  
✅ **Human‑in‑the‑Loop** — Final review of critical or contested decisions, ensuring accountability and customer-centric outcomes  

---

## 📈 Business Impact
### 💰 Quantitative
- Reduced delinquency and overdue accounts  
- Higher recovery and repayment rates  
- Cost savings via automated, intelligent prioritization  
- Improved operational efficiency across collections  

### 🌟 Qualitative
- Builds trust and long‑term customer relationships  
- Enables personalized support and financial literacy  
- Ensures consistent and fair customer experience across all segments  
- Positions Geldium as a responsible, forward‑thinking digital lender  

---

## 💡 Key Learnings from Task 4
- Created a **scalable AI-driven collections framework** that balances automation and accountability  
- Emphasized the role of ethics, fairness, and compliance in AI-driven financial services  
- Developed a **forward‑looking strategy** aligning business objectives with responsible customer treatment  
- Gained experience in translating technical AI insights into actionable business outcomes  

---

✅ **Summary**
With Task 4, I demonstrated how AI can evolve from **predicting risk** (Task 2) and **informing decisions** (Task 3) to **automating intelligent, fair, and compliant collections** — making a direct, measurable, and responsible impact for both **business** and **customers**.  

--
