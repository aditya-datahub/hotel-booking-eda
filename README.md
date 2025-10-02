# 💎 Hotel Booking Demand & Cancellation Deep Dive

## 🌟 Project Overview
This project performs an **Exploratory Data Analysis (EDA)** on a large hotel booking dataset. The goal is to uncover the hidden drivers behind the **cancellation rate** and identify the key factors influencing the **Average Daily Rate (ADR)** to provide a clear, data-backed understanding of booking patterns.

---

## 🛠️ Data Preparation & Hygiene
We started with 119,390 records and 32 features.

* **🗑️ Data Reduction:** Features with excessive missing values (**`company`** and **`agent`**) were **dropped** to focus on higher-quality data.
* **📉 Outlier Control:** Extreme outliers in the **Average Daily Rate (ADR)** were **removed** (e.g., ADR $\ge 5000$) to ensure valid statistical representation.
* **⏰ Time Ready:** The **`reservation_status_date`** column was converted to a datetime object for time-series analysis.

---

## 📈 Breakthrough Findings

### 1. The Cancellation Crisis
The overall cancellation rate is a stark **38.04%**, with risk heavily concentrated by hotel type:

| Hotel Type | Cancellation Rate | ⚠️ Severity |
| :--- | :---: | :--- |
| **City Hotel** | **42.96%** | **HIGH** |
| **Resort Hotel** | 27.98% | LOW |

### 2. The Source of the Problem
The analysis highlights critical geographic and market drivers of cancellations:

* **🌍 Geographic Hotspot:** An overwhelming **70.55%** of all canceled bookings originate from **Portugal (PRT)**. This is the single biggest source of cancellation volume.
* **🤝 Market Segment Risk:** The **Groups** segment shows a **disproportionately high cancellation rate**, accounting for $\sim$28% of cancellations despite being a smaller portion of total bookings.

### 3. Financial Impact
The cost of a cancellation fluctuates significantly throughout the year:
* **$$ Highest Loss:** The **ADR for canceled reservations peaks in September**. Cancellations during this period result in the greatest financial loss per booking.
* **Monthly Volume:** The volume of reservations (both canceled and non-canceled) remains relatively stable across the months, suggesting the **drivers of cancellation are related more to customer profile** (market/country) than seasonality.
