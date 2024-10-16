# Customer-Segmentation-Using-KMeans-Clustering
---
## Project Overview

ShopEase, established in 2017, is a fast-growing e-commerce platform and supermarket chain that offers a wide range of products including clothing, groceries, sportswear, electronics, and home & garden essentials. Despite its rapid expansion, ShopEase has only scratched the surface of leveraging its customer data for strategic decision-making.
With years of data collected from its loyalty program, sales records, and customer demographics, ShopEase embarked on a customer segmentation project. This project aims to analyze customer behavior and create actionable segments to personalize marketing campaigns, enhance customer engagement, and drive retention. By clustering customers based on their age, income, spending habits, and loyalty metrics like membership years and purchase frequency, ShopEase is positioned to optimize its marketing strategies and improve overall customer satisfaction.

- An interactive Power BI dashboard can be downloaded [here](https://github.com/Chiagoziemchidera/Customer-Segmentation-Using-KMeans-Clustering/tree/main/Extras%20%26%20Resource%23)
- The step-by-step implementation of this project (including code) can be seen in [README_Technical](https://github.com/Chiagoziemchidera/Customer-Segmentation-Using-KMeans-Clustering/blob/main/README_Technical.md).

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

In this dataset, each grain represents an individual customer. For each customer, the dataset captures key demographic and behavioral information, such as their age, gender, annual income, spending habits (via the spending score), membership duration in the loyalty program, and purchase frequency. These attributes are used to understand and analyze customer behavior. The dataset used is found [here](https://github.com/Chiagoziemchidera/Customer-Segmentation-Using-KMeans-Clustering/tree/main/Extras%20%26%20Resource%23).

## Overview of Findings/Insights
The K-Means clustering algorithm segmented customers into four distinct groups:

- Cluster 0: "Older New Customers."
  
  Characteristics: Older demographic, new customers, and average spending and purchase frequency.

  Insights: This group represents an opportunity to cultivate loyalty among older customers who may be new to your brand. Their average spending and purchase frequency suggest room for growth in both engagement and transaction value.
- Cluster 1: "Budget-Conscious Loyal Shoppers."

  Characteristics: Mid-aged, loyal customers, low spenders, and average purchase frequency.
  
  Insights: While this group is loyal, their spending levels are low. There’s potential to increase their average order value or cross-sell additional products.
- Cluster 2: "Younger New customers."
  
  Characteristics: Younger demographic, new customers, average spend and purchase frequency.

  Insights: Young customers with average spending have high potential for long-term engagement. As new customers, their experience with the brand is still developing, and they could become valuable lifetime customers.
- Cluster 3: "Loyal High-Spending Customers"
  
  Characteristics: Mid-aged, high spenders and loyal customers with high purchase frequency.

  Insights: This is your most valuable segment, representing long-term loyal customers who spend frequently and significantly. Maintaining their satisfaction and loyalty should be a top priority.

![download (3)](https://github.com/user-attachments/assets/946b2159-6cb5-4e2c-b45d-17516f7db36c)

<img width="809" alt="cluster points" src="https://github.com/user-attachments/assets/35ee114e-9dc3-4de6-989d-49bf24ade177">

In analyzing customer segmentation, income did not significantly contribute to the final clustering model. This outcome highlights that income alone may not be a strong differentiator in defining distinct customer groups. Instead, behaviors such as spending habits, and other features like age and purchase frequency provided clearer segmentation. This suggests that customers with varying income levels and loyalty may still share similar purchasing patterns, allowing businesses to target specific behavioral traits rather than focusing solely on financial status.

---
## Recommendations
The Marketing and customer experience team should consider the following targeted strategies based on the insights gained from the customer segmentation:

### Cluster 0 - "Older New Customers.":
- Loyalty Programs: Tailor loyalty programs for this demographic, offering incentives like senior discounts, early access to promotions, or rewards for frequent purchases. This can help convert them into long-term, loyal customers.
- Targeted Marketing: Use age-appropriate marketing strategies such as personalized recommendations, email newsletters, and product offerings suited to their needs.
- Customer Support: Provide top-notch customer support, possibly including tutorials or guided shopping experiences to familiarize them with your offerings.

### Cluster 1 - "Budget-Conscious Loyal Shoppers.":
- Upselling and Cross-Selling: Introduce product bundles or personalized recommendations for higher-value items. Offering complementary products based on past purchases could increase their spend per transaction.
- Exclusive Deals for Loyal Customers: Provide exclusive deals or limited-time offers for loyal customers to make them feel valued and encourage higher spending.
- Customer Engagement: Run surveys or feedback campaigns to understand why they spend less and identify barriers to higher spending. Adjust offerings based on their preferences.

### Cluster 2 - "Younger New customers."
- Brand Engagement: Focus on building strong brand affinity through social media, personalized content, and engagement with modern platforms like Instagram, TikTok, or influencers popular with younger audiences.
- New Customer Onboarding: Implement a well-designed onboarding process, offering product tutorials, onboarding discounts, and regular communication to keep them engaged in the early stages of their customer journey.
- Subscription or Membership Models: Encourage recurring purchases through subscription services or membership models that offer benefits for regular engagement. Consider offering rewards for referrals to tap into their social networks.

### Cluster 3 - "Loyal High-Spending Customers":
- VIP Treatment: Offer personalized service, exclusive access to premium products, or invite them to special events. A "VIP" or "premium" loyalty program for top-tier customers can increase their sense of belonging.
- Early Access and Special Offers: Provide early access to new product launches or exclusive deals tailored to their preferences, ensuring they feel valued and prioritized.
- Continue to Build Relationships: Make sure to continuously engage with them through direct communication—personalized emails, thank-you notes, or feedback requests—that acknowledge their loyalty and importance.

By applying these strategies, ShopEase can maximize customer engagement, increase purchase frequency, and foster long-term loyalty, ultimately driving sustained growth and commercial success.
