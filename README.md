# Streaming Platform Data Analysis (PySpark Project)
A PySpark data project integrating streaming platform datasets (Netflix, HBO Max, Apple TV and Amazon Prime Video), performing data enrichment, cleaning, and analysis to uncover content availability trends across countries.

This project provides an analysis of movies and TV shows available in **Czechia** across multiple streaming platforms. Using international IMDb ratings, it covers insights about the best-rated content, most popular genres, and platform-specific trends for titles available in Czech Republic.

## Key Steps
1. **Data Preparation**:
   - The datasets for Netflix, HBO Max, Apple TV+, and Amazon Prime Video were ingested and combined into a PySpark DataFrame.
   - Data cleaning included handling invalid values, ensuring consistency in columns like genres, release years and IMDb ratings.

2. **Data Exploration**:
   - Exploration identified missing or invalid entries in the dataset.
   - Columns such as `genres`, `availableCountries`, and `releaseYear` were transformed to enhance usability.

3. **Insights and Analysis for Czechia**:
   - The dataset was filtered to focus on movies and TV shows available in Czechia.
   - Number of movies and TV shows available on each platform available in Czechia.
   - Identification of the best-rated genres of movies and TV series.
   - Analysis of top 10 rated movies and TV series available in Czechia.
   - Average IMDb ratings by platform for movies and TV series.

## Tools and Technologies Used

- **PySpark**: For data ingestion, cleaning, and analysis.
- **Google Cloud Dataproc Cluster**: For running Jupyter notebook on a distributed environment.
- **Google Cloud Storage**: For storing and accessing the raw datasets.
- **BigQuery Studio**: For saving processed datasets.

## How to Use

1. **Set Up a GCP Account**:
   - Create a Google Cloud Platform (GCP) account at [https://cloud.google.com/](https://cloud.google.com/).
   - Enable the required services: **Dataproc**, **Cloud Storage**, and **BigQuery**.

2. **Create a GCP Dataproc Cluster**:
   - Navigate to the **Dataproc** section in the GCP console.
   - Create a new cluster with the following specifications:
     - Choose a region close to your location.
     - Use the default cluster configuration.
     - Ensure the cluster supports Jupyter Notebooks.
    - **Or you can follow these instructions:** [Running Jupyter Notebook on a Spark Cluster on GCP Dataproc](https://dasiyql.medium.com/deploy-application-from-jupyter-lab-to-a-spark-cluster-on-gcp-part-2-ca792f99c8a6).

3. **Run the Jupyter Notebook**:
   - Use the Jupyter Notebook environment on the Dataproc cluster (no local Spark installation is required).
   - Upload the project notebook to the cluster and execute the cells step-by-step.

4. **Create a GCS Bucket**:
   - Navigate to the **Cloud Storage** section in the GCP console.
   - Create a new bucket:
     - Choose a bucket name: `raw-platform-data`.
     - Select a region.
     - Use the default bucket configuration.
   - Upload source datasets into a bucket.

5. **Run the script**:
    - Upload .ipynb script to the service bucket that is used by Dataproc cluster.
    - Run Jupyter in Web Interfaces inside the cluster. 
    - Stop or delete the cluster after using.

## Dataset Sources:
- https://www.kaggle.com/datasets/octopusteam/full-netflix-dataset
- https://www.kaggle.com/datasets/octopusteam/full-amazon-prime-dataset
- https://www.kaggle.com/datasets/octopusteam/full-apple-tv-dataset
- https://www.kaggle.com/datasets/octopusteam/full-hbo-max-dataset