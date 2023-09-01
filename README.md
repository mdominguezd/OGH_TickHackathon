# Open Geo Hub Summer School Hackathon 2023

Repository created for reporting the results obtained for the Open Geo Hub Summer School Hackathon 2023. 

## Target variable
The approach taken to get the results was to aggregate the data of tick occurrences for the month of may in a 100mx100m resolution grid which was then normalized based on the population density. The values in this grid where considered to be the target value.

## Covariates
For the covariate gathering, the `Data_exploration.Rmd` code was used. The final outputs of that code are:

- A stacked raster with most of the covariates that were used. 
- Two additional rasters with possible covariates derived from OSM data of hiking trails. (To get them `Retrieve_HikingData.ipynb` should be ran first.)

*Disclosure:* The temporal aspect was not considered and we decided to only focus on aggregated data for may. All of the weather data is mean values for may months between 2015-2020.

## Feature selection
Taking all of the covariates that were retrieved a forward feature selection process was done (`model building.Rmd`). Three variables were selected:

- Distance to buildings
- NDVI
- Population densiity

## Model
Finally, a random forest model was fitted to the data and the final raster is calculated and saved to `Ticks May risk.tif`.

### Plan B
An alternative for the random forest model was done. Probabilities of tick occurrence where calculated using the mahalanobis distance using the three variables that were significant. The code for this approach can be found in `model_Maha.Rmd`


### Pre-requirements
The prepared data of tick ocurrence and coariates is expected to be uploaded to the repository in a folder called **prepared**

#### Python Environment:
For reproducibility purposes the python enviornment to run the code in this repository can be created using the `OGH_HackATick.yaml`.


