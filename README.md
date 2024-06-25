
## Sales data Analysis and its dashboards using Power Bi

1. Total Sales  A card visual can display the total sales metric.

2. Total Products  Another card visual can display the total number of products in your data set.

3. Total Profit Yet another card visual can display the total profit metric.

4. Top % Product Name Wise Profit  A pie chart or donut chart can show the percentage of profit each product contributes to the total.

5. Market Wise Profit and Sales  A dual axis column chart can be used to display sales and profit for each market.

6. Sum of Sales by Region  A stacked bar chart can show sales for each region.

7. Segment Wise Sales  A bar chart can display sales for each segment.

8. Category Wise Profit  Another bar chart can display profit for each category.

These are just a few examples, and the best visuals for your dashboard will depend on your specific data and the questions you want to answer. Power BI offers a wide variety of visualizations that you can use to create a customized dashboard that meets your needs.

## Here are some additional tips for creating a sales dashboard in Power BI:

1. Start by identifying the key metrics you want to track. What are the most important things you want to know about your sales performance?

2. Once you know your key metrics, choose the right visualizations to display them. Consider the type of data you are working with and the message you want to convey.

3. Use filters and slicers to allow users to drill down into your data. This will help them to see the details behind the numbers.

4. Format your dashboard to be visually appealing and easy to read. Use clear and concise labels, and avoid cluttering your dashboard with too many visuals.

## 1.  Total Sales
This measure calculates the total sales amount.

Total Sales = SUM(Sales[SalesAmount])

## 2. Total Products
This measure counts the distinct number of products sold.

DAX Function:

Total Products = DISTINCTCOUNT(Sales[ProductID])

## 3. Total Profit
This measure calculates the total profit, assuming you have sales and cost columns.

DAX Function:

Total Profit = SUM(Sales[SalesAmount]) - SUM(Sales[CostAmount])

##  4. Top % Product Name Wise Profit
This measure calculates the profit percentage for each product and sorts them to identify the top products.

DAX Function:


Profit Percentage = 
DIVIDE(
    SUM(Sales[SalesAmount]) - SUM(Sales[CostAmount]),
    SUMX(ALL(Sales), Sales[SalesAmount] - Sales[CostAmount])
)

## 5. Market Wise Profit and Sales
These measures calculate total sales and profit for each market.

DAX Functions:

Market Sales = CALCULATE(SUM(Sales[SalesAmount]), Sales[Market])
Market Profit = CALCULATE(SUM(Sales[SalesAmount]) - SUM(Sales[CostAmount]), Sales[Market])

## 6. Sum of Sales by Region
This measure calculates the total sales amount for each region.

DAX Function:

Sales by Region = CALCULATE(SUM(Sales[SalesAmount]), Sales[Region])

## 8. Categories Wise Profit
This measure calculates the total profit for each product category.

DAX Function:

Category Profit = 
CALCULATE(
    SUM(Sales[SalesAmount]) - SUM(Sales[CostAmount]),
    Sales[Category]
)

## Example Visual Setup : 

KPI Cards: Display Total Sales, Total Products, Total Profit.

Bar Chart: Show Top % Product Name Wise Profit.

Clustered Column Chart: Display Market Wise Profit and Sales.

Map Visual: Show Sum of Sales by Region.

Segment Sales: Use a bar chart for Segment Wise Sales.

Category Profit: Use a column chart for Categories Wise Profit.

