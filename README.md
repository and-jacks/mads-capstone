# NYC Transit Ridership Forecast Project

## Overview

This project aims to predict **NYC transit ridership** using a combination of historical ridership data, **weather information**, and event data. It leverages machine learning models to forecast hourly ridership at various stations, providing insights into transit usage trends and aiding in resource planning.

### Project Goals

- **Predict hourly transit ridership** for NYC subway stations.
- Incorporate **weather data** to understand its impact on ridership.
- Use **machine learning models** like Random Forest, time series, LSTM, and others.  add more--- for predictions.

## Data Sources
- **MTA Subway Hourly Ridership:** Beginning July 2020 - [Link to data source](https://data.ny.gov/Transportation/MTA-Subway-Hourly-Ridership-Beginning-July-2020/wujg-7c2s/about_data)
  - **Data Dictionary** - [Link to data dictionary](https://data.ny.gov/api/views/wujg-7c2s/files/41d9b5bf-aeda-4a7e-b15c-a3c5f01ee345?download=true&filename=MTA_SubwayHourlyRidership_DataDictionary.pdf)
  - **MTA Open Data Program** - Licensing - [Link to License](https://new.mta.info/open-data)
  
- **Weather Data** - NOAA - Climate Data Online - National Centers for Environmental Information - Central Park NY - [Link to Weather Data](https://www.ncdc.noaa.gov/cdo-web/datasets)
  **Note** : Due to the recent weather events in the easter part of the United States, the data center that provides and manages weather data history is running slow.   
  - **Data Dictionary** - Daily Summaries PDF - [Link to Data Dictionary](http://www.ncei.noaa.gov/pub/data/cdo/documentation/GHCND_documentation.pdf)
  - **NOAA Open Data Dissemination (NODD)** -- License Free for Public Use - [Link to NODD](https://www.noaa.gov/information-technology/open-data-dissemination)

## 
-

## Explanation
**Might be too large** just a though
```mermaid
graph TB;
    A([Data Porcessing and Modeling]):::folder
    A --> B([Downloaded Raw Data]):::folder
    
    B --> B1[(Hourly Ridership Data: df_filled_22.pkl, df_filled_23.pkl)]:::file
    B --> B2[(Weather Data: weather_data_ny.csv)]:::file
    
    B1 --> C1[[Process Ridership Data: ridership_data.ipynb]]:::notebook
    C1 --> D1[(Ridership Cleaned Data: ridership_long.pkl)]:::file
    
    B2 --> C2[[Process Weather Data: weather_eda.ipynb]]:::notebook
    C2 --> D2[(Weather Cleaned Data: weather_data_cleaned.csv)]:::file
    
    D1 --> E[[Merge Datasets: ridership_weather.ipynb]]:::notebook
    D2 --> E
    
    E --> F[(Final Merged Data: ridership_weather.csv)]:::file

    F --> G[[RandomForest Model: RandomForest_model.ipynb]]:::notebook
    G --> H1[(Predictions: predictions_ridership.csv)]:::file
    G --> H2[(Station Metrics: stations_metrics.csv)]:::file

    classDef folder fill:#444444,stroke:#333,stroke-width:2px;
    classDef file fill:#336699,stroke:#333,stroke-width:2px;
    classDef notebook fill:#8b4513,stroke:#333,stroke-width:2px;




