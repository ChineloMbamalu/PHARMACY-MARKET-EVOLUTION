# PHARMACY-MARKET-EVOLUTION

<img width="1280" height="735" alt="image" src="https://github.com/user-attachments/assets/cdf6f9c5-5b51-422f-a36a-564865a604d9" />

**Project Overview**

This project analyses trends in the pharmacy industry, focusing on market growth and closures across pharmacy sizes. The objective was to understand how the number of pharmacies has evolved, identify patterns in openings and closures, and assess whether distance-selling (online) pharmacies are influencing traditional physical pharmacies.

Using Excel for data cleaning, PostgreSQL for data analysis, and Power BI for visualisation, the project explores key business questions such as:

a. Are pharmacy closures increasing or decreasing over time?

b. Which pharmacy size is most affected?

c. Which pharmacy size is showing the most growth?

d. Is the industry shifting toward digital (distance-selling) models?

**Data Source**

The dataset was sourced from the NHS Business Services Authority (NHSBSA) Open Data Portal.

Format: CSV

Content: The pharmacy opening and closures dataset shows the number of pharmacies in England that are included in the Pharmaceutical List held by NHS England on the last calendar day of each month.

Coverage: From 2021 onwards

Scope: Includes small, medium, and large pharmacies and distance-selling pharmacies

The dataset represents industry-level trends in pharmacy operations, providing insight into both physical and online pharmacy growth and decline.

**Data Preparation**

Before analysis, the dataset was cleaned in Excel and transformed to ensure accuracy and usability:

a. Converted the date format from DD/MM/YYYY to YYYY-MM-DD for compatibility with PostgreSQL

b. Changed numeric columns from general to proper number data types

c. Verified that there were no duplicate records

d. Created additional Year and Month columns using the =YEAR() and =MONTH() formulas to support time-based analysis

e. Ensured column consistency for accurate aggregation and querying

These steps improved data integrity and enabled efficient querying.

**Database Design**

The analysis was built using a single-table structure in PostgreSQL:

**Main Table: Pharmacy_Dataset**

It contains all raw data, including pharmacy counts, openings and closures, net changes, size categories (small, medium, and large) and distance-selling metrics. The data types include dates and integers.
 
**Data Modelling (Power BI):**

Although only one table was used in PostgreSQL, additional derived tables were created and modelled in Power BI to establish relationships:

a. Pharmacy yearly trends

b. Distance sellers' trends

c. Physical vs online pharmacy comparison

Relationships were created to:

a. Compare distance-selling vs physical pharmacy trends

b. Analyse yearly performance across datasets

**SQL Logic**

Several SQL queries were written to answer key business questions:

 

a. **Monthly & Yearly Trends**

Aggregated openings and closures across all pharmacy sizes

Identified fluctuations in market activity

Purpose: to understand seasonal and long-term trends


 

b. **Pharmacy Closure by Size**


Used **UNION ALL** to combine and compare closures across small, medium, and large pharmacies

Purpose: Determine which pharmacy size is most affected by closures

 

c. **Market Size & Net Change**

Calculated yearly totals using MAX(total_pharmacies)

Computed annual net change using aggregated net values

Purpose: Assess whether the market is growing or contracting


 

d. **Distance Sellers vs Physical Pharmacies**

Created separate tables for distance-selling trends and Physical pharmacy net change

Compared both using grouped yearly data

Purpose: Evaluate whether online pharmacies are replacing physical ones


 

e. **Growth Contribution by Pharmacy Size**

Summed net change by size category

Purpose: Identify which segment drives industry growth or decline


 

f. **KPI Queries**

Total online pharmacies: 24K

Total physical pharmacies: 634K

Total net change for physical pharmacies: -743

Total net change for online (distance sellers) pharmacies: 85

Purpose: Provide summary metrics for dashboard cards


 

Visualisation Decisions

The dashboard was built in Power BI using the following visuals:


a. Line Charts: used for yearly trends and net changes, which help show patterns over time clearly.

b. Bar Chart: used to show pharmacy closures by size, allowing easy comparison across categories.

c. Gauge Chart: used to track the total growth of small pharmacies and their net growth.

 

**KPI Cards (4)**

a. Total online pharmacies: the sum of all the distance sellers across all pharmacy sizes

b. Total physical pharmacies: the sum of all the physical pharmacies across all pharmacy sizes

c. Total Online net change: the sum of all the distance sellers' net change across all pharmacy sizes

d. Total Physical net change: the sum of all the physical pharmacies' net change across all pharmacy sizes

**Slicer (Year)**: for filtering and interaction


These visual choices ensure that trends, comparisons, and key metrics are easy to interpret at a glance.

 
**Insights & Findings**

Several important insights were derived from the analysis:

1. **Market Contraction**

The physical pharmacy market is declining over time, with closures exceeding openings. Although the rate of decline is slowing, the trend indicates a long-term contraction risk.

2. **Pharmacy Size Dynamics**

Small pharmacies show positive growth (+1,352), while medium (-365) and large (-1,730) pharmacies are declining. This suggests that smaller pharmacies may be more adaptable, possibly due to lower operating costs such as rent and labour.

3. **Digital Shift in Pharmacy Services**

Distance-selling (online) pharmacies show consistent growth, while physical pharmacies decline. This indicates a shift toward digital healthcare delivery models.

4. **Online vs Physical Gap**

Physical pharmacies recorded a net change of -743 compared to +85 for online pharmacies. This suggests that access to in-person healthcare services may be declining in favour of digital alternatives.


This highlights a growing reliance on digital access to medications, potentially impacting in-person healthcare access.

 
**Reflection**

This project provided valuable experience in data analysis and storytelling using SQL and Power BI.

 
**Key Learnings**

a. Writing SQL queries to extract meaningful insights

b. Structuring and transforming raw data for analysis

c. Designing dashboards that communicate clear business insights

 
**Challenges**

a. Interpreting complex columns such as net change and category breakdowns

b. Understanding relationships between multiple metrics within a single dataset

 
**What I Would Do Differently**

a. Create a data dictionary at the start to better understand each column
   
b. Explore additional metrics such as closure rates (proportions) rather than just totals

 
**References**

[Open Data Portal (ODP) | NHSBSA](https://www.nhsbsa.nhs.uk/access-our-data-products/open-data-portal-odp)

[Excel, SQL & Power BI Project for Data Analysts | Pharmacy Openings and Closures End-to-End Tutorial](https://www.youtube.com/watch?v=nsQ-U_gx1Wo&t=124s)
 
 
 
