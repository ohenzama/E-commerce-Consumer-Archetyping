<h1>E-commerce Consumer Archetyping</h1>

<h2>Tools Used</h2>

- <b>Python:</b> Data Cleaning, Pre-processing, EDA, Unsupervised Machine Learning (K-means clustering) 
- <b>POWER BI:</b> Dashboarding

<h2>Dataset and Description</h2>
<b>Source: </b>
<br />
<br />
<b>Size: </b>
<br />
<br />
<b>Description: </b> Dataset of a fictional company that sells gaming products. Contains more than 20,000 records of online purchase orders. Each row is a record of a purchase made by a customer. 
<br />
<br />
<b>Features: </b>
**USER_ID:** ID of costumer 

**ORDER_ID:** unique id of order

**PURCHASE_TS:** timestamp of purchase instance

**SHIP_TS**: timestamp of shipping instance

**REFUND_TS:** timestamp of refund, if applicable

**PRODUCT_NAME:** specific gaming product ordered

**PRODUCT_ID:** ID of product ordered

**USD_PRICE:** USD ****price of product ordered

**PURCHASE PLATFORM:** platform the customer used to purchase the product

**MARKETING_CHANNEL**: marketting method that led the customer to make the purchase

**ACCOUNT_CREATION_METHOD:** method of user’s account creation

**COUNTRY_CODE:** country from which the customer made the purchase
<br />
<br />


<h2>Data Cleaning and Pre-Processing</h2>
- Trimmed whitespaces in the text

- Some rows had too many missing values, so those were removed.
  
- Standardized missing value placeholders, replacing blank spaces with consistent NA representation

- Removed duplicate order IDs
  
- Data type transformations (changed **PURCHASE_TS**  to datetime type)
  
- **Standardizing text:** there were some products that were spelled differently (ex: the spacing and casing were off), so I identified all the unique values and picked a consistent way to spell them.
  
- **Logical Error Fix:** Some rows had “SHIP_TS” greater than “PURCHASE_TS” which didn’t make sense. Removing them would be a hefty data loss of about 2000 rows. If this were an actual company’s dataset, I would have referred to the stakeholders and inquired if those date should actually be flipped. So I just pretended I did that, then I swapped the dates where I found those errors to occur.


<h2>Machine Learning (K-means clustering)</h2>
- Created an aggregated dataframe to compute the **Monetary values** and **rRcency** of each unique user

- Since K-means clustering is sensitive to outliers, used boxplots to check outliers for the **Monetary Value** and **Recency** distributions. Outliers were detected for monetary values, and a little for recency, so those were filtered out using the IQR formula for outliers.
  
- A table of main values was made, and then a table of outlier values were made. Clustering will be performed on the main table.
**For the main table...**
 
- Standardized the data
  
- Used inertia and silhouette score to **find optimal k = 4**, also achieving *inertia percent reduction of 77%*

<h2>Results and Insights</h2>

<h2>Recommendations</h2>

<h2>Dashboard</h2>

https://github.com/user-attachments/assets/4f794dc2-9bca-415e-b4f0-d5a42256a516



<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
