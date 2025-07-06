# 📊 RFM-Based Customer Segmentation for Strategic Insights

## 📌 Overview

This project performs **customer segmentation** using **RFM (Recency, Frequency, Monetary)** analysis on a sales dataset stored in **Google BigQuery**. The goal is to understand customer behavior, identify high-value customers, detect churn risks, and support personalized marketing strategies.

By assigning scores to R, F, and M values and grouping customers into behavioral segments (e.g., *Champions*, *Loyal Customers*, *About to Sleep*), businesses can:

* Improve retention
* Personalize outreach
* Maximize revenue

---

## ❓ Business Questions Answered

* Who are our most valuable customers?
* Which customers are about to churn?
* Who used to buy frequently but have stopped?
* Which segments need re-engagement campaigns?
* Who is most likely to respond to upsell or cross-sell offers?
* How can we tailor loyalty programs for different segments?

---

## 🔍 Quick Insights

* **Total Orders:** 307
* **Unique Customers:** 92
* **Customer Region:** 19 countries (Top 3: USA - 35, France - 12, UK - 5)
* **Average Order Value:** £32,679.57
* **Most Popular Order Days:** Friday, Wednesday, and Thursday
* **Top Customers by Sales:** Euro Shopping Channel, Mini Gifts Distributors Ltd., Australian Collectors, Co.
* **Most Frequent Buyer:** Euro Shopping Channel (26 orders)
* **Total Sales:** £10,032,628.85
* **Total Quantity Ordered:** 99,067

---

## 🧠 RFM Analysis Approach

### ✅ RFM Metrics:

* **Recency (R):** Days since last purchase (lower is better)
* **Frequency (F):** Total distinct order count (higher is better)
* **Monetary (M):** Total amount spent (higher is better)

### ✅ Scoring Method:

Each metric is divided into **5 bins** using `NTILE(5)`:

* Score **5 = Best behavior**, **1 = Lowest**

### ✅ Segmentation:

Customers are grouped using combined RFM scores (`RFM_COMBINATION`) into defined segments:

* **Champions**
* **Loyal Customers**
* **Potential Loyalists**
* **Promising Customers**
* **Needs Attention**
* **About to Sleep**
* **Other**

---

## 🗞 Segment Summary (Top-Level)

| Segment                 | Customers | Avg Recency (Days) | Total Orders | Avg Orders | Total Order Value (£) | Avg Order Value (£) |
| ----------------------- | --------- | ------------------ | ------------ | ---------- | --------------------- | ------------------- |
| **Champions**           | 16        | 35.4               | 100          | 6.2        | 3,516,792             | 219,799.5           |
| **Loyal Customers**     | 14        | 116.7              | 48           | 3.4        | 1,435,999             | 102,571.4           |
| **Promising**           | 11        | 217.9              | 29           | 2.6        | 970,181               | 88,198.3            |
| **About to Sleep**      | 12        | 379.3              | 23           | 1.9        | 760,440               | 63,370.0            |
| **Needs Attention**     | 1         | 270.0              | 3            | 3.0        | 111,640               | 111,640.0           |
| **Potential Loyalists** | 1         | 187.0              | 3            | 3.0        | 24,180                | 24,180.0            |
| **Other**               | 37        | 192.5              | 101          | 2.7        | 3,213,395             | 86,848.5            |

---

## 📦 Quantity & Sales by Segment

| Segment                 | Total Quantity Ordered | Total Sales (£) |
| ----------------------- | ---------------------- | --------------- |
| **Champions**           | 32,508                 | 3,291,935       |
| **Other**               | 31,589                 | 3,173,862       |
| **Loyal Customers**     | 15,443                 | 1,589,871       |
| **Promising**           | 10,821                 | 1,108,614       |
| **About to Sleep**      | 7,361                  | 723,398         |
| **Needs Attention**     | 973                    | 111,640         |
| **Potential Loyalists** | 372                    | 33,309          |

---

## 🌟 Segment-Wise Strategy Recommendations

| Segment                 | Action Plan                                                                                     |
| ----------------------- | ----------------------------------------------------------------------------------------------- |
| **Champions**           | Offer **exclusive perks**, priority support, referral bonuses, and early access to new products |
| **Loyal Customers**     | Strengthen **loyalty programs**, provide upsell/cross-sell offers, and gather feedback          |
| **Promising**           | Send **targeted promotions**, encourage repeat purchases with time-limited discounts            |
| **About to Sleep**      | Launch **win-back campaigns**, offer surveys, and highlight what's new                          |
| **Needs Attention**     | Personal outreach or reminders; evaluate why engagement dropped                                 |
| **Potential Loyalists** | Provide engaging content, post-purchase follow-ups, and trust-building communication            |
| **Other**               | Monitor performance; nurture with low-cost awareness campaigns                                  |

---

## 🛠 Technologies Used

* **SQL (BigQuery Standard SQL)**
* **Window Functions:** `NTILE()`, `DATE_DIFF()`
* **Data Modeling:** `VIEW`, `CASE WHEN`, `JOIN`
* **Data Aggregation & Analysis**

---

## 📈 Key Takeaways

* **RFM segmentation** helps prioritize customer engagement.
* **Champions** contribute **most revenue** but require retention.
* **Loyal customers** are valuable for **long-term growth**.
* **"About to Sleep"** and **"Needs Attention"** are early warning flags for **churn**.
* Custom strategies must be tailored for each customer type to optimize results.
  
