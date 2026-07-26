# 📊 Sales & Commercial Analytics Power BI Dashboard (PDF Export)

> **📌 Data Privacy & Anonymization Notice:**  
> This repository contains documentation and sample exports of an enterprise **Commercial Sales & Revenue Power BI Dashboard**. To comply with strict data privacy guidelines and Non-Disclosure Agreements (NDAs), all customer account names have been sanitized to generic placeholders (e.g., *Customer 1*, *Customer 2*, *Customer 16*) while retaining accurate financial metrics, budget comparisons, and underlying DAX logic.

---

## 🎯 Executive Overview

This Power BI dashboard export provides executive-level visibility into global commercial performance, revenue vs. budget variances, unit volume trends, and promotional trade spend (Customer Investment).

It allows Key Account Managers (KAMs), Commercial Directors, and Finance teams to track:
* Revenue performance against targets across multiple sales channels.
* Account-level **Drivers vs. Drainers** (identifying top-performing accounts vs. underperforming revenue gaps).
* Product contribution and volume concentration across core SKUs.
* Promotional efficiency and trade spend compliance.

---

## 📑 Dashboard Architecture & Page Breakdown

The attached dashboard PDF export consists of **6 primary analytical pages**:

### 1. Sales Overview
* **Focus:** High-level executive performance summary and SKU distribution.
* **Core KPIs:**
  * **Total Sales:** £4.38M Gross Revenue
  * **Units Sold:** 7,062,382 Total Units
  * **Customer Investment:** £268.02K Total Trade Spend
  * **Sales vs. Budget %:** -18.80% Variance
  * **Units vs. Budget %:** -12.18% Variance
  * **Investment vs. Budget %:** -53.27% Variance
* **Key Visuals:** Top 10 SKU Bar Chart, Sales by Channel Share %, Top 10 Account Volume Rankings (`Customer 1` to `Customer 76`), and Monthly Revenue Trends.

### 2. Drivers & Drainers By Revenue
* **Focus:** Variance analysis isolating outperforming and underperforming customer accounts.
* **Top 10 Revenue Drivers:** Identifies accounts exceeding revenue targets (e.g., `Customer 3` generating +£52.4K variance over budget).
* **Top 10 Revenue Drainers:** Highlights accounts trailing budget targets (e.g., `Customer 11` creating a -£674.5K gap against budget).

### 3. Channel & Product Performance Trends
* **Focus:** Multi-period seasonality tracking (2025 vs. 2026 YTD) comparing Gross Revenue, Budgeted Forecasts, and Prior Year (LY) figures.
* **Key Visuals:** Clustered Column & Line Visuals tracking monthly unit throughput and cumulative Sales YTD vs. Budget YTD growth curves.

### 4. SKU Distribution & Service Metrics
* **Focus:** Product-level volume concentration across core SKUs (`OPSALTED35`, `OPSESAME35`, `NOCON`) and supply chain performance.
* **Service KPIs:**
  * **Lost Sales (£):** Quantification of revenue loss from out-of-stock events.
  * **OTIF Rate (%):** On-Time In-Full delivery fulfillment tracking across operational weeks.

### 5. Performance Trends (MTD vs. YTD)
* **Focus:** Detailed comparison of Month-To-Date (MTD) vs. Year-To-Date (YTD) actuals against budget baselines across Gross Revenue, Units Sold, and Customer Investment budgets.

### 6. Customer Investment Report
* **Focus:** Financial audit of trade spend, listing fees, and promotional retro allowances.
* **Key Spend Categories:**
  * `5102 - Shopper Marketing - CI` (52.66% Share | £141.1K)
  * `5107 - Promotions / Meal Deal Retros` (18.76% Share | £50.3K)
  * `5101 - Listing Fees` (10.70% Share | £28.7K)
  * `5108 - Data & Retailer Analytics` (£12.3K)
  * `5109 - Other Customer Investment` (£18.7K)

---

## 🧮 Calculated KPIs & DAX Formulas

Below are the core DAX measures powering the calculations throughout the report:

| Metric Name | Description | DAX Formula Logic | Target Benchmark |
| :--- | :--- | :--- | :--- |
| **Total Sales (£)** | Gross sales revenue realized across all fulfilled orders. | `SUM(Sales[GrossAmount])` | £4.38M |
| **Sales vs. Budget %** | Percentage variance between actual revenue and target budget. | `DIVIDE([Total Sales] - [Budget Sales], [Budget Sales], 0)` | $\ge 0.0\%$ |
| **Units vs. Budget %** | Volume variance comparing actual units sold against budget targets. | `DIVIDE([Units Sold] - [Budget Units], [Budget Units], 0)` | $\ge 0.0\%$ |
| **Revenue Variance Driver** | Dollar variance to isolate top drivers vs. drainers. | `[Total Sales] - [Budget Sales]` | $> 0$ (Driver) |
| **Customer Investment %** | Trade spend efficiency ratio as a percentage of gross revenue. | `DIVIDE([Total Customer Investment], [Total Sales], 0)` | $\le 6.5\%$ |

---

## 🎛️ Report Filters & Slicer Architecture

The dashboard pages feature a standardized Power BI Top Slicer Bar:
* **Channel Slicer:** Filters data by sales channel (*Grocery*, *Foodservice & FTG*, *Travel*, *Wholesale & Vending*, *Ecommerce*, *High Street*).
* **Product Description Slicer:** Isolates performance down to individual SKUs and packaging sizes.
* **Customer Slicer:** Granular account-level filtering across all customer accounts.
* **Date Range Slicer:** Custom date span selection (`01/01/2025` to `31/05/2026`).
