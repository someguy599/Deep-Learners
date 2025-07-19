---
title: "Classifying Movies Into Subgroups Using Models"
showToc: true
tocOpen: true
summary: We formed clusters of movie types based on various genres for better movie recommendations for viewers. 
date: 2025-07-11
---

## Introduction

In this mini project, we aimed to recognize patterns from a dataset of movies based on various genres, durations and popularities for better movie recommendations to viewers. 

---
## Data Acquisition 

We were given a dataset of 300 random fictional movies and their respective genres (could be multiple), runtimes (minutes), popularities (1-100), average rating (1-10). The data was already cleaned.

Below is a small sample of the data we recieved. 

{{< figure src="movietable.png" alt="Movie table" caption="Sample of the movie dataset showing title, genres, runtime, popularity, and average rating" class="center" width="100%" >}}

---
## Data Analysis 

### Exploring

First, we simply visualized the data and their individual features using basic plots such as histograms, box plots, and bar charts. 

{{< figure src="popularity.png" alt="Popularity" caption="Distribution of movie popularity scores across the dataset" class="center" width="100%" >}}

{{< figure src="runtime.png" alt="Runtime" caption="Distribution of movie runtimes in minutes" class="center" width="100%" >}}

{{< figure src="voteavg.png" alt="Voteavg" caption="Distribution of average user ratings for movies" class="center" width="100%" >}}

{{< figure src="genres.png" alt="Genre" caption="Frequency of different genres in the movie dataset" class="center" width="100%" >}}
### PCA and K-Means Clustering 

Using PCA (Principal Component Analysis), we reduced the many features of the data down to just two principal components. This made it possible to plot all movies on a simple 2D graph, where similar movies appear closer together. 

We then used KMeans clustering to group movies into three clusters based on these components. We then analyzed each cluster to see which genres were most common, and calculated the average popularity and ratings for each group.

{{< figure src="pcakmeans.png" alt="PCA K-Means" caption="2D scatter plot showing movie clusters identified using PCA and K-means clustering" class="center" width="100%" >}}

**<u>Cluster 0: Dramatic and/or Sci-Fi</u>**

- **Top 3 genres (percentage of cluster):**
    - Drama: 98.7%
    - Sci-Fi: 73.7%
    - Action: 48.7%
- **Average popularity:** 51.03
- **Average rating:** 6.58
- **Average runtime:** 105.32 minutes



**<u>Cluster 1: Comedies and Lighthearted Movies</u>**

- **Top 3 genres (percentage of cluster):**
    - Comedy: 90.2%
    - Romance: 57.4%
    - Sci-Fi: 52.5%
- **Average popularity:** 48.26
- **Average rating:** 6.66
- **Average runtime:** 104.60 minutes



 **<u>Cluster 2: Exciting Horror Films</u>**

- **Top 3 genres (percentage of cluster):**
    - Action: 65.7%
    - Horror: 64.7%
    - Romance: 46.1%
- **Average popularity:** 53.51
- **Average rating:** 6.37
- **Average runtime:** 95.32 minutes

Here is a visualization of the genres of the movies in each cluster (bar graph).

{{< figure src="genrepca.png" alt="Genre PCA" caption="Bar chart showing genre distribution across PCA-based clusters" class="center" width="100%" >}}

---



### t-SNE Reduction and K-Means Clustering 

t-SNE is another technique for reducing the data to two dimensions, but it focuses more on keeping similar movies close together. 

After applying t-SNE, we used KMeans again to create four clusters. By looking at the clusters, we recognized distinct patterns between these subgroups, just like before. 

{{< figure src="tsnekmeans.png" alt="t-SNE K-Means" caption="2D scatter plot showing movie clusters identified using t-SNE and K-means clustering" class="center" width="100%" >}}

**<u>Cluster 0: Dramatic and/or Sci-Fi</u>**

- **Top 3 genres:**
    - Drama: 92.1%
    - Sci-Fi: 75.3%
    - Action: 50.6%
- **Average popularity:** 51.97
- **Average rating:** 6.50



**<u>Cluster 1: Various Comedies</u>**

- **Top 3 genres:**
    - Comedy: 98.6%
    - Sci-Fi: 65.8%
    - Horror: 52.1%
- **Average popularity:** 50.28
- **Average rating:** 6.64



**<u>Cluster 2: Exciting Horror Films</u>**

- **Top 3 genres:**
    - Horror: 63.3%
    - Action: 55.7%
    - Romance: 29.1%
- **Average popularity:** 51.25
- **Average rating:** 6.46



**<u>Cluster 3: Rom-Coms</u>**

- **Top 3 genres:**
    - Drama: 91.5%
    - Romance: 86.4%
    - Comedy: 84.7%
- **Average popularity:** 48.81
- **Average rating:** 6.58

Here is a visualization of the genres of the movies in each cluster (bar graph).

{{< figure src="genretsne.png" alt="Genre t-SNE" caption="Bar chart showing genre distribution across t-SNE-based clusters" class="center" width="100%" >}}

---

## Conclusion 

As we can see from the results, the K-Means clustering using the PCA and t-SNE dimension reduction methods were both helpful, with the latter being a bit more specific and splitting comedy movies into rom-coms and other comedies, allowing for better reccomendations for viewers. Overall, we learned the use and effectiveness of dimensionality reduction and clustering algorithms, both of which are unsupervised learning methods.
