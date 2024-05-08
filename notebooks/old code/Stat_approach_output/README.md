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

# Test 3
## experiment:
 test_3.pkl: zero shot learning
numerator = uniform distribution (represents good banner), data_good
representative_heatmap picked filtered from landed_clicks > 0.8 and most number of clicks
denominator = aggregate on bad data from the other dataset, data_bad_6p

## results:
old:
Time per banner:  0.05911106590033265
Best f1 is 0.81 at threshold 0.48
Confusion matrix at best threshold: 
[[1498   23]
 [  95  117]]
AUC:  0.7563823452792974

new:
Time per banner:  0.1036784818857023
Best f1 is 0.85 at threshold 0.49
Confusion matrix at best threshold: 
[[2785   19]
 [  87  139]]
AUC: 0.7662560122707132

# Test 3 bis
## experiment:
same as Test 3 but improved denominator 
`combined_agg_broken = data_broken_proba[333346].drop(columns = ['grid_id']).merge(data_broken_proba[333346].drop(columns = ['grid_id']), on = ['click_x_bin','click_y_bin'], how='outer').fillna(0)`
replaced by
`combined_agg_broken = data_broken_proba[333346].drop(columns = ['grid_id']).merge(data_broken_proba[333519].drop(columns = ['grid_id']), on = ['click_x_bin','click_y_bin'], how='outer').fillna(0)`
old:
Time per banner:  0.05952530160365735
Best f1 is 0.86 at threshold 0.5
Confusion matrix at best threshold: 
[[1510   11]
 [  81  131]]
AUC:  0.7755883046158807

## results:
old:
Time per banner:  0.05952530160365735
Best f1 is 0.86 at threshold 0.5
Confusion matrix at best threshold: 
[[1510   11]
 [  81  131]]
AUC:  0.7755883046158807

new:
Time per banner:  0.10255962661390651
Best f1 is 0.86 at threshold 0.47
Confusion matrix at best threshold: 
[[2777   27]
 [  79  147]]
AUC: 0.8079679156199108

#   
## experiment:
same as Test 3 bis but improved numerator: replaced uniform distribution by 
```
BOXES_FROM_BDRY = 5

data = pd.DataFrame(list(product(range(0,60),range(0,50))), 
                    columns=['click_x_bin', 'click_y_bin'])

data['clicks'] = 1
data.loc[data.click_x_bin < BOXES_FROM_BDRY, 'clicks'] = 0
data.loc[data.click_y_bin < BOXES_FROM_BDRY, 'clicks'] = 0
data.loc[data.click_x_bin > data.click_x_bin.max() - BOXES_FROM_BDRY, 'clicks'] = 0
data.loc[data.click_y_bin > data.click_y_bin.max() - BOXES_FROM_BDRY, 'clicks'] = 0

data['proba'] = data['clicks']/data.clicks.sum()
# data['norm'] = data['proba']/np.sqrt(np.square(data['proba']).sum(axis=0))
```
Also changed the min and max from -1000, 1000 to reflect the real min and max in the distribution

## results:
old:
Time per banner:  0.059471884560736356
Best f1 is 0.91 at threshold 0.23
Confusion matrix at best threshold: 
[[1503   18]
 [  44  168]]
AUC:  0.9288793370796274


new:
Time per banner:  0.1041606050119935
Best f1 is 0.89 at threshold 0.25
Confusion matrix at best threshold: 
[[2774   30]
 [  58  168]]
AUC: 0.922340714276697


# Test 4
## experiment:
test_4.pkl: one shot learning, combining tests 1 and 2
numerator = representative_heatmap picked filtered from landed_clicks > 0.8 and most number of clicks
denominator = 50% uniform, 50% aggregate on bad data from the other dataset

## results:
old:
Time per banner:  0.059601034515521734
Best f1 is 0.95 at threshold 0.53
Confusion matrix at best threshold: 
[[1507   14]
 [  22  190]]
AUC: 0.99

new:
Time per banner:  0.1023451297590048
Best f1 is 0.92 at threshold 0.55
Confusion matrix at best threshold: 
[[2782   22]
 [  44  182]]
 AUC: 0.97


 # Test 5
 numerator = 
 denominator = 