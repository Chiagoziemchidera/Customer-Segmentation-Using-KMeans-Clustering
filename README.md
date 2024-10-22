# Customer-Segmentation-Using-KMeans-Clustering
---
## Project Overview

ShopEase is a fast-growing online retail platform and supermarket chain that offers a wide range of products including clothing, groceries, sportswear, electronics, and home & garden essentials. Despite its rapid expansion, ShopEase has only scratched the surface of leveraging its customer data for strategic decision-making.
With years of data collected from its sales records and customer purchase pattern, ShopEase embarked on a customer segmentation project. This project aims to analyze customer behavior and create actionable segments to personalize marketing campaigns, enhance customer engagement, and drive retention. By clustering customers based on their monetary value and purchase frequency, ShopEase is positioned to optimize its marketing strategies and improve overall customer satisfaction.

- The step-by-step implementation of this project can be seen in [Clustering Notebook](https://github.com/Chiagoziemchidera/Customer-Segmentation-Using-KMeans-Clustering/blob/main/Customer_Segmentation_KMeans_.ipynb).

## Data Structure
This is a transactional data set which contains all the transactions occurring between 01/12/2010 and 09/12/2011. Many customers of the company are wholesalers.

| **Variable Name** | **Role**    | **Type**      | **Description**                                                                 | **Units**  | **Missing Values** |
|-------------------|-------------|---------------|---------------------------------------------------------------------------------|------------|--------------------|
| InvoiceNo         | ID          | Categorical   | a 6-digit integral number uniquely assigned to each transaction. If this code starts with letter 'c', it indicates a cancellation | -          | no                 |
| StockCode         | ID          | Categorical   | a 5-digit integral number uniquely assigned to each distinct product             | -          | no                 |
| Description       | Feature     | Categorical   | product name                                                                    | -          | no                 |
| Quantity          | Feature     | Integer       | the quantities of each product (item) per transaction                            | -          | no                 |
| InvoiceDate       | Feature     | Date          | the day and time when each transaction was generated                             | -          | no                 |
| UnitPrice         | Feature     | Continuous    | product price per unit                                                           | sterling   | no                 |
| CustomerID        | Feature     | Categorical   | a 5-digit integral number uniquely assigned to each customer                     | -          | no                 |
| Country           | Feature     | Categorical   | the name of the country where each customer resides                              | -          | no                 |


In this dataset, each row (or instance) represent a single customer, including their associated purchase history. For each customer, the dataset captures key behavioral information, such as their spending habits and purchase frequency. These attributes are used to understand and analyze customer behavior. The dataset used contains `536,642` rows and can be gotten [here](https://github.com/Chiagoziemchidera/Customer-Segmentation-Using-KMeans-Clustering/tree/main/Extras%20%26%20Resource%23).

After data cleaning, 27.1% of the dataset was removed, consisting of transactions that did not represent customer purchases, such as postage charges, commissions, shipping costs, bank charges, and other similar expenses.

![features EDA](https://github.com/user-attachments/assets/ef222c57-0759-43ec-92b9-180c48ee3d08)

### Monetary Value Distribution (Left Plot):
Most customers have a low monetary value (below 50,000), with very few high-spending customers. The presence of outliers at very high monetary values suggests a small group of customers with significant spending power.
The dataset is right-skewed, as the bulk of customers are clustered at the lower end, indicating that most spend relatively little.

### Frequency Distribution (Middle Plot):
The majority of customers have very few purchase occurrences (most are below 10 purchases), with a very small number of customers showing higher purchase frequencies (up to 200).
This suggests that most customers are infrequent buyers, while a few might engage in repeated purchases.

### Recency Distribution (Right Plot):
The recency plot shows that most customers have made purchases recently (with recency close to 0), but there are a significant number of customers who haven’t purchased in a long time.
The distribution is also right-skewed, with most recent purchases being concentrated on the lower end (indicating recent activity).

![features EDA non-outlier](https://github.com/user-attachments/assets/f19b10d9-2d01-4569-b2ce-e8b7d4695330)

These distributions represents the non-outlier dataset and is typical in RFM (Recency, Frequency, Monetary) analysis, where customer behaviors are often right-skewed because a small portion of customers contribute to the majority of revenue, while most customers engage less frequently.

## Overview of Findings/Insights
The K-Means clustering algorithm segmented customers into seven distinct groups (4 clusters from a non-outlier data and 4 clusters from the outlier data :

### Non-outlier data insights

![non-outlier scatter](https://github.com/user-attachments/assets/3e635561-7a0c-4543-8b0f-0e485276bf66)

#### 1. Cluster 0: **Actives**
*Characteristics: Average spend customers who purchase relatively regularly, though most are recent buyers.*

#### 2. Cluster 1: **Browsers**
*Characteristics: Lower-value, infrequent buyers who have averagely purchased recently.*

#### 3. Cluster 2: **Champions**
*Characteristics: High frequent and high-value customers, and most have made recent purchases.*

#### 4. Cluster 3: **Inactives**
*Characteristics: Low-value, few frequent buyers, many of whom are not actively purchasing.*

### Outlier data insights

![outlier scatter 2](https://github.com/user-attachments/assets/6cee57b9-dbe1-4845-88d1-356b907fe8ae)

#### 1. Cluster 4: **Regulars**
*Characteristics: Most are average spenders, frequent buyers, and recent purchasers.*

#### 2. Cluster 5: **Elites**
*Characteristics: Extreme spenders, very frequent buyers, and very recent.*

#### 3. Cluster 6: **Steadies**
*Characteristics: Low spend, high frequency, and not recent buyers.*

#### 4. Cluster 7: **Dynamos**
*Characteristics: High spend, high frequency, and very recent buyers.*

![summary](https://github.com/user-attachments/assets/52ac92b9-a445-4b10-ad12-e5eb454a528d)

---
## Recommendations
The Marketing and customer experience team should consider the following targeted strategies based on the insights gained from the customer segmentation:

Based on the similarities in customer behaviors, merging some clusters to optimize marketing strategies is recommended. The merged clusters allow for more streamlined targeting while maintaining distinct approaches for different customer groups. By reducing the number of segments, marketing efforts can be more focused and efficient.


### 1. Combined Cluster 0/4: **Actives-Regulars**
*Characteristics: Average spenders, frequent buyers, recent purchasers.*

#### Reason for Merging:
Both clusters represent customers who purchase frequently with average spend levels and recent activity. The behavior of these two segments is closely aligned, making it unnecessary to differentiate them for marketing purposes.

#### Marketing Strategies:
1. **Personalized Engagement Campaigns**: Use data-driven insights to send tailored offers and personalized product recommendations tied to their past shopping behavior to maintain consistent engagement.
2. **Habit Reinforcement Programs**: Implement a loyalty program that rewards frequent purchases with tiered benefits like discounts, early access to new products, or exclusive collections.
3. **Cross-sell & Upsell Tactics**: Leverage their frequent buying habits by suggesting complementary or higher-value products with targeted promotions like "Complete Your Set" or "You Might Also Like."

---

### 2. Combined Cluster 5/7: **Elite-Dynamos**
*Characteristics: High to extreme spenders, very frequent buyers, very recent.*

#### Reason for Merging:
Both clusters represent high-value, frequent purchasers with recent activity. Their distinction based on spending levels can be managed with similar high-end marketing strategies focused on exclusivity and VIP treatment.

#### Marketing Strategies:
1. **High-value VIP Perks**: Provide white-glove services like personal shopping consultations, invitations to private events, or early access to high-end collections. Position them as premium members of an exclusive club.
2. **Exclusive Access & Flash Sales**: Offer time-sensitive flash sales and priority access to limited-edition or high-end products to reward their spending and further drive engagement.
3. **Personalized Thank-Yous & Luxury Gifts**: Send personalized thank-you notes or surprise luxury gifts with purchases to strengthen brand loyalty and emotional connection.

---

### 3. Combined Cluster 1/3: **Browsers-Inactives**
*Characteristics: Low-spend, infrequent buyers, ranging from recent to dormant.*

#### Reason for Merging:
Both clusters exhibit low-spend and infrequent purchasing patterns, with the primary distinction being the time since their last purchase. Combining them into a single segment allows for a cohesive re-engagement strategy targeting low-value buyers.

#### Marketing Strategies:
1. **Reactivation & Urgency-driven Campaigns**: Run FOMO-based campaigns with strong incentives like time-limited discounts or personalized offers to prompt immediate action. Messages like "We Miss You!" or "Flash Sale: 24 Hours Only!" can help drive conversions.
2. **Retargeting & Abandonment Campaigns**: Deploy retargeting ads and abandonment recovery emails to remind them of viewed products or incomplete checkouts, encouraging them to complete their purchase.
3. **Win-Back Surveys & Content**: Use surveys to understand why they’ve gone dormant and adjust marketing strategies accordingly. Share educational content or product guides to showcase the value of higher-end products and encourage re-engagement.

---

### 4. Cluster 2: **Champions**
*Characteristics: High spenders, frequent buyers, recent activity.*

#### Marketing Strategies:
1. **Exclusive VIP Programs**: Create exclusive access to upcoming collections, special events, or premium product lines to reward their loyalty and keep them engaged.
2. **Referral & Advocacy Incentives**: Introduce a referral program that leverages their advocacy to bring in new high-value customers. Offer special bonuses for successful referrals.
3. **Personalized Experiences**: Deepen emotional connections with personalized thank-you notes, surprise gifts, or customized offers based on their preferences.

---

### 5. Cluster 6: **Steadies**
*Characteristics: Low spend, high frequency, not recent.*

#### Marketing Strategies:
1. **Frequent Small Promotions**: Keep them engaged with continuous, low-value promotions or rewards that align with their modest but frequent purchasing habits, such as "Buy More, Save More" offers.
2. **Subscription-based Programs**: Launch subscription services that offer regular rewards or incentives for small but frequent purchases, encouraging long-term engagement.
3. **Re-Engagement Newsletters**: Send regular newsletters featuring new product arrivals or trending items that match their buying patterns to reignite interest and purchasing activity.

---

By applying these strategies, ShopEase can maximize customer engagement, increase purchase frequency, and foster long-term loyalty, ultimately driving sustained growth and commercial success.

