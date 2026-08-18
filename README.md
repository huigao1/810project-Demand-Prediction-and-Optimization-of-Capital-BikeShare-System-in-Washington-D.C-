# Washington, D.C. Bikeshare Demand Prediction and Optimization

A machine learning project that forecasts daily demand for Capital Bikeshare and analyzes how weather, time, and station location affect ridership and bike availability across Washington, D.C.

## Project Overview

Capital Bikeshare has become an important part of Washington, D.C.'s transportation network. As ridership grows, operators face two connected challenges: predicting demand accurately and keeping enough bikes and open docks available at the right stations.

This project analyzes more than 16 million historical trips together with station activity and weather data. It combines exploratory data analysis, feature engineering, model comparison, hyperparameter tuning, and station-level imbalance analysis to support more efficient resource allocation.

## Objectives

- Forecast daily Capital Bikeshare demand
- Measure the effects of weather and seasonal conditions on ridership
- Identify the busiest and least-used stations
- Detect pickup and drop-off imbalances by location and time
- Recommend operational strategies for bike rebalancing

## Data

The analysis covers Capital Bikeshare activity from 2020 to 2024 and combines four datasets:

| Dataset | Size | Description |
| --- | ---: | --- |
| Trip records | 16M+ rows | Ride time, station, location, bike type, and rider type |
| Station usage | 873K+ rows | Daily pickup and drop-off counts by station |
| Station list | 916 rows | Station names and identifiers |
| Weather | 1,500+ rows | Temperature, precipitation, humidity, wind, visibility, and other daily conditions |

Data sources:

- [Capital Bikeshare System Data](https://capitalbikeshare.com/system-data)
- [Visual Crossing Weather Data](https://www.visualcrossing.com/)

## Project Workflow

1. Cleaned and integrated trip, station, usage, and weather data
2. Explored temporal, weather, and spatial demand patterns
3. Engineered holiday, weekend, and seasonal features
4. Reduced redundant variables and compared feature-selection methods
5. Evaluated six regression algorithms and a stacking ensemble
6. Tuned models using grid, random, and Bayesian search
7. Translated model outputs into rebalancing and planning recommendations

## Models Evaluated

- Decision Tree
- Random Forest
- Support Vector Regression
- Gradient Boosting
- XGBoost
- CatBoost
- Stacking ensemble

## Model Performance

| Model | Best R² |
| --- | ---: |
| Decision Tree | 0.761 |
| Random Forest | 0.815 |
| Support Vector Regression | 0.560 |
| Gradient Boosting | 0.826 |
| XGBoost | 0.826 |
| **CatBoost** | **0.834** |
| Stacking ensemble | 0.830 |

Bayesian-optimized CatBoost produced the strongest result with an **R² of 0.834**. The stacking model also performed well, reaching an R² of 0.830, but did not outperform the best individual model.

## Key Findings

### Weather and seasonality

- Moderate temperatures and partly cloudy conditions were associated with higher demand.
- Precipitation, humidity, strong winds, and heavy cloud cover were negatively associated with ridership.
- Summer, weekends, afternoons, and evenings showed distinct usage patterns.

### Station activity

- The busiest stations were concentrated in central Washington near commuter hubs, government buildings, and tourist destinations.
- Lower-usage stations were more common in suburban or less-connected areas.
- Major transit hubs experienced sharp pickup and drop-off imbalances during commuting periods.
- Station imbalance was greatest at night, followed by the morning and afternoon periods.

## Business Recommendations

- Use daily demand forecasts to plan bike and dock capacity in advance.
- Incorporate weather forecasts into operational staffing and redistribution decisions.
- Prioritize dynamic rebalancing at high-volume transit and tourist stations.
- Adjust allocation strategies for weekends, holidays, seasons, and time of day.
- Add station-level context such as nearby transit, attractions, schools, and retail locations to improve future predictions.

## Technology

`Python` `Pandas` `NumPy` `scikit-learn` `XGBoost` `CatBoost` `Google Colab` `Google Cloud Storage`

## Limitations and Future Work

The project focuses primarily on daily pickup demand. Future work could forecast pickups and drop-offs separately at each station, estimate upcoming shortages and dock congestion, and include neighborhood characteristics and nearby points of interest. These additions would support a more precise real-time bike redistribution system.


## Project Context

This project was completed for **BA810** in December 2024. It demonstrates large-scale data processing, exploratory analysis, machine learning, model optimization, and the translation of predictive insights into urban mobility recommendations.
