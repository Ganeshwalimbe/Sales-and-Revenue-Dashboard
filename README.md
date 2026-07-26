# 📊 Sales & Commercial Analytics Power BI Dashboard

> **📌 Portfolio & Data Privacy Notice:**  
> This repository contains documentation, visual design blueprints, and a lightweight web prototype (`index.html`) reflecting an enterprise **Commercial Sales & Revenue Dashboard**. To comply with privacy standards and non-disclosure agreements (NDAs), all customer names have been sanitized to generic placeholders (e.g., *Customer 1*, *Customer 2*, *Customer 16*) while preserving exact financial metrics and underlying DAX logic.

---

## Executive Summary

This Power BI reporting solution provides full visibility into executive sales performance, customer profitability, driver/drainer operational variance, and promotional customer investments across global sales channels.

It enables Commercial Directors, Key Account Managers (KAMs), and Finance teams to monitor revenue against budget, evaluate unit volumes, track promotional spend efficiency, and isolate top revenue drivers vs. underperforming customer accounts.

---

## 📑 Report Architecture & Page Breakdown

The dashboard solution consists of **6 primary analytical pages**:

### 1. Sales Overview
* **Focus:** High-level executive KPI tracking, SKU performance, and channel share.
* **Core Metrics:**
  * **Total Sales:** £4.38M YTD Gross Revenue
  * **Units Sold:** 7,062,382 Total Volume
  * **Customer Investment:** £268.02K Total Promotional Spend
  * **Sales vs. Budget %:** -18.80% Variance
  * **Units vs. Budget %:** -12.18% Variance
  * **Investment vs. Budget %:** -53.27% Variance
* **Visuals:** Top 10 SKU Horizontal Bar Visual, Sales by Channel Treemap/Donut, Top 10 Account Volume Ranking (`Customer 1` to `Customer 76`), and Monthly Revenue Run-rate.

### 2. Drivers & Drainers By Revenue
* **Focus:** Variance analysis comparing actual sales performance against target budgets across key customer accounts.
* **Top 10 Revenue Drivers:** Identifies accounts outperforming budget targets (e.g., `Customer 3` generating +£52.4K variance over budget).
* **Top 10 Revenue Drainers:** Highlights underperforming accounts creating revenue gaps (e.g., `Customer 11` trailing budget targets by -£674.5K).

### 3. Channel & Product Performance Trends
* **Focus:** Multi-year trend analysis (2025 vs. 2026 YTD) comparing Gross Revenue, Budget Forecasts, and Prior Year (LY) metrics.
* **Visuals:** Combined Clustered Column & Line Visuals tracking monthly seasonality, unit throughput, and cumulative Sales YTD vs. Budget YTD growth curves.

### 4. SKU Distribution & Service Metrics
* **Focus:** Volume concentration by product code (`OPSALTED35`, `OPSESAME35`, `NOCON`) alongside supply chain service performance.
* **Service KPIs:**
  * **Lost Sales Impact (£):** Quantification of revenue lost due to out-of-stock events.
  * **OTIF Rate (%):** On-Time In-Full fulfillment percentage tracked across operational delivery weeks.

### 5. Performance & Volume Trends (MTD vs. YTD)
* **Focus:** Detailed breakdown comparing Month-To-Date (MTD) vs. Year-To-Date (YTD) performance across Gross Revenue, Unit Throughput, and Customer Investment budgets.

### 6. Customer Investment Report
* **Focus:** Financial auditing of trade spend, promotional retros, and customer account allowances.
* **Breakdown Categories:**
  * `5102 - Shopper Marketing - CI` (52.66% Share | £141.1K)
  * `5107 - Promotions / Meal Deal Retros` (18.76% Share | £50.3K)
  * `5101 - Listing Fees` (10.70% Share | £28.7K)
  * `5108 - Data & Retailer Analytics` (£12.3K)
  * `5109 - Other Customer Investment` (£18.7K)

---

## 🧮 Core Calculated Metrics & DAX Formulas

Below are the key DAX measures used to power the dashboard visuals:

| Metric Name | Description | DAX Formula Logic | Target Benchmark |
| :--- | :--- | :--- | :--- |
| **Total Sales (£)** | Gross sales revenue realized across all fulfilled orders. | `SUM(Sales[GrossAmount])` | £4.38M |
| **Sales vs. Budget %** | Percentage variance between actual revenue and target budget. | `DIVIDE([Total Sales] - [Budget Sales], [Budget Sales], 0)` | $\ge 0.0\%$ |
| **Units vs. Budget %** | Volume variance comparing actual units sold against budget targets. | `DIVIDE([Units Sold] - [Budget Units], [Budget Units], 0)` | $\ge 0.0\%$ |
| **Revenue Variance Driver** | Account-level dollar variance to isolate drivers vs. drainers. | `[Total Sales] - [Budget Sales]` | $> 0$ (Driver) |
| **Customer Investment %** | Trade spend efficiency ratio as a percentage of gross revenue. | `DIVIDE([Total Customer Investment], [Total Sales], 0)` | $\le 6.5\%$ |
| **Sales YTD (£)** | Cumulative Year-To-Date revenue using standard time intelligence. | `TOTALYTD([Total Sales], 'Date'[Date])` | Growth vs. LY |

---

## 🎛️ Dynamic Slicer & Filtering Controls

The report header incorporates a unified Power BI Slicer Pane:
* **Channel Slicer:** Filters data by sales channel (*Grocery*, *Foodservice & FTG*, *Travel*, *Wholesale & Vending*, *Ecommerce*, *High Street*).
* **Product Description Slicer:** Isolates performance down to individual product SKUs and packaging configurations.
* **Customer Slicer:** Granular dropdown filtering across all key retail and wholesale accounts.
* **Date Slider:** Dynamic date range selection (`01/01/2025` to `31/05/2026`).

---

## 🛠️ How to Deploy / View the Prototype

1. **Local Preview:** Open `index.html` in any browser to interact with the responsive Power BI canvas layout.
2. **GitHub Pages Deployment:** 
   * Commit `index.html` and `README.md` to your public GitHub repository.
   * Navigate to **Settings → Pages** and set the branch to `main`.
   * Access the live dashboard URL generated by GitHub.
