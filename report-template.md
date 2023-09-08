# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Michael Kwabena Adu-Gyamfi

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
The output of my predictions which were less than zero were set to zero

### What was the top ranked model that performed?
KNeighborsUnif_BAG_L1 for the initial and add_feature model. LightGBM_BAG_L1/T1 for the hpo_model.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
From the EDA, it was seen that in a day, the bike count was around 200 for most of the time. Also , it was seen that humidity range from 40 to 80 had a higher density.
Also the different seasons had almost the same counts.
To add additional features, I separate the `datetime` column into hours, month and day.

### How much better did your model preform after adding additional features and why do you think that is?
The score changed from 1.79580 to 0.67563 . The changed was due to the fact after adding additional features, the model was able to recognize patterns better. For instance, it may recognize that demand is very low or high during particular hours. These patterns may have not been recognized by the mdodel if the `datetime` column was not slitted.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
TODO: The model score changed from 0.67563 to 0.47225. 

### If you were given more time with this dataset, where do you think you would spend more time?
I would spend more time trying lots of hyperparameters. I would also increase the training time.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|training_time|GMB_learning_rate|num_trials|score|
|--|--|--|--|--|
|initial|600|0.1|5|1.79580|
|add_features|600|0.1|5|0.67563|
|hpo|600|0.001|10|0.47225|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
The data used was almost clean.I did some feature engineering on the datetime column to split it in hour, days and month to enable the model recognize patterns easily and also improve accuracy.I then used histogram to visualize the density of the columns and used graphs to represent how training accuracy increased with time.It was a great dataset to work with.