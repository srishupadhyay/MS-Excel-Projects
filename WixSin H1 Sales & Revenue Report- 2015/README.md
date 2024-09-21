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
I used a variety of **PIVOT CHARTS** like **BAR CHART**, **LINE CHART** & **PIE CHART** to answer all the required questions in the objectives. line charts to show revenue trends, bar charts to compare product categories and states, and pie charts to display product segment contributions. I added slicers to make the dashboard interactive, allowing users to filter the data by product or region.

## INSIGHTS
From the dashboard, I found that revenue had grown consistently over the months, with certain products and regions driving most of the sales. Alberta and British Columbia, in particular, contributed significantly to total revenue. These insights led to actionable recommendations for optimizing marketing efforts and product focus.

## RECOMMENDATIONS
By following a structured data analysis process—cleaning and combining data, performing exploratory analysis, and creating visualizations—I was able to create an interactive Excel dashboard that provided valuable business insights.
















