# Data Dictionary

## Project note

The data in this project is synthetic and does not represent real customers,
stores, or supermarket transactions.

## `fact_sales`

| Column | Meaning | Example or format |
|---|---|---|
| `sale_id` | Primary Key | BIGINT AUTO_INCREMENT |
| `ticket_id` | Transaction Reciept | VARCHAR |
| `product_key` | Product identifier; links to the product dimension | Integer Forign_Key |
| `customer_key` | Customer identifier; links to the customer dimension | Integer Forign_Key |
| `store_key` | Store identifier; links to the store dimension | Integer Forign_Key|
| `quantity` | Number of units on this sales line | Int |
| `unit_price` | Price recorded for one unit | Decimal(14,2)  |
| `cost_price` | Sales amount for this line | Decimal(14,2) |
| `Gross_revenue` | Quantity *Unit_price | DECIMAL(14,2) GENERATED ALWAYS AS (quantity * unit_price) STORED |
| `cost_of_goods_sold` | Total sales amount for this line | DECIMAL(14,2) GENERATED ALWAYS AS (quantity * cost_price) STORED |
| `Gross_profit` | Direct expenses (Prime Profit  | DECIMAL(14,2) GENERATED ALWAYS AS ((quantity * unit_price) - (quantity * cost_price)) STORED |

## `dim_date`

| Column | Meaning | Example or format |
|---|---|---|
| `date_key` | Unique date used to connect date_key to Fact_sales | DATE PRIMARY KEY |
| `Actual year` | Calendar year | INT NOT NULL |
| `quater` | Calendar quater | INT NOT NULL |
| `Month` | Calendar month | INT NOT NULL |
| `Month_name` | Describe the month | VARCHAR(15) NOT NULL |
| `Day_of_week` | Describe the day | VARCHAR(15) NOT NULL |
| `is_weekend` | Describe the weekend | VARCHAR(3) NOT NULL |
| `Month_start` | long date | DATE NOT NULL |
| `Month_end` | Long date | DATE NOT NULL |

## `dim_products`

| Column | Meaning | Example or format |
|---|---|---|
| `product_key` | Unique product identifier connect product_key to Fact_sales | INT AUTO_INCREMENT PRIMARY KEY |
| `product_id` | Unique product identifier Natural key | INT NOT NULL UNIQUE | 
| `product name` | Product name | VARCHAR(150) NOT NULLr |
| `category` | Product category | VARCHAR(100) NOT NULL |
| `tier` | Product levels | ENUM(Essential,Premium) |
| `base_price` | Product direct price | DECIMAL(10,2) NOT NULL |
| `base_cost` | Product direct cost | DECIMAL(10,2) NOT NULL |


## `dim_customers`

| Column | Meaning | Example or format |
|---|---|---|
| `customer_key` | Unique customer identifier connects customer_key to fact_sales | INT AUTO_INCREMENT PRIMARY KEY |
| `customer_id` | Unique customer identifier naturel key | INT NOT NULL UNIQUE |
| `gender` | Customer age | VARCHAR(10) NOT NULL |
| `income_bracket` | Describe the income group | VARCHAR(20) NOT NULL |
| `loyalty_status` | Describe the loyalty to stay or not to saty | VARCHAR(20) NOT NULL |


## `dim_stores`

| Column | Meaning | Example or format |
|---|---|---|
| `store_key` | Unique store identifier connect store_key to Fact_sales | INT AUTO_INCREMENT PRIMARY KEY |
| `store_Id` | Unique store identifier Natural key | INT NOT NULL UNIQUE |
| `supermarket` | Supermarket or chain name | VARCHAR(100) NOT NULL |
| `Retail_model` | Describe the selling strategies | VARCHAR(100) NOT NULL |
| `state` | State where the store is located | VARCHAR(50) NOT NULL |
| `Location_type` | Brach in each state | VARCHAR(80) NOT NULL |


## Notes

- My **Sales or Revenue** figure is my Gross_Revenue column, **Total_transaction** is the distinct count of my ticket_id , and also **Basket size** is the Total_Units_Solds divided by the Total_transaction.
- For this Data it was generated from one from **GitHub** and converted to **Synthetics Data** using **ChatGPT** AI tool. 
