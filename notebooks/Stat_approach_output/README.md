# Test 1
## experiment:
test_1.pkl: one shot learning
numerator = representative_heatmap picked filtered from landed_clicks > 0.8 and most number of clicks
denominator = aggregate on bad data from the other dataset

## results:
old:
Time per banner:  0.05968683576281196
Best f1 is 0.95 at threshold 0.43
Confusion matrix at best threshold: 
[[1502   19]
 [  15  197]]
 AUC = 0.99

new:
Time per banner:  0.1023451297590048
Best f1 is 0.92 at threshold 0.55
Confusion matrix at best threshold: 
[[2782   22]
 [  44  182]]
 AUC = 0.96

 # Test 2
 ## experiment:
 test_2.pkl: one shot learning
numerator = representative_heatmap picked filtered from landed_clicks > 0.8 and most number of clicks
denominator = uniform distribution (represents broken banner)

 ## results:
 old:
Time per banner:  0.05903197614292292
Best f1 is 0.94 at threshold 0.55
Confusion matrix at best threshold: 
[[1508   13]
 [  29  183]]
AUC:  0.9811227717613784

new: 
Time per banner:  0.10251886026300613
Best f1 is 0.9 at threshold 0.56
Confusion matrix at best threshold: 
[[2769   35]
 [  48  178]]
AUC: 0.9585674068650348
