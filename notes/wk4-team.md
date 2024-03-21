Feb 7
# Agenda
- What we need to produce for next week
- How to create ground truth labels
- Extra ideas
  - Data augmentation with Gaussian noise to smooth out the plots?



## Ideas

Idea 0: data augmentation
- Data augmentation by adding gaussian noise?

Idea 1: 3000 dimension vector
- 50*60 bins = 3000 dimension vector with number of clicks per bin 
- Caveat: lose the metric structure
- Algos: k-NN, k-Means (k=2), PCA, isolation forest


Idea 2: Hardcode rules


Further ideas:
- add in other datasett by joining tables to get more features.
- Idea 2: Use the images and use resnet (CNN)

## Division of work
1a. Preprocess data to get 3k dimension vectors (1 person) - including normalization and possibly cleaning the corner datapoints

Train test split on all the data

1b. Hardcoded rules to generate label for each heatmap
(grid_id, banner_id, label) -> label generated using hardcoded rules that show whether a banner is broken or not

2a. Apply PCA to reduce 3k dimension vectors to 2 dimension vectors
Jean

2b. Apply 4 sklearn methods directly to 3k dimension vectors
Jenny, Ling, Xinyi

2c (do later). Apply PCA to reduce 3k dim to n dim and afterwards apply 4 sklearn methods

Martin -> 1a and 1b
