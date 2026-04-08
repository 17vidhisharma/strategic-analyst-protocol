<p align="center">
  <h1 align="center">Detecting Business Logic Failures in Financial Data</h1>
  <p align="center">
    Uncovering hidden losses and reporting failures using a structured analyst framework
  </p>
</p>

---

## Executive Summary

The Enterprise segment is structurally unprofitable, generating approximately **$777K in hidden losses** due to pricing below cost.

These losses are not reflected in reported profit, creating a false view of performance and leading to misinformed business decisions.

This project demonstrates how a structured analyst approach can move from raw data to **clear, decision-ready insights**.

---

## Problem

Most dashboards report performance.

Very few detect when the **business logic itself is broken**.

In this dataset:
- Costs exceed revenue in multiple transactions
- Profit is recorded as NULL instead of negative
- Losses are effectively invisible in reporting

---

## Approach

This analysis applies a structured **Analyst Decision Framework**:

1. Audit the dataset for inconsistencies  
2. Identify business logic failures (not just data errors)  
3. Quantify impact  
4. Translate findings into a business narrative (S → C → R)  
5. Recommend concrete actions  

Full framework: `analyst-skill-SKILL.md`

---

## Dataset

Source: Kaggle Financials Dataset  

- 700 transactions  
- 5 segments  
- 5 countries  
- Time period: 2013–2014  

Each row represents a transaction across segment, product, geography, and pricing structure.

---

## Key Insight

**Enterprise is the only segment destroying value — and current reporting hides it.**

- 58 out of 100 Enterprise transactions have **COGS > Sales**
- Total hidden loss: **$777,321**
- Profit is recorded as NULL instead of negative
- Standard reports show Enterprise as neutral

---

## Business Narrative (S → C → R)

**Situation**  
The business appears healthy overall, with $118.7M revenue and 14.2% margin.

**Complication**  
The Enterprise segment (16.5% of revenue) operates at a **-3.1% margin**, generating hidden losses not reflected in reporting.

**Resolution**  
This indicates a systemic pricing and reporting failure. Immediate action is required to correct profit logic and enforce pricing discipline.

---

## Data Processing

### Issues Found
- Profit column contains NULL values for loss-making rows  
- 58 transactions where **COGS > Sales**  
- Formatting inconsistencies in column names  

### Fix Applied
Corrected Profit = Sales − COGS

Loss-making rows were flagged instead of removed.

---

## Key Metrics

| Metric | Purpose |
|------|--------|
| Corrected Profit | Reveals true profitability |
| Profit Margin % | Enables segment comparison |
| Loss Flag | Identifies logic failures |
| Discount Impact | Measures pricing effect |
| Revenue Share % | Provides business context |

---

## Dashboard

The dashboard is designed for **fast executive understanding**.
  
<img width="1440" height="2474" alt="image" src="https://github.com/user-attachments/assets/a0ced3b7-d428-4563-a68a-2053fbe50da0" />


### Layout

- KPI row:
  - Total Revenue
  - Total COGS
  - Net Profit
  - Enterprise Margin (flagged)
  - Loss Row Count (flagged)

- Main chart:
  - Segment margin comparison (Enterprise highlighted)

- Supporting visuals:
  - Enterprise loss trend (2013 → 2014)
  - Revenue share by segment
  - COGS vs Sales comparison

View: `financials_enterprise_glitch_dashboard.html`

---

## Business Impact

- Hidden loss of **$777K** (~4.6% of total profit)
- Loss increased **117% year-over-year**
- Segment appears neutral but is structurally unprofitable

---

## Recommendations

**1. Pricing Audit (within 7 days)**  
Review Enterprise deals where discounts push price below cost  
→ Identify root cause of loss  

**2. Fix Profit Reporting**  
Replace NULL profit values with calculated profit  
→ Restore accurate financial visibility  

**3. Enforce Pricing Floor**  
Prevent deals below cost in CRM systems  
→ Stop future losses  

---

## Risk of Inaction

Enterprise losses are projected to reach **$900K–$1.1M annually**, while remaining hidden in standard reports.

This can lead to:
- incorrect strategic decisions  
- expansion of loss-making operations  
- long-term margin erosion  

---
[View Full Analysis Output](./analysis-output.md)
---
## Tools Used

- Power BI  
- Excel / CSV  
- Structured analytical framework  



---

## Final Principle

If the output does not help a business leader decide what to do next, the analysis is incomplete.
