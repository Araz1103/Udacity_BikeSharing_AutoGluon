# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### ARAZ SHARMA

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
I realised that the score I got on the competition was terrible compared to everyone else's and it struck me that we had done no EDA. Before starting any training, we must try to find the types of features we have, categorical or numerical, so we can encode them accordingly. For AutoGluon, I realised that the category features must be in that datatype for it to identify properly.

### What was the top ranked model that performed?
With the Initial Training, the top ranked model came out to be the WeightedEnsemble_L3

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
The EDA helped to find the type of features we had in the data and which of them were categorical in nature. From this, we made sure that the categorical ones were converted into the category types, for AutoGluon to interpret them as that. For additional features, I decided to split up the datetime into hours, days and months, for the model to get more information from that, since it was one of the primary features we were using.

### How much better did your model preform after adding additional features and why do you think that is?
The model improved tremendously after EDA & additional features. The score improved from 1.393 to 0.558, and became much comparable to the scores on the leaderboard. The reason for that, is that now AutoGluon realised that weather & season were categories, and not integers. Also, the additional features from datetime would have certainly helped the model get more information to learn from, since it could gather separate information from hours, days & months, compared to when they were together. 

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
I tried experimenting with the time limit and hyperparamters dictionary, to try specific architectures with different time limits. I got the best performance with 700 seconds on the default paramters, of 0.5581 followed by training for 800 seconds for only NNs giving 0.57513. With only Gradient Boosting Methods and both NNs & GBMs for 1200 seconds, we observe different scores. We see that with more time limits we can better performaces, but it also depends on how much time AutoGluon uses per model it is training, as it stops epochs in between if constrained for time. We also see that a lot of times GBMs are performing better than NNs and we can try to explore more architectures in those!

### If you were given more time with this dataset, where do you think you would spend more time?
With more time, I would try to engineer more and better features, and tune the hyperparameters for the NN Architectures, to get even better performance. 

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|Training Data|Time Limit|Architectures allowed to use|score|
|--|--|--|--|--|
|initial|Standard Features & Non-Category|700|Default|1.393|
|add_features|Hours, Days & Months added with Categorised|700|Default|0.5581|
|hpo|Hours, Days & Months added with Categorised|800 & 1200|Tried with only NNs, only GBMs & Both|0.57513|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![model_test_score.png](img/model_test_score.png)

## Summary
 I learnt a lot during this project! I learnt about AutoGluon, and how to use with with SageMaker in AWS! I feel more confident about using it to train a variety of models, tune the hyperparameters and experiment with it. I also learnt the importance of EDA and Feature Engineering, and how we could submit to Kaggle Competitions! With more time, I think I can improve the performance of the models and reach a good position on Leaderboards!
