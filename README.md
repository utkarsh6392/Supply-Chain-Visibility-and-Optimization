# Supply Chain Analytics Dashboard

## Project Overview

This project is an end-to-end **Supply Chain Analytics and Optimization
Dashboard** built in **Microsoft Power BI**.

The dashboard combines sales, inventory, supplier, warehouse, delivery,
and transportation data into a single analytical solution. It helps
supply chain managers monitor operational performance, identify risks,
and make data-driven decisions.

The solution contains the following major dashboards:

1.  Executive Analytics
2.  Supplier Scorecard Generation
3.  Inventory Report
4.  Warehouse Efficiency
5.  Delivery Performance
6.  Transportation Analytics

The Power BI model uses a fact-and-dimension structure to connect
business transactions with supplier, customer, product, warehouse,
location, shipping, and date information.

------------------------------------------------------------------------

## Objectives

The main objectives of this project are:

-   Monitor overall supply chain performance.
-   Analyze sales and order trends.
-   Measure supplier reliability and quality.
-   Identify slow-moving and dead stock.
-   Track inventory turnover and inventory value.
-   Measure warehouse utilization and operational efficiency.
-   Monitor late and on-time delivery performance.
-   Compare scheduled shipping time with actual shipping time.
-   Analyze transportation cost, discount, profit, and shipping modes.
-   Identify regions, warehouses, suppliers, and products requiring
    attention.
-   Provide interactive filters for business-level analysis.

------------------------------------------------------------------------

## Tools and Technologies

-   Microsoft Power BI
-   Power Query
-   DAX
-   Data Modeling
-   Star Schema
-   Interactive Dashboards
-   KPI Cards
-   Bar Charts
-   Line Charts
-   Donut Charts
-   Gauge Charts
-   Scatter Plots
-   Tables and Matrix Visuals
-   Slicers

------------------------------------------------------------------------

# Data Model

The model contains a central transaction table named `fact_table` and
multiple dimension tables.

## Fact Table

### `fact_table`

The fact table contains the main transactional data used for sales,
orders, inventory, customers, products, suppliers, warehouse, and
delivery analysis.

Important fields visible in the model include:

-   Inventory ID
-   benefit_per_order
-   capacity
-   category_id
-   category_name
-   customer_city
-   customer_country
-   customer_fname
-   customer_id
-   product information
-   supplier information
-   warehouse information
-   order information
-   shipping information
-   sales and quantity fields

------------------------------------------------------------------------

## Dimension Tables

### `Dim_Product`

Contains product-level information.

Important fields:

-   product_card_id
-   product_name
-   product_price
-   product_status
-   category_id
-   department_id
-   product_category_id

### `Dim_Category`

Contains product category information.

Important field:

-   category_id

### `Dim_Department`

Contains department information.

Important field:

-   department_id

### `Dim_Customer`

Contains customer information.

Important fields:

-   customer_id
-   customer_fname
-   customer_lname
-   customer_city
-   customer_state
-   customer_country
-   customer_segment
-   customer_street
-   customer_zipcode

### `Dim_supplier`

Contains supplier performance information.

Important fields:

-   supplier_id
-   supplier_name
-   lead_time\_(days)
-   quality_score
-   quality_score (bins)
-   reliability\_%
-   Reliability Tier
-   product_card_id

### `Dim_Warehouse`

Contains warehouse capacity and utilization information.

Important fields:

-   warehouse_id
-   warehouse_name
-   capacity
-   utilization\_%
-   region

### `Dim_Location`

Contains geographical order information.

Important fields:

-   Location_id
-   market
-   order_city
-   order_country
-   order_region
-   order_state

### `Dim_Shipping`

Contains shipping and delivery information.

Important fields:

-   shipping_id
-   shipping_mode
-   shipping_date\_(dateorders)
-   days_for_shipment\_(scheduled)
-   days_for_shipping\_(real)
-   delivery_status
-   late_delivery_risk

### `Dim_Inventory`

Contains inventory-related information.

Important fields:

-   product_card_id
-   warehouse_id
-   stock_qty
-   safety_stock
-   reorder_level
-   inventory_value
-   last_restock_date

### `Dim_Date`

Contains date attributes used for time-series analysis.

Important fields:

-   Date
-   Day
-   Day Name
-   Month
-   Month Number
-   Year
-   Quarter

### `Prophet_Sales_Forecast`

Contains actual sales and forecast values.

Important fields:

-   Date
-   Actual Sales
-   Forecast Sales
-   Forecast Lower
-   Forecast Upper

------------------------------------------------------------------------

# Dashboard 1: Executive Analytics

The Executive Analytics dashboard provides a high-level view of the
entire supply chain.

## Main KPIs

The dashboard includes:

-   Total Orders: 7,104
-   Total Warehouses: 10
-   Total Suppliers: 118
-   Dead Stock Quantity: 45,605
-   Fulfillment Rate: 95.97%
-   Product Count: 42
-   Average Supplier Reliability: 53.90%
-   Inventory Turnover Ratio: 0.47x
-   Late Delivery: 51.22%
-   Average Warehouse Utilization: 55.15%

## Main Visuals

### Sales and Forecast Trend

Compares actual sales with forecast values over time.

This helps identify:

-   Sales growth
-   Forecast behavior
-   Seasonal patterns
-   Unexpected sales spikes
-   Periods of weak performance

### Sales by Region

The regional sales table compares sales performance across geographical
regions.

### Executive Narrative

The dashboard also uses Power BI's narrative capability to identify
changes in total sales and highlight periods of growth or decline.

## Business Value

This page is designed for management-level review. It provides a quick
understanding of supply chain health before moving into detailed
supplier, inventory, warehouse, delivery, or transportation analysis.

------------------------------------------------------------------------

# Dashboard 2: Supplier Scorecard Generation

The Supplier Scorecard dashboard evaluates supplier performance using
quality, reliability, and lead-time information.

## Main KPIs

-   Total Suppliers: 118
-   Average Quality Score: 75.71
-   Average Reliability: 53.90%
-   Average Lead Time: 17.31 days

## Main Visuals

### Supplier Performance Table

Shows supplier names and their average lead time and performance
measures.

### Lead Time vs Reliability

The scatter chart compares:

-   Supplier lead time
-   Supplier reliability
-   Quality score

This helps identify suppliers that have high lead times and low
reliability.

### Supplier Composite Score

The supplier ranking visual compares suppliers using a composite
performance score.

### Quality Score Distribution

Quality scores are grouped into bins to show the number of suppliers in
each quality range.

### Reliability Tier Distribution

Suppliers are classified into:

-   Low Tier
-   Medium Tier
-   High Tier

## Business Value

The supplier dashboard helps procurement teams:

-   Identify weak suppliers.
-   Compare supplier quality.
-   Monitor reliability.
-   Identify long lead-time suppliers.
-   Support supplier selection.
-   Prioritize supplier improvement programs.

------------------------------------------------------------------------

# Dashboard 3: Inventory Report

The Inventory Report focuses on inventory health, stock movement, and
working capital risk.

## Main KPIs

-   Inventory Turnover Ratio: 0.47x
-   Slow Moving Quantity: approximately 152K
-   Reorder Level: approximately 1M
-   Dead Stock Quantity: approximately 46K

## Main Visuals

### Total Sales by Category

Compares sales performance across product categories.

### Stock Quantity vs Reorder Level

Shows current stock and reorder level by product.

This helps determine products that may require replenishment or
inventory reduction.

### Stock Status

Inventory is classified into:

-   Active Stock
-   Dead Stock
-   Slow-Moving Stock

### Inventory Value by Warehouse

Compares the value of inventory stored in each warehouse.

### Inventory Value Over Time

Shows inventory value across the order-date timeline.

## Business Value

This page helps reduce:

-   Excess inventory
-   Dead stock
-   Carrying cost
-   Stock-out risk
-   Working capital blockage

It also supports better replenishment planning.

------------------------------------------------------------------------

# Dashboard 4: Warehouse Efficiency

The Warehouse Efficiency dashboard measures warehouse utilization and
operational performance.

## Main KPIs

-   Minimum Utilization: 15.93%
-   Total Warehouses: 10
-   Maximum Utilization: 84.24%
-   Average Utilization: 55.15%

## Main Visuals

### Average Utilization by Warehouse

Ranks warehouses based on their average utilization.

The displayed results show significant differences between warehouses,
making it possible to identify both highly utilized and underutilized
locations.

### Stock vs Capacity

A scatter plot compares:

-   Warehouse capacity
-   Total stock
-   Average utilization

This helps identify warehouses with capacity available for additional
inventory.

### Utilization Distribution

The pie chart compares utilization levels across warehouses.

### Warehouse Units Shipped

Shows the number of units shipped from each warehouse.

### Warehouse Performance Table

The table compares:

-   Warehouse name
-   Order count
-   Warehouse units shipped
-   Total sales
-   Units per order

## Business Value

This dashboard supports:

-   Capacity planning
-   Warehouse balancing
-   Inventory allocation
-   Resource utilization
-   Operational efficiency

------------------------------------------------------------------------

# Dashboard 5: Delivery Performance

The Delivery Performance dashboard measures delivery reliability and
shipping performance.

## Main KPIs

The page tracks:

-   Advance shipping days
-   Total orders
-   Late delivery rate
-   On-time delivery rate

The current dashboard shows a late delivery rate of approximately
**51.22%**.

## Main Visuals

### Late Delivery by Region

Ranks regions according to late delivery percentage.

This helps identify geographical areas with delivery problems.

### Late Delivery Gauge

Displays the overall late delivery percentage.

### Scheduled vs Actual Shipping Days

Compares average scheduled shipping days with actual shipping days for:

-   Same Day
-   First Class
-   Second Class
-   Standard Class

### Delivery Status Distribution

Compares:

-   Late Delivery
-   Advance Shipping
-   On-Time Delivery

### On-Time Delivery by Warehouse

Compares on-time delivery performance across warehouses.

## Business Value

The delivery dashboard helps identify:

-   High-risk regions
-   Poor-performing warehouses
-   Shipping modes causing delays
-   Difference between planned and actual delivery time
-   Opportunities to improve customer service

------------------------------------------------------------------------

# Dashboard 6: Transportation Analytics

The Transportation Analytics dashboard analyzes shipping mode,
discounts, profit, and late delivery behavior.

## Main KPIs

The page includes:

-   Total Discount Given
-   Average Profit per Order
-   Average Discount Rate: 10.34%
-   Same-Day Share: 1.39%

## Main Visuals

### Total Discount by Shipping Mode

Compares discounts provided for:

-   Standard Class
-   Second Class
-   First Class
-   Same Day

### Late Rate by Shipping Mode

Compares late delivery rates between shipping modes.

### Total Orders by Shipping Mode

Shows the distribution of orders across shipping modes.

### Average Profit per Order

Compares average profit generated by each shipping mode.

### Market-Level Delivery Analysis

The market matrix compares late delivery performance across geographical
markets.

## Business Value

Transportation analysis helps optimize:

-   Shipping mode selection
-   Transportation cost
-   Discounts
-   Profitability
-   Delivery reliability

------------------------------------------------------------------------

# DAX Measures

The following DAX measures can be used to reproduce the main KPIs and
calculations in the dashboard.

## 1. Total Orders

``` dax
Total Orders =
DISTINCTCOUNT(fact_table[Order Id])
```

If the model does not contain a unique order ID, use:

``` dax
Total Orders =
COUNTROWS(fact_table)
```

------------------------------------------------------------------------

## 2. Total Suppliers

``` dax
Total Suppliers =
DISTINCTCOUNT(Dim_supplier[supplier_id])
```

------------------------------------------------------------------------

## 3. Total Warehouses

``` dax
Total Warehouses =
DISTINCTCOUNT(Dim_Warehouse[warehouse_id])
```

------------------------------------------------------------------------

## 4. Product Count

``` dax
Product Count =
DISTINCTCOUNT(Dim_Product[product_card_id])
```

------------------------------------------------------------------------

## 5. Average Supplier Reliability

``` dax
Avg Supplier Reliability % =
AVERAGE(Dim_supplier[reliability_%])
```

Format the result as Percentage if the source column stores decimal
values.

If the source column stores values such as 53.90 instead of 0.5390, use:

``` dax
Avg Supplier Reliability % =
DIVIDE(
    AVERAGE(Dim_supplier[reliability_%]),
    100
)
```

------------------------------------------------------------------------

## 6. Average Supplier Quality Score

``` dax
Avg Quality Score =
AVERAGE(Dim_supplier[quality_score])
```

------------------------------------------------------------------------

## 7. Average Supplier Lead Time

``` dax
Avg Lead Time Days =
AVERAGE(Dim_supplier[lead_time_(days)])
```

------------------------------------------------------------------------

## 8. Inventory Value

``` dax
Total Inventory Value =
SUM(Dim_Inventory[inventory_value])
```

------------------------------------------------------------------------

## 9. Total Stock Quantity

``` dax
Total Stock Quantity =
SUM(Dim_Inventory[stock_qty])
```

------------------------------------------------------------------------

## 10. Reorder Level

``` dax
Total Reorder Level =
SUM(Dim_Inventory[reorder_level])
```

------------------------------------------------------------------------

## 11. Dead Stock Quantity

If the fact table contains a stock status field:

``` dax
Dead Stock Quantity =
CALCULATE(
    SUM(Dim_Inventory[stock_qty]),
    Dim_Inventory[Stock Status] = "Dead Stock"
)
```

If stock status is calculated from days since the last sale, the
following approach can be used:

``` dax
Dead Stock Quantity =
CALCULATE(
    SUM(Dim_Inventory[stock_qty]),
    FILTER(
        Dim_Inventory,
        Dim_Inventory[Days Since Last Sale] > 180
    )
)
```

The threshold of 180 days should be adjusted according to the business
requirement.

------------------------------------------------------------------------

## 12. Slow Moving Quantity

``` dax
Slow Moving Quantity =
CALCULATE(
    SUM(Dim_Inventory[stock_qty]),
    FILTER(
        Dim_Inventory,
        Dim_Inventory[Days Since Last Sale] > 90 &&
        Dim_Inventory[Days Since Last Sale] <= 180
    )
)
```

------------------------------------------------------------------------

## 13. Days Since Last Sale

This calculation determines how many days have passed since the last
sale of a product.

``` dax
Days Since Last Sale =
VAR LastSale =
    CALCULATE(
        MAX(fact_table[order_date_(dateorders)]),
        ALLEXCEPT(
            fact_table,
            fact_table[product_name]
        )
    )
VAR MaxDate =
    CALCULATE(
        MAX(fact_table[order_date_(dateorders)]),
        ALL(fact_table)
    )
RETURN
    DATEDIFF(
        LastSale,
        MaxDate,
        DAY
    )
```

------------------------------------------------------------------------

## 14. Inventory Turnover Ratio

Inventory turnover can be calculated as:

``` dax
Inventory Turnover Ratio =
DIVIDE(
    [Total Sales],
    [Total Inventory Value],
    0
)
```

If cost of goods sold is available, a more standard business formula is:

``` dax
Inventory Turnover Ratio =
DIVIDE(
    [COGS],
    [Average Inventory Value],
    0
)
```

------------------------------------------------------------------------

## 15. Total Sales

If sales amount is stored in a sales column:

``` dax
Total Sales =
SUM(fact_table[Sales])
```

If sales are calculated from quantity and price:

``` dax
Total Sales =
SUMX(
    fact_table,
    fact_table[order_item_quantity] *
    fact_table[sales]
)
```

Use the version matching the actual dataset fields.

------------------------------------------------------------------------

## 16. Fulfillment Rate

``` dax
Fulfillment Rate =
DIVIDE(
    [On Time Orders],
    [Total Orders],
    0
)
```

Format as Percentage.

------------------------------------------------------------------------

## 17. Late Delivery %

If `delivery_status` contains the value `Late delivery`:

``` dax
Late Delivery % =
DIVIDE(
    CALCULATE(
        COUNTROWS(Dim_Shipping),
        Dim_Shipping[delivery_status] = "Late delivery"
    ),
    COUNTROWS(Dim_Shipping),
    0
)
```

If delivery status is stored in the fact table:

``` dax
Late Delivery % =
DIVIDE(
    CALCULATE(
        COUNTROWS(fact_table),
        fact_table[delivery_status] = "Late delivery"
    ),
    COUNTROWS(fact_table),
    0
)
```

------------------------------------------------------------------------

## 18. On-Time Delivery %

``` dax
On Time Delivery % =
DIVIDE(
    CALCULATE(
        COUNTROWS(Dim_Shipping),
        Dim_Shipping[delivery_status] = "On Time"
    ),
    COUNTROWS(Dim_Shipping),
    0
)
```

If the dataset uses a different status such as `Advance shipping`,
adjust the filter accordingly.

------------------------------------------------------------------------

## 19. Advance Shipping %

``` dax
Advance Shipping % =
DIVIDE(
    CALCULATE(
        COUNTROWS(Dim_Shipping),
        Dim_Shipping[delivery_status] = "Advance shipping"
    ),
    COUNTROWS(Dim_Shipping),
    0
)
```

------------------------------------------------------------------------

## 20. Average Actual Shipping Days

``` dax
Avg Actual Shipping Days =
AVERAGE(
    Dim_Shipping[days_for_shipping_(real)]
)
```

------------------------------------------------------------------------

## 21. Average Scheduled Shipping Days

``` dax
Avg Scheduled Shipping Days =
AVERAGE(
    Dim_Shipping[days_for_shipment_(scheduled)]
)
```

------------------------------------------------------------------------

## 22. Shipping Delay

``` dax
Shipping Delay Days =
[Avg Actual Shipping Days] -
[Avg Scheduled Shipping Days]
```

A positive value indicates that actual shipping took longer than
scheduled.

------------------------------------------------------------------------

## 23. Average Warehouse Utilization

``` dax
Avg Utilization % =
AVERAGE(Dim_Warehouse[utilization_%])
```

------------------------------------------------------------------------

## 24. Minimum Warehouse Utilization

``` dax
Min Utilization % =
MIN(Dim_Warehouse[utilization_%])
```

------------------------------------------------------------------------

## 25. Maximum Warehouse Utilization

``` dax
Max Utilization % =
MAX(Dim_Warehouse[utilization_%])
```

------------------------------------------------------------------------

## 26. Warehouse Units Shipped

``` dax
Warehouse Units Shipped =
SUM(fact_table[order_item_quantity])
```

Use the actual quantity field available in the dataset if its name
differs.

------------------------------------------------------------------------

## 27. Units per Order

``` dax
Units per Order =
DIVIDE(
    [Warehouse Units Shipped],
    [Total Orders],
    0
)
```

------------------------------------------------------------------------

## 28. Total Discount

``` dax
Total Discount Given =
SUM(fact_table[order_item_discount])
```

------------------------------------------------------------------------

## 29. Average Discount Rate

``` dax
Avg Discount Rate =
AVERAGE(fact_table[order_item_discount_rate])
```

Format as Percentage if the source values are decimal.

------------------------------------------------------------------------

## 30. Average Profit per Order

``` dax
Avg Profit Per Order =
DIVIDE(
    SUM(fact_table[benefit_per_order]),
    [Total Orders],
    0
)
```

------------------------------------------------------------------------

## 31. Same Day Share

``` dax
Same Day Share % =
DIVIDE(
    CALCULATE(
        [Total Orders],
        Dim_Shipping[shipping_mode] = "Same Day"
    ),
    [Total Orders],
    0
)
```

------------------------------------------------------------------------

## 32. Supplier Reliability Tier

A calculated column can classify suppliers into performance tiers.

``` dax
Reliability Tier =
SWITCH(
    TRUE(),
    Dim_supplier[reliability_%] >= 0.80, "High Tier",
    Dim_supplier[reliability_%] >= 0.50, "Medium Tier",
    "Low Tier"
)
```

If the source values are stored between 0 and 100:

``` dax
Reliability Tier =
SWITCH(
    TRUE(),
    Dim_supplier[reliability_%] >= 80, "High Tier",
    Dim_supplier[reliability_%] >= 50, "Medium Tier",
    "Low Tier"
)
```

------------------------------------------------------------------------

## 33. Supplier Composite Score

A composite supplier score can combine quality, reliability, and lead
time.

``` dax
Supplier Composite Score =
VAR QualityScore =
    DIVIDE(
        AVERAGE(Dim_supplier[quality_score]),
        100,
        0
    )
VAR ReliabilityScore =
    AVERAGE(Dim_supplier[reliability_%])
VAR LeadTimeScore =
    1 -
    DIVIDE(
        AVERAGE(Dim_supplier[lead_time_(days)]),
        MAXX(
            ALL(Dim_supplier),
            Dim_supplier[lead_time_(days)]
        ),
        0
    )
RETURN
    ROUND(
        (
            QualityScore * 0.40 +
            ReliabilityScore * 0.40 +
            LeadTimeScore * 0.20
        ) * 100,
        2
    )
```

This gives higher weight to quality and reliability while also
considering lead time.

------------------------------------------------------------------------

# Additional DAX Calculations

## Total Orders by Shipping Mode

``` dax
Orders by Shipping Mode =
CALCULATE(
    [Total Orders],
    VALUES(Dim_Shipping[shipping_mode])
)
```

## Late Orders

``` dax
Late Orders =
CALCULATE(
    [Total Orders],
    Dim_Shipping[delivery_status] = "Late delivery"
)
```

## On-Time Orders

``` dax
On Time Orders =
CALCULATE(
    [Total Orders],
    Dim_Shipping[delivery_status] = "On Time"
)
```

## Advance Shipping Orders

``` dax
Advance Shipping Orders =
CALCULATE(
    [Total Orders],
    Dim_Shipping[delivery_status] = "Advance shipping"
)
```

## Average Profit per Shipping Mode

``` dax
Avg Profit by Shipping Mode =
AVERAGE(fact_table[benefit_per_order])
```

Place `Dim_Shipping[shipping_mode]` on the visual axis to compare
shipping modes.

------------------------------------------------------------------------

# Time Intelligence

A proper date table should be marked as the Date Table in Power BI.

## Total Sales Previous Year

``` dax
Sales Previous Year =
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR(Dim_Date[Date])
)
```

## Sales Growth %

``` dax
Sales Growth % =
DIVIDE(
    [Total Sales] - [Sales Previous Year],
    [Sales Previous Year],
    0
)
```

## Year-to-Date Sales

``` dax
Sales YTD =
TOTALYTD(
    [Total Sales],
    Dim_Date[Date]
)
```

## Month-to-Date Sales

``` dax
Sales MTD =
TOTALMTD(
    [Total Sales],
    Dim_Date[Date]
)
```

------------------------------------------------------------------------

# Forecast Analysis

The `Prophet_Sales_Forecast` table can be used to compare actual sales
with forecast sales.

## Actual Sales

``` dax
Actual Sales =
SUM(Prophet_Sales_Forecast[Actual Sales])
```

## Forecast Sales

``` dax
Forecast Sales =
SUM(Prophet_Sales_Forecast[Forecast Sales])
```

## Forecast Error

``` dax
Forecast Error =
[Actual Sales] - [Forecast Sales]
```

## Forecast Error %

``` dax
Forecast Error % =
DIVIDE(
    [Forecast Error],
    [Actual Sales],
    0
)
```

## Forecast Lower Bound

``` dax
Forecast Lower =
SUM(Prophet_Sales_Forecast[Forecast Lower])
```

## Forecast Upper Bound

``` dax
Forecast Upper =
SUM(Prophet_Sales_Forecast[Forecast Upper])
```

------------------------------------------------------------------------

# Recommended Power BI Relationships

The preferred model is a star-schema-style structure where dimensions
filter the central fact table.

Typical relationships include:

``` text
Dim_Product       1 ---- * fact_table
Dim_Category      1 ---- * Dim_Product
Dim_Department    1 ---- * Dim_Product
Dim_Customer      1 ---- * fact_table
Dim_supplier      1 ---- * fact_table
Dim_Warehouse     1 ---- * fact_table
Dim_Location      1 ---- * fact_table
Dim_Shipping      1 ---- * fact_table
Dim_Date          1 ---- * fact_table
Dim_Inventory     1 ---- * fact_table
```

The exact relationship keys should match the actual Power BI model.

Recommended relationship direction:

``` text
Dimension Table  ->  Fact Table
```

Use single-direction filtering wherever possible to avoid ambiguous
filter paths.

------------------------------------------------------------------------

# Key Business Findings

Based on the dashboard screenshots, the project highlights several
important supply chain areas.

## Supplier Performance

-   There are 118 suppliers.
-   Average quality score is approximately 75.71.
-   Average reliability is approximately 53.90%.
-   Average lead time is approximately 17.31 days.
-   Supplier performance varies significantly across quality and
    lead-time ranges.

## Inventory

-   Inventory turnover is approximately 0.47x.
-   Dead stock is approximately 45K units.
-   Slow-moving inventory is approximately 152K units.
-   Inventory is distributed across multiple warehouses with significant
    differences in inventory value.
-   Low inventory turnover indicates an opportunity to improve stock
    movement.

## Warehouse

-   There are 10 warehouses.
-   Average utilization is approximately 55.15%.
-   Maximum utilization is approximately 84.24%.
-   Some warehouses have much higher utilization than others.
-   Warehouse balancing can improve capacity utilization.

## Delivery

-   Overall late delivery is approximately 51.22%.
-   Late delivery varies considerably by region.
-   Shipping modes show different scheduled and actual shipping
    durations.
-   Warehouse-level on-time delivery performance also varies.

## Transportation

-   Average discount rate is approximately 10.34%.
-   Same-day shipping represents approximately 1.39% of orders.
-   Shipping mode affects both delivery performance and profit per
    order.
-   Standard Class accounts for the largest share of orders in the
    displayed analysis.

------------------------------------------------------------------------

# Recommended Management Actions

## Supplier Management

-   Review suppliers with low reliability.
-   Negotiate shorter lead times with high-delay suppliers.
-   Prioritize suppliers with strong quality and reliability.
-   Use supplier scorecards for quarterly performance reviews.

## Inventory Management

-   Reduce dead stock through clearance or redistribution.
-   Monitor slow-moving products.
-   Improve reorder policies.
-   Balance safety stock against demand.
-   Increase inventory turnover.

## Warehouse Management

-   Rebalance inventory between highly utilized and underutilized
    warehouses.
-   Use capacity data for warehouse allocation.
-   Investigate warehouses with low utilization.
-   Monitor units shipped per warehouse.

## Delivery Management

-   Investigate regions with high late-delivery rates.
-   Review warehouses with poor on-time delivery.
-   Compare scheduled and actual shipping times.
-   Optimize shipping mode selection.

## Transportation Management

-   Compare profit and delivery performance before selecting shipping
    modes.
-   Control excessive discounting.
-   Monitor same-day shipping profitability.
-   Evaluate shipping modes with high late rates.

------------------------------------------------------------------------

# Dashboard Filters

The dashboards include interactive filtering options such as:

-   Category
-   Market
-   Supplier
-   Product
-   Warehouse
-   Order Date
-   Shipping Mode
-   Region

These filters allow users to drill down from overall supply chain
performance to specific products, suppliers, warehouses, regions, and
time periods.

------------------------------------------------------------------------

# Project Workflow

``` text
Source Data
    |
    v
Power Query
    |
    v
Data Cleaning and Transformation
    |
    v
Data Model
    |
    +---- Dimension Tables
    |
    +---- Fact Table
    |
    v
DAX Measures and Calculated Columns
    |
    v
Power BI Visualizations
    |
    v
Interactive Dashboards
    |
    v
Business Insights and Decision Making
```

------------------------------------------------------------------------

# Data Modeling Best Practices Used

-   Separate fact and dimension tables.
-   Use unique keys for dimension tables.
-   Use one-to-many relationships where appropriate.
-   Keep filter direction simple.
-   Create reusable DAX measures instead of repeating calculations.
-   Use a dedicated date table for time intelligence.
-   Format percentages, currency, quantities, and ratios appropriately.
-   Use slicers for interactive analysis.
-   Avoid unnecessary calculated columns when a measure is sufficient.

------------------------------------------------------------------------

# Conclusion

The Supply Chain Analytics Dashboard provides a complete view of supply
chain operations from supplier performance to final delivery and
transportation.

The solution combines:

-   Executive-level KPIs
-   Supplier scorecards
-   Inventory analysis
-   Warehouse efficiency
-   Delivery performance
-   Transportation analytics
-   Sales forecasting
-   Interactive filtering
-   DAX-based business calculations

The dashboard can help organizations identify operational bottlenecks,
reduce inventory risk, improve supplier selection, increase warehouse
efficiency, improve delivery reliability, and optimize transportation
decisions.

The project demonstrates practical use of Power BI, DAX, data modeling,
KPI design, and business intelligence for real-world supply chain
management.
