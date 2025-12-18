<h1 align=center> Customer-Purchase-Data-Analysis </h1>
This project performs Exploratory Data Analysis (EDA) on a customer purchase dataset using Python Pandas. The goal is to extract insights about customer demographics, spending behavior, and credit card usage. It is designed to build a strong Portfolio Project for interviews and LinkedIn.

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
import pandas as pd
df = pd.read_csv('/content/sample_data/Cust_Purch_FakeData.csv')

**2. Finding the max and min ages of customer.**
print("Max. age of the customer is:  ", df['age'].max() )
print("Min. age of the customer is:  ", df['age'].min() )
print("Avg. age of the customer is:  ", df['age'].mean().round(0))

**3. Most common customer's names.**
df['first'].value_counts().head(3)

**4. Finding the customers with the same phone number.**
df['phone'].value_counts().head(2) # lets find what phone number is twice!
df[df['phone'] == phonedf.index[0]] # Now we know the phone number, let's find out the other stuff!

**5. How many customers have profession "Structural Engineer"?**
def find_string(title):
    if 'structural engineer' in title.lower():
        return True
    else:
        return False
df['profession'].apply(find_string)
df['profession'].apply(find_string).sum()

**6. How many male customers are 'Structural Engineer'?**
((df['gender'] == 'Male') & (df['profession'] == 'Structural Engineer')).sum()

**7. Find out the female Structural Engineers from province Alberta (AB)?**
df[
    (df['gender'] == 'Female') &
    (df['profession'] == 'Structural Engineer') &
    (df['province'] == 'AB')

**8. We need to send new cards to the customers well before the expire, how many cards are expiring in 2019?**
df['cc_exp'].apply(lambda x: x[5:] == '19').sum()

**9. find the customer who spent 100 CAD using Visa?**
df[
    (df['price(CAD)'] >= 100) &
    (df['cc_type'].str.lower() == 'visa')
]

**10. Top 5 most popular email providers.**
df['email_provider'] = df['email'].str.split('@').str[1] # Extract the domain part after '@'
provider_counts = df['email_provider'].value_counts() # Count occurrences of each provider
provider_counts.head(5)
