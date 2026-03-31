# AI Revenue Root Cause Analysis System

## Overview
This project is an automated analytics system that detects revenue drops and explains the root cause using AI.

Instead of relying on dashboards, the system proactively identifies anomalies, analyzes contributing segments, and delivers structured insights through automated alerts.

---

## Problem
Most analytics workflows depend on dashboards that require manual monitoring.

This leads to delays in identifying critical issues such as revenue drops, and even longer delays in understanding the underlying cause.

The goal of this project is to reduce the time from:
**“What happened?” → “Why did it happen?” → “What should we do next?”**

---

## Solution
This system automates the entire process:

- Monitors daily revenue from Snowflake  
- Detects significant deviations from a rolling 7-day average  
- Analyzes impact by customer segment  
- Uses AI to generate business-ready explanations  
- Sends a structured alert with insights  

---

## Workflow

<img width="1879" height="888" alt="08CDDC83-5859-4FF1-8D81-C75766872A32" src="https://github.com/user-attachments/assets/e449c564-61b6-45b8-a101-52b15dd4d583" />

---
## Workflow Explanation

This project is designed as an end-to-end automated analytics workflow that transforms raw revenue data into actionable insights without manual intervention.

The workflow consists of the following steps:

### 1. Data Extraction (Snowflake)
The system queries Snowflake to retrieve daily revenue data. It calculates:
- Latest day’s revenue  
- Rolling 7-day average revenue  

This establishes the baseline for comparison.

---

### 2. Anomaly Detection
The workflow compares today’s revenue against the 7-day average.

If the decline exceeds a defined threshold (e.g., 30%), the system flags it as a significant anomaly and triggers further analysis.

---

### 3. Segment-Level Analysis
To identify the root cause, the system breaks down revenue by customer segment (e.g., SMB, Mid-Market, Enterprise).

It compares:
- Current revenue by segment  
- Historical baseline for each segment  

This helps determine which segments contributed most to the decline.

---

### 4. AI-Based Explanation
The structured output from the analysis is passed to an AI model.

The model generates:
- A concise headline  
- A detailed explanation of the issue  
- Key observations on segment impact  

This step converts raw data into a business-friendly narrative.

---

### 5. Alert Formatting
The system combines:
- Key metrics (revenue, averages, percentage change)  
- AI-generated insights  

It formats the output into a clean, executive-style message.

---

### 6. Automated Delivery
The final alert is sent via email.

This ensures that stakeholders are notified immediately with both the issue and its root cause, without needing to access dashboards or run queries.

---

### Summary

The workflow transforms the analytics process into:

**Data → Detection → Diagnosis → Explanation → Action**

This approach shifts analytics from passive reporting to proactive decision support.

##  Output

<img width="542" height="590" alt="Screenshot 2026-03-29 at 7 16 24 PM" src="https://github.com/user-attachments/assets/a3f08a13-6bd2-4501-a98c-f55c7ac2f241" />

The system detected a ~63% drop in revenue and identified that:

- The decline was driven by Mid-Market and Enterprise segments  
- SMB remained stable  
- The issue was concentrated in higher-value segments  

This enables faster investigation and decision-making.

---

## Tech Stack
- Snowflake (Data Warehouse)
- SQL (Data Analysis)
- n8n (Workflow Automation)
- OpenAI (AI-based explanation)

---

## How to Run

1. Load sample data into Snowflake (or use your own dataset)  
2. Run SQL queries to generate revenue metrics and segment analysis  
3. Import the n8n workflow (`workflow.json`)  
4. Configure your OpenAI API key  
5. Trigger the workflow  

---

## Key Takeaways

- Moves beyond dashboards to proactive insight generation  
- Combines analytics, automation, and AI in a single system  
- Reduces manual effort in identifying and explaining business issues  

---

## Future Improvements

- Add statistical anomaly detection (z-score / forecasting)  
- Introduce confidence scoring for AI explanations  
- Integrate Slack or real-time alerting systems  

---

## Author
Vaishnav Mulay

---


