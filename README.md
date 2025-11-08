# NISSAN HR ATTRITION ANALYTICS: Mitigating Turnover Risk and Improving Retention

![Image](https://github.com/user-attachments/assets/4bd3ffa1-21f4-4541-b886-07d8d9c1e6eb)
## 1. Project Background

A major automotive company (NISSAN) is facing challenges with talent retention, characterized by a significant **Attrition Rate (31%)** and high volume of employee exits. High turnover threatens institutional knowledge, disrupts operational continuity, and drives up recruitment and training costs.

This project delivers a comprehensive, multi-page analytical solution to diagnose the root causes of attrition, identify high-risk areas, and provide actionable recommendations to stabilize the workforce.

The analysis is structured around the following key areas:
* **Attrition Metrics & Trends:** Evaluation of the overall **Attrition Rate**, **Total Exits**, and **Average Tenure** trends over time.
* **Churn Attribution:** Analysis of the **Top Reasons for Exits** (e.g., Career Change, Retirement) and **Recruitment Source** effectiveness.
* **Risk Segmentation:** Identification of critical high-risk segments, including **early exits (≤ 2 years)**, **high-churn departments**, and **managers with the highest turnover**.
* **Post-COVID Impact:** Evaluation of how the pandemic period influenced employee tenure and departmental churn.


* **Interactive Dashboard (6 Pages):** The full HR Attrition Analytics dashboard can be accessed [here](LINK_TO_POWER_BI_DASHBOARD).
##  Data Structure & Initial Checks

#### Data Overview
The analysis was built on a focused **Star Schema** data model designed to efficiently link employee transactional events (exits) to time dimensions for trend analysis. The data was sourced from NISSAN's HR database.

#### Data Model (Star Schema)
The model consists of two connected tables:

* **`attrition sheet` (Fact Table):** Contains detailed employee exit records, including **Employee ID, Department, Date of Hire, Exit Reason, Education Level,** and **Performance Ratings**.
* **`DATE TABLE` (Dimension Table):** Contains hierarchical time attributes used for tracking the **Attrition Trend Over Time**, and analyzing **Early Exits** (e.g., tenure $\leq$ 2 years).

The tables are connected via a **One-to-Many relationship** between the `DATE TABLE` and the `attrition sheet` on the `Date of Hire` field.


![Image](https://github.com/user-attachments/assets/88c27bef-65df-4ed2-8b09-2de86e83752f)

####  Data Cleaning and Preparation
The data cleaning and preparation process was primarily executed using **Power Query (M Language)** to ensure data quality and integrity before analysis.

* **Fact Table Transformation:** Power Query was used to handle missing values, standardize text fields (e.g., Department names), and ensure the accuracy of the `Date of Hire` field.
* **Dimensional Table Creation:** A dedicated **`DATE TABLE`** was created and standardized to enable consistent time intelligence and trend analysis.
* **Key Metric Calculation (DAX):** Complex measures like **Attrition Rate (31%)**, **Avg Tenure of Leavers (5.31)**, **% Leavers Within First Two Years (16%)**, and the **Attrition Trend Over Time** were calculated using DAX (Data Analysis Expressions).
  ![Image](https://github.com/user-attachments/assets/f7a173bd-0610-4c91-9a7c-73ec471856de)

##  Executive Summary

NISSAN is facing a significant talent retention challenge, evidenced by a high **Attrition Rate of 31%** across 3,000 total exits, with an average tenure for leavers of only **5.31 years**. The core risk lies in **early exits**, as **16%** of leavers depart within the first two years, and the primary exit driver is **Retirement (22.59%)**. Immediate strategic action is required to stabilize early-career talent, reassess underperforming recruitment channels, and implement targeted retention programs in high-churn departments.


#### Overall Attrition Health & Exit Reasons

* **High Attrition Rate:** The overall **Attrition Rate stands at 31%**, representing 3,000 total employee exits.
* **Top Exit Drivers:** The leading reasons for exits are **Retirement (22.59%)**, **Work-Life Balance (20.61%)**, and **Career Change (19.48%)**.

![Image](https://github.com/user-attachments/assets/12eb7e5c-a3cd-4994-b8a3-e25cf48825c8)

#### Recruitment Source & Early Churn Risk

* **Early Exit Crisis:** A critical **16% of all leavers depart within their first two years** of employment, indicating fundamental failures in the onboarding or initial role fit process.
* **Underperforming Recruitment Sources:** Sources like **"Online Job Board"** show higher exit rates than trusted channels like **"Referral"** and **"LinkedIn."** Resources should be redirected to top-performing sources.

![Image](https://github.com/user-attachments/assets/89146540-3d50-4d33-b90a-28352969279c)


#### Manager and Departmental Risk

* **High-Risk Departments:** The analysis clearly identifies departments that suffer the highest concentration of attrition counts.
* **Managerial Impact:** Data identifies **Managers with the Most Employee Exits**, mandating focused leadership support and feedback reviews to address potential poor management practices.
* **Post-COVID Impact:** Departments like **Customer Service and Operations** suffered the most significant attrition impact after the COVID-19 period.

![Image](https://github.com/user-attachments/assets/27c92803-fe0e-4cfc-89a4-7bf2198f08d8)
![Image](https://github.com/user-attachments/assets/9fdb13a4-7f95-479b-ad83-6167c52597f9)
![Image](https://github.com/user-attachments/assets/0d1ab8ba-dd0e-45f6-988c-87da1a4adf7c)

## Business Recommendations

Based on the diagnosis of the 31% Attrition Rate, high concentration of early exits, and manager/departmental risks, the following five strategic actions are critical to stabilize the workforce and improve talent retention:

* **1. Strengthen Onboarding to Address Early Exits (16% Risk):** Implement a robust **90-day retention program** focused specifically on employees in their first two years, including mandatory mentorship and frequent check-ins.
* **2. Prioritize Retention in High-Churn Departments:** Focus training, recognition, and workload balance initiatives in high-churn departments and those hit hardest Post-COVID (Customer Service, Operations).
* **3. Audit and Restructure Recruitment Sources:** Immediately redirect recruitment efforts and budget away from low-retention sources like **"Online Job Board"** and toward high-performing channels such as **"Referral"** and **"LinkedIn."**
* **4. Implement Managerial Leadership Support:** Identify and enroll **Managers with the Most Employee Exits** in mandatory leadership support programs and formal feedback reviews.
* **5. Adjust Compensation and Work-Life Balance Strategy:** Conduct a competitive assessment of mid-range salaries and introduce flexible work options to mitigate issues related to **Retirement** and **Work-Life Balance**.

---

Thank you for reading! Leave a comment if you have any questions about the analysis.
