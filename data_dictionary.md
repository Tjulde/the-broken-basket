# Data Dictionary

## Project note

The data in this project is synthetic and does not represent real customers,
stores, or supermarket transactions.

## `fact_sales`

| Column | Meaning | Example or format |
|---|---|---|
| `sale_id` | Primary Key | BIGINT AUTO_INCREMENT |
| `ticket_id` | Transaction Reciept | VARCHAR |
| `product_key` | Product identifier; links to the product dimension | Integer |
| `customer_key` | Customer identifier; links to the customer dimension | Integer |
| `store_key` | Store identifier; links to the store dimension | Integer |
| `quantity` | Number of units on this sales line | Number |
| `unit_price` | Price recorded for one unit | Currency |
| `cost_price` | Sales amount for this line | Currency |
| `Gross_revenue` | Quantity *Unit_price | Currency |
| `cost_of_goods_sold` | Total sales amount for this line | Currency |
| `Gross_profit` | Direct expenses (Prime Profit  | Currency |

## `dim_date`

| Column | Meaning | Example or format |
|---|---|---|
| `date_key` | Unique date used to connect date_key to Fact_sales | YYYY-MM-DD |
| `Actual year` | Calendar year | 2026 |
| `quater` | Calendar quater | whole number |
| `Month` | Calendar month | whole number |
| `Month_name` | Describe the month | text |
| `Day_of_week` | Describe the day | text |
| `is_weekend` | Describe the weekend | text |
| `Month_start` | long date | date |
| `Month_end` | Long date | date |

## `dim_products`

| Column | Meaning | Example or format |
|---|---|---|
| `product_key` | Unique product identifier connect product_key to Fact_sales | Integer |
| `product_id` | Unique product identifier Natural key | Integer | 
| `product name` | Product name | varchar |
| `category` | Product category | varchar |
| `tier` | Product levels | ENUM(Essential,Premium) |
| `base_price` | Product direct price | DECIMAL |
| `base_cost` | Product direct cost | DECIMAL |


## `dim_customers`

| Column | Meaning | Example or format |
|---|---|---|
| `[actual customer key]` | Unique customer identifier | Integer |
| `[actual segment column]` | Customer segment, if included | Example segment |
| `[actual income column]` | Income bracket, if included | Example bracket |

## `dim_stores`

| Column | Meaning | Example or format |
|---|---|---|
| `store_key` | Unique store identifier connect store_key to Fact_sales | Integer |
| `store_Id` | Unique store identifier Natural key | Integer |
| `supermarket` | Supermarket or chain name | VARCHAR |
| `state` | State where the store is located | Lagos |
| `Location_type` | Brach in each state | High-Income_zone |


## Notes

- Describe how your database defines sales, revenue, basket size, and transaction.
- Explain any missing values or unusual codes.
- Record any assumptions used to create synthetic data.
