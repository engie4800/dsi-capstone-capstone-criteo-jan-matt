# Pre-meeting notes
ask about impact on business?
- what is the impact of a broken banner on the revenue of the business? how many banners perday?

ask about the next half of project: esp when we will get the data
Phase 4: (Weeks 8 - 10) In-depth modeling and algorithms 
Phase 5: (Weeks 11 & 12) Model accuracy, tuning and comparison 

ask about state of the art - how or where to look

shift focus on zero shot learning: how model on one grid can be generalized on other grid!!!

Exact collection period for the metrics and heatmap datasets, and also regions


# Meeting notes
## ResNet/ViT model
- Key idea: Feature extraction using the body of the models, no head
- To improve resuls - data enhancement: bootstrap upsample to 50k clicks per image. PCAs and MVU produce good reults so Martin proposes we continue with these upsampled images
- Additional method - cosine similarity between each image and an anker (random choice or non-broken grid_id). 
- Question from Jan: upsampling doesn't need a minimum number of clicks, when we upsample from 200/2k clicks we get the same result?
- Response from Martin: yep we used a bootstrap distribution with gaussian noise
- Question 2: generalizing the clean distribution of cosine similarity to 3rd or 4th grid_id - Martin believes that with a new anker that is a merge of all three grid_ids, it should work! 


Finetuning ResNet 50: 
- generate synthetic data to improve feature vectors, pictures the same size, generates images with a random number of clusters and overlayed with random noise. 40% accuracy
- on cosine similarity: excellent results, there is a separation between broken and not broken for both ViT and Resnet
- Predict cluster centers

## Questions
- business importance of identifying clusters 
Jan will check the statistics. millions per year 
Criteo: 2 billion in revenue (not growth/profit), ~100 million ads shown a day. he will check how much the broken banners saved in revenue.

he has a dataset of broken traffic, napkin calculation

system in place: ONLY Look at metrics and not heatmap dataset (decisions made in miliseconds). look at KPIs and metrics. they look the KPI once a day or every 8 hours. CTR, landing rate = 0 , frames per second under a certain threshold => after a few days, they get an alert. they reactive, have an analytics team and engineers look at it. 


[business: we flag many displays as broken but don't stop showing immediately! leave a lot of money on the table, business metric]

for their current system that is run once a day, they want us to focus on threhsold on number of clicks! such that for a low number of clicks we can get results. also need a solution that can be scaled up as 100s of thousands (i.e. minimize number of computations, don't need to retrain model every time)

martin needs number of domains, with reasonable minimum number of clicks (e.g. 200) to calculate the minimum number of time

------
discussion on grid ID and metrics
increase probability that a given ad leads to a sale (individual user)

grid ID itself has no link to a broken banner! it's more of from a business perspective, how to make the ad more attractive! 

why are we using "grid ID" in particular and not the product itself? this is because the products are chosen in real time! where the ad is, based on the user, the ad hosting website and medium. not all URLs can show all grid IDs.

side note: ad types are evolving, there are not just images but videos now too

as long as we can identify the broken banner, criteo doesn't care about the grid ID! if we can get the end result faster we can use the grid ID, otherwise we don't care



# Report division breakdown
stuff left
- introduction (xinyi)
- state of the art/previous work (ling)
- problem statement (jean)
- data (jean)
- preprocessing (pca , standardization) (jenny)
- conclusion
- future direction (ViT/resnet/contrastive learning)  
- adding combined and metrics dataset (martin)
- making the report coherent (martin)