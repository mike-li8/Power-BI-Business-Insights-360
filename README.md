# Power-BI-Business-Insights-360

## Summary
This project was made from my enrollment in [Codebasics](https://codebasics.io/) [Data Analytics Bootcamp](https://codebasics.io/bootcamps/data-analytics-bootcamp-with-practical-job-assistance). The bootcamp exhibits a fictional company called AtliQ Technologies which is rapidly proliferating to many markets around the globe. However, AtliQ relied on Excel files for their data analytics needs which made it difficult and time consuming to easily generate insights from sales data, hindering AtliQ's growth in Latin America. The objective of this project is to create a Power BI dashboard for which stakeholders from various business departments such as finance, sales, marketing, supply chain, and executive can quickly and effectively gather insights from the data to make better informed decisions.



## Technology Learnings
### Power BI
* Techniques
  * Connecting to data from MySQL database
  * DAX to create
      * Measures
      * Columns
      * Tables
* Filter Context
* Create a dyanamic switch between visuals using a combination of:
  * Field Parameters
  * Bookmarks


## AtliQ Business Model
AtliQ manufactures computer hardware **products** (e.g. mouse, keyboard, printer, monitor) and then sells them to various **customers** which are stores (e.g. Amazon, Best Buy). Hence, AtliQ's customers are in the form of store businesses (e.g. Amazon) and should not be confused with customers in the form of people (e.g. end consumers purchasing products from Amazon).

AtliQ's sells to customers categorized into two different **platforms**:
1. Brick & Motar
   * stores that have a physical store locations
2. E-Commerce
   * stores which only sell products online

AtliQ sells to customers categorized by three different **channels**:
1. Retailer
   * Stores not owned by AtliQ hardware (e.g. Amazon)
3. Direct
   * Stores owned by AtliQ hardware
5. Distributor
   * In markets where laws/regulations disallow AtliQ from selling directly to customers. 

Sample Profit and Loss (P&L) Statement for AtliQ
Example of a mouse being sold to Chroma
| Line Item | Description | P&L Value |
| -- | -- | -- |
| Gross Price |  The Base Price of a Product | $30.00 |
| Pre-Invoice Deduction | For each fiscal year, the sales team determines a discount given for each customer based on factors such as sales performance in previous years. | - $2.00 |
| Net Invoice Sales | The amount of money that is billed to the customer to obtain the product | $28.00 |
| Post-Invoice Deudctions | Rebates paid to customers **after** AtliQ sells products to them. For example, a prmotion can be given to give customers discounts for holidays. Rebates can be given for placing a product at a prime location inside a store. Performance rebates can be given if a customer generates a lot of sales for AtliQ | - $3.00 |
| Net Sales | Revenue | $25.00 |
| Cost of Goods Sold (COGS) | Expenses AtliQ incurs such as manufacturing the products, shipping of products, and storage of products in warehouses | -$20.00
| Gross Margin | Profit after deducing COGS | $5.00 |


## Tables Imported from MySQL

#### Fact Tables
| Table Name    | Description   |
| ------------- | ------------- |
| fact_forecast_monthly  | Table of predicted sales at a monthly level.  |
| fact_sales_monthly           | Table of actual sales at a monthly level. |
| freight_cost | Details the freight cost for a particular market and fiscal year |
| gross_price | The gross price of a unique product for a given fiscal year |
| manufacturing_cost | The manufacturing cost of a unique product for a given year |
| post_invoice_deductions | For a specific customer and product and at a specific month, a rebate given to customer. |
| pre_invoice_deductions | For a unique customer and fiscal year, the discount given to the customer |



#### Dimension Tables
| Table Name    | Primary Key Field   | Description |
| ------------- | ------------- | ----------- |
| dim_market  | market  |
| dim_customer  | customer_code  |
| dim_product  | product_code  |

### Business Understanding and Acumen
* Fiscal Date vs Calendar Date
* YTD (Year-to-Date)
* YTG (Year-to-Go)
* Profit and Loss Statement
* Marketshare
* Revenue
* Profit
* Cost of Goods Sold (COGS)

* Supply Chain Basics
