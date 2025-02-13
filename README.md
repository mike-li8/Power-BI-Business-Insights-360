# Power BI Business Insights 360


## Problem Statement and Project Objective
The [Codebasics](https://codebasics.io/) [Data Analytics Bootcamp](https://codebasics.io/bootcamps/data-analytics-bootcamp-with-practical-job-assistance) exhibits a fictional company called AtliQ Technologies. AtliQ was rapidly proliferating to various markets around the world. However, AtliQ relied on Excel files for their data analytics needs. Since AtliQ's data was spread across multiple large tables (some containing over a million records), analyzing them in Excel was cumbersome. Moreover, stakeholders found that static reports produced from Excel pivot tables were difficult and time-consuming to digest. This weakened data anaytics capability hindered AtliQ's success when they attempted to expand to markets in Latin America.

The objective of this project is to create a Power BI dashboard which stakeholders from various business verticals (**finance**, **sales**, **marketing**, **supply chain**, and **executive**) can use to effectively and efficiently gather insights from data to help inform important company decisions. The interactive and visual nature of Power BI dashboards should help stakeholders better interpret the data with less time compared to static reports produced in Excel.


## AtliQ Business Model
### Overview
AtliQ manufactures computer hardware **products** (e.g., mouse, keyboard, printer, monitor) and then sells them to various **customers** which are stores such as Amazon and Best Buy. Hence, AtliQ's customers are in the form of <ins>store businesses</ins> (e.g., Amazon, Best Buy) and should not be confused with customers in the form of people (i.e., the people purchasing products from Amazon or Best Buy).

### Customers
AtliQ's customers are categorized into two different **platforms**:
1. Brick & Motar
   * stores that have physical location(s)
2. E-Commerce
   * stores which only sell products online

AtliQ's customers are categorized into three different **channels**:
1. Retailer
   * Stores not owned by AtliQ (e.g. Amazon, Best Buy)
3. Direct
   * Stores owned by AtliQ. These are AltiQ Exclusive and AtliQ E-Store.
5. Distributor
   * Some markets have laws/regulations which only allow AtliQ to sell products to a distributor type customer within that market. AtliQ sells products to the distributor; the distributor then sells the products to various stores within that market.

### Condensed Profit and Loss (P&L) Statement
This example of a simplified P&L statement should give a better understanding of AtliQ's business model. In this example, the P&L calculations and values are derived from one sales transaction of one product being sold to one customer.
| Line Item | Description | P&L Value Calculation | P & L Value |
| :- | :- | :- | -: |
| Gross Price |  The base price of a product | `not applicable` | $50.00 |
| Pre-Invoice Deduction | For every fiscal year, the sales team determines a pre-invoice deduction percentage for each <ins>specific customer</ins>. The pre-invoice deduction percentage is based on AtliQ's relationship and experience with the customer. The pre-invoice deduction is applied to the gross price of the product before it is billed to the customer. In this example, the customer receives a pre-invoice deduction of 10% of gross price. | `$50.00 * 0.10` | $5.00 |
| Net Invoice Sales | The amount of money that is billed to the customer to obtain the product. | `$50.00 - $5.00` | $45.00 |
| Post-Invoice Deudctions | For each calendar month, the sales team determines a post-invoice deduction percentage based on a specific <ins>customer and product</ins>. For example, if AtliQ sells a product to a customer and that customer agrees to display the product at a prime location within the store during a specific calendar month, AtliQ may pay that customer a post-invoice deduction. AtliQ pays a post-invoice deduction amount as a rebate to the customer after net invoice sales. In this example, the customer receives a post-invoice deduction of 20% of net invoice sales. | `$45.00 * 0.20` | $9.00 |
| Net Sales | AtliQ's Revenue | `$45.00 - $9.00` | $36.00 |
| Cost of Goods Sold (COGS) | Expenses AtliQ incurs such as manufacturing products, shipping products, and storing products in warehouses. | `not applicable` | $16.00 |
| Gross Margin | AtliQ's Profit after deducing COGS. | `$36.00 - $16.00` | $20.00 |
| Operational Expenses | Expenses AtliQ incurs from activities such as advertising and promotions for products performed by the marketing team. | `not applicable` | $15.00 |
| Net Profit | AtliQ's profit after deducting operational expenses | `$20.00 - $15.00` | $5.00 |


### AtliQ Fiscal Year
AtliQ's fiscal year begins in September and ends in August the following year. The example below shows AtliQ's fiscal dates (for fiscal year 2021) compared to calendar dates.
| 	Calendar Month and Year	 | 	AtliQ Fiscal Year	 | 	AtliQ Fiscal Month Number | 	AtliQ Fiscal Quarter	 |
| 	-:	 | 	-:	 | 	-:	 | 	-:	 |
| 	September 2020	 | 	2021	 | 	1	 | 	Q1	 |
| 	October 2020	 | 	2021	 | 	2	 | 	Q1	 |
| 	November 2020	 | 	2021	 | 	3	 | 	Q1	 |
| 	December 2020	 | 	2021	 | 	4	 | 	Q2	 |
| 	January 2021	 | 	2021	 | 	5	 | 	Q2	 |
| 	February 2021	 | 	2021	 | 	6	 | 	Q2	 |
| 	March 2021	 | 	2021	 | 	7	 | 	Q3	 |
| 	April 2021	 | 	2021	 | 	8	 | 	Q3	 |
| 	May 2021	 | 	2021	 | 	9	 | 	Q3	 |
| 	June 2021	 | 	2021	 | 	10	 | 	Q4	 |
| 	July 2021	 | 	2021	 | 	11	 | 	Q4	 |
| 	August 2021	 | 	2021	 | 	12	 | 	Q4	 |



## Data Sources
### Data Tables Prepared by Data Engineer
AtliQ's data engineers prepared various dimension and fact tables and stored them in a MySQL database schema.

#### Dimension Tables
Sample records from each table are provided below. For readability, primary key values for some tables have been converted to natural numbers.

**dim_market**
| market | sub_zone | region |
| :- | :- | :- |
| Japan | ROA | APAC |
| Sweden | NE | EU |
| Brazil | LATAM | LATAM |

`market` is a primary key field.

**dim_customer**
| 	customer_code	 | 	customer	 | 	market	 | 	platform	 | 	channel	 |
| 	-:	 | 	:-	 | 	:-	 | 	:-	 | 	:-	 |
| 	1	 | 	Amazon	 | 	USA	 | 	E-Commerce	 | 	Retailer	 |
| 	2	 | 	Amazon	 | 	Japan	 | 	E-Commerce	 | 	Retailer	 |
| 	3	 | 	Staples	 | 	USA	 | 	Brick & Mortar	 | 	Retailer	 |
| 	4	 | 	Staples	 | 	Canada	 | 	Brick & Mortar	 | 	Retailer	 |
| 	5	 | 	AltiQ Exclusive	 | 	South Korea	 | 	Brick & Mortar	 | 	Direct	 |
| 	6	 | 	Atliq e Store	 | 	Newzealand	 | 	E-Commerce	 | 	Direct	 |
| 	7	 | 	Neptune	 | 	China	 | 	Brick & Mortar	 | 	Distributor	 |

`customer_code` is a primary key field. 

**dim_product**
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
|  10 | 	N & S	 | 	Storage	 | 	External&nbsp;Solid&nbsp;State&nbsp;Drives	 | 	AQ Neuer SSD	 | 	Premium	 |

`product_code` is a primary key field.


#### Fact Tables
Sample records from each table are provided below.

fact_forecast_monthly
| 	date	 | 	product_code	 | 	division	 | 	category	 | 	product	 | 	customer_code	 | 	customer_name	 | 	market	 | 	platform	 | 	channel	 | 	forecast_quantity	 |
| 	-:	 | 	-:	 | 	:-	 | 	:-	 | 	:-	 | 	-:	 | 	:-	 | 	:-	 | 	:-	 | 	:-	 | 	-:	 |
| 	2018-09-01	 | 	1	 | 	P & A	 | 	Graphic Card	 | 	AQ Mforce Gen Y	 | 	1	 | 	Amazon	 | 	USA	 | 	E-Commerce	 | 	Retailer	 | 	107	 |
| 	2018-09-01	 | 	2	 | 	P & A	 | 	Graphic Card	 | 	AQ Mforce Gen Y	 | 	2	 | 	Amazon	 | 	Japan	 | 	E-Commerce	 | 	Retailer	 | 	13	 |
| 	2018-10-01	 | 	3	 | 	P & A	 | 	Mouse	 | 	AQ Master wired x1 Ms	 | 	4	 | 	Staples	 | 	Canada	 | 	Brick&nbsp;&&nbsp;Mortar	 | 	Retailer	 | 	63	 |
| 	2018-10-01	 | 	4	 | 	P & A	 | 	Mouse	 | 	AQ&nbsp;Master&nbsp;wired&nbsp;x1&nbsp;Ms	 | 	4	 | 	Staples	 | 	Canada	 | 	Brick & Mortar	 | 	Retailer	 | 	81	 |
| 	2018-11-01	 | 	5	 | 	PC	 | 	Business Laptop	 | 	AQ BZ Compact	 | 	5	 | 	AltiQ Exclusive	 | 	South Korea	 | 	Brick & Mortar	 | 	Direct	 | 	186	 |
| 	2018-11-01	 | 	6	 | 	PC	 | 	Business Laptop	 | 	AQ BZ Compact	 | 	2	 | 	Amazon	 | 	Japan	 | 	E-Commerce	 | 	Retailer	 | 	19	 |
| 	2018-12-01	 | 	7	 | 	N & S	 | 	Wi fi extender	 | 	AQ Wi Power Dx1	 | 	3	 | 	Staples	 | 	USA	 | 	Brick & Mortar	 | 	Retailer	 | 	91	 |
| 	2018-12-01	 | 	8	 | 	N & S	 | 	Wi fi extender	 | 	AQ Wi Power Dx2	 | 	6	 | 	Atliq e Store	 | 	Newzealand	 | 	E-Commerce	 | 	Direct	 | 	121	 |
| 	2019-01-01	 | 	9	 | 	N & S	 | 	External Solid State Drives	 | 	AQ Digit SSD	 | 	7	 | 	Neptune	 | 	China	 | 	Brick & Mortar	 | 	Distributor	 | 	106	 |
| 	2019-01-01	 | 	10	 | 	N & S	 | 	External&nbsp;Solid&nbsp;State&nbsp;Drives	 | 	AQ Neuer SSD	 | 	3	 | 	Staples	 | 	USA	 | 	Brick & Mortar	 | 	Retailer	 | 	90	 |

Notes:
* This table contains data on the predicted quantity of a product required for a specific customer, on a monthly level.
* The data engineer provided this table in **denormalized** format.
* The columns `date`, `product_code`, and `customer_code` make up a **composite primary key**.


fact_sales_monthly
| 	date	 | 	product_code	 | 	division	 | 	category	 | 	product	 | 	customer_code	 | 	customer_name	 | 	market	 | 	platform	 | 	channel	 | 	sold_quantity	 |
| 	-:	 | 	-:	 | 	:-	 | 	:-	 | 	:-	 | 	-:	 | 	:-	 | 	:-	 | 	:-	 | 	:-	 | 	-:	 |
| 	2018-09-01	 | 	1	 | 	P & A	 | 	Graphic Card	 | 	AQ Mforce Gen Y	 | 	1	 | 	Amazon	 | 	USA	 | 	E-Commerce	 | 	Retailer	 | 	70	 |
| 	2018-09-01	 | 	2	 | 	P & A	 | 	Graphic Card	 | 	AQ Mforce Gen Y	 | 	2	 | 	Amazon	 | 	Japan	 | 	E-Commerce	 | 	Retailer	 | 	152	 |
| 	2018-10-01	 | 	3	 | 	P & A	 | 	Mouse	 | 	AQ Master wired x1 Ms	 | 	4	 | 	Staples	 | 	Canada	 | 	Brick&nbsp;&&nbsp;Mortar	 | 	Retailer	 | 	129	 |
| 	2018-10-01	 | 	4	 | 	P & A	 | 	Mouse	 | 	AQ&nbsp;Master&nbsp;wired&nbsp;x1&nbsp;Ms	 | 	4	 | 	Staples	 | 	Canada	 | 	Brick & Mortar	 | 	Retailer	 | 	60	 |
| 	2018-11-01	 | 	5	 | 	PC	 | 	Business Laptop	 | 	AQ BZ Compact	 | 	5	 | 	AltiQ Exclusive	 | 	South Korea	 | 	Brick & Mortar	 | 	Direct	 | 	164	 |
| 	2018-11-01	 | 	6	 | 	PC	 | 	Business Laptop	 | 	AQ BZ Compact	 | 	2	 | 	Amazon	 | 	Japan	 | 	E-Commerce	 | 	Retailer	 | 	158	 |
| 	2018-12-01	 | 	7	 | 	N & S	 | 	Wi fi extender	 | 	AQ Wi Power Dx1	 | 	3	 | 	Staples	 | 	USA	 | 	Brick & Mortar	 | 	Retailer	 | 	163	 |
| 	2018-12-01	 | 	8	 | 	N & S	 | 	Wi fi extender	 | 	AQ Wi Power Dx2	 | 	6	 | 	Atliq e Store	 | 	Newzealand	 | 	E-Commerce	 | 	Direct	 | 	66	 |
| 	2019-01-01	 | 	9	 | 	N & S	 | 	External Solid State Drives	 | 	AQ Digit SSD	 | 	7	 | 	Neptune	 | 	China	 | 	Brick & Mortar	 | 	Distributor	 | 	140	 |
| 	2019-01-01	 | 	10	 | 	N & S	 | 	External&nbsp;Solid&nbsp;State&nbsp;Drives	 | 	AQ Neuer SSD	 | 	3	 | 	Staples	 | 	USA	 | 	Brick & Mortar	 | 	Retailer	 | 	61	 |

Notes:
* This table contains data on the actual sold quantity of a product for a specific customer, on a monthly level.
* The data engineer provided this table in **denormalized** format.
* The columns `date`, `product_code`, and `customer_code` make up a **composite primary key**.


freight_cost
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

Notes:
* Freight cost is one component of COGS. This table contains data at a fiscal year level on freight cost (as a percentage of net sales) for each specific market.
* The columns `market` and `fiscal_year` make up a **composite primary key**.


gross_price
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

Notes:
* Gross price is the base price of a product. This table contains data on the gross price of each specific product on a fiscal year level. 
* The columns `product_code` and `fiscal_year` make up a **composite primary key**.


manufacturing_cost
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


Notes:
* Manufacturing cost is one component of COGS. This table contains data at a fiscal year level on manufacturing cost ($) for each specific product.
* The columns `product_code` and `cost_year` make up a **composite primary key**.



post_invoice_deductions
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

Notes:
* This table contains data on post invoice deductions (as a percentage of net invoice sales) of a product for a specific customer, on a monthly level.
* The columns `customer_code`, `product_code` and `date` make up a **composite primary key**.


pre_invoice_deductions
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

Notes:
* This table contains data on pre invoice deductions (as a percentage of gross price) for each specific customer, on a fiscal year level.
* The columns `customer_code`, and `fiscal_year` make up a **composite primary key**.

### Additional Data Tables
Additional data tables were provided in stakeholder meetings. Sample records from each table are provided below.

operational_expenses
| 	market	 | 	fiscal_year	 | 	ads_promotions_pct	 | 	other_operational_expense_pct	 |
| 	:-	 | 	-:	 | 	-:	 | 	-:	 |
| 	Brazil	 | 	2018	 | 	0.11178	 | 	0.17172	 |
| 	Brazil	 | 	2019	 | 	0.156975	 | 	0.21147	 |
| 	Brazil	 | 	2020	 | 	0.14214	 | 	0.185606	 |
| 	Brazil	 | 	2021	 | 	0.1451875	 | 	0.203414	 |
| 	Brazil	 | 	2022	 | 	0.18952	 | 	0.196524	 |
| 	Canada	 | 	2018	 | 	0.141264	 | 	0.363528	 |
| 	Canada	 | 	2019	 | 	0.125895	 | 	0.27489	 |
| 	Canada	 | 	2020	 | 	0.101043	 | 	0.231132	 |
| 	Canada	 | 	2021	 | 	0.143117	 | 	0.283305	 |
| 	Canada	 | 	2022	 | 	0.314356	 | 	0.365959	 |

Notes:
* Provided in .csv format
* This table contains data on operational expenses (as a percentage of net sales) for each specific market, on a fiscal year level.
* The columns `market`, and `fiscal_year` make up a **composite primary key**.

targets
| 	market	 | 	month	 | 	ns_target	 | 	gm_target	 | 	np_target	 |
| 	:-	 | 	-:	 | 	-:	 | 	-:	 | 	-:	 |
| 	France	 | 	9/1/2021	 | 	$10,198,819.89	 | 	$3,346,388.95	 | 	-$725,768.42	 |
| 	France	 | 	10/1/2021	 | 	$15,549,771.95	 | 	$4,403,518.54	 | 	-$1,422,866.33	 |
| 	France	 | 	11/1/2021	 | 	$15,904,636.14	 | 	$6,218,833.51	 | 	-$916,393.33	 |
| 	France	 | 	12/1/2021	 | 	$17,697,536.05	 | 	$4,805,448.09	 | 	-$1,607,007.06	 |
| 	Indonesia	 | 	9/1/2021	 | 	$8,064,974.87	 | 	$2,796,600.63	 | 	-$1,089,126.47	 |
| 	Indonesia	 | 	10/1/2021	 | 	$10,900,556.90	 | 	$3,853,546.03	 | 	-$1,278,820.63	 |
| 	Indonesia	 | 	11/1/2021	 | 	$11,918,830.63	 | 	$4,232,776.48	 | 	-$1,673,999.76	 |
| 	Indonesia	 | 	12/1/2021	 | 	$12,657,658.69	 | 	$4,186,339.00	 | 	-$2,248,949.51	 |

Notes:
* Provided in .xlsx format
* This table contains data on benchmark targets set by AtliQ (for net sales, gross margin, and net profit). Target data is available for each specific market on a monthly level.
* The columns `market`, and `month` make up a **composite primary key**.

marketshare
| 	sub_zone	 | 	category	 | 	fy_desc	 | 	total_market_sales_$	 | 	atliq_sales_$	 | 	dale_sales_$	 | 	innovo_sales_$	 | 	pacer_sales_$	 | 	bp_sales_$	 | 	others_sales_$	 |
| 	:-	 | 	:-	 | 	-:	 | 	-:	 | 	-:	 | 	-:	 | 	-:	 | 	-:	 | 	-:	 | 	-:	 |
| 	LATAM	 | 	Business&nbsp;Laptop	 | 	2019	 | 	1084.4776	 | 	0.286	 | 	255.9367136	 | 	117.7308883	 | 	82.41162178	 | 	57.68813525	 | 	570.4242411	 |
| 	LATAM	 | 	Business Laptop	 | 	2020	 | 	1523.0215	 | 	1.04346	 | 	319.834515	 | 	102.3470448	 | 	84.94804718	 | 	54.24393374	 | 	960.6044993	 |
| 	LATAM	 | 	Business Laptop	 | 	2021	 | 	1813.3458	 | 	1.34904	 | 	377.1759264	 | 	128.239815	 | 	93.61506493	 | 	55.14312044	 | 	1157.822833	 |
| 	LATAM	 | 	Business Laptop	 | 	2022	 | 	2782.7793	 | 	10.44978	 | 	550.9903014	 | 	333.3491323	 | 	136.6731443	 | 	350.016589	 | 	1401.300353	 |
| 	LATAM	 | 	Gaming Laptop	 | 	2019	 | 	1178.78	 | 	0.05588	 | 	278.19208	 | 	111.276832	 | 	50.0745744	 | 	57.86395264	 | 	681.316681	 |
| 	LATAM	 | 	Gaming Laptop	 | 	2020	 | 	1799.9345	 | 	0.15862	 | 	435.584149	 | 	150.2765314	 | 	132.2433476	 | 	94.67421479	 | 	986.9976372	 |
| 	LATAM	 | 	Gaming Laptop	 | 	2021	 | 	2417.7944	 | 	0.83688	 | 	469.0521136	 | 	197.0018877	 | 	133.9612836	 | 	161.5415479	 | 	1455.400687	 |
| 	LATAM	 | 	Gaming Laptop	 | 	2022	 | 	3091.977	 | 	8.40752	 | 	927.5931	 | 	389.589102	 | 	179.2109869	 | 	331.1507367	 | 	1256.025554	 |

Notes:
* Provided in .xlsx format
* This table contains data on the marketshare of various personal computer (PC) manufacturers (atliq, dale, innovo, pacer, bp). This marketshare data is available for each specific sub zone, product category (PC type product categories only) and fiscal year.



## ETL (extract transform load) and Data Cleaning in Power Query
The data tables from MySQL, .csv, and .xlsx were imported into **Power Query**:</br>
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/PowerQuery%20Initial%20Import.PNG?raw=true)


### Additional Queries created using M-Language
#### Add step to query: `fact_forecast_monthly`
Add a step to
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/fact_forecast_Monthly_icon.PNG?raw=true)
to remove unnecessary redundant columns:
```
= Table.SelectColumns(fact_forecast_monthly, {"date", "product_code", "customer_code", "forecast_quantity"})
```
Sample records from query result:</br>
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/Forecast_Monthly.PNG?raw=true)


#### Add step to query: `fact_sales_monthly`
Add a step to
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/fact_sales_monthly_icon.PNG?raw=true)
to remove unnecessary redundant columns:
```
= Table.SelectColumns(fact_sales_monthly,{"date", "product_code", "customer_code", "sold_quantity"})
```
Sample records from query result:</br>
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/Sales_Monthly.PNG?raw=true)


#### Create new query: `Last_Sales_Month`
Create new query
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/Last_Sales_Month%20Icon.PNG?raw=true)
to generate a single date value representing the last month sales data is available in the table `fact_sales_monthly`:

```
let
    LastSalesMonth = List.Max(fact_sales_monthly[date])
in
    LastSalesMonth
```
Query result:</br>
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/Last_Sales_Month.PNG?raw=true)


#### Create new query: `Refresh Date`
Create new query
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/Refresh%20Date%20Icon.PNG?raw=true)
to generate a single date value representing the latest day the refresh button was pressed for this dashboard:
```
= DateTime.Date(DateTime.LocalNow())
```
Query result:</br>
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/Refresh%20Date.PNG?raw=true)



#### Create new query: `Combine Sales and Forecast`
Create new query
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/Combined%20Sales%20and%20Forecast%20Icon.PNG?raw=true)
:
```
let
    // Filter the forecast table to only include records with dates where sales data is not avaliable
    #"FilterForecastTable" = Table.SelectRows(fact_forecast_monthly, each [date] > Last_Sales_Month),

    // Rename sold_quanity column in sales table to Qty
    #"Rename sold_quantity to Qty" = Table.RenameColumns(fact_sales_monthly, {{"sold_quantity", "Qty"}}),

    // Rename forecast_quantity column in forecast table to Qty
    #"Rename forecast_quantity to Qty" = Table.RenameColumns(fact_forecast_monthly, {{"forecast_quantity", "Qty"}}),

    // Union of Sales and Forecast tables
    UnionSalesForecast = Table.Combine({#"Rename sold_quantity to Qty", #"Rename forecast_quantity to Qty"})
in
    UnionSalesForecast
```
Sample records from query result:<br>
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/Combined%20Sales%20and%20Forecast.PNG?raw=true)

`Combine Sales and Forecast` query combines the `fact_sales_monthly` query with the `fact_forecast_monthly` query based on the diagram below (similar to SQL Union):
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/Combined%20Sales%20and%20Forecast%20Diagram.PNG?raw=true)

`Combine Sales and Forecast` contains:
1. All sales data from `fact_sales_monthly` up to and including the last sales month (December 2021).
2. Forecasted sales data from `fact_forecast_monthly` starting from January 2022 onwards.


#### Create new query: `Fact_Actuals_Estimates`
Create new query
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/Fact_Actuals_Estimates%20Icon.PNG?raw=true)
to:
* Left join `Combine Sales and Forecast` with `gross_price`
* Left join `Combine Sales and Forecast` with `pre_invoice_deductions`
* Add calculated column for gross sales
* Add calculated column for net invoice sales

```
let
    // Add fiscal year column to act as a key field matching records for a left join
    #"Add fiscal year column" = Table.AddColumn(#"Combine Sales and Forecast", "fiscal_year", each Date.Year(Date.AddMonths([date],4))),
    #"Changed fiscal_year column datatype" = Table.TransformColumnTypes(#"Add fiscal year column",{{"fiscal_year", type text}}),

    // Left join with gross_price table
    #"Left Join with gross_price" = Table.NestedJoin(#"Changed fiscal_year column datatype", {"product_code", "fiscal_year"}, gross_price, {"product_code", "fiscal_year"}, "gross_price", JoinKind.LeftOuter),
    #"Expanded gross_price" = Table.ExpandTableColumn(#"Left Join with gross_price", "gross_price", {"gross_price"}, {"gross_price"}),

    // Calculated column for gross_sales_amount
    #"Calculated Column for gross_sales_amount" = Table.AddColumn(#"Expanded gross_price", "gross_sales_amount", each [Qty] * [gross_price]),

    // Left join with pre_invoice_deductions table
    #"Left Join with pre_invoice_deductions" = Table.NestedJoin(#"Calculated Column for gross_sales_amount", {"customer_code", "fiscal_year"}, pre_invoice_deductions, {"customer_code", "fiscal_year"}, "pre_invoice_deductions", JoinKind.LeftOuter),
    #"Expanded pre_invoice_deductions" = Table.ExpandTableColumn(#"Left Join with pre_invoice_deductions", "pre_invoice_deductions", {"pre_invoice_discount_pct"}, {"pre_invoice_discount_pct"}),

    // Calculated column for net_invoice_sales_amount
    #"Calculated column for net_invoice_sales_amount" = Table.AddColumn(#"Expanded pre_invoice_deductions", "net_invoice_sales_amount", each [gross_sales_amount] - [gross_sales_amount] * [pre_invoice_discount_pct]),

    // Remove unnecessary columns used to help with the join
    #"Removed unnecessary redundant columns" = Table.RemoveColumns(#"Calculated column for net_invoice_sales_amount",{"fiscal_year", "gross_price", "pre_invoice_discount_pct"}),

    // Set datatypes for columns
    #"Set columns to appropriate datatypes" = Table.TransformColumnTypes(#"Removed unnecessary redundant columns",{{"gross_sales_amount", Currency.Type}, {"net_invoice_sales_amount", Currency.Type}})
in
    #"Set columns to appropriate datatypes"
```
Sample records from query result:</br>
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/Fact_Actuals_Estimates.PNG?raw=true)




#### Create new query: `dim_date`
Create new query
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/dim_date%20icon.PNG?raw=true)
to create a new date dimension table with three columns:
* `date` for each calendar date. This is a primary key field.
* `month` for calendar month (first day of the calendar month)
* `fiscal_year` for AtliQ’s fiscal year for each respective calendar date/month
```
let
    // Find minimum date from forecast table
    MinForecastDate = List.Min(fact_forecast_monthly[date]),
    // Find minimum date from sales table
    MinSalesDate = List.Min(fact_sales_monthly[date]),
    // Find the lower of MinForecastDate and MinSalesDate. This is the lowest date in dim_date table.
    StartDate = List.Min({MinForecastDate, MinSalesDate}),

    // Find maximum date from forecast table
    MaxForecastDate = List.Max(fact_forecast_monthly[date]),
    // Find maximum date from sales table
    MaxSalesDate = List.Max(fact_sales_monthly[date]),
    // Find the higher of MaxForecastDate and MaxSalesDate. This is the highest date in dim_date table.
    EndDate = List.Max({MaxForecastDate, MaxSalesDate}),

    // Create a list of dates from StartDate to EndDate and sort ascending
    DateList = List.Dates(StartDate, Duration.Days(EndDate - StartDate) + 1, #duration(1, 0, 0, 0)),
    DateList_SortASC = List.Sort(DateList,Order.Ascending),

    // Convert list of dates to table and assign appropriate datatype to date column
    DateTable = Table.FromList(DateList_SortASC, Splitter.SplitByNothing(), {"date"}),
    #"Changed data type of date column" = Table.TransformColumnTypes(DateTable,{{"date", type date}}),

    // Since data in forecast and sales tables are aggregated on a monthly level,
    // add a month column representing the first day of the month
    #"Add month column" = Table.AddColumn(#"Changed data type of date column", "month", each Date.StartOfMonth([date]), type date),

    // Add column for AtliQ's fiscal year by adding 4 months to the calendar month
    #"Add Fiscal Year column" = Table.AddColumn(#"Add month column", "fiscal_year", each Text.From(Date.Year(Date.AddMonths([month], 4))), type text)

in
    #"Add Fiscal Year column"
```

Sample records from query result:<br>
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/dim_date.PNG?raw=true)



#### Add two steps to query: `Marketshare`
Add two additional steps to the ![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/Marketshare%20Icon.PNG?raw=true) query:
1. Transform the table to make it more suitable for building data model and visuals later.
```
= Table.UnpivotOtherColumns(marketshare, {"sub_zone", "category", "fy_desc", "total_market_sales_$"}, "Manufacturer", "sales_$")
```
2. Remove the text "sales_$" after the "_" delimiter for each manufacturer name.
```
= Table.TransformColumns(marketshare, {{"Manufacturer", each Text.BeforeDelimiter(_, "_"), type text}})
```
Sample records from query result:<br>
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/Marketshare.PNG?raw=true)

### Data Cleaning
Data cleaning is a vital step to reduce the likelihood of errors and biases when business stakeholders use the final dashboard to inform the decision-making process.
Various data cleaning tasks were formed using Power Query (this list is not exhaustive):
* Identifying duplicate values and rectifying them with an appropriate method
* Investigating outliers in quantitative fields with business stakeholders and removing them if appropriate.
* Text fields: fixing spelling mistakes, removing extra white space
* Ensuring primary key fields contain unique values
* Ensuring composite primary key fields contain unique combinations of values
* Connecting with business stakeholders to determine an appropriate interpretation of null/blank values and rectifying them with an appropriate method if needed.


### Final Queries Loaded
The image below shows the final queries loaded from Power Query to Power BI. To improve query load time, queries not required to build the Power BI dashboard have their load disabled (queries in *italic* in the image have their load disabled). Queries with their load disabled are either intermediate step queries or queries containing data that are already included in queries with their load enabled.<br>
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Power%20Query%20Screenshots/PowerQuery%20Final%20Queries.PNG?raw=true)









## Data Modelling
### DAX Calculated Tables
To complete the snowflake schema, three additional fact tables need to be created using DAX calculated table:
```
fiscal_year = ALLNOBLANKROW(dim_date[fiscal_year])
```

```
sub_zone = ALLNOBLANKROW(dim_market[sub_zone])
```

```
category = ALLNOBLANKROW(dim_product[category])
```

Data Model in Power BI
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Data%20Model%20Screenshots/DataModel.PNG?raw=true)

### DAX Calculated Columns
#### dim_date
```
fy_month_num = MONTH(DATE(YEAR(dim_date[date]),MONTH(dim_date[date]) + 4, 1))
```

```
quarters = "Q" & ROUNDUP(dim_date[fy_month_num]/3,0)
```

```
ytd_ytg = 

var LASTSALESDATE = MAX(Last_Sales_Month[Last_Sales_Month])

var FY_MONTH_NUMBER = MONTH(DATE(YEAR(LASTSALESDATE),MONTH(LASTSALESDATE)+4, 1))

RETURN
IF(
    dim_date[fy_month_num] > FY_MONTH_NUMBER,
    "YTG",
    "YTD")
```

#### Fact_Actuals_Estimates

```
post_invoice_deduction_amount = 
var res = CALCULATE(
    MAX(post_invoice_deductions[discounts_pct]),
    RELATEDTABLE(post_invoice_deductions))
RETURN res * Fact_Actuals_Estimates[net_invoice_sales_amount]
```

```
post_invoice_other_deduction_amount = 
var res = CALCULATE(MAX(post_invoice_deductions[other_deductions_pct]), 
RELATEDTABLE(post_invoice_deductions))
RETURN res * Fact_Actuals_Estimates[net_invoice_sales_amount]
```

```
net_sales_amount = Fact_Actuals_Estimates[net_invoice_sales_amount] - Fact_Actuals_Estimates[post_invoice_deduction_amount] - Fact_Actuals_Estimates[post_invoice_other_deduction_amount]
```

```
manufacturing_cost = 
var res = CALCULATE(
    MAX(manufacturing_cost[manufacturing_cost]),
    RELATEDTABLE(manufacturing_cost))
RETURN res * Fact_Actuals_Estimates[Qty]
```

```
freight_cost = 
var res = CALCULATE(
    MAX(freight_cost[freight_pct]),
    RELATEDTABLE(freight_cost))
RETURN res * Fact_Actuals_Estimates[net_sales_amount]
```

```
other_cost = 
var res = CALCULATE(MAX(freight_cost[other_cost_pct]), 
RELATEDTABLE(freight_cost))
RETURN res * Fact_Actuals_Estimates[net_sales_amount]
```

```
ads_promotion = 
var res = CALCULATE(
    MAX('operational_expenses'[ads_promotions_pct]),
    RELATEDTABLE('operational_expenses'))
RETURN res * Fact_Actuals_Estimates[net_sales_amount]
```

```
other_operational_expense = 
var res = CALCULATE(
    MAX('operational_expenses'[other_operational_expense_pct]),
    RELATEDTABLE('operational_expenses'))
RETURN res * Fact_Actuals_Estimates[net_sales_amount]
```

































### Calculated Table for BM Toggle

![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Dashboard%20Screenshots/BM%20Toggle%20Image.PNG?raw=true)


```
BM Toggle Switch Table = 

VAR x = UNION(
    ROW("Primary_Key", 1, "Selection", "vs LY", "Selection_1", "Last Year: "),
    ROW("Primary_Key", 2, "Selection", "vs Target", "Selection_1", "Target: ")
)

RETURN x
```

![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Dashboard%20Screenshots/toggle%20switch%20table.PNG?raw=true)


### Basic DAX Measures for P&L Values


#### Gross Sales
```
GS $ = SUM(Fact_Actuals_Estimates[gross_sales_amount])
```

#### Net Invoice Sales
```
NIS $ = SUM(Fact_Actuals_Estimates[net_invoice_sales_amount])
```

#### Pre Invoice Deductions
```
Pre Invoice Deduction $ = [GS $] - [NIS $]
```

#### Post Invoice Deductions
```
Post Invoice Deduction $ = SUM(Fact_Actuals_Estimates[post_invoice_deduction_amount])
```

#### Post Invoice Other Deductions
```
Post Invoice Other Deduction $ = SUM(Fact_Actuals_Estimates[post_invoice_other_deduction_amount])
```

#### Total Post Invoice Deductions
```
Total Post Invoice Deduction $ = [Post Invoice Deduction $] + [Post Invoice Other Deduction $]
```

#### Filter Check
```
Customer / Product Filter Check = 
ISCROSSFILTERED(dim_product[product]) || ISFILTERED(dim_customer[customer])
```

#### Net Sales
```
NS $ = SUM(Fact_Actuals_Estimates[net_sales_amount])
```

```
NS $ LY = 
CALCULATE(
    [NS $],
    SAMEPERIODLASTYEAR(dim_date[date])
)
```

```
NS Target $ = 

VAR tgt = SUM(targets[ns_target])

RETURN
IF([Customer / Product Filter Check], BLANK(), tgt)
```

```
NS BM $ = 

// returns appropriate measure based on the toggle switch position
SWITCH(
    TRUE(),
    SELECTEDVALUE('BM Toggle Switch Table'[Primary_Key]) = 1, [NS $ LY],
    SELECTEDVALUE('BM Toggle Switch Table'[Primary_Key]) = 2, [NS Target $]
    )
```

```
Percent Change NS $ vs BM = 

VAR res = DIVIDE([NS $] - [NS BM $], ABS([NS BM $]), 0)

RETURN
IF(
    ISBLANK([NS $]) || ISBLANK([NS BM $]),
    BLANK(),
    res
)
```



#### Cost of Goods Sold
```
Manufacturing Cost $ = SUM(Fact_Actuals_Estimates[manufacturing_cost])
```

```
Freight Cost $ = SUM(Fact_Actuals_Estimates[freight_cost])
```

```
Other Cost $ = SUM(Fact_Actuals_Estimates[other_cost])
```

```
Total COGS $ = [Manufacturing Cost $] + [Freight Cost $] + [Other Cost $]
```

#### Total Sold Quantity
```
Quantity = SUM(Fact_Actuals_Estimates[Qty])
```



#### Gross Margin
```
GM $ = [NS $] - [Total COGS $]
```

```
GM Target $ = SUM(targets[gm_target])
```


```
GM % = DIVIDE([GM $],[NS $],0)
```

```
GM % LY =
CALCULATE(
    [GM %],
    SAMEPERIODLASTYEAR(dim_date[date])
)
```

```
GM % Target = DIVIDE([GM Target $], SUM(targets[ns_target]), 0)
```

```
GM % BM = 

// returns appropriate measure based on the toggle switch position
SWITCH(
    TRUE(),
    SELECTEDVALUE('BM Toggle Switch Table'[Primary_Key]) = 1, [GM % LY],
    SELECTEDVALUE('BM Toggle Switch Table'[Primary_Key]) = 2, [GM % Target]
)
```


```
Percent Change GM % vs BM = 

VAR res = DIVIDE([GM %] - [GM % BM], ABS([GM % BM]), 0)

RETURN
IF(
    ISBLANK([GM %]) || ISBLANK([GM % BM]),
    BLANK(),
    res
)
```



```
GM / Unit = DIVIDE([GM $],[Quantity],0)
```


#### Operational Expenses
```
Ads & Promotions $ = SUM(Fact_Actuals_Estimates[ads_promotion])
```

```
Other Operational Expense $ = SUM(Fact_Actuals_Estimates[other_operational_expense])
```

```
Operational Expense $ = [Ads & Promotions $] + [Other Operational Expense $]
```


#### Net Profit
```
NP $ = [GM $] - [Operational Expense $]
```

```
NP Target $ = SUM(targets[np_target])
```

```
NP % = DIVIDE([NP $], [NS $],0)
```

```
NP % LY =
CALCULATE(
    [NP %],
    SAMEPERIODLASTYEAR(dim_date[date])
)
```

```
NP % Target = DIVIDE([NP Target $], SUM(targets[ns_target]),0)
```

```
NP % BM = 

// returns appropriate measure based on the toggle switch position
SWITCH(
    TRUE(),
    SELECTEDVALUE('BM Toggle Switch Table'[Primary_Key]) = 1, [NP % LY],
    SELECTEDVALUE('BM Toggle Switch Table'[Primary_Key]) = 2, [NP % Target]
)
```


```
Percent Change NP % vs BM = 

VAR res = DIVIDE([NP %] - [NP % BM], ABS([NP % BM]), 0)

RETURN
IF(
    ISBLANK([NP %]) || ISBLANK([NP % BM]),
    BLANK(),
    res
)
```


```
NP / Unit = DIVIDE([NP $],[Quantity],0)
```

### Supply Chain Learnings and DAX Measures
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Supply%20Chain%20Screenshots/SupplyChain%20Basics.PNG?raw=true)


```
Sales Qty = 
CALCULATE(
    [Quantity],
    Fact_Actuals_Estimates[date] <= MAX(Last_Sales_Month[Last_Sales_Month])
)

```

```
Forecast Qty = 

VAR LASTSALESDATE = MAX(Last_Sales_Month[Last_Sales_Month])

RETURN
CALCULATE(
    SUM(fact_forecast_monthly[forecast_quantity]),
    fact_forecast_monthly[date] <= LASTSALESDATE
    )
```

```
Net Error = [Forecast Qty] - [Sales Qty]
```

```
Net Error LY =
CALCULATE(
    [Net Error],
    SAMEPERIODLASTYEAR(dim_date[date])
)
```

```
Percent Change Net Error = 

VAR res = DIVIDE([Net Error] - [Net Error LY], ABS([Net Error LY]))

RETURN
IF(
    ISBLANK([Net Error]) || ISBLANK([Net Error LY]),
    BLANK(),
    res
)
```


```
Net Error % = DIVIDE([Net Error],[Forecast Qty],0)
```



```
ABS Error = 
SUMX(
    DISTINCT(dim_date[month]),
    SUMX(
        DISTINCT(dim_product[product_code]),
        ABS([Net Error])
    )
)
```

```
ABS Error % = DIVIDE([ABS Error], [Forecast Qty],0)
```

```
ABS Error LY =
CALCULATE(
    [ABS Error],
    SAMEPERIODLASTYEAR(dim_date[date])
)
```

```
Percent Change ABS Error = 

VAR res = DIVIDE([ABS Error] - [ABS Error LY], ABS([ABS Error LY]))

RETURN
IF(
    ISBLANK([ABS Error]) || ISBLANK([ABS Error LY]),
    BLANK(),
    res
)
```




```
Forecast Accuracy % = 
IF(
    [ABS Error %] <> BLANK(),
    1 - [ABS Error %],
    BLANK()
)
```


```
Forecast Accuracy % LY = 
CALCULATE(
    [Forecast Accuracy %],
    SAMEPERIODLASTYEAR(dim_date[date])
)
```

```
Forecast Accuracy % BM = 
// returns appropriate measure based on the toggle switch position
SWITCH(
    TRUE(),
    SELECTEDVALUE('BM Toggle Switch Table'[Primary_Key]) = 1, [Forecast Accuracy % LY],
    SELECTEDVALUE('BM Toggle Switch Table'[Primary_Key]) = 2, BLANK()
)
```


```
Percent Change Forecast Accuracy % = 

VAR res = DIVIDE([Forecast Accuracy %] - [Forecast Accuracy % LY], ABS([Forecast Accuracy % LY]))

RETURN
IF(
    ISBLANK([Forecast Accuracy %]) || ISBLANK([Forecast Accuracy % LY]),
    BLANK(),
    res
)
```




```
Risk = 
IF(
    [Net Error] > 0,
    "EI",
    IF(
        [Net Error] < 0,
        "OOS",
        BLANK()
    )
)
```


### DAX for Visuals
#### Finance View: Profit and Loss Statement Using Matrix Visual
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Dashboard%20Screenshots/Profit%20and%20Loss%20Visual.PNG?raw=true)

P & L Columns
```
P & L Columns = 

// fetch all the values in fy_desc as the user can select any value from fy_desc
VAR x = ALLNOBLANKROW(fiscal_year[fy_desc])

RETURN
// adding all the values from fy_desc with below values
UNION(
    ROW("Col Header", "Chg"),       // ‘YoY Chg’ is a requirement from mock up
    ROW("Col Header", "Pct Chg"),     // ‘YoY Chg %’ is a requirement from mock up
    ROW("Col Header", "BM"),
    x
)
```
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Dashboard%20Screenshots/P%20and%20L%20Columns%20Table.PNG?raw=true)





P & L Rows</br>
![image alt](https://github.com/mike-li8/Power-BI-Business-Insights-360/blob/main/Dashboard%20Screenshots/P%20and%20L%20Rows%20Table.PNG?raw=true)



```
P & L Values = 

VAR res = 
SWITCH(
    TRUE(),
    // Main P&L Values in Finance View
    MAX('P & L Rows'[Primary_Key]) = 1, [GS $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 2, [Pre Invoice Deduction $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 3, [NIS $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 4, [Post Invoice Deduction $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 5, [Post Invoice Other Deduction $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 6, [Total Post Invoice Deduction $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 7, [NS $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 8, [Manufacturing Cost $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 9, [Freight Cost $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 10, [Other Cost $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 11, [Total COGS $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 12, [GM $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 13, [GM %]*100,
    MAX('P & L Rows'[Primary_Key]) = 14, [GM / Unit],
    MAX('P & L Rows'[Primary_Key]) = 15, [Operational Expense $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 16, [NP $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 17, [NP %]*100,
    MAX('P & L Rows'[Primary_Key]) = 18, [Ads & Promotions $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 19, [Other Operational Expense $]/1000000,
    MAX('P & L Rows'[Primary_Key]) = 20, [NP / Unit]
)

RETURN
IF(HASONEVALUE('P & L Rows'[Description]), res, [NS $]/1000000)
```


```
P & L LY = 
CALCULATE(
    [P & L Values],
    SAMEPERIODLASTYEAR(dim_date[date])
)
```


```
P & L Targets = 

VAR res =
SWITCH(
    TRUE(),
    MAX('P & L Rows'[Primary_Key]) = 7,
    IF([Customer / Product Filter Check], BLANK(), [NS Target $]/1000000),
    MAX('P & L Rows'[Primary_Key]) = 12,
    IF([Customer / Product Filter Check], BLANK(), [GM Target $]/1000000),
    MAX('P & L Rows'[Primary_Key]) = 13,
    [GM % Target]*100,
    MAX('P & L Rows'[Primary_Key]) = 16,
    IF([Customer / Product Filter Check], BLANK(), [NP Target $]/1000000),
    MAX('P & L Rows'[Primary_Key]) = 17,
    [NP % Target]*100
)

RETURN
IF(
    HASONEVALUE('P & L Rows'[Description]),
    res,
    IF(
        [Customer / Product Filter Check],
        BLANK(),
        [NS Target $]/1000000
    )
)
```


```
P & L BM = 
SWITCH(
    TRUE(),
    SELECTEDVALUE('BM Toggle Switch Table'[Primary_Key]) = 1, [P & L LY],
    SELECTEDVALUE('BM Toggle Switch Table'[Primary_Key]) = 2, [P & L Targets]
)
```



```
P & L Chg = 

VAR res = [P & L Values] - [P & L BM]

RETURN
IF(ISBLANK([P & L BM]) || ISBLANK([P & L Values]), BLANK(), res)
```


```
P & L Chg % = 

VAR res = DIVIDE([P & L Chg],ABS([P & L BM]),0) * 100

RETURN
IF(ISBLANK([P & L Values]) || ISBLANK([P & L BM]), BLANK(), res)
```



```
P & L Final Value = 
SWITCH(
    TRUE(),
    SELECTEDVALUE(fiscal_year[fy_desc]) = MAX('P & L Columns'[Col Header]), [P & L Values],
    MAX('P & L Columns'[Col Header]) = "BM", [P & L BM],
    MAX('P & L Columns'[Col Header]) = "Chg", [P & L Chg],
    MAX('P & L Columns'[Col Header]) = "Pct Chg", [P & L Chg %]
)
```

```
Selected P & L Row = 
IF(
    HASONEVALUE('P & L Rows'[Description]),
    SELECTEDVALUE('P & L Rows'[Description]),
    "Net Sales"
)
```


#### Executive View
```
AtliQ MS % = 

VAR atliq_sales = 
CALCULATE(
    SUM(marketshare[sales_$]),
    marketshare[Manufacturer] = "atliq"
)

VAR total_market_sales = 
CALCULATE(
    SUM(marketshare[total_market_sales_$]),
    marketshare[Manufacturer] = "atliq"
)

RETURN
DIVIDE(atliq_sales, total_market_sales,0)
```

```
Market Share % = 
DIVIDE(
    SUM(marketshare[sales_$]),
    SUM(marketshare[total_market_sales_$]),
    0
)
```

```
RC % = 
DIVIDE(
    [NS $],
    CALCULATE(
        [NS $],
        ALL(dim_market),
        ALL(dim_customer),
        ALL(dim_product)
    ),
    0
)
```






#### Sales and Marketing View: Performance Matrix Dyanamic Average Line, Bookmarks, Filter Slider

##### DAX measures to calculate average
```
Average GM% by Customer = 

AVERAGEX(
    VALUES(dim_customer[customer]),
    CALCULATE(
        [GM %],
        RELATEDTABLE(Fact_Actuals_Estimates)
    )
)
```


```
Average GM% by Market = 

AVERAGEX(
    VALUES(dim_market[market]),
    CALCULATE(
        [GM %],
        RELATEDTABLE(Fact_Actuals_Estimates)
    )
)
```


```
Average Net Profit % by Customer = 

AVERAGEX(
    VALUES(dim_customer[customer]),
    CALCULATE(
        [NP %],
        RELATEDTABLE(Fact_Actuals_Estimates)
    )
)
```


```
Average Net Profit % by Market = 

AVERAGEX(
    VALUES(dim_market[market]),
    CALCULATE(
        [NP %],
        RELATEDTABLE(Fact_Actuals_Estimates)
    )
)
```



```
Average NS $ by Customer = 

AVERAGEX(
    VALUES(dim_customer[customer]),
    SUMX(
        RELATEDTABLE(Fact_Actuals_Estimates),
        Fact_Actuals_Estimates[net_sales_amount]
    )
)
```

```
Average NS $ by Market = 

AVERAGEX(
    VALUES(dim_market[market]),
    SUMX(
        RELATEDTABLE(Fact_Actuals_Estimates),
        Fact_Actuals_Estimates[net_sales_amount]
    )
)
```






##### Field Parameters (same for S1, S2, S3)

```
Parameter_SalesViewScatterChart_Customers_Bookmark_S1 = {
    ("market", NAMEOF('dim_market'[market]), 0),
    ("customer", NAMEOF('dim_customer'[customer]), 1)
}
```


```
Parameter_SalesViewScatterChart_y_axis_Bookmark_S1 = {
    ("GM %", NAMEOF('Key Measures'[GM %]), 0),
    ("Net Profit %", NAMEOF('Key Measures'[NP %]), 1)
}
```


##### Average Lines (same for S1, S2, S3)
```
sales matrix horizontal average line bookmark S1 = 

VAR gm_pct_or_np_pct =
SELECTEDVALUE(
    Parameter_SalesViewScatterChart_y_axis_Bookmark_S1[Order])

VAR customer_hierarchy = 
SELECTEDVALUE(
    Parameter_SalesViewScatterChart_Customers_Bookmark_S1[Order])

RETURN
SWITCH(
    TRUE(),
    // GM % and market
    gm_pct_or_np_pct = 0 && customer_hierarchy = 0,
    [Average GM% by Market],
    // GM % and customer
    gm_pct_or_np_pct = 0 && customer_hierarchy = 1,
    [Average GM% by Customer],

    // Net Profit % and market
    gm_pct_or_np_pct = 1 && customer_hierarchy = 0,
    [Average Net Profit % by Market],
    // Net Profit % and customer
    gm_pct_or_np_pct = 1 && customer_hierarchy = 1,
    [Average Net Profit % by Customer]
)
```


```
sales view matrix vertical average line bookmark S1 = 

VAR selected_field_parameter =
SELECTEDVALUE(Parameter_SalesViewScatterChart_Customers_Bookmark_S1[Order])

RETURN
SWITCH(
    TRUE(),
    // market selected
    selected_field_parameter = 0,
    [Average NS $ by Market],
    // customer selected
    selected_field_parameter = 1,
    [Average NS $ by Customer]
)
```









##### Bookmark S2
```
SalesViewScatterChart_Bookmark_S2_Filter = 

VAR selected_y_axis = SELECTEDVALUE(Parameter_SalesViewScatterChart_y_axis_Bookmark_S2[Order])

RETURN
SWITCH(
    TRUE(),
    selected_y_axis = 0,
    IF(
        NOT(ISBLANK([GM %])) && NOT(ISBLANK([GM % BM])) &&
        [GM %] >= [GM % BM],
        "SHOW",
        "HIDE"
    ),

    selected_y_axis = 1,
    IF(
        NOT(ISBLANK([NP %])) && NOT(ISBLANK([NP % BM])) &&
        [NP %] >= [NP % BM],
        "SHOW",
        "HIDE"
    )
)
```

```
Parameter_Bookmark_S2_Slider = GENERATESERIES(0, 100, 1)
```



```
Parameter_Bookmark_S2_Slider Value = 

VAR whole_number = SELECTEDVALUE('Parameter_Bookmark_S2_Slider'[Parameter_Bookmark_S2_Slider])
VAR decimal_number = whole_number/100

RETURN
decimal_number
```



```
Bookmark_S2_Slider_Filter = 

VAR selected_y_axis = SELECTEDVALUE(Parameter_SalesViewScatterChart_y_axis_Bookmark_S2[Order])

VAR delta_gm_pct = ABS([GM %] - [GM % BM])

VAR delta_np_pct = ABS([NP %] - [NP % BM])

RETURN
SWITCH(
    TRUE(),
    // 0 - GM %
    selected_y_axis = 0,
    IF(
        delta_gm_pct >= [Parameter_Bookmark_S2_Slider Value],
        "SHOW",
        "HIDE"
    ),

    selected_y_axis = 1,
    // 1 - NP %
    IF(
        delta_np_pct >= [Parameter_Bookmark_S2_Slider Value],
        "SHOW",
        "HIDE"
    )
)
```

```
Bookmark S2 Button1 Text = 

VAR gm_pct_or_np_pct = 
SWITCH(
    TRUE(),
    SELECTEDVALUE(Parameter_SalesViewScatterChart_y_axis_Bookmark_S2[Order]) = 0,
    "GM %",
    SELECTEDVALUE(Parameter_SalesViewScatterChart_y_axis_Bookmark_S2[Order]) = 1,
    "NP %"
)

RETURN
"Only Show Customers that Meet or Exceed " & gm_pct_or_np_pct & " BM"
```


##### Bookmark S3
```
SalesViewScatterChart_Bookmark_S3_Filter = 

VAR selected_y_axis = SELECTEDVALUE(Parameter_SalesViewScatterChart_y_axis_Bookmark_S3[Order])

RETURN
SWITCH(
    TRUE(),
    selected_y_axis = 0,
    IF(
        NOT(ISBLANK([GM %])) && NOT(ISBLANK([GM % BM])) &&
        [GM %] < [GM % BM],
        "SHOW",
        "HIDE"
    ),

    selected_y_axis = 1,
    IF(
        NOT(ISBLANK([NP %])) && NOT(ISBLANK([NP % BM])) &&
        [NP %] < [NP % BM],
        "SHOW",
        "HIDE"
    )
)
```

```
Bookmark S3 Button1 Text = 

VAR gm_pct_or_np_pct = 
SWITCH(
    TRUE(),
    SELECTEDVALUE(Parameter_SalesViewScatterChart_y_axis_Bookmark_S3[Order]) = 0,
    "GM %",
    SELECTEDVALUE(Parameter_SalesViewScatterChart_y_axis_Bookmark_S3[Order]) = 1,
    "NP %"
)

RETURN
"Only Show Customers that Do Not Meet " & gm_pct_or_np_pct & " BM"
```




#### Finance and Executive View: Dynamic Top/Bottom N
```
Top Bottom N Toggle = 

VAR x = UNION(
    ROW("Primary_Key", 0, "Selection", "Top"),
    ROW("Primary_Key", 1, "Selection", "Bottom")
)

RETURN x
```

```
Parameter_Top_Bottom_N_Value = GENERATESERIES(1, 10, 1)
```





```
P&L Value by Customer Asc Dense Ranking = 
RANKX(
    FILTER(
        ALLSELECTED(dim_customer[customer]),
        NOT(ISBLANK([P & L Values]))
    ),
    [P & L Values],
    ,
    ASC,
    Dense
)
```




```
P&L Value by Customer Desc Dense Ranking = 
RANKX(
    FILTER(
        ALLSELECTED(dim_customer[customer]),
        NOT(ISBLANK([P & L Values]))
    ),
    [P & L Values],
    ,
    DESC,
    Dense
)
```



```
Filter Top Bottom N Customers by P&L Value = 

// 0 - Top, 1 - Bottom
VAR top_or_bottom = SELECTEDVALUE('Top Bottom N Toggle'[Primary_Key])

// Integer between 1-10
VAR n = [Selected_Parameter_Top_Bottom_N_Value]


RETURN
SWITCH(
    TRUE(),

    // top n customers
    top_or_bottom = 0,
    IF(
        [P&L Value by Customer Desc Dense Ranking] <= n,
        [P & L Values]
    ),

    // bottom n customers
    top_or_bottom = 1,
    IF(
        [P&L Value by Customer Asc Dense Ranking] <= n,
        [P & L Values]
    )
)
```




```
P&L Value by Product Asc Dense Ranking = 
RANKX(
    FILTER(
        ALLSELECTED(dim_product[product]),
        NOT(ISBLANK([P & L Values]))
    ),
    [P & L Values],
    ,
    ASC,
    Dense
)
```




```
P&L Value by Product Desc Dense Ranking = 
RANKX(
    FILTER(
        ALLSELECTED(dim_product[product]),
        NOT(ISBLANK([P & L Values]))
    ),
    [P & L Values],
    ,
    DESC,
    Dense
)
```


```
Filter Top Bottom N Products by P&L Value = 

// 0 - Top, 1 - Bottom
VAR top_or_bottom = SELECTEDVALUE('Top Bottom N Toggle'[Primary_Key])

// Integer between 1-10
VAR n = [Selected_Parameter_Top_Bottom_N_Value]


RETURN
SWITCH(
    TRUE(),

    // top n products
    top_or_bottom = 0,
    IF(
        [P&L Value by Product Desc Dense Ranking] <= n,
        [P & L Values]
    ),

    // bottom n products
    top_or_bottom = 1,
    IF(
        [P&L Value by Product Asc Dense Ranking] <= n,
        [P & L Values]
    )
)
```




#### New Card Visual
Example of Net Sales $ Card

```
NS $ Color = 
SWITCH(
    TRUE(),
    // Blank
    ISBLANK([NS $]) || ISBLANK([NS BM $]),
    "#000000",

    [NS $] > [NS BM $],
    // Green
    "#43A047",

    [NS $] = [NS BM $],
    "#000000",

    // Red
    "#c3312a"
)
```


```
NS $ Image = 
SWITCH(
    TRUE(),

    ISBLANK([NS BM $]),
    "https://i.ibb.co/bjzgy541/BM-na-large.png",

    [NS $] > [NS BM $],
    // Green Up Arrow
    "https://i.ibb.co/67dsYqY5/Green-Up.png",

    [NS $] = [NS BM $],
    // Neutral
    "https://i.ibb.co/vxQT3xWk/Neutral.png",

    // Red Down Arrow
    "https://i.ibb.co/Vc8F5L0C/Red-Down.png"
)
```

```
NS $ Reference Label Detail = 

SWITCH(
    TRUE(),

    ISBLANK([Percent Change NS $ vs BM]),
    "n/a",

    // Positive Percent Change
    [Percent Change NS $ vs BM] > 0,
    "| " & FORMAT([Percent Change NS $ vs BM]*100, "0.00") & "%  ▲ |",

    // 0% Change
    [Percent Change NS $ vs BM] = 0,
    "| " & FORMAT([Percent Change NS $ vs BM]*100, "0.00") & "% |",

    // Negative Percent Change
    [Percent Change NS $ vs BM] < 0,
    "| " & FORMAT([Percent Change NS $ vs BM]*100, "0.00") & "%  ▼ |"
)
```




### Impact of this Project and Examples of Insights
