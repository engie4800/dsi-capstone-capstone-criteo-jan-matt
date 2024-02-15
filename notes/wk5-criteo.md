# Meeting notes
## Presentation summary
Martin
- Created baseline for clearly broken grid, done by hand because many cases where it's not clear whether it's broken
  - Definition of baseline = triangle/line structure not visible even with noisy bootstrap enhancement
- DBScan results: Jan wants an algo that can take any grid id and output, whereas DBScan for now needs to be trained on the same grid_id
  - precision/recall: plot an ROC curve with all the different precision and recall possibilities based on threshold.
- Brief discussion on class imbalance, we don't need to use data augmentation techniques because the real-life scenario has a class imbalance and we want to apply our algorithm. Our algo should address the class imbalance.

Ling
- Isolation forest: see slides 9 to 11 for details 
  - plot precision-recall curve and present results as such
- Discussion on whether our hand-labelled broken banners are actually broken. Conclusion: we need to use CTR, landing rate, frame per second etc. from the metric datasets to define a broken banner. e.g. if CTR = 0, low landing rate, (CTR?), high closing rate (if everyone closes the ad before it is loaded, the banner is likely broken), low FPS, low TTR 
  - esp below 1k clicks this is useful
- Any good anomaly detection should contain at least 90% of the strange looking datasets

Jean (work on CNN and standardizing by vectors)
- two clusters, two vectors -> explain why there shd be a clear separation using PCA? delve into the math, is this even true? 
- maybe we can use a methodology that does feature importance 
***REPORT can put in this PCA result and explain why it doesn't work***- standardize by the nb of clicks for each heatmap and then standardize by each component. but it is not clear whether PCA can capture precisely the anomaly we are looking for. if we don't standardize heatmap compomennt, maybe the first component is the number of clicks.
- can look other more powerful dimensionality reduction methods
- RESNET/CNN : he doesn't like the idea that much because he wants to apply the algorithm to where there aren't enough clicks!
  - either come up with a rule that we need at least 500 clicks
  - or we use Martin's bootstrapping method


Jenny
- Metrics data have a lot of missing values, replaced with min for each column but it is not very reliable
- Normalized data and applied k-means with grid ID 
- some grid_ID and domain in metrics data don't exist in heatmap data like ID_1413
- suggestion: compare k-means with DBScan method and see which is apropriate for our dataset
- metrics: 2 months (same month as heatmap plus another month), heatmap: 1 month. we can trust the KPIs!!!!

Xinyi
- kNN 
- Jan advice: normalize numerical features


Table with different methods with accuracy, recall, minimum amount of clicks for each method

Can summarize qns in github

Can put ppt in the github

# Pre-meeting notes

## Progress update
- Ling: Isolation forest and ground truth labels
- Martin: Starter_code and ground truth labels
- Jenny: first ideas for metrics dataset
- Jean: PCA (with explained variance %) or PCA + **explained variance**, PCA to 10 / knn / k means


## To add to the ppt slides
- Ground truth labels (Martin)
- Isolation forest results (Ling)
- PCA/ KNN / (Jean) + ground truth
- First ideas for metrics (Jenny/Xinyi)

## Questions to ask
- the dataset "metric" and "heatmap" were collected over different periods of time, the banners might not be broken at different time periods? 
  - try to see if it's possible for the metrics data and heatmap data to be over the same time period


## To think
- definition of broken banner: human behavior, if we have >=3 clusters is that a broken banner? domain knowledge! 
    - both metrics dataset and 
