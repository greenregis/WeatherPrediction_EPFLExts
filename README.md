# Weather prediction in Neuchâtel
## Capstone project for the EPFL Extension School (Advanced Data Science : Machine Learning program)

Welcome to the capstone project about weather data I submitted in the program "Applied Data Science: Machine Learning" at the EPFL Extension School. 

*What is the weather like?* is perhaps one of the most common questions.  
*What will the weather be like?* is maybe one of the questions with the most expected answer.  
Weather is part of people's daily lives. Meteorological measurements are recorded in many places, at different time-scales to give an outline of the answer

Weather forecasts relies on mathematical models based on the laws of physics. The Machine Learning approch proposed here is not as reliable as these complex numerical methods to predict weather as a whole. It is not intended to be an alternative. But too great is the temptation to apply these new techniques to these data.

## About the data
The data used in this project comes from the webportal of [MeteoSwiss](https://gate.meteoswiss.ch/idaweb/login.do). It provides 975 measurement values like temperature, precipitation, wind, sunshine and so on for 2.749 weather stations. Some parameters are available in various scale (e.g. month total, daily total, percentage, ...), some are not available for each station (e.g. snow) and sometimes technical issues imply missing values. I downloaded the file [order_92009_data.txt](meteosuisse/commandes/order_92009_data.txt) containing 7 features recorded in the 24 main stations of the Swiss Meteorogical Network (SwissMetNet) for years from 2014 to 2020. The other file [stations_data.csv](meteosuisse/commandes/stations_data.csv) provides informations about the stations.

## Issues addressed
I focused on predicting the daily temperature in Neuchâtel for year 2020.
Three different issues are addressed :
 - The *technical problem* : predict the temperature if the temperature sensor encountered problems. It corresponds to guess the temperature with all the other data available;
 - The *predictions problem* : no use of temperature on D-day is allowed;
 - The *new station problem* : if the temperature were never recorded up now in a station, try to build this serie. The same could be addressed to a completely new station.

## Machine Learning solutions
After the exploration of the data and its cleaning, four regressions models (kNN, Ridge, Lasso, RandomForest) are compared. The best model found is then applied on various variables selections (based on relations with the target, geographic characteristics, ...) to get the predicted temperatures for these three issues.

## The Jupyter notebooks
The notebook *Weather_prediction_in_Neuchatel* is the main part of the project and contains the data cleaning and explorating part, as well as the Machine Learning models.

The notebook *Weather_prediction_in_Neuchatel_adjusted_version* is an adapted copy of the latter notebook, in which the seasonal adjusted measurements are used for the predictions.
