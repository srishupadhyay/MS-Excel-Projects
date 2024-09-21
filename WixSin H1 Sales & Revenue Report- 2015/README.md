# WIXSIN H1 SALES & REVENUE REPORT - 2015

## AIM
To assist the management of **WixSin Company** in optimizing their sales operations by providing actionable insights derived from a detailed analysis of their H1 sales dataset.

## OBJECTIVES
The primary objectives of the analysis were to evaluate the company’s performance and identify key areas that influence revenue growth, product sales, and regional performance. Specifically, I aimed to:



- **Assess if revenue is growing consistently month-over-month.**
- **Identify the days with the highest revenue.**
- **Evaluate each product category's contribution to total revenue.**
- ***Analyze revenue by state to identify top-performing regions.***
- ***Determine which customer segment generates the most revenue.***
- ***Identify the top 5 best-selling products.***
- ***Provide recommendations to sustain or boost revenue.***




## DATA DISCOVERY
The analysis began by reviewing four key datasets:

- **Sales**        : ProductID, Date, Revenue, and Zip codes.
- **Product**      : ProductID, Product Name, Category, and Segment.
- **Manufacturer** : ManufacturerID and Manufacturer Name.
- **Location**     : Zip, State, and Country.

Understanding the structure of these datasets helped me determine how to connect them for a meaningful analysis and plan the necessary steps for data preparation to answer the business questions and named different tables from all the sheets using **( CTRL + T )**.

## DATA PREPARATION
The next step involved combining the data across the sheets using **STRUCTURAL REFERENCING** with **INDEX-MATCH** functions for **DATA-MODELING** & **DATA-COMBING**, linking the columns like **Product Name, Category, Segment**, and **State** from different tables. Example formulas used:

<div style="font-size: 20px;">

<strong><code>=INDEX(Product[Product Name],MATCH([@ProductID],Product[ProductID],0))</code></strong>

</div>

<div style="font-size: 20px;">

<strong><code>=INDEX(Product[Category],MATCH([@[Product_Name]],Product[Product Name],0))</code></strong>

</div>

<div style="font-size: 20px;">

<strong><code>=INDEX(Product[Segment],MATCH([@Category],Product[Category],0))</code></strong>

</div>

<div style="font-size: 20px;">

<strong><code>=INDEX(Location[State],MATCH([@Zip],Location[Zip],0))</code></strong>

</div>
</br>


To extract the manufacturer name from the product name, I applied the **LEN** function nested in **LEFT** function to eliminate excess text after the product name:
<div style="font-size: 20px;">

<strong><code>=LEFT([@[Product_Name]],LEN([@[Product_Name]])-5)</code></strong>

</div>
</br>

Using the **TEXT** function, I extracted Year, Month, and Day from the sales date:

<div style="font-size: 20px;">

<strong><code>=TEXT([@Date],"YYYY")</code></strong>

</div>

<div style="font-size: 20px;">

<strong><code>=TEXT([@Date],"MMMM")</code></strong>

</div>

<div style="font-size: 20px;">

<strong><code>=TEXT([@Date],"DDDD")</code></strong>

</div></br>

I ensured that categories were correctly assigned to their data types, and after completing this step, the dataset was fully prepared for detailed analysis.

## DASHBOARD
![Dashboard SS](https://github.com/user-attachments/assets/e5104eae-210f-48a7-b432-85f7a35275e3)
</br>


<div align="center">
    <a href="https://github.com/srishupadhyay/MS-Excel-Projects/blob/0433fb46e94cada87f014ffd5950c97e3c96fdf0/WixSin%20H1%20Sales%20%26%20Revenue%20Report-%202015/Data/Data%20H1.xlsx">Click here to download the dataset</a>
</div>
</br>

<div align="center">
    <a href="https://github.com/srishupadhyay/MS-Excel-Projects/blob/8cf32fdbeaf2cc054854ce717268967a93c05c23/WixSin%20H1%20Sales%20%26%20Revenue%20Report-%202015/Data%2BSol/DASHBOARD.xlsx">Click here to download Dashboard File</a>
</div>
</br>

I used a variety of **PIVOT CHARTS** like **BAR CHART**, **LINE CHART** & **PIE CHART** to answer questions in the objectives. There is a slicer that filters down results based on product segment. A separate **Product Info Finder** gives you the product name, manufacturer name, category, and segment by entering the product ID. There are 2 KPI Indicators on the top showing **Total Revenue** & **Total Units Sold.**

## TRENDS
- **Month-over-month revenue:** Revenue sharply increases from the start of January to $791,665, peaking in April at $2,233,855. It falls constantly till June - $1,57,418, creating a peak shape.

  
Recommendation: 
The revenue range is the highest during the <u>Spring Season</u> and starts to decline with the start of <u>Summer</u>. Special seasonal offers can be promoted on the lowest-selling products to sustain growth.</br>



- **Days with the highest revenue:**


<div align="center">

| Day        | Revenue           |
|------------|-------------------|
| Monday     | $1,821,451        |
| Thursday   | $1,807,757        |
| Tuesday    | $1,717,407        |
| Sunday     | $1,643,868        |
| Wednesday  | $1,422,189        |
| Friday     | $921,299          |
| Saturday   | $492,211          |
| **Grand Total** | **$9,826,183.08** |

</div>

Recommendation: 
The above-mentioned offers and seasonal deals should be targeted from Wednesday to Friday to boost revenue.</br>

- **Total revenue contribution by category:**
<div align="center">

| Segment    | Percentage        |
|------------|-------------------|
| Mix        | 2.32%             |
| Rural      | 8.67%             |
| Urban      | 86.96%            |
| Youth      | 2.05%             |
| **Grand Total** | **100.00%**       |

</div>

- **Top-performing regions:** Ontario leads with **$3,115,228** and Alberta follows closely with **$2,963,158**, while Quebec lags significantly at **$260,340**. Strengthening efforts in Ontario and Alberta and improving Quebec’s performance could enhance total revenue.

- **Revenue by customer segment:** Moderation dominates with **$8,544,606** in revenue, far surpassing other segments. Productivity follows with **$851,594**, while All Season and Youth contribute much smaller amounts, at **$228,165** and **$201,819** respectively.

- **Identify the top 5 best-selling products.**
<div align="center">

| Product       | Revenue         |
|---------------|-----------------|
| Maximus UM-96 | $258,285        |
| Maximus UM-92 | $383,652        |
| Maximus UM-12 | $430,623        |
| Maximus UM-11 | $458,685        |
| Maximus UM-43 | $574,086        |
| **Grand Total** | **$2,105,330.85** |

</div>
















