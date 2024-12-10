# SpatialFireClusteringAnalysis

# Myanmar Forest and Agricultural Fires - April 2021

## Overview
This project applies various clustering algorithms to analyze forest and agricultural fires in Myanmar during the month of April 2021. By leveraging geospatial and statistical techniques, the project aims to uncover patterns and insights from fire events during this period.

## Data
The analysis is based on forest and agricultural fire occurrences, categorized by:
- **Forest Fires**: Focused on clustering fires in forested regions.
- **Agricultural Fires**: Focused on clustering fires in agricultural lands.

The datasets contain geospatial coordinates and fire radiative power (FRP) values for the months of March, April, and May.

## Clustering Algorithms Used
The following clustering algorithms were applied:
1. **KMeans**
2. **DBSCAN**
3. **HiSpatial Clustering**
4. **Hierarchical Clustering**
5. **BIRCH**
6. **HDBSCAN**
7. **Gaussian Mixture Models (GMM)**

### Evaluation Metrics
Each algorithm's performance was assessed using the following metrics:
- **Silhouette Score**: Measures how similar an object is to its own cluster compared to other clusters. Higher scores indicate better-defined clusters.
- **Davies-Bouldin Index**: Lower values signify better clustering, as they represent a smaller average ratio of intra-cluster distance to inter-cluster distance.

## Results
### Forest Fires
| Clustering Algorithm | Number of Clusters | Silhouette Score | Davies-Bouldin Index |
|-----------------------|--------------------|------------------|-----------------------|
| KMeans               | 6                  | 46.92%           | 27.2307              |
| DBSCAN               | 2                  | 29.19%           | 42.5491              |
| HiSpatial            | 8                  | -57.33%          | 29.0232              |
| Hierarchical         | 6                  | 39.04%           | 32.2842              |
| BIRCH                | 6                  | 52.00%           | 118.3592             |
| HDBSCAN              | 3                  | 17.82%           | 6.9184               |
| GMM                  | 4                  | 22.35%           | 1.6693               |

### Agricultural Fires
| Clustering Algorithm | Number of Clusters | Silhouette Score | Davies-Bouldin Index |
|-----------------------|--------------------|------------------|-----------------------|
| KMeans               | 8                  | 40.03%           | 279.6517             |
| DBSCAN               | 3                  | 42.92%           | 36.7471              |
| HiSpatial            | 5                  | -17.33%          | 25.6489              |
| Hierarchical         | 10                 | 38.25%           | 13.6215              |
| BIRCH                | 3                  | 51.97%           | 11.9873              |
| HDBSCAN              | 4                  | 34.88%           | 49.9387              |
| GMM                  | 2                  | 50.62%           | 2.5213               |

## Key Insights
### Forest Fires
- **KMeans** is ranked the best because it strikes a good balance between Silhouette Score (46.92%) and Davies-Bouldin Index (27.2307). It manages to create well-separated, cohesive clusters overall.
- **Hierarchical** follows due to its ability to provide moderate results for both cohesion (Silhouette Score: 39.04%) and separation (DBI: 32.2842).
- **GMM** is strong in separation (DBI: 1.6693) but weak in cohesion (Silhouette Score: 22.35%), making it less ideal for this task.
- **HDBSCAN** and **DBSCAN** perform well in terms of separation but have poor cohesion, making them less effective compared to KMeans and Hierarchical.
- **BIRCH** has good internal cohesion (Silhouette Score: 52%) but extremely poor cluster separation (DBI: 118.3592), placing it lower in the ranking.
- **HiSpatial** performs the worst due to very poor cohesion (Silhouette Score: -57.33%), even though it shows moderate separation (DBI: 29.0232).

### Agricultural Fires
- **GMM** is ranked first because it balances both Silhouette Score (50.62%) and Davies-Bouldin Index (2.5213), forming well-separated, cohesive clusters.
- **BIRCH** ranks second due to its excellent cohesion (Silhouette Score: 51.97%) and moderate separation (DBI: 11.9873).
- **DBSCAN** is third due to its moderate cohesion (Silhouette Score: 42.92%) and poor separation (DBI: 36.7471), though still performing decently compared to others.
- **Hierarchical** is ranked fourth because it shows reasonable separation (DBI: 13.6215) but only moderate cohesion (Silhouette Score: 38.25%).
- **HDBSCAN** performs poorly in terms of both cohesion (Silhouette Score: 34.88%) and separation (DBI: 49.9387), placing it fifth.
- **KMeans** comes sixth due to poor separation (DBI: 279.6517) and moderate cohesion (Silhouette Score: 40.03%), making it less effective here.
- **HiSpatial** is ranked last because of very poor cohesion (Silhouette Score: -17.33%), despite some reasonable separation (DBI: 25.6489).

## Repository Contents
- **Data**: Preprocessed datasets used for clustering.
- **Scripts**: Python scripts for implementing and evaluating clustering algorithms.
- **Results**: Tables and visualizations of clustering performance.
- **Reports**: Detailed analysis and insights derived from clustering results.
