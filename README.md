# .github
This repository contains all the work produced from the collaboration between Criteo and Columbia University for the Data Science Capstone &amp; Ethics (ENGI E4800), Spring 2024 semester

Columbia University contributors: Xinyi Chen, Martin Fluder, Jean Law, Ling Lin, Yue Yin

Criteo: [Jan Benzing](https://github.com/janbenzing), [Matt Merenich](https://github.com/mmerenich21)  

## Context:
Criteo (NASDAQ: CRTO) is a worldwide leader in data-driven advertising. Every day, we serve around 4 billion ads, and we have around 20+ millions of clicks. We have various algorithms that help us serve the most appropriate ads that provide a good user experience (UX) to the final user. However, we noticed that some clicks have odd patterns, so-called misclicks. Practice showed that those misclicks are due to slow phones, heavy banners, and misleading websites that spoil UX. Heatmaps can usually spot this. In the case of slow banners, heat maps look completely broken.

Criteo is working on spotting such misclicks and slow banner issues. For that, we’ve developed a p-misclick metric (the probability of a click being a misclick) and a heatmap generation tool (the user can observe the click distribution on a given scope). We want to automatize this approach. Your objective is to build a clusterization/anomaly detection algorithm (i.e., fully unsupervised learning) to predict whether the given heatmap is broken. Thus, we could spot the “hot points” with issues and address them.

## Repository
This repository contains the following directories:
- `datasets`: all datasets provided by Criteo, as well as a train-test split for the first dataset provided
- `heatmap_plots`: plots of the heatmaps, `broken_banners` contains the plots of the broken banners of the first dataset provided, `new_data_classify` is the visualization of all the heatmaps from the time series dataset 
- `reports`: midterm and final report
- `notebooks`: all code used to implement the methods that have been presented in the final report. Directory `old code` contains code for data preprocessing, data visualization and other methods tested.
- `notes`: informal meeting notes with mentors, professor and internal team
- `presentations`: all presentation slides during weekly updates with mentors