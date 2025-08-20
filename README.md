# CyberCluster: Unsupervised Intrusion Detection with K-means

An unsupervised machine learning approach to detect cybersecurity intrusions and anomalies using K-means clustering. This project identifies patterns in network traffic data to flag potential security threats without relying on pre-labeled attack data.

## 📊 Table of Contents

- [Overview](#-overview)
- [Installation](#️-installation)
- [Usage](#-usage)
- [Methodology](#-methodology)
- [Results](#-results)
- [Contributing](#-contributing)
- [Contact](#-contact)

## 🚀 Overview

CyberCluster leverages K-means clustering to analyze network session data and identify potential security threats. This unsupervised approach:

- Processes network traffic data including protocol types, encryption methods, session durations, and access patterns
- Identifies distinct behavioral clusters in network traffic
- Detects anomalies that deviate significantly from established patterns
- Classifies network sessions into categories ranging from "Normal" to "Suspicious"
- Provides security teams with prioritized investigation targets

## 🛠️ Installation

### Prerequisites

- Python 3.8 or higher
- Jupyter Notebook
- Required Python packages (see requirements in notebook)

### Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/adeel-iqbal/cybersecurity-intrusion-detection-kmeans.git
   cd cybersecurity-intrusion-detection-kmeans
   ```

2. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

3. **Open `cybersecurity_intrusion_detection_kmeans.ipynb`** to run the analysis.

## 📝 Usage

1. Open the Jupyter notebook: `cybersecurity_intrusion_detection_kmeans.ipynb`
2. Execute cells sequentially to:
   - Load and preprocess the cybersecurity dataset
   - Determine optimal cluster count using Elbow Method and Silhouette Score
   - Train the K-means model with k=8 clusters
   - Detect anomalies based on distance to cluster centroids
   - Visualize results and interpret findings

> **Note**: The dataset `cybersecurity_intrusion_data.csv` should be in the same directory as the notebook.

## 🔬 Methodology

### Data Preprocessing

- **Feature Selection**: Removed identifier columns and target labels
- **Missing Value Handling**: Imputed categorical features with most frequent values
- **Categorical Encoding**: Mapped protocol types, encryption methods, and browsers to numerical values
- **Feature Scaling**: Standardized all features to ensure equal weighting

### Clustering Process

**Optimal Cluster Determination:**
- Elbow Method to identify inertia reduction points
- Silhouette Score to evaluate cluster separation quality
- Selected k=8 based on both metrics

**K-means Implementation:**
- Initialized with 8 clusters
- Used Euclidean distance metric

**Anomaly Detection:**
- Calculated distances to cluster centroids
- Flagged points beyond 95th percentile as anomalies
- Identified 477 potential threats (5% of dataset)

### Cluster Interpretation

| Cluster Type | Clusters | Description |
|--------------|----------|-------------|
| **Normal** | 1, 3, 4, 6 | Standard network behavior patterns |
| **Normal - Heavy Usage** | 0 | High activity but within expected parameters |
| **Suspicious - Long Session** | 2 | Unusually extended session durations |
| **Suspicious** | 5, 7 | Irregular patterns in login attempts or access times |

## 📈 Results

### Key Findings

- ✅ Successfully identified 8 distinct behavioral clusters in network traffic
- ⚠️ Detected 477 anomalies representing potential security threats
- 🔍 Cluster 2 ("Suspicious - Long Session") contained the most anomalies (120)
- 📊 Achieved clear separation between normal and suspicious behaviors in PCA visualization

### Performance Metrics

| Metric | Value |
|--------|-------|
| **Cluster Distribution** | Varied sizes from 439 to 2034 records per cluster |
| **Anomaly Rate** | 5% of total records flagged for investigation |
| **Silhouette Score** | Peak at k=8 indicating well-defined clusters |
| **Inertia Reduction** | Significant drop up to k=8 with diminishing returns beyond |

### Visualizations

- 📈 Elbow Method plot for optimal k selection
- 📊 Silhouette Score analysis
- 🎯 PCA cluster visualization with anomaly highlighting
- 📋 Feature importance analysis per cluster

## 🤝 Contributing

We welcome contributions to enhance CyberCluster! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request


## 📞 Contact

**Adeel Iqbal** - [@adeel-iqbal](https://github.com/adeel-iqbal) - adeelmemon096@yahoo.com

**Project Link**: [https://github.com/adeel-iqbal/cybersecurity-intrusion-detection-kmeans](https://github.com/adeel-iqbal/cybersecurity-intrusion-detection-kmeans)

---

<div align="center">

**Made with ❤️ for cybersecurity professionals**

</div>
