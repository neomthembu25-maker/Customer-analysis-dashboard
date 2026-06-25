☕ Coffee Shop Customer Analysis Dashboard

📊 Project Overview
This project analyzes customer behavior for a coffee shop using Microsoft Excel. I built an interactive dashboard to identify customer segments, track spending patterns, and provide actionable insights to improve customer retention and revenue.

🎯 Business Problem
The coffee shop needed to understand:
•	Who are their most valuable customers?
•	Why are customers leaving?
•	How can they improve retention and increase revenue?
•	Which products drive the most value?

🔑 Key Questions Answered
•	Who are our most valuable customers (VIPs)?
•	Which customers are at risk of leaving?
•	What products do different customer segments prefer?
•	How can we improve customer retention?
•	What is the revenue contribution by product and segment?
Tool	Purpose
Microsoft Excel:	Data cleaning, analysis, and dashboard creation
Power Query:	Data transformation and preparation
PivotTables:	Data summarization and segmentation
Power Pivot:	Data modeling and relationships
DAX Formulas:	Custom calculations and KPIs
Slicers & Timeline:	Interactive filtering
Conditional Formatting:	Visual highlighting of key metrics
________________________________________
🛠️ Tools & Technologies
________________________________________
📊 Dashboard Features


🔢 Key Performance Indicators (KPIs)
•	Total Customers: 1,316
•	Total Revenue: R41,995.69
•	Average Spend/Visit: R31.91
📈 Interactive Charts
1.	Customer Segment Distribution - Bar chart showing segment sizes
2.	Revenue by Segment - Breakdown of revenue contribution
3.	Product Performance - Revenue and volume by product
4.	Segment Composition - Customer distribution by segment
5.	Customer Lifetime Value - Spend patterns by segment
🎛️ Interactive Filters
•	Segment Slicer: Filter by customer segment
•	Product Slicer: Filter by favorite product
•	Priority Slicer: Filter by customer priority
•	Timeline: Filter by date range
________________________________________
👥 Customer Segmentation
Segment Definitions
Segment	Description	Criteria	Customers	% of Total
VIP	Top customers by spend and frequency	Top 1% by spend, 20+ visits	18	1.4%
Loyal	Regular customers with high engagement	10+ visits, consistent spend	26	2.0%
Regular	Consistent but moderate spenders	5-9 visits, moderate spend	60	4.6%
Recent	New or returning customers	First purchase within 30 days	76	5.8%
Occasional	Infrequent purchasers	1-4 visits, irregular	147	11.2%
At Risk	Haven't purchased in 90+ days	No purchase in 90+ days	989	75.1%
Segment Insights
🔴 Critical Finding: 75% of Customers Are "At Risk"
•	989 customers haven't purchased in 90+ days
•	Represents R16,400+ in potential lost revenue
•	Recommendation: Launch re-engagement campaign with targeted offers
🟢 High-Value Segments
•	VIPs (1.4%) spend 2x more than average customers
•	Loyal customers account for 10.5% of all visits
•	Recommendation: Implement loyalty program with exclusive benefits
________________________________________
📈 Key Insights
1. Customer Retention is the Biggest Opportunity
 
2. Revenue Distribution by Product
Product	Revenue (ZAR)	% of Total
Latte	R28,358.00	25.3%
Americano with Milk	R25,365.92	22.6%
Americano	R19,997.04	17.8%
Cappuccino	R14,573.38	13.0%
Hot Chocolate	R8,431.50	7.5%
Cortado	R7,276.22	6.5%
Cocoa	R6,139.42	5.5%
Espresso	R2,104.10	1.9%
Top Performers:
•	Latte and Americano with Milk together generate 47.9% of total revenue
•	These two products are the undisputed "cash cows" of the business
Underperformers:
•	Espresso accounts for only 1.9% of revenue
•	Consider promoting espresso-based drinks or bundling them
3. Monthly Trends (2024-2025)
•	Peak Months: September (R9,600), October (R9,058), August (R8,264)
•	Lowest Months: April (R7,670), March (R6,364)
•	Strong Growth: February 2025 showed highest monthly revenue (R18,253)
•	Seasonal Pattern: Q3 and Q4 show consistently higher revenue
4. Segment Product Preferences
Segment	Top Products	Key Insight
At Risk	Latte, Americano with Milk	Broad product mix - no clear favorite
Loyal	Cortado (119 visits), Latte	Strong Cortado loyalty (32% of visits)
VIP	Americano (198 visits), Latte	Americana preference (47% of visits)
Regular	Latte, Americano with Milk	Balanced preferences
Recent	Latte, Americano with Milk	Similar to new customer preferences
5. Customer Lifetime Value by Segment
Segment	Avg Visits/Customer	Avg Spend/Visit	Segment Value
VIP	23.5	R31.51	High
Loyal	14.3	R31.73	High
Regular	8.2	R31.85	Medium
Recent	1.4	R31.47	Low
Occasional	6.1	R32.47	Medium
At Risk	1.2	R31.88	Low
________________________________________
🔍 Data Preparation
Raw Data
•	Source: https://www.kaggle.com/datasets/ihelon/coffee-sales
•	Rows: 1,700+ transactions
•	Columns: Date, Customer ID, Product, Amount, Payment Type
•	Currency: South African Rands (ZAR)
Cleaning Process
1.	Removed Duplicates: Ensured unique customer records
2.	Handled Missing Values: Separated cash (anonymous) from card customers
3.	Created Customer Portfolio: Aggregated transactions by customer
4.	Calculated Metrics: Total Spent, Avg Spend/Visit, Recency, etc.
5.	Segment Classification: Created segments using business rules
Key Formulas Used
excel
// Customer Portfolio Formulas
=SUMIFS(Data!E:E, Data!D:D, A2)                           // Total Spent per Customer
=MINIFS(Data!B:B, Data!D:D, A2)                           // First Purchase Date
=MAXIFS(Data!B:B, Data!D:D, A2)                           // Last Purchase Date
=COUNTIFS(Data!D:D, A2)                                   // Total Visits
=MAX(Data!B:B) - C2                                       // Recency (Days)
=D2/E2                                                    // Avg Spend/Visit

// Customer Segmentation (Array Formula)
=IF(AND(TotalVisits>=20, AvgSpend>=35, Recency<=30), "VIP",
   IF(AND(TotalVisits>=10, AvgSpend>=30, Recency<=60), "Loyal",
   IF(AND(TotalVisits>=5, AvgSpend>=25, Recency<=90), "Regular",
   IF(Recency<=30, "Recent",
   IF(TotalVisits>=2, "Occasional", "At Risk")))))
________________________________________
📸 Dashboard Preview
  
________________________________________
🚀 How to Use This Dashboard
Step 1: Download the File
1.	Navigate to the Dashboard/ folder
2.	Download Coffee_Shop_Customer_Dashboard.xlsx
Step 2: Open in Excel
•	Required: Microsoft Excel 2016 or later
•	Enable Content: Click "Enable Editing" and "Enable Content" for Slicers
Step 3: Explore the Dashboard
1.	Use Slicers to filter by Segment, Product, or Priority
2.	Use Timeline to view specific date ranges
3.	Click on any chart to drill down into specific segments
4.	Review KPIs at the top for quick insights
Step 4: Export and Share
1.	Export as PDF: File → Export → Create PDF
2.	Share link: Send GitHub repository link to stakeholders
________________________________________
💡 Recommendations
1. Immediate Actions (Next 30 Days)
Priority	Action	Expected Impact	ROI
🔴 High	Launch re-engagement campaign for "At Risk" customers	Recover 5-10% of at-risk customers	R1,600 - R3,200
🔴 High	Implement loyalty program for VIP and Loyal segments	Increase retention by 15%	R6,300
🟡 Medium	Feature Latte and Americano with Milk in promotions	Boost top revenue products by 10%	R5,300
🟢 Low	Create seasonal promotions for slow months (April, March)	Increase off-peak sales by 15%	R2,000
2. Long-Term Strategy
Strategy	Description	Timeline
Predictive Analytics	Build churn prediction model	3-6 months
Personalization	Send targeted offers based on customer preferences	2-4 months
Product Innovation	Introduce new products based on segment preferences	3-6 months
Automation	Automate data refresh and reporting	1-2 months
Customer Feedback	Implement NPS (Net Promoter Score) surveys	1 month
3. Segment-Specific Strategies
Segment	Strategy
At Risk	Send "We miss you" emails with discount offers
Occasional	Upsell promotions (bundle deals)
Recent	Welcome series with rewards for 2nd & 3rd visits
Regular	Loyalty program with tiered rewards
Loyal	Exclusive previews of new products
VIP	Personal concierge service, free drinks, priority ordering
________________________________________
📈 Future Improvements
Enhancement	Description	Priority
Power BI Version	Create an interactive online dashboard	High
Predictive Churn Model	Use Python to predict which customers will churn	High
Customer Lifetime Value (CLV)	Calculate CLV for each segment	High
Automated Data Refresh	Connect to live sales data	Medium
Executive Summary	One-page summary for management	Medium
Cohort Analysis	Track customer behavior over time	Medium
RFM Scoring	Implement Recency, Frequency, Monetary scoring	Low
NPS Integration	Add customer satisfaction data	Low
________________________________________
📂 Repository Structure
coffee-shop-customer-portfolio/
│
├── Dashboard/
│   └── Coffee_Shop_Customer_Dashboard.xlsx
│
├── Images/
│   └── dashboard_screenshot.png
│
├── Data/
│   └── coffee_shop_transactions.csv (sample)
│
├── README.md
└── LICENSE
________________________________________
📊 Key Metrics Summary
Metric	Value
Total Customers	1,316
Total Revenue	R41,995.69
Average Spend/Visit	R31.91
Most Valuable Customer	ANON-0000-0000-0009 (127 visits)
Top Product	Latte (R28,358)
Largest Segment	At Risk (989 customers)
Smallest Segment	VIP (18 customers)
Best Month	February 2025 (R18,253)
Worst Month	April 2024 (R7,670)
________________________________________
🎯 Business Impact Summary
What This Dashboard Revealed:
✅ Retention Opportunity: 75% of customers are at risk - immediate re-engagement needed
✅ Revenue Concentration: Top 2 products (Latte & Americano with Milk) drive 48% of revenue
✅ High-Value Segments: VIPs (1.4%) spend 2x more than average customers
✅ Seasonal Patterns: Q3 & Q4 are peak seasons, Q1 & Q2 need promotions
✅ Product Opportunities: Cortado and Cocoa show strong niche loyalty
✅ Growth Trend: 2025 showing strong growth (February highest revenue)
Estimated Revenue Impact:
Action	Estimated Impact
Re-engagement campaign	+R1,600 - R3,200
Loyalty program	+R6,300
Top product promotion	+R5,300
Seasonal promotions	+R2,000
Total Potential	+R15,000 - R17,000
________________________________________
👨‍💻 About the Author
Neo Mthembu
Bcom Statistics Student |Data Analyst
📧 Neomthembu25@gmail.com
🔗 https://www.linkedin.com/in/neo-mthembu-902b4621a/
🐙 https://github.com/neomthembu25-maker
Connect with Me
I'm always open to connecting with fellow data enthusiasts and professionals. Feel free to reach out if you have questions or would like to collaborate on future projects.
________________________________________

🙏 Acknowledgments
•	Data provided by Yaroslav Isaienkov
•	Dashboard inspired by best practices in customer analytics
•	Special thanks to the data community for continuous learning resources
________________________________________
