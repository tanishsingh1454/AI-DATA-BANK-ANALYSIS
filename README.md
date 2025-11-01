# 🏦 AI Bank Power BI Project

## 📊 Project Overview
The **AI Bank Power BI Dashboard** provides a detailed analysis of customer transactions, account activity, and financial performance.  
This project showcases how Power BI can transform raw banking data into clear visual insights — helping stakeholders understand customer behavior and account trends.

---

## 🎯 Objectives
- Analyze and visualize **customer and transaction data**.  
- Identify **inactive accounts** and **monthly transaction trends**.  
- Compare **account performance** between Savings and Current accounts.  
- Understand **customer demographics** (gender, age group, and balance patterns).

---

## 📈 Key Insights

### 🧾 Sales & Transaction Analysis
- **Monthly Transaction Trend:** Highest in **March, September, and December** (~4M).  
- **Transaction Type:** Equal split between **Credit (50%)** and **Debit (50%)**.  
- **Inactive Accounts:** Increased steadily from 2024 to 2025, reaching **5 inactive accounts**.  

### 👥 Customer Analysis
- **Gender Breakdown:** 25% Male, 25% Female, 50% Blank/Unspecified.  
- **Age Group:** Majority customers fall in the **36–50 years** category.  
- **Account Type Distribution:** Equal count — **200 Savings** and **200 Current** accounts.  
- **Top Account Holder:** *Priya Singh* shows the highest (negative) balance of **-15,787.44K**.

---

## 🧮 DAX Formulas Used

```DAX
-- Total Transaction Amount
Total Transaction Amount = SUM(Transaction[Amount])

-- Inactive Accounts
Inactive Accounts = CALCULATE(
    COUNTROWS(Account),
    FILTER(Account, Account[Status] = "Inactive")
)

-- Total Balance by AccountType
Total Balance by AccountType = SUM(Account[Balance])

-- Monthly Transaction Amount
Monthly Transaction Amount = 
CALCULATE(
    SUM(Transaction[Amount]),
    GROUPBY(Transaction, Transaction[Month])
)

-- Customer Age Group
Customer Age Group = 
SWITCH(
    TRUE(),
    Customer[Age] >= 18 && Customer[Age] <= 25, "18-25",
    Customer[Age] >= 26 && Customer[Age] <= 35, "26-35",
    Customer[Age] >= 36 && Customer[Age] <= 50, "36-50",
    "50+"
)


🚀 Outcomes

Developed an interactive Power BI dashboard for AI Bank.

Automated account and transaction tracking.

Enhanced insights into customer demographics and financial behavior.

Delivered a clear view of monthly performance and account health.

📂 Project Files

📁 AI bank power bi project.pbit – Power BI Template

🖼️ Dashboard screenshots (visuals included in this repo)

📝 README.md – Project documentation

🧠 Future Enhancements

🔮 Add AI-based forecasting for future transaction volumes.

🤖 Integrate Python for churn and risk prediction.

🔁 Connect to live banking databases for automatic refresh.
