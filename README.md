# .github
This repository contains all the work produced from the collaboration between Criteo and Columbia University for the Data Science Capstone &amp; Ethics (ENGI E4800), Spring 2024 semester

Columbia University contributors: HERE

Criteo: [Jan Benzing](https://github.com/janbenzing), [Matt Merenich](https://github.com/mmerenich21)  

Context:
Criteo (NASDAQ: CRTO) is a worldwide leader in data-driven advertising. Every day we serve around 4 billion ads and we have around 20+ millions of clicks. We have various of algorithms that are helping us to serve the most appropriate ads that would provide a good user experience (UX) to the final user. However we noticed that some clicks have odd pattern, so-called misclicks. Practice showed that those misclicks are due to slow phones, heavy banners, misleading web sites that spoil UX. This can be usually spotted by heatmaps. In case of slow banners heatmaps look completely broken.

Criteo is working on spotting such misclicks, slow banners issues. For that we’ve developed p-misclick metric (the probability of a click to be a misclick), and a heatmap generation tool (user can observe the click distribution on a given scope). We would like to automatize this approach. Your objective is to build clusterization/anomaly detection algorithm (i.e. fully unsupervised learning) that would predict if the given heatmap is broken or not. Thus, we would be able to spot the “hot points” with issues and address them.

