# BUILDING-DASHBOARD-USING-POWER-BI
 ------ | ----------- | ----- | ------ |
| North  | Electronics | 15320 | 4100   |
| South  | Furniture   | 18300 | 5200   |
| East   | Clothing    | 9200  | 2200   |
| West   | Electronics | 14750 | 3900   |
| North  | Furniture   | 11200 | 3200   |
| South  | Clothing    | 9800  | 2400   |
| East   | Electronics | 13200 | 4100   |
| West   | Furniture   | 15600 | 4600   |
| North  | Clothing    | 9100  | 2100   |
| South  | Electronics | 14100 | 4000   |
| East   | Furniture   | 12900 | 3600
| West.  | Clothing.   | 10000 |  2500

import numpy as np
# Simulate business dataset: sales data by region and product category
sample_data = {
    'Region': ['North', 'South', 'East', 'West'] * 3,
    'Category': ['Electronics', 'Furniture', 'Clothing'] * 4,
    'Sales': np.random.randint(5000, 20000, 12),
    'Profit': np.random.randint(1000, 7000, 12)
}

df_sample = pd.DataFrame(sample_data)
region_summary = df_sample.groupby('Region')[['Sales', 'Profit']].sum()
category_summary = df_sample.groupby('Category')[['Sales', 'Profit']].sum()

# Plotting
plt.figure(figsize=(14, 6))

# Region Sales and Profit
plt.subplot(1, 2, 1)
region_summary.plot(kind='bar', ax=plt.gca(), title='Sales & Profit by Region')
plt.ylabel('USD ($)')
plt.xticks(rotation=0)

# Category Sales and Profit
plt.subplot(1, 2, 2)
category_summary.plot(kind='bar', ax=plt.gca(), title='Sales & Profit by Category', color=['#4e79a7', '#f28e2b'])
plt.ylabel('USD ($)')
plt.xticks(rotation=0)
plt.tight_layout()
plt.savefig("/mnt/data/power_bi_dashboard.png")
"/mnt/data/power_bi_dashboard_.png"
