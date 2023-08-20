# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Ryan Vogt

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
I realized that for the model it was possible for a prediction to be negative. In order to submit the output of the predictor we needed to change all negative values to zero.

### What was the top ranked model that performed?
Across all three tests the weighted ensemble with three layers of stacking (WeightedEnsemble_L3) was consistently the best performing.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
During the Exploratory Data Analysis one thing that I noticed was that the temp and atemp variables were normally distributed whereas the humidity
and windspeed were more skewed. To add more features I decided to take the datetime column and add four additional columns for year, month, day and hour.

### How much better did your model preform after adding additional features and why do you think that is?
The model performed significantly better after adding the new features. The Kaggle RMSE score improved from 1.79556 all the way to 0.62326!!
I think logically it makes a lot of sense that month, day and hour values would have significant predictive power. Intuitively during the summertime or on weekends 
people are more likley to rent a bike so this is useful information for the model to know.
          
## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
My model actually performed slightly worse on the kaggle out of sample test set after changing the hyper parameters. In sample training was also extremely close to the same compared to the baseline.
One reason for this is by choosing the "best_quality" preset the process is already tuned to produce "State of the Art" results so there is little additional value to be added by
manually tuning the hyperparameters. Also the slight decrease in Kaggle performance could be due to overfitting.

### If you were given more time with this dataset, where do you think you would spend more time?
I would spend more time trying to Engineer more features as this is where I think value could be added. 

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|?|?|?|?|
|add_features|?|?|?|?|
|hpo|?|?|?|?|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
TODO: Add your explanation
