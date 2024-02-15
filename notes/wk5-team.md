# Ethics
- Done ethics proposal, need to send in by Feb 19

# Results
- Martin worried that our PCA results (after standardizing each heatmap nb of clicks) are too good. PCA explained variance for first two variables is only 4%

# Next steps: broken banners dataset

- Martin suggests that we can apply PCA to k dimensions since there are too many useless parameters, but we can also explore without doing PCA

- train-test split (we do not touch the test set). (side remark: cross-validation a possible idea but not important because we are not doing supervised learning)
  - idea: save the IDs of 20% of the data and label them as the test set, **DO NOT TOUCH when training model!!!!!** Martin will help us split it :)

- plot precision-recall curve on test set and present results as such + other metrics such as accuracy, F1, hyperparameters? 
  - bonus: understanding why one method works better than the other

- conclusion: for this week, we train our models on train set, and afterwards we test it on the test set and plot the curves

- aim: have clear results by Monday. 


# Next steps: metrics dataset 

- from criteo meeting - we need to use CTR, landing rate, frame per second etc. from the metric datasets to define a broken banner. e.g. if CTR = 0, low landing rate, (CTR?), high closing rate (if everyone closes the ad before it is loaded, the banner is likely broken), low FPS, low TTR 
  - esp below 1k clicks this is useful
- Any good anomaly detection should contain at least 90% of the strange looking datasets

- possible steps: exploring its features (find threshold for CTR), use a clustering/other unsupervised algorithm 

- conclusion: for this week, we will focus on using the ground truth to understand the metrics: CTR, low landing rate, high closing rate...

# who does what????
- heatmap pca for other grid id + checking through (+ resnet????????? but not priority) (jean)
- heatmap isolation forest (or SVM/ other anomaly detection methods if isolation forest is not promising): hyperparameter tuning / try PCA (ling)
- heatmap k-means + testing with PCA beforehand (jenny)
- knn on metrics dataset (xinyi)
- split for train/test + looking at metrics in metric dataset (martin)

other methods: gaussian mixtures, dbscan...

# Questions for Sining and prof?
- ppt or posters?
- midterm progress report rubrics / evaluation criteria?