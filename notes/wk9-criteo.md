# Questions clarified
* Personalization is on the user level
* the majority of the banners are independent of products
* Criteo has a blacklist of websites
* Small publishers definition: xx% of viewers
* CPC model: guarantee conversion rate of xx% if pay xx amount
* Average order value: ensures everyone who buys spends $xx on average
* How to address scalability: Sample domain ids, big data flow, can figure out how many ads are produced everyday and see the order of magnitude
* By the end of the week, Jan will put the other grid_ids on GitHub
* Heatmap dataset takes 2 months time range
* Sining wants us to do some crude mathematical approaches: Kulback Leiber distance between the average heat map to individual heatmap


# Presentation of work
* Contrastive learning: SimCLR
    * generate banners that are not broken
    * generate other types of grid_ids
* The left will be presented next week due to time constraint


# Other notes
Layout/grid ID = how we can position the different products , mixed or horizontal or vertical (e.g. triangle)
It is true that broken banner might depend on advertiser (e.g. Nike vs Reebok), but the majority of broken banners are independent of products as Criteo only has 20k advertisers and most are well integrated - all they need to provide is the link, and the link is working.

Key source of broken banner: publisher (seems to be equivalent to domain ID) (company that makes money thanks to ads) who configured the frame and layout, domain, dimensions, where the image has to go. E.g. clicks may just not happen, ads show up in places that they don't. New York times, Washington post, sports/news/blogs/reddit etc - we work with them directly, don't have the inventory.

Otherwise we have website aggregators with smaller websites, backup advertising besides big publishers.

Criteo does black listing: Don't buy inventory any more for this website, we prefer buying somewhere else.
Many fake websites, illegal websites, no porn etc. Many small websites -> big inventory

How much revenue lost -> cannot disclose

They might share how many publishers they have, how many percent are small publishers, number of visitors per month, medium or small website

Criteo has two models to make money: 1.Cost per click model, conversion models in which we pay a certain amount of month and they promise a certain sale or conversion rate. E.g. return to ad spend of 4:1. In the beginning: show 1m ads earn 1k dollars
After more ML models came out -> can predict so well what the users are gonna do, probability of a landed click, percentage of chance to do a landing on a website, probability of doing a sale, logistic regression

=> They charge not just by click/visualization, but also by predicting impact/business of company

They also calculate average order value = probability of someone that is buying something at at least this price

Scalability of Criteo - number of websites is around 100k, below 10k websites generate budget 

To make broken banner detection more scalable: how can we sample them, without looking at every grid ID on every domain

Combination score of volume of ad, severity of the problem to prioritize how the flags are being serviced

Data: 2 months heatmaps, 1 month metrics. Assumption: 4,5,6% broken banners. Aim is to divide it by 2. 
Some are repaired but others break so the broken banner rate is usually quite constant for a given domain 

Cost involved for us whether to contact the given domain or not

Sining
Baseline metrics - 1 million ads in 1 minute 
Our method - 1 million ads in 3 minutes, it takes 30 min to run students algo 
Scalability is 1:10

Jan
Look at how many ads per day, see how long the job takes to run

Sining
Baseline method, math method to determine if banner is broken