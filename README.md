<h1 align=center> Customer-Purchase-Data-Analysis </h1>
This project performs Exploratory Data Analysis (EDA) on a customer purchase dataset using Python Pandas. The goal is to extract insights about customer demographics, spending behavior, and credit card usage.

## Dataset Overview
| Column       | Description                 |
| ------------ | --------------------------- |
| `first`      | First name of the customer  |
| `last`       | Last name of the customer   |
| `age`        | Customer age                |
| `email`      | Email address               |
| `phone`      | Contact phone number        |
| `company`    | Employer of the customer    |
| `profession` | Customer profession         |
| `province`   | Province (e.g., AB, BC, ON) |
| `cc_type`    | Credit card provider        |
| `cc_exp`     | Credit card expiration date |
| `price(CAD)` | Amount spent in CAD         |

## Analysis Performed
- Detecting duplicate phone numbers
- Finding customers who did not spend anything
- Counting credit cards expiring in a given year (e.g., 2019)
- Extracting email providers and ranking most popular domains
- Filtering customers by specific email domains (gmail, yahoo, edu, etc.)
- Sorting credit card types by popularity
- Identifying high–value customers (≥100 CAD purchase)
- Filtering by spending + card provider (e.g., Visa customers spending ≥100 CAD)

**1. Import Pandas and Read the csv file.**
