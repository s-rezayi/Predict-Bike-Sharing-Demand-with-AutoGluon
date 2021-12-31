# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Soheil Rezayi

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
The negative results needed to be set to zero. Kaggle does not accept negative results for this competition.

### What was the top ranked model that performed?
For all sections, the WeightedEnsemble_L3 was the best model.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
I added month, hour, and weekday to the dataset.
I analyzed the data for the outliers and removed count column outliers.

### How much better did your model preform after adding additional features and why do you think that is?
The score improved from 1.39413 to 0.47568.
A combination of feature engineering tasks was performed to achieve this:
First hour, month, and weekday column were extracted from date column and their dtype set to categorical.
The dtype of other categorical columns, such as season and weather were also corrected.
Outliers were also removed.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
I tried a lot of combination of hyperparameter tuning although the score did not improve so much. It improved from 0.47568 to 0.46800.

### If you were given more time with this dataset, where do you think you would spend more time?
Definitely, on feature engineering. It is by far more efficient than hyperparameter tuning.

### Create a table with the models you ran, the hyperparameters modified, and the Kaggle score.
'| model        |   time | presets      | num_bag_folds   | num_bag_sets   | num_stack_levels   |   score |\n
 |:-------------|-------:|:-------------|:----------------|:---------------|:-------------------|--------:|\n
 | initial      |    600 | best_quality | Default         | Default        | Default            | 1.39413 |\n
 | add_features |   1200 | best_quality | Default         | Default        | Default            | 0.47568 |\n
 | hpo          |   1200 | best_quality | 7               | 1              | 2                  | 0.468   |'

### Create a line plot showing the top Kaggle score for the three (or more) prediction submissions during the project.

![model_test_score.png](model_test_score.png)

## Summary
I improved the model by adding and changing the dataset features which resulted in reducing the RMSLE error 0.91845. I also, tuned the hyperparameters of TabularPredector. However, despite the effort and combining different combinations, hyperparameter tuning did not improve the results significantly.
