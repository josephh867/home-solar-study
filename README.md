# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Group Project: Predicting Solar Power Generation with Weather Forecasting
By: Garrett Hart, Joseph Hicks, and Corina Lentz

## Project Directory
 
- [**Assets Folder**](/assets) - Contains all of the plots we created for our analysis and presentation, as well as the project instructions and other miscellaneous files.
- [**Datasets Folder**](/data) - Contains all of the relevant data for the project.
- [**Executive Summary**](executive-summary.md) - The executive summary for our project.
- [**Project Presentation**](project-05-presentation.pdf) - A slide deck used to explain how we approached this project.
- [**Weather Data Gathering Notebook**](/code/code1-weather-data-gathering.ipynb) - The notebook that details how the World Weather Online API was used to gather our weather data.
- [**Data Cleaning and EDA Notebook**](/code/code2-data-wrangling-eda.ipynb) - This notebook details how our PV and weather data was cleaned and merged. It also contains our EDA code and plots and some background information on the data.
- [**Modeling and Conclusions Notebook**](/code/code3-modeling.ipynb) - This notebook details how we fit the various models we used in this project as well as some brief conclusions.


## Problem Statement and Background

For this project, our goal was to **forecast solar panel output** for a residential array located in Antwerp, Belgium based on forecasted weather data using a supervised regression model. Such a model is valuable due to the way most modern power grids work - because storing electrical energy long term is difficult and costly, most power grids output exactly as much energy as is demanded by the areas they serve. Going over or under this demand can lead to blackouts or damage to electrical equipment. Therefore, having an accurate predictor of the output of power from a solar array days ahead of time can allow plant operators to act proactively in the face of changing weather conditions and demand.


## Description of Data

For this project, we made use of the following data sources:

|Dataset|Size|Source|Description|
|---|---|---|---|
|`PV_Elec_Gas3.csv`|73 KB|[Kaggle](https://www.kaggle.com/fvcoppen/solarpanelspower)|The solar panel output data, kindly donated to us by the user [fvcoppen](https://www.kaggle.com/fvcoppen). This also contains information about the cumulative gas power output daily from October 2011 to November 2020.|
|`weather_antwerp`|164 KB|[World Weather Online API](https://www.worldweatheronline.com/developer/)|The daily weather data we used as the features for our models. This data was gathered using World Weather Online's premium historical weather API ([*documentation*](https://www.worldweatheronline.com/developer/api/docs/historical-weather-api.aspx)). The specifics of how the data was requested can be found [here.](/code/weather_data_gathering.ipynb)|

Once the data was sourced, we utilized `pandas` to reset the data index and merge the two datasets on the `date` column. This allowed us to perform further EDA via `matplotlib` and `statsmodels` and create one-day and two-day lag terms to feed into our models. Once the data was cleaned and merged, we saved it to the following csv file:

|Dataset|Size|Description|
|---|---|---|
|`cleaned_data.csv`|259 KB|*3410 entries x 16 features*|

## Software, Library and Module Requirements

This project requires `Python` version `3.8.8` or greater to run properly. Within Python, we made use of the following modules and libraries:


|Module|Minimum Required Version|
|---|---|
|`numpy`|`1.19.5`|
|`pandas`|`1.2.4`|
|`matplotlib`|`3.3.4`|
|`seaborn`|`0.11.1`|
|`requests`|`2.25.1`|
|`scikit-learn`|`0.24.1`|
|`statsmodels`|`0.12.2`|



