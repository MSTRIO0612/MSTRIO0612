
import pandas as pd
import matplotlib.pyplot as plt

# Load the financial inclusion data
financial_inclusion_data = pd.read_csv('financial_inclusion_data.csv')

# Explore the data
print(financial_inclusion_data.head())

# Check for missing values
print(financial_inclusion_data.isnull().sum())

# Summary statistics
print(financial_inclusion_data.describe())

# Visualize the distribution of account ownership by gender
gender_account = financial_inclusion_data.groupby('gender_of_respondent')['has_a_bank_account'].value_counts(normalize=True).unstack()
gender_account.plot(kind='bar', stacked='True')
plt.title('Account Owners
