<h1>E-commerce Consumer Archetyping</h1>

<h2>Tools Used</h2>

- <b>Python:</b> Data Cleaning, Pre-processing, EDA, Unsupervised Machine Learning (K-means clustering) 
- <b>POWER BI:</b> Dashboarding

<h2>Dataset and Description</h2>
<b>Source: </b>
<br />
<br />
<b>Size: </b> (21864, 11)
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
- Created an aggregated dataframe to compute the **Monetary values** and **Recency** of each unique user

- Since K-means clustering is sensitive to outliers, used boxplots to check outliers for the **Monetary Value** and **Recency** distributions. Outliers were detected for monetary values, and a little for recency, so those were filtered out using the IQR formula for outliers.
  
- A table of main values was made, and then a table of outlier values were made. Clustering will be performed on the main table.


**For the main table...**
 
- Standardized the data
  
- Used inertia and silhouette score to **find optimal k = 4**, also achieving *inertia percent reduction of 77%*

- Created a violin plot reporting distributions of monetary value and recency for each cluster. This plot identified important customers based on monetary value, as well as the clusters with high risk of churn based on recency. 

<h2>Results and Recommendations </h2>

**Cluster 0** is recent recency and low monetary value. These are our loyal low-spending users. Primary goal with this cluster is to identify popular products among them and try to get them to buy more. Using the dashboard, we see that Nintendo switch is the most popular product among users in cluster 0. We can try marketing products similar to the Switch, or cheap, complimentary products to go with the switch. 

**Cluster 1** yielded high monetary value, yet late recency. These are our at-risk users. Primary goal with this cluster is to implement personalized advertising strategies to get them to buy from us again. The Gaming Monitor was the most popular product for Cluster 1. We could double down on products similar to the gaming monitor, or also invest in updated versions with the hope that the high-spending cluster will buy them.

**Cluster 2** yielded high monetary value and recent recency. These are our loyal high-spending users. If advertising costs are being considered, marketing strategy on this cluster should be lighter compared to the other clusters.

**Cluster 3** yielded low monetary value and late recency. This is our least important group, as they didn’t give us that much money anyway. If advertising costs are being considered, marketing strategy on this cluster, if any, should be the LIGHTEST compared to the other clusters.

<h2>Intervention Strategy Simulation </h2>
- Assigned base retention using a proxy of lower recency corresponding to higher retention probability. 
- Determined lift effects per cluster. 
**Cluster 0:** loyal low-spending user; **moderate** marketing approach. treatment effect is 5%

**Cluster 1:** churning/at risk users; **aggressive** marketing approach. treatment effect is 10%.

**Clusters 2 and 3:** **conservative** marketing approach. treatment effect between 2-4%.
- Used our proxy to calculate baseline retention rate. Calculated baseline retention rates of 0.69732978 for cluster 0, 0.12040556 for cluster 1, 0.7 for cluster 2, and 0.1 for cluster 3.

- Calculated new retention rates. Mapped each cluster to its lift effect (either 0.05, 0.10, 0.02, or 0.04) to calculate customer retention after applying personalized marketing strategies. 

- Observed improved customer retention across all segments by 9.3%.

<h2>Dashboard /  EDA </h2>

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
