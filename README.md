# Customer-Segmentation-Using-KMeans-Clustering
---
## Project Overview

ShopEase, established in 2017, is a fast-growing e-commerce platform and supermarket chain that offers a wide range of products including clothing, groceries, sportswear, electronics, and home & garden essentials. Despite its rapid expansion, ShopEase has only scratched the surface of leveraging its customer data for strategic decision-making.
With years of data collected from its loyalty program, sales records, and customer demographics, ShopEase embarked on a customer segmentation project. This project aims to analyze customer behavior and create actionable segments to personalize marketing campaigns, enhance customer engagement, and drive retention. By clustering customers based on their age, income, spending habits, and loyalty metrics like membership years and purchase frequency, ShopEase is positioned to optimize its marketing strategies and improve overall customer satisfaction.

- An interactive Power BI dashboard can be downloaded [here]
- The step-by-step implementation of this project (including code) can be seen in [Extras and Resources].

## Data Structure
The dataset used for this segmentation included 1000 rows and the following key variables:

- `ID`: Unique identifier for each customer.
- `Age`: Customer’s age.
- `Age Group`: Customer's Age Group.
- `Gender`: Male, Female, and Other.
- `Income`: Annual income of the customer.
- `Spending Score`: A calculated metric representing the customer’s spending habits at ShopEase.
- `Membership Years`: Duration of membership in ShopEase’s loyalty program.
- `Purchase Frequency`: The number of purchases made by the customer within a year.

In this dataset, each grain represents an individual customer. For each customer, the dataset captures key demographic and behavioral information, such as their age, gender, annual income, spending habits (via the spending score), membership duration in the loyalty program, and purchase frequency. These attributes are used to understand and analyze customer behavior. The dataset used is found [here].
Before running the K-Means clustering algorithm, data cleaning and scaling were performed to ensure an error-free analysis.

## Overview of Findings/Insights
The K-Means clustering algorithm segmented customers into four distinct groups:

- Cluster 0: Older customers with low spending and average engagement — "Cautious older shoppers."
- Cluster 1: Younger customers with low spending and moderate engagement — "Price-conscious young shoppers."
- Cluster 2: High-spending, long-term loyal customers with frequent purchases — "Valuable loyal shoppers."
- Cluster 3: New high-spending customers with lower purchase frequency — "New high-value customers."

![pair scatter plot](https://github.com/user-attachments/assets/80bff89d-508f-4b99-a025-f54e0bdd0716)

### Key insights: ###
1. Cluster 2 represents long-term, high-spending customers who frequently shop across various categories like clothing, electronics, and home & garden, contributing significantly to revenue.
2. Cluster 3 shows potential in new customers who make large purchases but are not yet engaged for repeat transactions, presenting an opportunity for retention.
3. Cluster 1 and Cluster 0 display cautious spending habits, requiring focused engagement to drive higher purchase frequency.

In analyzing customer segmentation, income and membership duration did not significantly contribute to the final clustering model. This outcome highlights that income or membership duration alone may not be a strong differentiator in defining distinct customer groups. Instead, behaviors such as spending habits, and other features like age and purchase frequency provided clearer segmentation. This suggests that customers with varying income levels and loyalty may still share similar purchasing patterns, allowing businesses to target specific behavioral traits rather than focusing solely on financial status.

---
## Recommendations
The Marketing team should consider the following targeted strategies based on the insights gained from the customer segmentation:

### Cluster 0 - Older, cautious shoppers:
- Targeted Discounts: Implement senior discount programs or exclusive promotions for older customers, particularly in categories like groceries and home & garden.
- Loyalty Program: Offer incentives for increased purchases, such as points multipliers for every purchase.
- Product Education: Provide helpful guides and tutorials for electronics or sportswear products to ease the purchase decision process for this cautious group.

### Cluster 1 - Price-conscious young shoppers:
- Upsell & Cross-sell: Use targeted promotions offering product bundles or discounts on complementary items in categories like sportswear and clothing.
- Referral Programs: Leverage social media to engage younger customers with referral campaigns, encouraging them to bring friends to the platform for shared discounts.
- Loyalty Boosters: Offer limited-time discounts or rewards for repeat purchases within a specific period to build a habit of frequent shopping.

### Cluster 2 - Valuable loyal shoppers:
- VIP Programs: Create a loyalty or VIP program with exclusive perks like early access to new products or personal shopping assistants, particularly for electronics and home & garden categories.
- Personalized Recommendations: Use their shopping history to offer personalized recommendations or exclusive deals on high-ticket items.
- Surprise Gifts: Send personalized thank-you messages or surprise gifts to recognize their loyalty and ensure retention.

### Cluster 3 - New, high-value customers:
- Onboarding Campaigns: Implement a personalized onboarding experience that showcases ShopEase’s full product range and loyalty benefits, encouraging repeat purchases.
- Time-Sensitive Offers: Send exclusive, time-sensitive discounts (e.g., “20% off your next purchase within 30 days”) to prompt quicker follow-up purchases.
- Customer Feedback: Collect feedback to improve the shopping experience for these high-spending new customers and offer incentives for future purchases in exchange.

By applying these strategies, ShopEase can maximize customer engagement, increase purchase frequency, and foster long-term loyalty, ultimately driving sustained growth and commercial success.
