# Project Technical Summary
---
This project aimed to segment customers based on their behavioral patterns and preferences using KMeans clustering. The segmentation process enabled me to group customers in ways to inform business strategies, marketing efforts, and customer service optimizations.

The workflow started with data cleaning, ensuring the dataset was free from errors or inconsistencies that could affect the model's performance. This involved correcting data types, removing duplicate rows, and correcting spelling errors.

Following the data cleaning, Exploratory Data Analysis (EDA) was performed using Python to identify patterns, correlations, and relationships within the data. Since KMeans clustering is sensitive to the scale of the data and not distribution, distribution analysis was not required.

To ensure the clustering algorithm was effective, the data was scaled before running the KMeans algorithm. 

Elbow method was used to determine the optimal number of clusters. Based on the result from the elbow method, k-means was applied with the chosen number of clusters (k = 4), and the resulting cluster labels were assigned to the original data for further analysis.

With many features in the dataset, PCA was employed to reduce the dimensions of the dataset while retaining the most important information. This made visualizing clusters easier.

After identifying the clusters, pair plots were used to gain more insights into the characteristics of each segment.

Finally, the insights gained from the clustering were visualized using Power BI, making them accessible and actionable for business decision-making. The visualizations included key attributes like gender distribution, preferred shopping categories, and age distributions, along with some descriptive analysis of each customer segment.

## Tools Used
- Excel: For data cleaning and preparation.
- Python: For data exploration (EDA), features scaling, clustering, and dimensionality reduction. (Python libraries: Pandas, NumPy, Matplotlib, Seaborn, Plotly.express, Scikit-learn, and OpenPyXL)
- Power BI: For building interactive and informative dashboards to visualize clustering insights.

## Data Cleaning Process (Excel)
Before starting the analysis, Excel was used to clean the raw data, which included:
- Data Type Adjustments: Ensured correct data types for numerical and categorical columns.
- Correcting Spelling Errors: Fixed spelling errors in column headers and categorical entries (e.g., product names).
- Removing Duplicates: Eliminated duplicate rows.
- Trailing Whitespaces: Removed unnecessary whitespaces for consistent formatting.

## Exploratory Data Analysis (EDA) using Python
Once the data was cleaned, EDA was performed in Python to understand the relationships between variables and to gain initial insights. Key features were examined using a correlation matrix to ensure that correlating features did not bias the clustering process, as KMeans uses Euclidean distance to calculate distances between data points. If two features were strongly correlated, they would carry redundant information, giving disproportionate weight to certain dimensions and potentially leading to skewed or redundant clusters. Since KMeans clustering is sensitive to data scale rather than distribution, distribution analysis was not required.
- Loading Data
  ```Python
  import pandas as pd
  df = pd.read_excel(r'C:\Users\Folio 1040 G3\Desktop\project\Customer segmentation.xlsx')  # Replace 'your_file.xlsx' with your file's path
  print(df.head())
  ```
  
- Library Import
  ```Python
  import seaborn as sns
  import matplotlib.pyplot as plt
  import numpy as np
  import plotly.express as px
  import plotly.graph_objects as go
   ```

- Correlation Matrix
  ```Python
  df_no_id = df.drop(columns=['ID', 'AGE GROUP', 'PREFERRED CATEGORY', 'LAST PURCHASE AMOUNT'])
  corr_matrix = df_no_id.corr()

  sns.heatmap(corr_matrix, annot=True, cmap='coolwarm')
  plt.title('Correlation Matrix')
  plt.show()
  ```

![correlation matrix](https://github.com/user-attachments/assets/1be5b6d3-d622-4a84-beb3-797c935dde01)

As no correlation was high enough, no features needed to be dropped.

 
## Scaling Data and Determining Optimal K
Since income had a different scale from the other features, the data was scaled using StandardScaler to ensure that the clustering algorithm treated all features equally, particularly when calculating distances between points. The elbow method was employed to determine the optimal number of clusters, balancing model complexity with interpretability. The "elbow" point is where increasing `k` yields diminishing returns in reducing WCSS. K-Means was performed with k ranging from 1 to 10. The Kmeans algorithm calculates the WCSS for each value of k and plot the results. Initially, WCSS decreases steeply, but after the optimal `k` which in this case was `4`, the rate of decrease slowed down significantly.

```Python
features = ['AGE', 'INCOME', 'SPENDING SCORE', 'MEMBERSHIP YEARS', 'PURCHASE FREQUENCY']
data = df[features]
```

```Python
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
scaled_data = scaler.fit_transform(data)
```

```Python
from sklearn.cluster import KMeans
import matplotlib.pyplot as plt

wcss = []
for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init='k-means++', max_iter=300, n_init=10, random_state=0)
    kmeans.fit(scaled_data)
    wcss.append(kmeans.inertia_)
    
plt.plot(range(1, 11), wcss)
plt.title('Elbow Method')
plt.xlabel('Number of Clusters')
plt.ylabel('WCSS')
plt.show()
```

![kcluster elbow](https://github.com/user-attachments/assets/485e0d7c-db74-4313-ba8b-1d035b43cff9)

## Applying k-means clustering Algorithm
Following the insights from the elbow method, the KMeans clustering algorithm was applied using the optimal number of clusters (k = 4). This allowed for segmentation of the data points based on their behavioral patterns. After completing the clustering, the resulting cluster labels were assigned to the original dataset, enabling targeted analyses of each cluster's characteristics and preferences.

```Python
optimal_k = 4  
kmeans = KMeans(n_clusters=optimal_k, init='k-means++', max_iter=300, n_init=10, random_state=0)
clusters = kmeans.fit_predict(scaled_data)

df['Cluster'] = clusters # Add cluster labels to your original DataFrame
```

## PCA Dimensionality Reduction
Principal Component Analysis (PCA) was used to reduce dimensionality and make the clustering results easier to visualize. By projecting the data into a 2D space, meaningful groupings and patterns became easier to spot.

```Python
from sklearn.decomposition import PCA

pca = PCA(n_components=2)
principal_components = pca.fit_transform(scaled_data)
df_pca = pd.DataFrame(data=principal_components, columns=['PC1', 'PC2'])
df_pca['Cluster'] = clusters

plt.figure(figsize=(8, 6))
plt.scatter(df_pca['PC1'], df_pca['PC2'], c=df_pca['Cluster'], cmap='viridis')
plt.title('Customer Segmentation using K-Means')
plt.xlabel('Principal Component 1')
plt.ylabel('Principal Component 2')
plt.show()
```

![PCA kmeans viz](https://github.com/user-attachments/assets/06309a48-d827-445d-b39f-126c901e6874)

```Python
df['PC1'] = df_pca['PC1']  # Add the PC1 column
df['PC2'] = df_pca['PC2']  # Add the PC2 column
```


## Gaining Insights Using Descriptive Analysis and Pair Plots
Once the clusters were identified, descriptive analysis was conducted for each cluster to extract deeper insights. Metrics such as the average, standard deviation, minimum, maximum, and median were examined to better understand the distinct characteristics of each cluster. Pair plots were also utilized to visualize the relationships and traits within each cluster, providing a comprehensive view of each segment.

```Python
# Pair plot for numerical variables
sns.pairplot(df, hue='Cluster', vars=['AGE', 'INCOME', 'SPENDING SCORE', 'MEMBERSHIP YEARS', 'PURCHASE FREQUENCY'])
plt.show()
```

![download](https://github.com/user-attachments/assets/0d47e4bd-3056-423d-b668-9a711137115a)

```Python
cluster_summary = df.groupby('Cluster').agg({
    'AGE': ['mean', 'median', 'min', 'max', 'std'],
    'INCOME': ['mean', 'median', 'min', 'max', 'std'],
    'SPENDING SCORE': ['mean', 'median', 'min', 'max', 'std'],
    'MEMBERSHIP YEARS': ['mean', 'median', 'min', 'max', 'std'],
    'PURCHASE FREQUENCY': ['mean', 'median', 'min', 'max', 'std']
}).reset_index()
```



## Power BI Visualizations
To make the results understandable to non-technical stakeholders, Power BI was used to create an interactive dashboard with multiple visualizations, including:
- Cards to describe key attributes (e.g., average income, average age).
- Pie charts to compare gender distribution in different clusters.
- Bar charts to show preferred shopping categories by cluster.
- Box plots to represent age distribution by cluster.

- DAX formula to calculate the most frequently bought category:

```DAX
Popular Category = 
    CALCULATE(
        FIRSTNONBLANK(
            customers_with_pca_and_clusters_1[PREFERRED CATEGORY],
            1
        ),
        TOPN(
            1,
            SUMMARIZE(
                customers_with_pca_and_clusters_1,
                customers_with_pca_and_clusters_1[PREFERRED CATEGORY],
                "Count", COUNT(customers_with_pca_and_clusters_1[PREFERRED CATEGORY])
            ),
            [Count],
            DESC
        )
    )
```

- Python code for box plot on dashboard:

```Python
# dataset = pandas.DataFrame(AGE, Cluster)
# dataset = dataset.drop_duplicates()

# Paste or type your script code here:
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd

plt.figure(figsize=(12, 12))

# Create the boxplot with Age on the Y-axis and Cluster on the X-axis
sns.boxplot(x=dataset['Cluster'], y=dataset['AGE'], palette='Blues', linewidth=2.5)

plt.title('Age Distribution by Cluster', fontsize=30, fontweight='bold')
plt.xlabel('Cluster', fontsize=30, fontweight='bold')  
plt.ylabel('AGE', fontsize=30, fontweight='bold')  

plt.tick_params(axis='both', labelsize=20)

for tick in plt.gca().get_xticklabels() + plt.gca().get_yticklabels():
    tick.set_fontweight('bold') 
    tick.set_fontsize(26)  

sns.despine() 

plt.tight_layout()
plt.show()
```

<img width="606" alt="bi screenshot" src="https://github.com/user-attachments/assets/34d93828-a59b-4340-929b-d8426df89d58">




