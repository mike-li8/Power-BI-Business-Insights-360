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

AtliQ Fiscal Year<br>
AtliQ's fiscal year begins in September and ends in August the following year.<br>
Example of AtliQ fiscal date vs caldendar date for AtliQ fiscal year 2021:
| 	Calendar Month and Year	 | 	AtliQ Fiscal Year	 | 	AtliQ Fiscal Month	 | 	AtliQ Fiscal Quarter	 |
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

### Dimension Tables Imported from MySQL and Sample Records
Given by data engineer

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
|  10 | 	N & S	 | 	Storage	 | 	External&nbsp;Solid&nbsp;State&nbsp;Drives	 | 	AQ Neuer SSD	 | 	Premium	 |


### Fact Tables Imported from MySQL and Sample Records
Given by data engineer

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


### Fact Tables Imported from CSV Files and Sample Records
Additional data from stakeholder meeting

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

### Importing datasets into Power BI Tables using Power Query
Dimension and fact tables dim_market, dim_product, dim_customer, fact_sales_monthly, fact_forecast_monthly imported into Power BI using Power Query. Data cleaning performed using Power Query GUI interface:
* Trimming white spaces in text
* Assigning appropriate data types for each column
* Replacing values

# Creating a dim_date dimension table using M-Language
To aid in building the data model, dim_date dimension table is created using Power Query M-Language
```
let
    // Retrieve the minimum and maximum dates from both fact_forecast_monthly and fact_sales_monthly
    // Min date from sales table
    MinDateSales = List.Min(List.Transform(fact_sales_monthly[date], each Date.From(_))),
    // Min date from forecast table
    MinDateForecast = List.Min(List.Transform(fact_forecast_monthly[date], each Date.From(_))),
    // Max date from sales table
    MaxDateSales = List.Max(List.Transform(fact_sales_monthly[date], each Date.From(_))),
    // Max date from forecast table
    MaxDateForecast = List.Max(List.Transform(fact_forecast_monthly[date], each Date.From(_))),

    // Determine the start and end dates for dim_date table
    StartDate = List.Min({MinDateSales, MinDateForecast}),
    EndDate = List.Max({MaxDateSales, MaxDateForecast}),
    
    // Create a list of dates from StartDate to EndDate
    DateList = List.Dates(StartDate, Duration.Days(EndDate - StartDate) + 1, #duration(1, 0, 0, 0)),
    
    // Convert the list to a table
    DateTable1 = Table.FromList(DateList, Splitter.SplitByNothing(), {"date"}),

    // Ensure "date" column is in date format
    DateTable2 = Table.TransformColumnTypes(DateTable1, {{"date", type date}}),

    // Since data in fact_sales_montly and fact_forecast_monthly are aggregated on a monthly level, add a month column representing first day of the month
    DateTable3 = Table.AddColumn(DateTable2, "month", each Date.StartOfMonth([date]), type date),

    // Add column for AtliQ's fiscal year by adding 4 months to the calendar month
    DateTable4 = Table.AddColumn(DateTable3, "fiscal_year", each Text.From(Date.Year(Date.AddMonths([month], 4))), type text)
in
    DateTable4
```

# Normalize sales and forecast tables
```
= Table.SelectColumns(gdb041_fact_forecast_monthly,{"date", "product_code", "customer_code", "forecast_quantity"})
```

```
= Table.SelectColumns(#"Renamed Columns",{"date", "product_code", "customer_code", "sold_quantity"})
```



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
