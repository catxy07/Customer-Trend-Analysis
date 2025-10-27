
# 🛍️ Customer Trend Behavior Analysis

### Uncovering key insights from transactional data to guide strategic business decisions.

---

## 📊 Project Overview

This project analyzes **3,900 customer transactions** to uncover spending patterns, product preferences, and subscription behaviors.  
By combining **Python-based Exploratory Data Analysis (EDA)** with **PostgreSQL SQL analytics**, this project delivers actionable insights to improve marketing, retention, and pricing strategies.

---

## 🎯 Project Goals

- Identify key drivers of customer revenue and spending.
- Compare purchase behaviors across genders, age groups, and subscription types.
- Evaluate the impact of discounts and shipping options on sales.
- Segment customers for loyalty and retention analysis.
- Recommend strategic actions based on data-backed insights.

---

## 🧩 Dataset Information

**Dataset Size:** 3,900 Rows × 18 Columns  
**Data Coverage:** Customer demographics, purchases, reviews, and subscriptions.

### **Key Features**
| Feature | Description |
|----------|-------------|
| `age` | Customer age |
| `gender` | Gender of the customer |
| `location` | City or region |
| `category` | Product category purchased |
| `purchase_amount` | Total purchase amount in USD |
| `season` | Season during purchase |
| `previous_purchases` | Number of past transactions |
| `subscription_status` | Whether the customer is subscribed |
| `review_rating` | Product review score |
| `discount_applied` | Whether a discount was used |
| `shipping_type` | Shipping mode (Standard/Express) |

---

## 🔧 Data Preparation & Cleaning

### **1. Data Cleaning**
- Imputed **37 missing values** in `review_rating` using **median rating per product category**.

### **2. Standardization**
- Renamed all columns to **snake_case** format for better readability and SQL integration.

### **3. Feature Engineering**
- Created new features:
  - `age_group` (Young Adult, Middle-aged, Senior)
  - `purchase_frequency_days` (average gap between purchases)

### **4. Database Integration**
- Loaded the cleaned DataFrame into **PostgreSQL** for structured SQL querying.

---

## 🧠 Key Business Insights

### **Revenue & Spending**

| Insight | Description |
|----------|--------------|
| **Male vs Female Revenue** | Male customers generated higher total revenue than female customers. |
| **High-Spending Discount Users** | Some customers used discounts but still spent above the average purchase amount. |

```sql
-- Example Query
SELECT gender, SUM(purchase_amount) AS revenue
FROM customer
GROUP BY gender;
