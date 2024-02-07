Feb 6
# General summary
- Met Jan and self introduction
#  Presentation by us on preliminary EDAV: discussion of heatmaps
  - Martin binned the banners in 50 bins (x-axis) by 60 bins (y-axis), 5*5 pixels -> kernel density estimate?
  - Heatmap dataset: distribution of both 333519/333346 is the same for the total number of clicks. No correlation between grid_id and nb of clicks
  - There are techniques to make the three zones more centred that we can try 
  - Bottom left corner - could be due to transform the heatmap. Usually it should be in the top right, but pixel to grid could have changed the orientation.
  - He will give new heatmaps with new patterns, more products in the banner.
  - Bottom right is always completely empty according to Martin. Could be that it's either broken or completely unclickable. Jan doesn't think it's a feature if determine whether the banner is broken or not. Patterns perfect line or perfectly space or a blank square could be a pixel problem, imperfect squre could be that some pixels in the banner are broken, pixel anomaly. Full line of straight clicks / randomly distribution pattern of clicks could be invalid traffic, bots, malicious activity. To find out how pixels and clicks work
  - Question: no user centric data
  - rule to guarantee broken banner: clicks are all super concentrated in one small area. Third row second column. 
  - 8-900 domains for each grid

# Mentor actions:
- Slide 6: three centred distributions. Just need to be sure that this layout exists and this layout isn't broken. They will provide us some layouts from the creative teams to ask all the possible layouts for 3 product banners. Usually it should be 3 products all aligned 
- He can give us more data for a given domain ID and the grid ID 
- Jan will verify that for 333519, the products don't need to align on one line. See if we can find the template.
- Question on the number of clicks - if you need more clicks per grid ID and domain, we can increase the number of it, but want to see if it's possible for what we have. Number of domains with more
- They will give us specific details on how the model will be run on the server
- 
# Our actions:
- We pace the project
- CTR, landed clicks, non-bounced clicks: features, want to play with the geometry of where the clicks are concentrated. Self-transformed features. come up with a few more. Do a PCA/correlation heatmap to see if we can find out some features that are basically correlated 
- We want to compare the model that we have to a baseline (baseline = if you take the centroids of the clusters, they form a straight line, then it's not a broken heatmap). Baseline metrics and evaluations. Baseline is specific to a particular banner, and we want to automated/self-supervised way for other types of banners.

To ask professor
- Ask Columbia for credits for GPU
- Ask for Zoom account for private meetings? 

# Second dataset
## Attributes
domain: identifier for domain
grid_id: identifier for grid, related to specific layout
webview_height, webview_width: dimensions of the banner
displays: # times the ad was displayed
clicks: # times users clicked (why are these numbers different from the heatmap data?)
landed_clicks: # clicks that successfully led to a landing page
non_bounced_clicks: # clicks where the user did not immediately leave the site
closing_events: # times users closed the ad?
avg_last_second_framerate: average framerate in the last second?
see Jan's email for sov descriptions


# Answers to questions:
- baseline -> we NEED the creative team's templates!!
  - Broken banners? 
  - For each domain ID/grid ID, it's the accumulated clicks over two months?
  - Extension of project for three products or more?
  - 1% of broken banners, they took 2 months of data from 2023, no modification or cleaning

- High sov means high percentage, click ad without meaning to, bug on website, highly interesting features 
- We should plot the distribution of broken banners vs non broken banner s
- Definition of a broken banner - for now the definition is any heatmap that displays anomalous behavior. Banner with a heat map not generated with user behavior 
- One metric for user behavior = certain amount of time to click on it. Then the banner is not broken. As long as you fall into a heatmap that is not representing user behavior, it is possible that the user clicked exactly a straight line, this is not possible as human beings. What you think is user behavior
- We need a metric that can clearly define when a banner is broken
- We do see a lot of metrics that are associated with broken banners. We don't have a metric definition but we only have user behavior definition
- Unsupervised model is the best. Cherry on telpp = dataset that has 6 products, and our solution will be able to work for 6
- for the given banner ID, we know for sure that it's 3 products -> see Jan's email. Our objective is to find a solution to know where you don't even need to know how many products. We know the distributions because most of the banners are not broken, we should still be able to identify outliers. Your baseline you need to know how many products you have. But if you have one that learns a general type of banners, it should know how the products were placed
- Objective in the scope of capstone project: we get a nice algorithm that can work on 3/6 products
- Constraints on computational resources: Memory: 16GB
CPUs: 8
Disk: 60GB
