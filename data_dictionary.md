# Data Dictionary

## Project note

The data in this project is synthetic and does not represent real customers,
stores, or supermarket transactions.

## `fact_sales`

| Column | Meaning | Example or format |
|---|---|---|
| `sales_key` | Unique identifier for a sales line | Integer |
| `date_key` | Date associated with the sale; links to the date dimension | YYYY-MM-DD |
| `product_key` | Product identifier; links to the product dimension | Integer |
| `customer_key` | Customer identifier; links to the customer dimension | Integer |
| `store_key` | Store identifier; links to the store dimension | Integer |
| `[actual quantity column]` | Number of units on this sales line | Number |
| `[actual price column]` | Price recorded for one unit | Currency |
| `[actual sales amount column]` | Sales amount for this line | Currency |

## `dim_date`

| Column | Meaning | Example or format |
|---|---|---|
| `[actual date key]` | Unique date used to connect dates to sales | YYYY-MM-DD |
| `[actual year column]` | Calendar year | 2026 |
| `[actual month column]` | Month name or number | March or 3 |

## `dim_products`

| Column | Meaning | Example or format |
|---|---|---|
| `[actual product key]` | Unique product identifier | Integer |
| `[actual product name column]` | Product name | Example product |
| `[actual category column]` | Product category | Example category |

## `dim_customers`

| Column | Meaning | Example or format |
|---|---|---|
| `[actual customer key]` | Unique customer identifier | Integer |
| `[actual segment column]` | Customer segment, if included | Example segment |
| `[actual income column]` | Income bracket, if included | Example bracket |

## `dim_stores`

| Column | Meaning | Example or format |
|---|---|---|
| `[actual store key]` | Unique store identifier | Integer |
| `[actual supermarket column]` | Supermarket or chain name | Example chain |
| `[actual state column]` | State where the store is located | Lagos |

## Notes

- Describe how your database defines sales, revenue, basket size, and transaction.
- Explain any missing values or unusual codes.
- Record any assumptions used to create synthetic data.
