![Project Cover](assets/cover.png)

# Iris Cluster Analysis

## Business Overview
This project explores unsupervised learning techniques to uncover natural groupings within the classic Iris dataset using only numeric flower measurements. Although the dataset includes known species labels, they are intentionally excluded during modeling to simulate real-world scenarios where labels are unavailable or costly to obtain. The analysis demonstrates how clustering can support pattern discovery, exploratory insight generation, and preliminary classification tasks across domains such as biology, market segmentation, and anomaly detection.

## Problem Statement
The primary objective is to determine whether meaningful natural clusters exist within the Iris dataset based solely on numeric features (sepal length, sepal width, petal length, and petal width), and to evaluate how closely these clusters align with the known species categories. Specifically, the project seeks to:
- Identify intrinsic groupings using unsupervised clustering techniques.
- Determine the optimal number of clusters that best represent the underlying structure of the data.
- Assess post-hoc alignment between discovered clusters and true species labels using quantitative evaluation metrics.

## Exploratory Data Analysis & Key Trends
Exploratory analysis revealed that petal measurements (length and width) exhibit significantly stronger variability and separation compared to sepal measurements. Pairwise plots and correlation analysis showed clear isolation of the setosa group, while versicolor and virginica displayed partial overlap. Univariate distributions further highlighted multimodal patterns in petal features, suggesting latent group structure. Principal Component Analysis (PCA) confirmed that the first two components capture approximately 96% of total variance, with petal variables driving most of the separation.

## Models Explored and Results
Three unsupervised clustering approaches were evaluated:
1. K-Means Clustering: Using k = 3 (selected via Elbow and Silhouette methods), K-Means produced balanced clusters and the strongest alignment with true species labels. Setosa was perfectly separated, with reasonable differentiation between versicolor and virginica. This model achieved the highest Adjusted Rand Index (ARI ≈ 0.62).
2. Hierarchical Clustering (Ward’s Method): The dendrogram revealed a similar structure, isolating setosa early while showing weaker separation between the remaining species. Performance was comparable but slightly lower than K-Means (ARI ≈ 0.62).
3. Gaussian Mixture Model (GMM): Model-based clustering favored a two-cluster solution, effectively separating setosa from the combined versicolor/virginica group. While statistically valid, this outcome did not align with the project’s goal of identifying three natural groupings.
Overall, K-Means with k = 3 was selected as the preferred model due to its interpretability, stability, and superior empirical performance.

## Dashboard Preview
An interactive flexdashboard accompanies this analysis, providing visual exploration of cluster assignments, PCA projections, and model comparisons. The dashboard enables users to dynamically inspect how different clustering methods partition the data and how these partitions relate to known species labels.

## Reflections & Lessons Learned
This project reinforces several key lessons in unsupervised learning:
- Feature selection and scaling are critical, as clustering results are highly sensitive to variable magnitude and variance.
- Multiple evaluation perspectives (geometric, statistical, and external validation) are essential for robust model selection.
- Even well-known datasets benefit from an unsupervised lens, offering insights transferable to real-world problems where labels are absent.

Overall, the analysis highlights the effectiveness of K-Means for uncovering dominant structure in compact, well-behaved numeric datasets, while also demonstrating the value of comparing multiple clustering paradigms before deployment.
