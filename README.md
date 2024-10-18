# Customer-Segmentation-Using-KMeans-Clustering
---
## Project Overview

ShopEase, established in 2017, is a fast-growing e-commerce platform and supermarket chain that offers a wide range of products including clothing, groceries, sportswear, electronics, and home & garden essentials. Despite its rapid expansion, ShopEase has only scratched the surface of leveraging its customer data for strategic decision-making.
With years of data collected from its sales records and customer purchase pattern, ShopEase embarked on a customer segmentation project. This project aims to analyze customer behavior and create actionable segments to personalize marketing campaigns, enhance customer engagement, and drive retention. By clustering customers based on their monetary value and purchase frequency, ShopEase is positioned to optimize its marketing strategies and improve overall customer satisfaction.

- The step-by-step implementation of this project can be seen in [Clustering Notebook](https://github.com/Chiagoziemchidera/Customer-Segmentation-Using-KMeans-Clustering/blob/main/Customer_Segmentation_KMeans.ipynb).

## Data Structure
The dataset used for this segmentation included 1000 rows and the following key variables:


In this dataset, each grain represents an individual customer. For each customer, the dataset captures key behavioral information, such as their spending habits and purchase frequency. These attributes are used to understand and analyze customer behavior. The dataset used is found [here](https://github.com/Chiagoziemchidera/Customer-Segmentation-Using-KMeans-Clustering/tree/main/Extras%20%26%20Resource%23).

## Overview of Findings/Insights
The K-Means clustering algorithm segmented customers into seven distinct groups (4 clusters from a non-outlier data and 3 clusters from the :

### Non-outlier data
#### Cluster 0: Loyalists
Rationale: This group consists of high-value customers who make regular purchases, though their buying activity hasn’t been very recent.

#### Cluster 1: Prospects
Rationale: This segment is made up of lower-value, occasional buyers who have recently made a purchase.

#### Cluster 2: VIPs
Rationale: This cluster features highly frequent, high-value customers who have made recent purchases.

#### Cluster 3: Dormants
Rationale: This group includes low-value, infrequent buyers, many of whom are currently inactive.

![non-outlier scatter](https://github.com/user-attachments/assets/02270aa7-8aae-480f-896f-092faac7f8b8)

### Outlier data
#### Cluster -1: BigHitters
Characteristics: High spenders who don’t buy often but have made very recent purchases

#### Cluster -2: DealHunters
Characteristics: Frequent buyers who typically spend less per transaction, with most making recent purchases.

#### Cluster -3: PowerPlayers
Characteristics: The most valuable outliers, marked by very high spending and frequent, recent purchases.

![outlier scatter](https://github.com/user-attachments/assets/a69d00a4-a65b-4e03-b553-01c3aaf56db6)

---
## Recommendations
The Marketing and customer experience team should consider the following targeted strategies based on the insights gained from the customer segmentation:

#### Cluster 0: Loyalists
* Strategy 1: Implement a loyalty program that rewards consistent purchases over time, like points accumulation for future discounts.
* Strategy 2: Create personalized offers based on past purchase behavior to encourage re-engagement.
* Strategy 3: Offer early access to new products or exclusive sales to increase engagement.

#### Cluster 1: Prospects
* Strategy 1: Run targeted promotions to incentivize another purchase, like time-limited discounts or free shipping.
* Strategy 2: Use retargeting ads to stay top-of-mind and remind them of their previous interest.
* Strategy 3: Send personalized follow-up emails with recommended products based on their last purchase.

#### Cluster 2: VIPs 
* Strategy 1: Offer exclusive, premium experiences such as early-bird access or curated recommendations.
* Strategy 2: Introduce a referral program to leverage their high satisfaction and spread positive word-of-mouth.
* Strategy 3: Use premium-tier perks like VIP customer service or invites to brand events to further nurture their loyalty.

#### Cluster 3: Dormants
* Strategy 1: Re-engage with win-back campaigns using deep discounts or compelling offers to entice them back.
* Strategy 2: Survey to understand why they’ve stopped purchasing and adjust messaging or product offerings accordingly.
* Strategy 3: Offer limited-time incentives tied to reminders about their last purchase or favorite product.

#### Cluster -1: BigHitters
* Strategy 1: Promote high-value products or bundles to match their spending habits and offer special “luxury tier” services.
* Strategy 2: Use targeted ads for high-end product launches or flash sales.
* Strategy 3: Encourage high-revenue behavior with exclusive invites to brand experiences or events.

### Cluster -2: DealHunters
* Strategy 1: Offer frequent small promotions like free shipping or flash sales to keep them engaged without compromising margins.
* Strategy 2: Create budget-friendly bundles or subscription services that cater to their buying habits.
* Strategy 3: Keep them engaged with regular, time-limited email offers or rewards for consistent small purchases.

### Cluster -3: PowerPlayers
* Strategy 1: Provide VIP services, high-level personalization, or direct access to account managers.
* Strategy 2: Invite them to ultra-exclusive product launches, behind-the-scenes events, or experiences.
* Strategy 3: Offer top-tier rewards or incentives for continued high-frequency and high-value purchasing.

By applying these strategies, ShopEase can maximize customer engagement, increase purchase frequency, and foster long-term loyalty, ultimately driving sustained growth and commercial success.

![summary](https://github.com/user-attachments/assets/6fdc785d-7492-4673-943f-d650e5907bf6)


