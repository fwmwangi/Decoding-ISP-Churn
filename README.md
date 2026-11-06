# 📉 Optimizing ISP Revenue: 360° Customer Churn & Network Analysis

**Author:** Francis Wairimu  
**Role:** Data Scientist & Sales Operations Strategist  
**Industry Focus:** Telecommunications & ISP Operations (Kenyan Market)  

---

## 🚀 Executive Summary
In the highly competitive Kenyan ISP market, customer acquisition is an expensive endeavor. Profitability relies entirely on **Customer Lifetime Value (CLV)** and retention. When customers churn, the business loses both recurring revenue and the initial Capital Expenditure (CapEx) spent on router installation and fiber deployment. 

This project moves beyond standard billing analysis to identify the **root causes of customer churn**. By analyzing payment methods, contract tenures, package types, and localized network outages, I built a data-driven retention pipeline designed to plug revenue leaks and optimize field operations.

---

## 🔍 The Identified Gap (The Root Cause)
Through data aggregation and Exploratory Data Analysis (EDA) using Python and SQL, the following operational gaps were identified:
1. **Infrastructure Failure vs. Price Sensitivity:** The highest churn rates were highly localized. The **Kiambu** and **Machakos** regions exhibited a churn rate of ~28.7%, which perfectly correlated with massive network outage rates (~50%) in those specific nodes. Customers aren't just leaving because of price; they are leaving because the network is failing them.
2. **Product Friction:** The premium '20Mbps FTTH' package suffers from a disproportionately high churn rate (41.8%) compared to the '5Mbps Hotspot' tier, indicating severe service degradation or bandwidth throttling during peak hours.
3. **Passive Churn:** Customers utilizing M-Pesa Paybill (manual push payments) showed the highest churn risk due to payment friction and forgotten renewals.

---

## 🛠️ Technical Stack & Methodology
* **Language/Libraries:** Python, Pandas, NumPy
* **Database:** SQLite3 (for production-level aggregations)
* **Visualization:** Seaborn, Matplotlib 
* **Workflow:** 
  1. **Data Localization:** Synthesized public IBM Telco data to reflect the Kenyan market (KES currency, M-Pesa integrations, coastal/upcountry regional mapping).
  2. **Data Cleaning:** Handled hidden NaN values and coerced string variables into correct numeric types.
  3. **SQL Integration:** Exported clean data to SQLite for robust business logic queries.
  4. **EDA Dashboarding:** Generated a 3x2 automated visualization dashboard tracking churn across 4 distinct business vectors.

*(Check out the `image/` folder for the generated 360° Business Dashboard)*

---

## 📈 Strategic Business Recommendations

As a Sales Operations strategist, acquiring a customer is only step one; maintaining them is the key to long-term business scaling. Here is the action plan to mitigate churn based on the data:

### ⚡ Short-Term & Immediate Actions
* **Targeted Node Maintenance:** Immediately dispatch field engineers to the Kiambu and Machakos regions. Halt new sales in these areas until the infrastructure uptime is stabilized to prevent burning through new leads.
* **Automated Downtime Credits:** Integrate the Mikrotik/Radius uptime APIs directly with the billing system (e.g., Centipid). If a customer experiences >3 hours of downtime, automatically push a 24-hour credit voucher via SMS. This preempts angry customer service calls and retaliation churn.
* **Proactive SMS Reminders:** Implement an automated bulk SMS integration (via Python) to send renewal reminders to M-Pesa Paybill users 48 hours before their current cycle expires.

### 🔭 Long-Term Strategy
* **Product Restructuring:** Audit the '20Mbps FTTH' product line. If the nodes cannot handle the bandwidth allocation during peak hours, restructure the package to a 'burst' speed model or cap sales to maintain quality of service.
* **Early Check-In Protocol:** The density data shows churn risk peaks in the first 5 months. Deploy an automated 'Early Onboarding' check-in call or WhatsApp survey at Month 3 to preemptively resolve hardware/router issues before the customer abandons the service.
* **Contract Incentives:** Offer targeted 10% discount campaigns to upgrade high-risk month-to-month M-Pesa users into secure 6-month or 1-year contracts.

### 🕵️‍♂️ Areas for Further Investigation
To completely eliminate churn, future data cycles should investigate:
1. **Competitor Mapping:** Are JTL Faiba or Safaricom running targeted localized promotions in Kiambu/Machakos that are exacerbating our outage-driven churn?
2. **Hardware Diagnostics:** Analyzing specific router MAC addresses to see if a certain batch of provided hardware is causing localized drop-offs.
3. **Support Ticket Sentiment:** Scraping customer service WhatsApp texts using NLP (Natural Language Processing) to determine exactly what customers are complaining about prior to disconnecting.

---

## 💻 How to Run This Project
1. Clone this repository to your local machine.
2. Ensure you have the `WA_Fn-UseC_-Telco-Customer-Churn.csv` dataset in the root directory.
3. Install required dependencies: `pip install pandas numpy matplotlib seaborn`
4. Run `isp_churn_analysis_final.ipynb` in Jupyter or VS Code to generate the localized SQLite database and the high-resolution visualization dashboard.

---
*Let's connect! I am passionate about translating messy data logs into streamlined sales operations and business strategy.*