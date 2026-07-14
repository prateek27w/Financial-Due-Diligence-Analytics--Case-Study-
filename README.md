# 📊 Stratton GmbH | Financial Due Diligence & Analytics Dashboard

> **End-to-End Power BI Case Study | Financial Analytics | Executive Reporting | Business Intelligence**

---

> **⚠️ Disclaimer**
>
> This project was developed as part of a real-world financial due diligence case study by radial consulting. It demonstrates an end-to-end Power BI implementation, including data transformation, dimensional modeling, DAX development, dashboard design, and executive-level business reporting.

---

# 📌 Project Overview

This project presents a complete **Financial Due Diligence Dashboard** developed in Power BI for **Stratton GmbH**, a medium-sized manufacturing and trading company operating in the **Skateboards** and **Skis** industry.

The solution was designed from a business consulting perspective, transforming raw transactional data into an executive-ready reporting solution that enables stakeholders to monitor revenue performance, identify high-performing product categories, and support strategic business decisions.

Unlike a traditional reporting dashboard, this solution emphasizes **analytical storytelling**, **business traceability**, and **decision-oriented insights**.

---

# 🏢 Company Overview

Stratton GmbH is a family-owned manufacturing and trading organization headquartered in **Munich, Germany**.

The company operates through multiple subsidiaries responsible for manufacturing and worldwide product distribution.

### Manufacturing Locations

- China
- Slovakia

### Distribution Companies

- Germany
- United States

Products are supplied through multiple sales channels including:

- Retail Stores
- Discount Chains
- Specialist Stores
- DIY Stores
- Direct Sales
- Online Commerce

Following the establishment of a new sales company in the United States, Stratton planned to raise additional investment to accelerate its growth strategy. As part of this initiative, a financial due diligence exercise was conducted to evaluate business performance and provide analytical insights for investors.

---

# 🎯 Business Problem

The management team required a scalable reporting solution capable of transforming multiple monthly datasets into a centralized analytical model.

The dashboard needed to answer key business questions such as:

- How has revenue evolved over time?
- Which product categories generate the highest revenue?
- Which periods demonstrate peak business performance?
- Which categories require management attention?
- How can stakeholders quickly understand overall business performance through executive reporting?

The final solution had to be transparent, interactive, and suitable for executive-level presentations. :contentReference[oaicite:1]{index=1}

---

# 🎯 Project Objectives

The primary objectives of this project were:

- Consolidate multiple monthly Excel files into a single analytical dataset.
- Perform structured data transformation using Power Query.
- Build a clean and scalable Star Schema data model.
- Develop reusable DAX measures for revenue analysis.
- Analyze financial performance across an 18-month reporting period.
- Design an executive-ready Power BI dashboard.
- Deliver business insights supported by transparent calculations.
- Present findings using a professional consulting-style reporting approach.

---

# 🛠 Tech Stack

| Category | Technology |
|----------|------------|
| Visualization | Power BI Desktop |
| ETL | Power Query (M) |
| Data Modeling | Star Schema |
| Calculations | DAX |
| Source Files | Microsoft Excel |
| Reporting | Interactive Dashboard |
| Domain | Financial Due Diligence |

# 📂 Dataset Overview

The dataset represents approximately **18 months of financial sales transactions**, covering the period from **January 2022 to June 2023**.

Instead of providing a single consolidated file, the source data was distributed across multiple monthly Excel files. This required a structured ETL process to combine, standardize, and prepare the data before any analytical modeling could begin.

The final analytical dataset contains information related to product categories, pricing, sales quantities, and revenue generation.

### Dataset Includes

- Product Category
- Month & Year (Extracted from individual file name, e g : SalesData_Jan2022)
- Units Sold
- Selling Price
- Purchase Price
- Margin

---

# 🔄 Data Preparation (Power Query)

A structured ETL process was implemented inside **Power Query** to prepare the dataset for reporting.

The following transformation steps were performed:

### ✅ Data Import

- Imported multiple monthly Excel files
- Combined all files into a unified dataset
- Standardized column structure across all months

---

### ✅ Data Cleaning

- Verified data types
- Renamed columns for consistency
- Removed redundant fields
- Checked for missing values
- Standardized category names

---

### ✅ Locale Handling

During development, an important data quality challenge was identified.

The source files followed **German regional formatting**, where:

- CSV files were **semicolon-separated ( ; )**
- Decimal values were represented using **comma ( , )** instead of a period ( . )

To ensure accurate numerical calculations, locale-specific parsing was applied during data import.

This validation step ensured that revenue-related calculations behaved correctly throughout the analytical model.

---

### ✅ Data Validation

Before building the semantic model, the dataset was validated to ensure:

- Correct data types
- Relationship readiness
- Revenue consistency
- Duplicate handling
- Category integrity

---

# 🏗 Data Modeling

A dimensional data model was designed following **Star Schema** principles.

The objective was to separate transactional data from descriptive attributes, resulting in a cleaner and more scalable analytical model.

---

## Fact Table

### SalesData_Combined

The central transactional table containing monthly sales information (obtained after combining multiple sales monthly tables using ETL).

Major attributes include:

- Month
- Product Category
- Units Sold
- Selling Price
- Purchase Price
- Margin

---

## Dimension Tables

### 📅 dim_date

A dedicated Date Dimension was created to support Time Intelligence calculations and reporting flexibility.

The table includes:

- Date
- Year
- Quarter
- Month Number
- Month Name
- Month-Year
- Year-Quarter
- Year-Month

The Date Dimension enables accurate monthly trend analysis, previous month comparisons, and scalable reporting.

---

### 📦 dim_category

A separate Category Dimension was created to eliminate redundancy and improve model normalization.

Benefits include:

- Cleaner relationships
- Reduced repetition
- Better filtering performance
- Improved maintainability

---

# ⭐ Star Schema

The final model follows a **Star Schema** architecture.

```text
                 dim_date
                     │
                     │
                     │
dim_category ───── SalesData_Combined
```

This modeling approach provides:

- Better performance
- Simpler DAX calculations
- Easier maintenance
- Improved scalability
- Cleaner filter propagation

---

# 🗂 Relationship Design

| From | To | Relationship |
|-------|----|--------------|
| dim_date[Date] | SalesData_Combined[Month_Year] | One-to-Many |
| dim_category[Category] | SalesData_Combined[Category] | One-to-Many |

Both relationships use **single-direction filtering**, following Power BI modeling best practices.

---

# 📐 DAX Measures

Several reusable DAX measures were created to support executive reporting and business analysis.

| Measure | Business Purpose |
|----------|------------------|
| Total Revenue | Calculates total revenue generated from product sales |
| Total Units Sold | Measures total quantity sold across all categories |
| Total Cost | Calculates total cost incurred based on product purchase price and quantity sold |
| Total Profit | Calculates total profit generated after deducting product cost from total revenue |
| Gross Margin | Aggregates margin values evaluating product contribution identifying areas generating +ve or -ve financial impact |
| Average Selling Price | Tracks average selling price over time |
| Previous Month Revenue | Enables month-over-month comparison |
| Revenue Growth % | Measures revenue growth against the previous month |
| Highest Revenue Category | Identifies the top-performing product category |
| Lowest Revenue Category | Identifies the lowest-performing product category |
| Peak Revenue Month | Determines the month with the highest revenue |
| Lowest Revenue Month | Determines the month with the lowest revenue |

---

# ⚙ Technical Highlights

Throughout the implementation, several Power BI best practices were followed:

- Star Schema data modeling
- Dedicated Date Dimension
- Dimension-based filtering
- Time Intelligence functions
- Dynamic KPI cards with YoY change percentage
- Dynamic Tool-tip
- Dedicated Filter Pane with interactive slicers
- Advanced DAX formulas
- Bookmark feature and navigator implementation
- Field Parameters for dynamic switch
- Show Applied Filters in real-time
- Executive-friendly dashboard design
- Consistent visual hierarchy and elements

---

# 🧠 Data Validation & Assumptions

A detailed validation of the source data was performed before finalizing the dashboard.

During analysis, it was observed that certain fields (such as Margin and Purchase Price) required careful interpretation due to regional formatting differences. To maintain analytical transparency, the executive reporting focused on revenue-based KPIs that could be consistently validated through the underlying transactional data.

This approach ensured that all reported insights remained traceable, explainable, and aligned with the available source data.

# 📊 Dashboard Walkthrough

The Power BI solution has been designed using a **three-page navigation structure**, allowing stakeholders to move from a high-level business overview to detailed revenue analysis and finally to executive-level insights.

Each page has been designed with a specific business objective while maintaining a consistent visual theme inspired by enterprise financial reporting.

---

# 🏠 Page 1 — Home

> 📸 **![image alt](https://github.com/prateek27w/Financial-Due-Diligence-Analytics--Case-Study-/blob/main/Radial_Home.png)**

The Home page acts as the landing page of the report and provides a clean navigation experience for business users.

### Key Features

- Executive landing page
- Interactive navigation buttons
- Consistent branding and theme
- Quick access to analytical pages
- Modern dashboard layout

### Business Purpose

Rather than exposing end users directly to analytical reports, the Home page provides a structured entry point similar to enterprise Power BI applications.

This improves usability and creates a professional reporting experience.

---

# 📈 Page 2 — Finance Performance Dashboard

> 📸 **[Insert Finance Dashboard Screenshot Here]**

This page focuses on monitoring revenue performance over time and provides interactive KPIs for management.

The dashboard enables decision-makers to evaluate revenue trends, category performance, and monthly business development through a single analytical view.

---

## Executive KPIs

The dashboard highlights the most important revenue-related metrics.

### KPIs Included

- Total Revenue
- Total Units Sold
- Total Cost
- Total Profit
- Gross Margin
- Average Selling Price
- Percentage Change (Vs Previous Year)

These KPIs provide an immediate overview of business performance before users begin detailed analysis.

---

## Performance Overtime Trend Analysis vs Previous Month

A monthly trend chart has been implemented to monitor important business metrics across the reporting period.

Business users can quickly identify:

- Growth trends
- Seasonal fluctuations
- Performance decline
- Previous Month comparison

---

## Category Performance

Metrics has been analyzed across all product categories to identify:

- Highest contributing categories
- Lowest contributing categories
- Category-wise performance distribution

This visualization helps management understand where the business generates the majority of its revenue.

---

## Detailed Revenue Matrix

A detailed matrix has been provided to support operational reporting.

The matrix allows users to analyze:

- Revenue
- Units Sold
- Total Cost
- Total Profit
- Gross Margin
- Average Selling Price

across individual product categories.

---

## Interactive Filtering

The dashboard includes interactive slicers for:

- Year
- Month
- Product Category

These filters allow stakeholders to dynamically explore revenue performance without modifying the report.

---

# 💡 Page 3 — Business Insights & Recommendations

> 📸 **[Insert Executive Insights Screenshot Here]**

The final page has been designed specifically for executive stakeholders.

Instead of presenting large numbers of charts, this page summarizes the most important analytical findings and converts them into actionable business insights.

The objective is to help decision-makers understand the current business situation within a few seconds.

---

## Executive Insight Cards

The dashboard dynamically identifies:

🏆 Highest Revenue Category

📉 Lowest Revenue Category

📈 Peak Revenue Month

📅 Lowest Revenue Month

These insights are calculated directly from the analytical model using DAX measures.

---

## Metrics Decomposition Tree

A Decomposition Tree has been implemented to support interactive root-cause analysis.

Business users can explore revenue by drilling through multiple business dimensions, allowing them to identify the major contributors to overall performance.

This feature enhances analytical transparency and supports management decision-making.

---

## Business Insights

The dashboard summarizes key analytical observations derived from the available revenue data.

Instead of requiring users to interpret multiple visuals, the most important findings are presented directly within the report.

---

## Business Recommendations

Based on the observed trends, practical business recommendations have been included to support future decision-making.

These recommendations convert analytical findings into actionable strategies for management.

---

# 📈 Business Insights

The dashboard transformed raw transactional data into meaningful business intelligence by identifying metric trends, category performance, and executive-level insights.

Below are the major findings derived from the analytical model.

---

## 🏆 Highest Revenue Generating Category

The analysis revealed that **Ski Salomon & Accessories** generated the highest overall revenue during the reporting period.

This indicates that the category plays a significant role in the company's overall sales performance and should continue to receive strategic attention.

---

## 📉 Lowest Revenue Generating Category

The **Ski Fischer & Accessories** category recorded the lowest revenue contribution.

This may indicate:

- Lower customer demand
- Product positioning challenges
- Pricing concerns
- Limited market penetration

Further business investigation would be required before taking corrective actions.

---

## 📅 Peak Revenue Period

Revenue reached its highest level during **May 2022**.

Possible business explanations include:

- Seasonal demand
- Promotional campaigns
- Product launches
- Higher customer purchases

Understanding the drivers behind this peak can help replicate similar business performance in future periods.

---

## 📉 Lowest Revenue Period

The analysis identified **November 2022** as the weakest revenue month within the available reporting period.

Potential contributing factors may include:

- Seasonal slowdown
- Reduced customer demand
- Inventory limitations
- Lower promotional activity

This period should be investigated further using operational and sales data.

---

## 📊 Revenue Distribution

Revenue is not evenly distributed across product categories.

A relatively small number of categories contribute a significant portion of total revenue, indicating opportunities for focused investment while also highlighting categories that may require performance improvement.

---

## 📈 Revenue Trend Analysis

Monthly revenue analysis demonstrates noticeable fluctuations throughout the reporting period.

Continuous monitoring of these trends enables management to:

- Detect declining performance early
- Measure business growth
- Compare historical performance
- Evaluate strategic initiatives

---

# 💼 Business Recommendations

Based on the analytical findings, the following recommendations are proposed.

---

## 1️⃣ Focus on High-Performing Categories

Increase marketing investment, inventory planning, and promotional efforts for the highest-performing product categories to maximize revenue growth.

---

## 2️⃣ Review Low-Performing Categories

Conduct detailed business analysis on underperforming categories to understand whether pricing, demand, distribution, or product positioning requires improvement.

---

## 3️⃣ Analyze Peak Revenue Drivers

Investigate the business activities that contributed to the exceptional revenue observed during peak months.

If repeatable, these strategies can become part of future business planning.

---

## 4️⃣ Improve Monthly Performance Monitoring

Implement regular executive reviews using Power BI to monitor month-over-month revenue performance and quickly identify emerging business trends.

---

## 5️⃣ Expand Executive Reporting

Extend the current dashboard by integrating profitability, inventory, customer, and regional analytics to support broader strategic decision-making.

---

# ⚠ Assumptions & Limitations

Every analytical solution depends on the quality of the underlying data.

During development, the following observations were made.

---

## Data Validation

Revenue calculations were successfully validated using the available transactional information.

---

## Regional Data Formatting

The source files followed **German regional formatting**, including semicolon-separated CSV files and comma-based decimal notation.

Appropriate locale handling was required during data preparation to ensure accurate numerical interpretation.

---

## Financial Measures

The provided Margin and Purchase Price fields required careful interpretation during analysis.

To maintain transparency and analytical reliability, the final executive reporting focused on validated revenue-based KPIs that could be consistently traced back to the underlying transactional data.

---

## Scope

This project focuses specifically on **Performance Analysis** and **Executive Reporting**.

Additional financial metrics such as Cost, Total Profit, EBITDA, or Operating Margin were intentionally excluded due to the available source data structure and validation considerations.

---

# 📚 Key Learnings

This project provided valuable practical experience beyond dashboard development.

Major learnings include:

- Importance of data profiling before visualization
- Validating regional data formats during ETL
- Designing scalable Star Schema models
- Developing reusable DAX measures
- Creating executive-friendly dashboards
- Converting analytical findings into business recommendations
- Building reports that prioritize clarity, transparency, and decision-making

The project also reinforced the importance of understanding business context before developing technical solutions.

---

# 🚀 Future Enhancements

The current implementation focuses on executive revenue reporting.

Potential future enhancements include:

- Row-Level Security (RLS)
- Incremental Refresh
- Forecasting
- Dynamic Tooltips
- Drill-through Reports
- Mobile Layout Optimization
- Power BI Service Deployment
- Scheduled Refresh
- Alerting & Subscriptions
- Customer & Regional Analysis

---

# 🏅 Skills Utilized

### Business Intelligence

- Financial Due Diligence
- Executive Reporting
- Business Analysis
- KPI Development

### Power BI

- Power Query
- Data Transformation
- Data Modeling
- Star Schema
- DAX
- Time Intelligence
- Interactive Dashboards

### Data Analytics

- Data Cleaning
- Data Validation
- Revenue Analysis
- Trend Analysis
- Business Storytelling
- Decision Support

---

# 🤝 Connect With Me

**Prateek Verma**

💼 LinkedIn

> *https://linkedin.com/in/prateek27w*

📂 GitHub

> *https://github.com/prateek27w*

📧 Email

> *prateek27w@gmail.com*

---

## ⭐ If you found this project interesting, feel free to connect with me or share your feedback.

Thank you for visiting this repository!
