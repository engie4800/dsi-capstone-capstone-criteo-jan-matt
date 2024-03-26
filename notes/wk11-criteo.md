# Questions clarified
- Criteo has more than five grid_id's
- grid_id + #products + domain = banner
- the compute power is low because Criteo does sampling

# Slides
- Cosine similarity for ViT and ResNet: picked an anker (mean of two representative samples)
- Fine tune ResNet on number of clusters, and position of clusters
- Jan: can always draw a symmetrical line?
- Jan: create 10 graphs similar to cosine similarity count vs location to see the migration of colored points(with threshold)
- PCA on four powerful features
- Jan: landing rate below 30% - broken, above 80% - clean, always see 6 products for the new data
- Jan: include f1-score for 0/1-shot approaches in the final report/poster
- Jan: explain why 333346 always performs better (probably due to different class imbalance in two grid_id's), can try to resample to make the class distribution same