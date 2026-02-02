# 🎯 Retail Customer Intelligence: Segmentation & Targeting Engine

> **Unlocking revenue by transforming 950k+ transactions into 5 actionable customer personas using K-Means and t-SNE.**

<img width="1024" height="501" alt="image" src="https://github.com/user-attachments/assets/571a318f-ca1e-48a7-a5d0-81a91aaca9f8" />


![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![ML](https://img.shields.io/badge/ML-Scikit_Learn-orange.svg)
![Status](https://img.shields.io/badge/Status-Complete-green.svg)

## 💼 Executive Summary
In a dataset of **951,668 transactions**, traditional "spray and pray" marketing was failing to engage high-value clients. This project moved beyond basic demographics to implement **Behavioral Segmentation**. 

By engineering features like **Recency, Frequency, and Monetary Value (RFM)** and applying unsupervised learning, the analysis identified **5 distinct customer cohorts**. The most critical finding was the identification of a **"VIP Champion"** segment—a small group generating outsized revenue—who were previously receiving generic treatment.

## 🔍 Key Business Insights (The "So What?")
The clustering model (K=5) revealed clear strategic opportunities. 
*Note: Clusters 0 and 1 appeared similar mathematically but were split by Age, a critical differentiator for marketing channel selection.*

| Segment | Label | Characteristics | Strategic Action |
| :--- | :--- | :--- | :--- |
| **Cluster 3** | 🏆 **VIP Champions** | High spend, frequent, ages 35-55. | **Retain:** Launch exclusive VIP tier with early access & premium service. |
| **Cluster 4** | 💎 **Whales** | Large but *infrequent* purchases (35-65). | **Nudge:** Alert them to new high-ticket drops; "Don't miss out" messaging. |
| **Cluster 2** | 💤 **At-Risk** | Low revenue, lapsed users (40-70). | **Win-Back:** "We Miss You" campaigns with aggressive discounts to re-activate. |
| **Cluster 0** | 👴 **Steady Seniors** | Moderate spend, reliable, ages 60-75. | **Engage:** Community events & loyalty rewards (Email/Mail focus). |
| **Cluster 1** | 📱 **Young Regulars** | Moderate spend, reliable, ages 30-40. | **Engage:** Mobile-first offers & social media campaigns. |

## 🛠️ Technical Methodology
The analysis navigated the complexity of real-world data where "clean" clusters rarely exist.

1.  **Determining K (The Mathematical Case):**
    *   **Silhouette Analysis:** While scores were generally low (typical for high-dimensional behavioral data), **K=5** yielded the mathematical peak.
    *   **Elbow Method:** Inertia decay significantly slowed after K=5, signaling diminishing returns for additional granularity.
    *   **Dendrogram:** Confirmed a natural hierarchical split between 2 and 5 groups.

2.  **Addressing Overlap (Cluster 0 vs 1):**
    *   Initial PCA showed overlap between these groups, suggesting linear separation was insufficient.
    *   However, deeper analysis revealed the overlap was driven by similar *spending* patterns but distinct *demographics* (Age Gap: 30s vs 60s). Keeping them separate allows for distinct marketing tones (TikTok vs. Email).

3.  **Advanced Visualization (t-SNE):**
    *   **PCA Limitation:** Principal Component Analysis explained 65% of variance but struggled with non-linear boundaries.
    *   **t-SNE Optimization:** By tuning **perplexity to 20** (better for capturing global structure in large datasets), the model successfully revealed 5 distinct "cores," visually validating the segmentation strategy [file:56].


