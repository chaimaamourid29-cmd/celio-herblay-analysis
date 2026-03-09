# Celio Herblay — Customer Loyalty Analysis 2025

**Author:** Chaimaa MOURID  
**Realisation:** 2026 | **Study case:** 2025  
**Tools:** MySQL · Power BI · GitHub

---

## Context

I work as a seller at Celio Herblay (Val d'Oise, France).  
From my daily experience at the cashier, I identified two recurring operational problems that cause silent revenue loss for the store:

1. **Expired coupons** — Customers accumulate €5 coupons through the loyalty program (€1 spent = 1 point, 150 points = €5 coupon). The coupon is visible on the cashier screen and is always applied when the customer visits. However, if the customer does not visit the store within the 2-month validity window, the coupon expires — and that visit never happens.

2. **Missed birthday discounts** — Every customer is entitled to a 20% discount on their most expensive item during their birthday month. Unlike coupons, this discount is **not visible on the main cashier screen** — it requires the seller to manually check the customer profile. As a result, sellers miss it most of the time.

This project quantifies the revenue impact of both problems using SQL analysis and Power BI visualization.

---

## Dataset

Simulated dataset based on realistic Célio pricing and customer behavior (Val d'Oise region).

| Table | Rows | Description |
|-------|------|-------------|
| customers | 100 | Loyalty card holders with points and coupon history |
| transactions | 593 | All purchases in 2025 with discount details |
| coupons | 267 | All coupons generated, used, expired or active |

**Realistic parameters:**
- Average annual spend per customer: €470
- Average basket per visit: €77.93
- Visits per year: 4 to 6
- Prices based on real Célio catalogue

---

## Key Findings

| Metric | Value |
|--------|-------|
| Total Revenue 2025 | €46,212 |
| Expired Coupons | 82 |
| Estimated Revenue Lost (Coupons) | €5,765 |
| Birthday Eligible Visits | 131 |
| Birthday Discounts Missed | 104 (79%) |
| Estimated Revenue Lost (Birthday) | €961 |
| **Total Estimated Loss** | **€6,726** |

---

## SQL Analysis

8 queries covering:
- Database overview
- Revenue overview (before and after discounts)
- Expired coupon analysis
- Estimated real revenue loss from expired coupons
- Birthday discount miss rate
- Coupon status breakdown
- Priority contact list (active coupons expiring soon)
- Customer segmentation (Active / At Risk / Sleeping)

→ See [`celio_analysis.sql`](celio_analysis.sql)

---

## Power BI Dashboard

The dashboard includes:
- 5 KPI cards (Total Revenue, Expired Coupons, Coupon Loss, Birthday Loss, Total Loss)
- Monthly Revenue trend (line chart)
- Coupon Status Breakdown (donut chart)
- Birthday Discount Performance (bar chart)
- Revenue by City (bar chart)
- Priority Contact List — customers with active coupons expiring soon (table)

---

## Business Recommendations

1. **SMS reminders** instead of email when a coupon is about to expire (higher open rate)
2. **Add birthday discount alert** to the main cashier screen — same visibility as coupons
3. **Verbal reminder** at the register when a customer has an expiring coupon
4. **Monthly action list** of customers with active coupons to proactively contact them

---

## Disclaimer

> The goal of this project is to learn and practice SQL analysis and Power BI. The dataset is entirely simulated — names, transactions, and figures are fictional and do not represent real Célio Herblay customers or actual store performance. It was generated to reflect realistic behavior based on real Célio pricing and French customer spending patterns, with the help of Claude AI (Anthropic) and my real experience as a seller.

---

## Files

| File | Description |
|------|-------------|
| `customers.csv` | Customer dataset |
| `transactions.csv` | Transactions dataset |
| `coupons.csv` | Coupons dataset |
| `celio_analysis.sql` | All SQL queries with results |
| `README.md` | This file |


| File | Description |
|------|-------------|
| `customers.csv` | Customer dataset |
| `transactions.csv` | Transactions dataset |
| `coupons.csv` | Coupons dataset |
| `celio_analysis.sql` | All SQL queries with results |
| `README.md` | This file |
