# Predicting NYC Metro Ridership: Data-Driven Insights for Smarter City Planning

## Overview

This project aims to predict **NYC transit ridership** using a combination of historical ridership data, **weather information**, and machine learning models. It explores patterns in transit usage, builds predictive tools, and provides insights to aid city planners and transit authorities in resource optimization and infrastructure planning.

## Project Goals

- **Predict hourly transit ridership** for NYC MTA subway stations.
- Analyze **temporal and geographical trends** in ridership.
- Incorporate **weather data** to understand its impact on ridership patterns.
- Use **machine learning models** like Random Forest, LSTM, and time series techniques for predictions.
- Develop tools and visualizations to provide actionable insights for transit authorities and city planners.

## Visualization of Planning Insights 
<img src="images/planning_map.png" alt="Planning Map" width="600"/>

The map above showcases planning insights derived from MTA ridership data, highlighting areas of high traffic and potential infrastructure needs.

---

## Data Sources

### New York City Metropolitan Transit Authority (NYC MTA)
- **MTA Subway Hourly Ridership:** Comprehensive hourly ridership data beginning July 2020.  
  [Link to data source](https://data.ny.gov/Transportation/MTA-Subway-Hourly-Ridership-Beginning-July-2020/wujg-7c2s/about_data)  
  - [Data Dictionary](https://data.ny.gov/api/views/wujg-7c2s/files/41d9b5bf-aeda-4a7e-b15c-a3c5f01ee345?download=true&filename=MTA_SubwayHourlyRidership_DataDictionary.pdf)  
  - [MTA Open Data Program Licensing](https://new.mta.info/open-data)  
- **MTA Subway Stations:** List of subway stations, including identifiers, locations, and associated lines.  
  [Link to data source](https://data.ny.gov/Transportation/MTA-Subway-Stations/39hk-dx4f/about_data)

### NOAA Weather Data
- **Weather Data:** Climate summaries for Central Park, NY, including temperature, precipitation, and extreme weather events.  
  [Link to Weather Data](https://www.ncdc.noaa.gov/cdo-web/datasets)  
  - [Data Dictionary](http://www.ncei.noaa.gov/pub/data/cdo/documentation/GHCND_documentation.pdf)  
  - [NOAA Open Data Dissemination Licensing](https://www.noaa.gov/information-technology/open-data-dissemination)
 
### Trip Advisor API 
  - API Access through Devloper Portal [Developer Portal](https://www.tripadvisor.com/developers)
      - Developer account would need to be crated to obtain an API key.
  - [Trip Advisor License](https://tripadvisor-content-api.readme.io/reference/terms-of-use)

---

## References

1. Hightower, Ashley, et al. "A Comparison of Time Series Methods for Post-COVID Transit Ridership Forecasting." *Journal of Public Transportation*, vol. 26, 2024.  
   [Read Article](https://doi.org/10.1016/j.jpubtr.2024.100097)

2. Mou, X. H., et al. (2023). "Prediction of Subway Ridership Using Deep Learning Algorithms." *2023 International Conference on Machine Learning and Artificial Intelligence (CMLAI)*, IEEE, 1–6.  
   [Read Article](https://ieeexplore.ieee.org/document/10444286)

3. Liu, Jingyi. (2023). "Analysis and Prediction of Subway Ridership: Take a Station in Hangzhou as an Example." *Highlights in Science, Engineering and Technology*, 39(1), 315–320.  
   [Read Article](https://doi.org/10.54097/hset.v39i.6547)

4. Park, Y., et al. (2022). "Machine Learning Approach for Study on Subway Passenger Flow." *Scientific Reports*, vol. 12, no. 2754.  
   [Read Article](https://doi.org/10.1038/s41598-022-06767-7)


---

## Methodology

### Data Cleaning and Preprocessing
Our preprocessing pipeline includes:
- Cleaning and aggregating hourly ridership data by station and borough.
- Integrating weather variables such as temperature and precipitation.
- Excluding data from the COVID-19 pandemic period to focus on stable post-pandemic trends.

### Visualization Tools
We developed interactive maps and heatmaps to analyze ridership patterns. These tools highlight:
- Daily, weekly, and seasonal trends.
- Over- and under-utilized stations.
- Peak and off-peak ridership distributions.

### Prediction Models
We implemented **LSTM neural networks** for time series forecasting, leveraging:
- Hourly ridership data for 2022 to forecast 2023 patterns.
- Contextual station features (borough, nearby attractions, and service lines).
- Evaluation metrics: Mean Absolute Error (MAE) and Symmetric Mean Absolute Percentage Error (SMAPE).

---

## Key Insights

### Findings
- **Temporal Challenges:** Peak rush hours exhibit the highest prediction errors due to dynamic commuter behavior.
- **Geographical Patterns:** Stations in the Bronx demonstrated unique prediction challenges linked to transit dependency and infrastructure variations.
- **Seasonal Variability:** Fall and spring showed the highest absolute and proportional errors, influenced by school schedules, tourism, and weather patterns.

### Recommendations
- Integrate more detailed event and economic data.
- Develop station-specific models to capture unique ridership patterns.
- Enhance feature engineering to incorporate neighborhood dynamics and transit interactions.

---

## Getting Started

### Prerequisites
1. Clone the repository:
   ```bash
   git clone https://github.com/and-jacks/mads-capstone.git
   ```
2. Create a Python environment:
   ```bash
   conda create -n mads python=3.12.4
   conda activate mads
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
### LSTM Forecasting
Folder - EDA_LSTM
  - 1a. Run `Andrew_EDA_LSTM_Viz_Final_12.3.24.ipynb`
   
### Visualizations
Folder - Visualization run
  - 1a. Run `station_data.ipynb`
  - 1b. Run `trend_viz,ipynb`

### Random Forest Regressor Pipeline Steps (created but not fully utilized)
Folder - Modeling_preprocess_clean
  - 1a. Run `eda_weather.ipynb` to process weather data.
  - 1b. Run `ridership_data_EDA.ipynb` to preprocess ridership data (exports a ~600MB file).
  - 1c. Run `ridership_wx.ipynb` to merge datasets (outputs a ~1GB file).
  - 1d. Run `RandomForest_model.ipynb` to train models and generate predictions and metrics.

---

## Contributions
- **Andrew Jackson:** Data pipelines and ridership forecasting.
- **Armando Medina:** Weather data integration, prediction analysis, and server setup.
- **Lydia Schrandt:** Interactive visualizations, nearby attractions integration, and report drafting.

---

## Ethical Considerations
- **Data Privacy:** Ensuring transparency in data collection and avoiding misuse for surveillance.
- **Equity in Modeling:** Addressing potential biases to prevent further marginalization of underserved communities.

---

## Appendix
- Event data exploration was excluded due to challenges in data quality and geospatial precision, though future iterations may incorporate a refined event dataset for enhanced prediction accuracy.
- Random Forest Model provided great results, but decided that LSTM was a better fit for our project. 
---

------------------------------------------------------







