# Customer-Intelligence-Retention-Analysis-Dashboard
                                           1. Project Overview
  The Customer Intelligence and Retention Dashboard is an integrated analytics solution designed to provide a comprehensive understanding of customer behavior, engagement patterns, revenue contribution, and retention performance.
   The project uses Microsoft Power BI for data transformation, modeling, and visualization to build interactive dashboards that support data‑driven decision making. By combining multiple datasets including Customer Master, Transactions, Engagement, Subscription, and Support, the solution provides a holistic view of the customer lifecycle.
   The final solution contains six interactive dashboard pages that allow stakeholders to explore customer analytics from different perspectives including customer overview, segmentation, engagement analysis, churn insights, and revenue performance
   
                                           2. Project Objectives

   The main objective of this project is to design a data analytics solution that helps organizations understand their customers and improve retention strategies.
Key objectives:
 1. Understand customer demographics and behavioral patterns.
 2. Identify high‑value and low‑value customers.
 3. Analyze customer engagement activity.
 4. Monitor customer churn and retention indicators.
 5. Evaluate revenue contribution across customers
    
Scope of Work

The project involves building an end‑to‑end Power BI analytics solution that includes:
1. Data preparation and transformation using Power Query
2. Data modeling using a star schema architecture
3. Creation of analytical metrics using DAX
4. Development of interactive dashboards
5. Implementation of filters, slicers, and navigation for user interaction
The final solution includes the following dashboards
 Index page.
 Customer Overview.
 Customer Segmentation.
 Engagement Analysis.
 Churn and Retention Insights.
 Revenue and Performance Analysis.
 
                                            3. Data source and Architecture

   The project integrates multiple datasets representing different aspects of customer data.
Customer Master – Contains demographic information about customers such as Customer ID, age, gender, region, and join date.
Transactions – Stores transaction details including transaction ID, customer ID, transaction date, and purchase amount.
Engagement – Tracks customer interaction data including login counts, session duration, and last activity date.
Subscription – Contains subscription details including subscription type, start date, renewal date, and subscription status.
Support – Records customer support interactions including ticket ID, issue type, resolution time, and ticket status.
Data Architecture follows a Star Schema where Customer Master acts as the central dimension table and other tables function as fact tables connected through Customer ID.

                                             4. Implementation Steps 

Step 1 – Data Import
 1. Import CSV datasets into Power BI Desktop
 2. Validate column structures and formats
 3. Load datasets into Power Query Editor
Step 2 – Data Cleaning (Power Query)
 1. Remove duplicate records
 2. Handle missing values
 3. Correct column data types
 4. Standardize column names
 5. Fix date formatting issues such as RenewalDate
Step 3 – Date Table Creation
 A separate Date Table was created to support time‑based analysis. The table contains fields such as Date, Year, Quarter, Month, and Month Name. This table enables time intelligence calculations and trend analysis across dashboards.

                                             5. Data Modelling
   
Relationships
1. CustomerMaster[CustomerID] → Transactions[CustomerID]
2. CustomerMaster[CustomerID] → Engagement[CustomerID]
3. CustomerMaster[CustomerID] → Subscription[CustomerID]
4. CustomerMaster[CustomerID] → Support[CustomerID]
Relationship Type: One‑to‑Man
Model Design Principles
 • Star schema architecture
 • Clear separation between dimension and fact tables
 • Use of a centralized date table
 • Avoidance of unnecessary many‑to‑many relationships
 • Optimization for performance and scalability

                                            6. DAX Measures Reference

Customer KPIs
 Total Customers→Total Customers = DISTINCTCOUNT('Customer_Master '[CustomerID])2.     
ActiveCustomers=CALCULATE(DISTINCTCOUNT('Engagement'[CustomerID]),NOT(ISBLANK('Engagement '[LastActivityDate])))
 New Customers = CALCULATE(DISTINCTCOUNT('Customer_Master 1'[CustomerID]), FILTER('Customer_Master 1','Customer_Master 1'[SignupDate] >=MIN(Datetable[Date])))
Revenue KPIs
Total Revenue = SUM('Transactions 1'[Amount])
Churn and Retention Metrics
 Churned Customers= CALCULATE(COUNTROWS('Subscription 1'),'Subscription 1'[Status] = "Churned")
Churn Rate= DIVIDE([Churned Customers], [Total Customers])
Engagement and RFM Metrics
Session Duration=AVERAGE('Engagement 1'[SessionDuration])

                                          7. Dashboard Pages Summary

Index Page – Navigation hub providing access to all dashboards.
Customer Overview – Displays total customers, revenue, demographics, and distribution.
Customer Segmentation – Categorizes customers into value segments based on revenue and behavior.
Engagement Analysis – Shows login trends, activity patterns, and active users.
Churn and Retention Insights – Analyzes churn trends and subscription status.
Revenue and Performance Analysis – Highlights revenue contribution by customers and segments.
Design Principles
 • Clean layout
 • Consistent color palette
 • Clear KPI cards
 • Logical visual grouping
 • Easy navigation
 
                                           8. Filters and Interactivity
   
Filters
 • Region filter
 • Customer segment filter
 • Subscription type filter
 • Date slicer
Interactivity Features
 • Slicers for dynamic filtering
 • Cross‑filtering between visuals
 • Drill‑down functionality in charts
 • Navigation buttons between pages
 
                                            9. Conclusion

The Customer Intelligence and Retention Dashboard provides a powerful analytical solution for understanding customer behavior and improving business performance

                                            10.Screenshots of Dashboard
      
<img width="472" height="266" alt="image" src="https://github.com/user-attachments/assets/3dcf7bd8-baa1-4527-bcee-e0c2a35d215f" />
<img width="480" height="270" alt="image" src="https://github.com/user-attachments/assets/f793bc90-f9c5-40bb-80fe-0947830ee04f" />








