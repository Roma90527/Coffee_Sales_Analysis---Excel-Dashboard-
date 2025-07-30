
# Coffee Sales Data Analysis Dashboard

This project focuses on analyzing a coffee sales dataset downloaded from [here](https://mavenanalytics.io/data-playground?order=date_added%2Cdesc&search=coffee%20sales%20) to anlyze the sales trends, product performance and store-wise distribution. The analysis conducted using Mirosoft Excel and Power Query Editor to clean, transform and visualize the data.

## Objective 
The primary objective of this project is to provide a clear understanding of customers purchasing pattern, identify top products and store locations, highlight the insights through visuals. These insights will be helpful for decision-making for sales, marketing and inventory management.

# Recommended Analytical Questions
Here are the key questions that need to analyzed and visualized.
1. How do total orders vary month over month?
2. What is the average footfall on different days of the week?
3. What are the busiest hours of the day?
4. Which products generate highest revenue?
5. What is the distribution of orders across product categories?
6. Which product size are most popular among customers?
7. Which store location have highest customer traffic(footfall)?

# Coffee sales Dashboard
![](https://github.com/Roma90527/Coffee_Sales_Analysis---Excel-Dashboard-/blob/main/Coffe%20Sales%20Analysis%20Dashboard.png?raw=true)
# Data cleaning and Transformation Steps 

## Standardizing Product Details Column

**Task:** Add a Column [Product_size] based on [Produc_detail] and remove Lg, Rg, and Sm  from the original [product_detail] column. 
1. In **Power Query Editor** , select Product_detail column.
2. Use **Add Column > Conditional Column** and select 
     - If [product_detail] contains Rg then Regular. Similarly for other values as well.
3. Select [Product_detail] column then > **Transform > Replace Values** and replace Lg with Space (" "). Repeat for other values.

## Removing White Spaces 
**Task:** Removing leading, trailing and extra white spaces in text field to ensure data consistency.
1. Select all text columns( Product_detail,Product_type, Store_location).
2. Use **Transform > Format > Trim** to remove any spaces. 
  **Note:** This step ensured that filters, grouping and lookups would work correctly.

## Calculating Total Sales 
**Task:** Add a column that represents the total sales per transaction.
1. Use **Add column > Custom column >**.  
2. In the formula box , enter:   
      [Transaction_qty]*[Unit_price] 
3. Name the new column as Total_Sales.

 ## Cleaning Transaction Time Column 
**Task:** Extract only the time portion from a combined date-time field.
1. Select [Transaction_time] column.
2. Use **Transform > Extract> Text After Delimeter** and set the delimer as a space ("  ").
3. The portion is extracted.
4. Change the data type to Time using **Transform> Data Type > Time**.

 ## Extracting Month and Day from Transaction_date
  **Task:** Extract month and day column for time series analysis.
  1. Select [transaction_date] column.
  2. Use **Add Column > Date > Month > Name of Month** to extract the month. 
  3.  Use **Add Column > Date > Day > day** to extract the day of the month. 
  
## Extracting Hours from Transaction_time
**Task:** Identify peak sales hours by extracting the hour fro transaction time.
  1. Select [transaction_time] column.
  2. Use **Add Column > Time > Hour > Hour** to extract the hours. 
  3. This will create a new column containing values 8,9,10, representing the hour of the transaction.
  
# Dashboard Design and Analytical insights
The final Excel dashboard developed to provide interactive , actionable insights using **KPIs, Slicers, and seven dynamic charts**. The visualisation are designed to help users grasp sales performance, customer behaviour, and product trends across time and store  locations.

## Key Performance Indicator(KPIs)
The top section of dashboard includes **four key performance indicators**, each recalculating dynamically based on slicer selections (Months and Days).  
1. **Total Sales:** Sum of all transaction revenue, measuring overall financial performance.
2. **Total Footfall:** Total number of transactions(i.e. unique transaction_id) representing customer vists.  
3. **Bill Per Person:** Calculated as Total_sales / Footfall, showing average spend per customer.
4. **Order Per Person:** Calculated as total_quantity / Footfall, indicating the average number of items each customer purchased.

## Slicer
Two slicers **Month name and Day name** are also included which allow users to filter the dashboard by time period, updating all visualization instantly to reflect selected time frame. 
## Recommended Analytical Questions and Corresponding insights
**Question 1:** How do total order vary month over month?  
The number of orders shows a consistent upward trend from January to June,indicating **growing customer engagement** and **sales momentum** over six-month period. The year starts with Starting at 17,314 orders in January, there is slight dip in February (16,359), possibly due to fewer days in the month. From March onward, the growth is sustained and significant, with orders increasing steadily to 21,229 in March, 25,335 in April, and surging to 33,527 in May and 35,352 in June. This **116%** growth from february to june suggests strong demand acceleartion.  

**Question 2:** What is the average footfall on different days of the week?  
The number of orders relatively stable across the weekdays, with Monday through Friday each recording over 21,000 transacrions. **Friday** records the highest number of orders (21,701), followed closely by Thursday (21,654) and Monday (21,643). Weekend sales slightly dip, with **satuarday** showing the **lowest** at 20,510,  a **4.6%** decrease compared to the weekdays average. This pattern shows the **customer routines**, for example weekdays coffee purchases during work breaks, with slightly reduced over weekend.


**Question 3:** What are the busiest hours of the week?  
The hourly distribution of orders shows a clear customer activity in the **morning hours**, with order volume starting at 6 AM and increasing steadily to peak between **10 AM and 11 AM**. This peak hours represent the highest customer engagement window, suggesting the most customers purchase coffee or other items. After 11 AM, the number of order gradually declines throughout the day, indicating reduced demand in afternoon and evening, This insights are helpful for assessing the importance of **morning operations**, such as staffing or promotion.


**Question 4:** Which products generate highest revenue?  
The top-performing products is **Brista Espresso**, generating **$91,000**, which significantly outspaces other items. It is followed by **Brewed Chai Tea ($77,081.95)** and **Hot Chocolate** ($72,416). **Gourmet Brewed Coffee** also performs strongly at $70,34.60. In contrast, **Brewed Black Tea** lags behind at $47,932, roughly **47%** than top products. This analysis highlighs **Brista Esprsso as the most profitable product**, indicating a high customer preference.


**Question 5:** What is the distribution of orders across product categories?  
The product category distribution is **heavily dominated by bakery items**, which account for **39%** of all orders, highlighting strong customer preferences. **Tea (28%)** and **Coffee(12%)** togather make up **40%**, confirming beverage as a important part of the business, Other notable categories include **Drinking Chocolate(10%)** and **Coffee Beans(6%)**, while other categories like **Branded Product (2%)**, **Flavours**, **Loose Tea** , and **packed Chocolate** each represent only **1%**, suggesting limited customer preferences. This distribution suggests opportunities to expand and promote popular categories.


**Question 6:** Which product size are most popular among customer?
The size distribution reveals that **Regular (31%)** and **Large (30%)** sizes are almost equally preferred, together accounting for **61% of all the orders**. **Small sizes** make up only **9%**, suggesting limited demand for small portion. It is cleared that **30% of the data is marked as "Unspecified"**, indicating product types where size is not applicable. The clear dominance of regular and large sizes indicate customer preference for standard or more generous portion, which can inform pricing strategies and inventory stocking.


**Question 7:** Which store location have highest customer traffic(footfall)?  
All three store locations show consistently high footfall, each serving over 47,000 customers within the time period analyzed. **Hell's Kitchen leads slightly in both footfall (50,735)** and **total sales($236,511.17)** indicating high throughput and high value transactions. **Astoria follows closely** with 50,599 customers and $232,243.91 in revenue. While **Lower Manhattan** has slightly lower footfall(47,782), its **total sales($230,057.25)** are comparable, suggesting higher **average bill per customer** at this location. These insights can guide **location-specific promotions** , staffing and **inventory decisions**. 

 # Deliverables
 1. Cleaned and structured Excel Sheet
 2. Power Query Transformation
 3. Excel dashboard with charts and KPIs
    
       