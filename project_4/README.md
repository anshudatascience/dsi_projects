
## Problem Statement

 - Goal over here is to predict the more accurate method of predicting outbreaks of West Nile virus in mosquitos will help the City of Chicago and CPHD more efficiently and effectively allocate resources towards preventing transmission of this potentially deadly virus.
 
 ##  Executive Summary

In 2002, the first human cases of West nile virus were reported and CDPH(Chicago Department of Public Health has established a comprehensive surveillance and control program that is still in effect today. The traps collects mosquitos, and the mosquitos are tested for the presence of West Nile virus before the end of the week. The traps are placed at specific location every year. Every week from late spring through the fall, mosquitos in traps across the city are tested for the virus. The results of these tests influence when and where the city will spray airborne pesticides to control adult mosquito populations.

- Some traps are "satellite traps". These are traps that are set up near (usually within 6 blocks) an established trap to enhance surveillance efforts. Satellite traps are postfixed with letters. For example, T220A is a satellite trap to T220.
- Goal over here is to predict the more accurate method of predicting outbreaks of West Nile virus in mosquitos will help the City of Chicago and CPHD more efficiently and effectively allocate resources towards preventing transmission of this potentially deadly virus.

## Data Dictionary
Weather dataset has Station 1 and Station 2 weather information
'Station 1: CHICAGO O'HARE INTERNATIONAL AIRPORT Lat: 41.995 Lon: -87.933 Elev:662 ft.above sea level'\

'Station 2: CHICAGO MIDWAY INTL ARPT Lat: 41.786 Lon: -87.752 Elev: 612 ft. above sea level'

Dataset used in thie project is included as train.csv and weather.csv..

train.csv - '2007, 2009, 2011,2013'

'Id': the id of the record -Test only
'Date': date that the WNV test is performed
'Address': approximate address of the location of trap. This is used to send to the GeoCoder.
'Species': the species of mosquitos
'Block': block number of address
'Street': street name
'Trap': Id of the trap
'AddressNumberAndStreet': approximate address returned from GeoCoder
'Latitude, Longitude: Latitude and Longitude' returned from GeoCoder
'AddressAccuracy': accuracy returned from GeoCoder
'NumMosquitos': number of mosquitoes caught in this trap
'WnvPresent': whether West Nile Virus was present in these mosquitos. 1 means WNV is present, and 0 means not present.
Test Data - '2008,2010,2012,2014'

'Id': the id of the record
'Date': date that the WNV test is performed
'Address': approximate address of the location of trap. This is used to send to the GeoCoder.
'Species': the species of mosquitos
'Block': block number of address
'Street': street name
'Trap': Id of the trap
'AddressNumberAndStreet': approximate address returned from GeoCoder
'Latitude, Longitude: Latitude and Longitude' returned from GeoCoder
'AddressAccuracy': accuracy returned from GeoCoder
Weather Data - '2007 to 2014'

'Station': station ID
'Date': date of weather recorded
'Tmax, Tmin', Tave: temperature in Fahrenheit
'Depart': departure from normal
'DewPoint': average dew point
'WetBulb': average wet bulb
'Heat, Cool': index
'Sunrise, Sunset': calculated, not observed
'PrecipTotal': precipitation in inches
'SnowFall': snow on ground in inches
'StnPressure': average station pressure
'Sealevel': average seal level pressure
'ResultSpeed, ResultDir, AvgSpeed': wind speed in mph, direction in degrees
Spray Data '2011,2013'

'Date': date of spray
'Time': time of spray
'Latitude': latitude of spray
'Longitude': longitude of spray


|**Model| Train accuracy| Test accuracy|Recall|ROC AUC**|
|:---|:---:|:---:|:---:|:---:|
|Logistic and balanced |0.69|0.687|0.7|0.693|
|Logistic Regression Smote|0.72|0.698|0.6|0.65|	
|Random Forest Smote|0.789|0.63|0.76|0.75|
|AdaBoost Smote|0.736|0.763|0.85|0.85|
|XGBoost weight|0.62|0.615|0.863|0.61|
|XGBoost Smote|0.66|0.60|0.72|0.60|

## Conclusion and Recommendation:

To predict the wnv we have chosen `'Recall'` to quantify whether the virus is present. In other words, the higher the Sensitivity/Recall the better our model is to predict the virus '`(Recall = TP/(TP + FN)'`, which means we want to find the higher value of Recall to lower the false negative values ). 
`'XGBoost weighted'` performed best with highest Recall and the kaggle score is the highest with `'0.647'`.

In this problem we are dealing with an Unbalanced Classification problem where the baseline score is 94% due to unbalanced data. In case of Unbalanced date, there is a need to upscale the minority class to get the right prediction. We have used smote upscaling and weighted scale techniques to deal with the unbalanced data.

- From EDA:
- we have come to conclusion that virus is present in month of Aug- Sep when the Tempratures are high and it is
conducive for the virus to breed.
-  Species Culex Pipens/Restuans, Culex Restuans, and Culex pipiens species are the main carrier of the virus 
- We could also see the sudden jump in Virus present in 2013 which is perhaps the reason why extra efforts of spraying was 
  done mainly in 2013. 
  
- Cost Benefit Analysis (2005): In 2005, costs of treatment is ~ 3x of spray costs.  Benefits of spray control outweigh the cost of spray control.  Given there were 46 infections in total, spray control will only need to prevent 15 infections to break-even from a cost point of view.


|**Recommendation**|:
- Spray data is limited to prove the affect of spray on the virus control so we have decided to do external research to determine cost-benefit analysis of spraying to contain the virus
- Weather data is given for specific time period 
- Some more feature engineering to take affect of mosquitos breeding will help in the better prediction. 
- We need to try the cluster Mean technique to improve the prediction 

https://github.com/thisisclement/West-Nile-Virus-Prediction/blob/master/code/proj4_eda.ipynb (Got inspiration to calculate the distance from the Station to Trap) 
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3322011/#R6 (Rearch Report)
https://www.cdc.gov/westnile/statsmaps/cumMapsData.html
