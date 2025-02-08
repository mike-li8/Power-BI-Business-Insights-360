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

Simplified Profit and Loss (P&L) Statement for AtliQ
Example of a mouse being sold to Chroma
| Line Item | Description | P&L Value |
| :- | :- | -: |
| Gross Price |  The Base Price of a Product | $30.00 |
| Pre-Invoice Deduction | For each fiscal year, the sales team determines a discount given for each customer based on factors such as sales performance in previous years. | - $2.00 |
| Net Invoice Sales | The amount of money that is billed to the customer to obtain the product | $28.00 |
| Post-Invoice Deudctions | Rebates paid to customers **after** AtliQ sells products to them. For example, a prmotion can be given to give customers discounts for holidays. Rebates can be given for placing a product at a prime location inside a store. Performance rebates can be given if a customer generates a lot of sales for AtliQ | - $3.00 |
| Net Sales | Revenue | $25.00 |
| Cost of Goods Sold (COGS) | Expenses AtliQ incurs such as manufacturing the products, shipping of products, and storage of products in warehouses | -$20.00
| Gross Margin | Profit after deducing COGS | $5.00 |
| Operational Expenses | Exepnses AtliQ incurs from activities such as advertising by marketing team. | -$3.00 |
| Net Profit | Profit after deducting operational expenses | $2.00 |

## Data Sources

### Dimension Tables Imported from MySQL and Sample Records

dim_market
| market | sub_zone | region |
| :- | :- | :- |
| Japan | ROA | APAC |
| Sweden | NE | EU |
| Brazil | LATAM | LATAM |

dim_customer
| 	customer_code	 | 	customer	 | 	market	 | 	platform	 | 	channel	 |
| 	-:	 | 	:-	 | 	:-	 | 	:-	 | 	:-	 |
| 	1	 | 	Amazon	 | 	USA	 | 	E-Commerce	 | 	Retailer	 |
| 	2	 | 	Amazon	 | 	Japan	 | 	E-Commerce	 | 	Retailer	 |
| 	3	 | 	Staples	 | 	USA	 | 	Brick & Mortar	 | 	Retailer	 |
| 	4	 | 	Staples	 | 	Canada	 | 	Brick & Mortar	 | 	Retailer	 |
| 	5	 | 	AltiQ Exclusive	 | 	South Korea	 | 	Brick & Mortar	 | 	Direct	 |
| 	6	 | 	Atliq e Store	 | 	Newzealand	 | 	E-Commerce	 | 	Direct	 |
| 	7	 | 	Neptune	 | 	China	 | 	Brick & Mortar	 | 	Distributor	 |

dim_product
| 	product_code	 | 	division	 | 	segment	 | 	category	 | 	product	 | 	variant	 |
| 	-:	 | 	:-	 | 	:-	 | 	:-	 | 	:-	 | 	:-	 |
| 	1	 | 	P & A	 | 	Peripherals	 | 	Graphic Card	 | 	AQ Mforce Gen Y	 | 	Plus 1	 |
| 	2	 | 	P & A	 | 	Peripherals	 | 	Graphic Card	 | 	AQ Mforce Gen Y	 | 	Plus 2	 |
| 	3	 | 	P & A	 | 	Accessories	 | 	Mouse	 | 	AQ Master wired x1 Ms	 | 	Premium 1	 |
| 	4	 | 	P & A	 | 	Accessories	 | 	Mouse	 | 	AQ Master wired x1 Ms	 | 	Premium 2	 |
| 	5	 | 	PC	 | 	Notebook	 | 	Business Laptop	 | 	AQ BZ Compact	 | 	Standard Blue	 |
| 	6	 | 	PC	 | 	Notebook	 | 	Business Laptop	 | 	AQ BZ Compact	 | 	Standard Red	 |
| 	7	 | 	N & S	 | 	Networking	 | 	Wi fi extender	 | 	AQ Wi Power Dx1	 | 	Standard	 |
| 	8  | 	N & S	 | 	Networking	 | 	Wi fi extender	 | 	AQ Wi Power Dx2	 | 	Standard	 |
| 	9	 | 	N & S	 | 	Storage	 | 	External Solid State Drives	 | 	AQ Digit SSD	 | 	Premium	 |
|  10 | 	N & S	 | 	Storage	 | 	External Solid State Drives	 | 	AQ Neuer SSD	 | 	Premium	 |


### Fact Tables Imported from MySQL and Sample Records
fact_forecast_monthly
| 	date	 | 	product_code	 | 	division	 | 	category	 | 	product	 | 	customer_code	 | 	customer_name	 | 	market	 | 	platform	 | 	channel	 | 	forecast_quantity	 |
| 	-:	 | 	-:	 | 	:-	 | 	:-	 | 	:-	 | 	-:	 | 	:-	 | 	:-	 | 	:-	 | 	:-	 | 	-:	 |
| 	2018-09-01	 | 	1	 | 	P & A	 | 	Graphic Card	 | 	AQ Mforce Gen Y	 | 	1	 | 	Amazon	 | 	USA	 | 	E-Commerce	 | 	Retailer	 | 	107	 |
| 	2018-09-01	 | 	2	 | 	P & A	 | 	Graphic Card	 | 	AQ Mforce Gen Y	 | 	2	 | 	Amazon	 | 	Japan	 | 	E-Commerce	 | 	Retailer	 | 	13	 |
| 	2018-10-01	 | 	3	 | 	P & A	 | 	Mouse	 | 	AQ Master wired x1 Ms	 | 	4	 | 	Staples	 | 	Canada	 | 	Brick & Mortar	 | 	Retailer	 | 	63	 |
| 	2018-10-01	 | 	4	 | 	P & A	 | 	Mouse	 | 	AQ Master wired x1 Ms	 | 	4	 | 	Staples	 | 	Canada	 | 	Brick & Mortar	 | 	Retailer	 | 	81	 |
| 	2018-11-01	 | 	5	 | 	PC	 | 	Business Laptop	 | 	AQ BZ Compact	 | 	5	 | 	AltiQ Exclusive	 | 	South Korea	 | 	Brick & Mortar	 | 	Direct	 | 	186	 |
| 	2018-11-01	 | 	6	 | 	PC	 | 	Business Laptop	 | 	AQ BZ Compact	 | 	2	 | 	Amazon	 | 	Japan	 | 	E-Commerce	 | 	Retailer	 | 	19	 |
| 	2018-12-01	 | 	7	 | 	N & S	 | 	Wi fi extender	 | 	AQ Wi Power Dx1	 | 	3	 | 	Staples	 | 	USA	 | 	Brick & Mortar	 | 	Retailer	 | 	91	 |
| 	2018-12-01	 | 	8	 | 	N & S	 | 	Wi fi extender	 | 	AQ Wi Power Dx2	 | 	6	 | 	Atliq e Store	 | 	Newzealand	 | 	E-Commerce	 | 	Direct	 | 	121	 |
| 	2019-01-01	 | 	9	 | 	N & S	 | 	External Solid State Drives	 | 	AQ Digit SSD	 | 	7	 | 	Neptune	 | 	China	 | 	Brick & Mortar	 | 	Distributor	 | 	106	 |
| 	2019-01-01	 | 	10	 | 	N & S	 | 	External Solid State Drives	 | 	AQ Neuer SSD	 | 	3	 | 	Staples	 | 	USA	 | 	Brick & Mortar	 | 	Retailer	 | 	90	 |

fact_sales_monthly
| 	date	 | 	product_code	 | 	division	 | 	category	 | 	product	 | 	customer_code	 | 	customer_name	 | 	market	 | 	platform	 | 	channel	 | 	forecast_quantity	 |
| 	-:	 | 	-:	 | 	:-	 | 	:-	 | 	:-	 | 	-:	 | 	:-	 | 	:-	 | 	:-	 | 	:-	 | 	-:	 |
| 	2018-09-01	 | 	1	 | 	P & A	 | 	Graphic Card	 | 	AQ Mforce Gen Y	 | 	1	 | 	Amazon	 | 	USA	 | 	E-Commerce	 | 	Retailer	 | 	70	 |
| 	2018-09-01	 | 	2	 | 	P & A	 | 	Graphic Card	 | 	AQ Mforce Gen Y	 | 	2	 | 	Amazon	 | 	Japan	 | 	E-Commerce	 | 	Retailer	 | 	152	 |
| 	2018-10-01	 | 	3	 | 	P & A	 | 	Mouse	 | 	AQ Master wired x1 Ms	 | 	4	 | 	Staples	 | 	Canada	 | 	Brick & Mortar	 | 	Retailer	 | 	129	 |
| 	2018-10-01	 | 	4	 | 	P & A	 | 	Mouse	 | 	AQ Master wired x1 Ms	 | 	4	 | 	Staples	 | 	Canada	 | 	Brick & Mortar	 | 	Retailer	 | 	60	 |
| 	2018-11-01	 | 	5	 | 	PC	 | 	Business Laptop	 | 	AQ BZ Compact	 | 	5	 | 	AltiQ Exclusive	 | 	South Korea	 | 	Brick & Mortar	 | 	Direct	 | 	164	 |
| 	2018-11-01	 | 	6	 | 	PC	 | 	Business Laptop	 | 	AQ BZ Compact	 | 	2	 | 	Amazon	 | 	Japan	 | 	E-Commerce	 | 	Retailer	 | 	158	 |
| 	2018-12-01	 | 	7	 | 	N & S	 | 	Wi fi extender	 | 	AQ Wi Power Dx1	 | 	3	 | 	Staples	 | 	USA	 | 	Brick & Mortar	 | 	Retailer	 | 	163	 |
| 	2018-12-01	 | 	8	 | 	N & S	 | 	Wi fi extender	 | 	AQ Wi Power Dx2	 | 	6	 | 	Atliq e Store	 | 	Newzealand	 | 	E-Commerce	 | 	Direct	 | 	66	 |
| 	2019-01-01	 | 	9	 | 	N & S	 | 	External Solid State Drives	 | 	AQ Digit SSD	 | 	7	 | 	Neptune	 | 	China	 | 	Brick & Mortar	 | 	Distributor	 | 	140	 |
| 	2019-01-01	 | 	10	 | 	N & S	 | 	External Solid State Drives	 | 	AQ Neuer SSD	 | 	3	 | 	Staples	 | 	USA	 | 	Brick & Mortar	 | 	Retailer	 | 	61	 |

fact_freight_cost
| 	market	 | 	fiscal_year	 | 	freight_pct	 | 	other_cost_pct	 |
| 	:-	 | 	-:	 | 	-:	 | 	-:	 |
| 	Australia	 | 	2018	 | 	0.0188	 | 	0.005	 |
| 	Australia	 | 	2019	 | 	0.0304	 | 	0.0048	 |
| 	Australia	 | 	2020	 | 	0.0254	 | 	0.0043	 |
| 	Australia	 | 	2021	 | 	0.0254	 | 	0.0043	 |
| 	Australia	 | 	2022	 | 	0.0254	 | 	0.0043	 |
| 	Bangladesh	 | 	2018	 | 	0.0219	 | 	0.0058	 |
| 	Bangladesh	 | 	2019	 | 	0.0249	 | 	0.0053	 |
| 	Bangladesh	 | 	2020	 | 	0.0258	 | 	0.0035	 |
| 	Bangladesh	 | 	2021	 | 	0.0258	 | 	0.0035	 |
| 	Bangladesh	 | 	2022	 | 	0.0258	 | 	0.0035	 |

fact_gross_price
| 	product_code	 | 	fiscal_year	 | 	gross_price	 |
| 	-:	 | 	-:	 | 	-:	 |
| 	1	 | 	2018	 | 	19.363	 |
| 	1	 | 	2019	 | 	19.3442	 |
| 	1	 | 	2020	 | 	22.1317	 |
| 	1	 | 	2021	 | 	21.7795	 |
| 	1	 | 	2022	 | 	23.992	 |
| 	2	 | 	2018	 | 	19.5743	 |
| 	2	 | 	2019	 | 	18.5072	 |
| 	2	 | 	2020	 | 	20.7734	 |
| 	2	 | 	2021	 | 	22.9729	 |
| 	2	 | 	2022	 | 	23.6298	 |

fact_manufacturing_cost
| 	product_code	 | 	cost_year	 | 	manufacturing_cost	 |
| 	-:	 | 	-:	 | 	-:	 |
| 	1	 | 	2018	 | 	5.9469	 |
| 	1	 | 	2019	 | 	5.5306	 |
| 	1	 | 	2020	 | 	6.3264	 |
| 	1	 | 	2021	 | 	6.59	 |
| 	1	 | 	2022	 | 	7.1831	 |
| 	2	 | 	2018	 | 	5.8958	 |
| 	2	 | 	2019	 | 	5.4242	 |
| 	2	 | 	2020	 | 	6.4789	 |
| 	2	 | 	2021	 | 	6.8199	 |
| 	2	 | 	2022	 | 	7.3655	 |


fact_post_invoice_deduction
| 	customer_code	 | 	product_code	 | 	date	 | 	discounts_pct	 | 	other_deductions_pct	 |
| 	-:	 | 	-:	 | 	-:	 | 	-:	 | 	-:	 |
| 	1	 | 	1	 | 	2021-09-01	 | 	0.243105105	 | 	0.064459945	 |
| 	1	 | 	2	 | 	2021-10-01	 | 	0.318823445	 | 	0.091317288	 |
| 	1	 | 	3	 | 	2021-09-01	 | 	0.277440802	 | 	0.064933693	 |
| 	1	 | 	4	 | 	2021-10-01	 | 	0.318786084	 | 	0.092226504	 |
| 	2	 | 	1	 | 	2021-09-01	 | 	0.309472563	 | 	0.075799178	 |
| 	2	 | 	2	 | 	2021-10-01	 | 	0.262301248	 | 	0.09568491	 |
| 	2	 | 	3	 | 	2021-09-01	 | 	0.227948668	 | 	0.094501586	 |
| 	2	 | 	4	 | 	2021-10-01	 | 	0.228410097	 | 	0.074617767	 |

fact_pre_invoice_deduction
| 	customer_code	 | 	fiscal_year	 | 	pre_invoice_discount_pct	 |
| 	-:	 | 	-:	 | 	-:	 |
| 	1	 | 	2018	 | 	0.082442198	 |
| 	1	 | 	2019	 | 	0.077658613	 |
| 	1	 | 	2020	 | 	0.073457811	 |
| 	1	 | 	2021	 | 	0.070269476	 |
| 	1	 | 	2022	 | 	0.10567783	 |
| 	2	 | 	2018	 | 	0.295567708	 |
| 	2	 | 	2019	 | 	0.257654803	 |
| 	2	 | 	2020	 | 	0.225480979	 |
| 	2	 | 	2021	 | 	0.206107124	 |
| 	2	 | 	2022	 | 	0.29309271	 |





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
