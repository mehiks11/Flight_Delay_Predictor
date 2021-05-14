# Predicting Flight Delays

## Abstract
The aim of this project was to create classification models to predict wether a domestic flight would be 25+ minutes late to arrival. This model could be used as a supplmenetal planning tool for ATC (air traffic control) in planning traffic routes and controlling ahead of flight departures. After creating three types of models: KNN, Logistic, and randomforest, I finalized the logistic model and optimized its f1 score for a balanced precision and recall rate. 


## Repo Set Up & Project Design
This project is a binary classification project that pulls on several data sources-- most of which were found on kaggle. Classifying status is based on several different attributes, including features like holiday season (bool), time features, weather conditions, etc. These are all used to test weather a flight will be 25+ minutes delayed on arrival. Accurately classifying these delays would aid ATC in planning air traffic flow days prior to scheduled departure, allowing them to have plans ready for most efficient and safe routes for flights.

This repository is broken up into two main folders: deliverables and code. Deliverables include items like initial project proposal, presentation slides, a simple MVP model.
The code folder includes 7 notebooks. 
- 2 of these notebooks (the ones labeled "Data Pulling") follow the process of collecting and cleaning the data.
- 1 [notebook](https://github.com/mehiks11/Flight_Delay_Predictor/blob/master/Code/Flight%20Project%20Initial%20Modeling%20(MVP).ipynb) contains the MVP model.
- 1 [notebook](https://github.com/mehiks11/Flight_Delay_Predictor/blob/master/Code/Flights%20Model%20Exploration%20(1).ipynb) follows the building of initial models like KNN and logistic.
- 1 [notebook](https://github.com/mehiks11/Flight_Delay_Predictor/blob/master/Code/Flights%20Model%20Exploration%20(2).ipynb) follows the building of initial treebased models like random forest.
- This [notebook](https://github.com/mehiks11/Flight_Delay_Predictor/blob/master/Code/Full%20Models.ipynb) holds the final model built on a much larger dataset. 
- This [notebook](https://github.com/mehiks11/Flight_Delay_Predictor/blob/master/Code/Flight%20Delay%20Predictions.ipynb) is where three test flights are considered and classified.



## Data
The dataset contains a final set of 12 million data points, with 15 features. A few important features include month, holiday season, weather condition, and airline. The main dataset ranges from 2016 - 2018, with flight information from US flights. The following three datasets were combined on date and city:
* [Flights Info](https://www.kaggle.com/yuanyuwendymu/airline-delay-and-cancellation-data-2009-2018)
* [Airport Info](https://datahub.io/core/airport-codes)
* [US Weather Events](https://www.kaggle.com/sobhanmoosavi/us-weather-events)


## Algorithms

*Feature Engineering*
1. Deciding weather a flight was during a holiady season required looking at dates and holidays.
2. All time features were cyclized by using sin and cos functions to show cyclical nature of time features (month, day of week, hour)
3. Weather severity was ordinalized 

*Models*
  
K-nearest neighbors, logistic regression, and random forest classifiers were built (on a sample of the larger dataset) and compared before finalizing on a class weighted logistic model (1:5.3). After much parameter and attribute tuning, it was found that logistic model yielded the best f1 and other scores. 

*Model Evaluation and Selection*

The entire dataset of 12 million records was split into a 70/30 train vs test, and all scores for f1 are reported below for the final metrics for the final model.

F1 was used because as a non-expert in aviation traffic, I am unsure of the cost-benefit analysis of having an imbalanced recall / precision rate. 

**Final logistic model Test Scores :**   
- Precision: .23 
- Recall: .69
- f1: .35


## Tools
- Numpy and Pandas for data manipulation
- Scikit-learn for modeling


## Communication
In addition to the slides and visuals presented, I hope to create an interactive dashboard embedded to my personal website to have as a visual representation of the findings from this project.
