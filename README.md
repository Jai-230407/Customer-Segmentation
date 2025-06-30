📘 Customer Segmentation Project — Theory & Explanation
🧠 Objective
The goal of this project is to perform customer segmentation by analyzing transactional data from an online retail business. This helps in understanding different customer behaviors and designing targeted marketing strategies (e.g., retention offers, loyalty programs, upselling).

📦 Dataset Overview
Source: Retail transactions (Online Retail.xlsx)

Key columns used: CustomerID, InvoiceDate, InvoiceNo, UnitPrice, Quantity, TotalPrice

🔨 Step-by-Step Methodology
1️⃣ Data Cleaning & Preprocessing
Removed rows with missing CustomerID, zero or negative Quantity/UnitPrice

Removed canceled orders (those with 'C' in InvoiceNo)

Created TotalPrice = Quantity × UnitPrice

✅ This ensures only meaningful, revenue-generating transactions are considered.

2️⃣ RFM Feature Engineering
Calculated three behavioral metrics per customer:

Recency: Days since last purchase

Frequency: Number of distinct invoices

MonetaryValue: Total spending

These are standard KPIs for understanding customer engagement and value.

3️⃣ Outlier Detection & Removal
Used Interquartile Range (IQR) method for Recency, Frequency, and MonetaryValue to eliminate extreme values.

✅ Outlier removal improves clustering quality by preventing skewed results.

4️⃣ Feature Scaling
Applied StandardScaler to normalize RFM values before clustering to prevent bias from variables on different scales.

5️⃣ Customer Clustering (KMeans)
Used KMeans clustering on scaled RFM data:

Tried different values of k (number of clusters)

Chose best k using:

Silhouette Score: Measures cohesion and separation between clusters

Calinski-Harabasz Index: Measures cluster compactness

Davies–Bouldin Index: Measures similarity between clusters

📌 Final model selected k = 4 for optimal segmentation.

7️⃣ Visualizations
Included powerful charts to communicate findings:

Violin plots (RFM by Cluster)

PCA 2D visualization of clusters

Heatmap of cluster centroids

Pairplots and barplots for interpretability

💡 Business Use Cases
Marketing: Send different promotions to different clusters

Churn Management: Identify and retain at-risk customers

Loyalty Programs: Reward frequent and high-spending customers

Customer Lifetime Value: Predict future value by segment

