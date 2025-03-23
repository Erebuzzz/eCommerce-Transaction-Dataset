# eCommerce Transaction Dataset

## Overview
This repository contains a synthetic dataset of eCommerce transactions designed for data analysis, machine learning, and business intelligence projects. The dataset simulates realistic online shopping behavior with comprehensive transaction details, customer information, and product data.

## Dataset Description

The dataset includes transactions from an imaginary online retailer with the following features:

- **Transaction details**: Order ID, timestamp, payment method, device type
- **Customer information**: Customer ID, demographics, location data
- **Product data**: Product categories, prices, quantities
- **Performance metrics**: Conversion rates, cart abandonment, session duration

## File Structure

```
eCommerce-Transaction-Dataset/
├── data/
│   ├── transactions.csv
│   ├── customers.csv
│   ├── products.csv
│   └── sessions.csv
├── notebooks/
│   ├── exploratory_analysis.ipynb
│   └── modeling.ipynb
├── scripts/
│   ├── data_cleaning.py
│   └── feature_engineering.py
└── README.md
```

## Data Dictionary

### transactions.csv
| Column | Description | Data Type |
|--------|-------------|-----------|
| transaction_id | Unique identifier for each transaction | string |
| customer_id | Customer identifier | string |
| transaction_date | Date and time of transaction | datetime |
| total_amount | Total transaction amount | float |
| payment_method | Method of payment | string |
| items_count | Number of items in transaction | integer |
| device_type | Device used for transaction | string |
| status | Transaction status | string |

### customers.csv
| Column | Description | Data Type |
|--------|-------------|-----------|
| customer_id | Unique identifier for each customer | string |
| join_date | Date when customer joined | date |
| country | Customer's country | string |
| city | Customer's city | string |
| gender | Customer's gender | string |
| age_group | Customer's age group | string |

### products.csv
| Column | Description | Data Type |
|--------|-------------|-----------|
| product_id | Unique identifier for each product | string |
| category | Product category | string |
| subcategory | Product subcategory | string |
| price | Product price | float |
| avg_rating | Average product rating | float |

## Usage Examples

### Loading the Data

```python
import pandas as pd

# Load transactions data
transactions = pd.read_csv('data/transactions.csv')

# Load customer data
customers = pd.read_csv('data/customers.csv')

# Load product data
products = pd.read_csv('data/products.csv')

# Preview data
transactions.head()
```

### Basic Analysis

```python
# Transaction summary by payment method
payment_summary = transactions.groupby('payment_method').agg({
    'transaction_id': 'count',
    'total_amount': 'sum'
}).rename(columns={'transaction_id': 'num_transactions'})

print(payment_summary)
```

## Applications

This dataset can be used for:

1. **Customer Segmentation**: Identify different customer groups based on purchase behavior
2. **Sales Forecasting**: Predict future sales trends
3. **Market Basket Analysis**: Discover frequently co-purchased products
4. **Churn Prediction**: Identify at-risk customers
5. **Anomaly Detection**: Find unusual transaction patterns
6. **Recommendation Systems**: Build product recommendation models
