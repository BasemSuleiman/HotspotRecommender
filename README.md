# New York City taxis historical order distribution check and availability prediction system

This is the capstone project of my master degree of data science in USYD, supervised by Dr. Basem Suleiman.

The below paper must be cited should any of the materials be used.

H. Huan, B Suleiman, and W. Yaqub. _Hotspots Recommender: Spatio-temporal Prediction of Ride-hailing and Taxicab Services._ Web Information System Engineering (WISE), 2022

The data set we use is [the New York City Taxi and Limousine Commission (TLC) Trip Record Data](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page), which is released and under supervision by **the New York City Taxi and Limousine Commission (TLC)**

The project fully utilizes Google Colab computation power and all intermedium data is stored in Google Drive, so please make sure you have authorized your drive to Colab when running the code and change the directory path to your own drive.

For a demo preview, please open the `DATA5709_Capstone_Shinyapp_online.ipynb` in [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/BasemSuleiman/HotspotRecommender/blob/main/DATA5709_Capstone_Shinyapp_online.ipynb). It dynamically creates a host and a temporary url for inspectation.

---------------

## Table of Content
- [Data download and preprocessing](#data-download-and-preprocessing)
- [Clean data initial analysis](#clean-data-initial-analysis)
- [Models]
	- [ARIMA](#arima)
	- [LSTM](#lstm)
	- [Rolling forecast](#rolling-forecast)
	- [Recommendation Strategy](#recommendation-strategy)
- [Evaluation and Plots](#evaluation)


The major workflow is showed

<a href="https://www.processon.com/view/link/60ac4a247d9c0821842de518" target = "_blank">
   <img alt="workflow" src="http://assets.processon.com/chart_image/60a7d5b6079129238fabae6f.png" width=650">
</a>
<<<<<<< HEAD

=======
                                                                                                            
## Rolling forecast
>>>>>>> f62c74b177b2cd64e1e99676609a686616b310ab

## Data download and preprocessing

`DATA5709_Capstone_preprocess.ipynb` [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/BasemSuleiman/HotspotRecommender/blob/main/DATA5709_Capstone_preprocess.ipynb)

## Clean data initial analysis

`DATA5709_Capstone_InitialDataAnalysis.ipynb` [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/BasemSuleiman/HotspotRecommender/blob/main/DATA5709_Capstone_InitialDataAnalysis.ipynb)

## Models
### ARIMA

`DATA5709_Capstone_ARIMA.ipynb` [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/BasemSuleiman/HotspotRecommender/blob/main/DATA5709_Capstone_ARIMA.ipynb)

### LSTM

`DATA5709_Capstone_LSTM.ipynb` [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/BasemSuleiman/HotspotRecommender/blob/main/DATA5709_Capstone_LSTM.ipynb)

<a href="https://www.processon.com/view/link/60ac4a701e08531e9c7f13dc" target = "_blank">
   <img alt="LSTM abstract" src="http://assets.processon.com/chart_image/60a71b115653bb5d3f387333.png" width=650">
</a>

### Rolling forecast
Since it's a time series problem,  we use the Rolling-forecast method to input a bundle of consecutive time steps for predicting the next one time step after this bundle.

<a href="https://www.processon.com/view/link/60ac4abc5653bb6411740cf3" target = "_blank">
   <img alt="Rolling Forecast" src="http://assets.processon.com/chart_image/60a726ace0b34d39389484d9.png" width=650">
</a>

### Recommendation Strategy

1. Build a list of avoidance places: we firstly identify places of the demography that the majority of people usually prefer ride-sharing over the traditional taxis,  by choosing places where traditional taxis hold only less than 1% market share. 

2. Look for a more profitable place: based on the requested location,  find the nearest place with the largest gap between total demands and total supplies.

3. Make suggestions: if the places found in Step 2 are in the Step 1 list,  eliminate those,  and find again. Until at last,  we make two suggestions with diagrams,  one is on current time frame,  the other is 10-min later.

## Evaluation

`DATA5709_Capstone_Evaluation_of_ARIMA_and_LSTM.ipynb` [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/BasemSuleiman/HotspotRecommender/blob/main/DATA5709_Capstone_Evaluation_of_ARIMA_and_LSTM.ipynb)
