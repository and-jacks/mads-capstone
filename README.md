# Predicting NYC Metro Ridership: Data-Driven Insights for Smarter City Planning

## Overview

This project aims to predict **NYC transit ridership** using a combination of historical ridership data and **weather information**. It leverages machine learning models to forecast hourly ridership at various stations, providing insights into transit usage trends and aiding in resource planning.

### Project Goals

- **Predict hourly transit ridership** for NYC MTA subway stations.
- Incorporate **weather data** to understand its impact on ridership.
- Use **machine learning models** like Random Forest, time series, LSTM, and others for predictions.

## Data Sources
- **New York Metropolitan Transportation Authority**
  - **MTA Subway Hourly Ridership:** Beginning July 2020 - [Link to data source](https://data.ny.gov/Transportation/MTA-Subway-Hourly-Ridership-Beginning-July-2020/wujg-7c2s/about_data)
  - **MTA Subway Stations**: List of all Subway Stations - [Link to Subway Station Data](https://data.ny.gov/Transportation/MTA-Subway-Stations/39hk-dx4f/about_data)
    - **Data Dictionary** - [Link to data dictionary](https://data.ny.gov/api/views/wujg-7c2s/files/41d9b5bf-aeda-4a7e-b15c-a3c5f01ee345?download=true&filename=MTA_SubwayHourlyRidership_DataDictionary.pdf)
    - **MTA Open Data Program** - Licensing - [Link to License](https://new.mta.info/open-data)
- **National Oceanic and Atmospheric Administration & National Centers for Environmental Information**
  - **Weather Data** - NOAA - Climate Data Online -  - Central Park NY - [Link to Weather Data](https://www.ncdc.noaa.gov/cdo-web/datasets)\n
    - **Data Dictionary** - Daily Summaries PDF - [Link to Data Dictionary](http://www.ncei.noaa.gov/pub/data/cdo/documentation/GHCND_documentation.pdf)
    - **NOAA Open Data Dissemination (NODD)** -- License Free for Public Use - [Link to NODD](https://www.noaa.gov/information-technology/open-data-dissemination)

## Data Processing and Modeling
**Might be too large** just a though
```mermaid
graph TB;
    A([Data Porcessing and Modeling]):::folder
    A --> B([Downloaded Raw Data]):::folder
    
    B --> B1[(Hourly Ridership Data: df_filled_22.pkl, df_filled_23.pkl)]:::file
    B --> B2[(Weather Data: weather_data_ny.csv)]:::file
    
    B1 --> C1[[Process Ridership Data: ridership_data.ipynb]]:::notebook
    C1 --> D1[(Ridership Cleaned Data: ridership_long.csv)]:::file
    
    B2 --> C2[[Process Weather Data: weather_eda.ipynb]]:::notebook
    C2 --> D2[(Weather Cleaned Data: weather_data_cleaned.csv)]:::file
    
    D1 --> E[[Merge Datasets: ridership_weather.ipynb]]:::notebook
    D2 --> E
    
    E --> F[(Final Merged Data: ridership_weather.csv)]:::file

    F --> G[[RandomForest Model: RandomForest_model.ipynb]]:::notebook
    G --> H1[(Predictions: predictions_ridership.csv)]:::file
    G --> H2[(Station Metrics: stations_metrics.csv)]:::file

      H1 --> J[[Visualizations]]:::notebook
    H2 --> J

    classDef folder fill:#444444,stroke:#333,stroke-width:2px;
    classDef file fill:#336699,stroke:#333,stroke-width:2px;
    classDef notebook fill:#8b4513,stroke:#333,stroke-width:2px;
```
## Getting Started
**Prerequisites**
1. Clone the repository:
```bash
git clone https://github.com/and-jacks/mads-capstone.git
```
2. Navigate to the cloned directory
3. Create a Python environment in the working directory using [miniconda](https://docs.anaconda.com/miniconda/install/) (install if necessary) with Python Version 3.12.4 and activate it. 
```bash
conda create -n mads python=3.12.4
conda activate mads
```
4. Install requirements.txt
```bash
pip install -r requirements.txt
```
**Ridership predictions with weather data**

5. Open Notebook and run.
   - 5a. Run the eda_weather.ipynb notebook first.
   - 5b. Run the ridership_data_EDA.ipynb next; this  will export a large 600MB CSV file and place it in the cleaned_data directory. This file will be used in the next step.
   - 5c. Run the ridership_wx.ipynb next to merge the datasets and output the final CSV file for modeling. This will create the ridership_weather.csv file.  Large file ~1GB
   - 5d. Run the RandomForest_model.ipynb to create the predictions and metrics CSV files in the predictions_metrics folder.  These files will be used for the visualizations.

   





