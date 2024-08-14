# Spark-Cluster

This project delivers a comprehensive solution for processing and visualizing visa numbers in Japan using PySpark and Plotly. The Spark clusters are configured within a Docker container deployed on Azure.

## Contents
- [System Architecture](#system-architecture)
- [Setup & Requirements](#setup--requirements)
- [Usage](#how-to-use)
- [Key Features](#key-features)
- [Notes](#additional-notes)

## System Architecture
![System Architecture](assets/Sparkcluster_architecture.png)

## Setup & Requirements
1. **Azure Account**: Make sure you have an active Azure account for cloud resources.
2. **Docker**: The Spark master-worker cluster is deployed inside a Docker container running on Azure.
3. **Python Dependencies**: Install the following Python libraries:
   - PySpark
   - Plotly Express
   - pycountry
   - pycountry_convert
   - fuzzywuzzy

## How to Use
- **Prepare the Data**: Place the CSV file named visa_number_in_japan.csv in the input folder.
- **Run the Pipeline**: Execute the provided Python script to process the data.
- **View Outputs**: The generated visualizations will be saved as interactive HTML files in the output folder. Additionally, cleaned and transformed data will also be stored as a CSV in the same directory.

## Key Features
- **System Setup**: The project uses a Spark master-worker cluster deployed via Docker on Azure for efficient data processing.
- **Data Ingestion**: Loads visa data for Japan from a CSV file.
- **Data Cleaning**: Performs tasks such as standardizing column headers, removing null values, and correcting country names using fuzzy string matching.
- **Data Transformation**: Adds enriched information by mapping countries to their respective continents.
- **Data Visualization**: Utilizes Plotly Express to create dynamic and interactive visualizations of visa trends in Japan.

## Additional Notes
- Ensure your Azure and Docker environments are properly set up to support the Spark master-worker cluster's operations.
- The accuracy of country corrections and continent mapping relies on the ;'pycountry' and 'pycountry_convert' libraries; keep these libraries updated for the best results.
- To handle unmatched country names, you can customize the 'country_mapping' dictionary located in the 'main.py' file. This allows you to manually define mappings for better data accuracy.