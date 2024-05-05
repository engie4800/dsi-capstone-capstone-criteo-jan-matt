# Comments
- Rendering might be different browsing on the web, the grid type might not be fancy
- For LRT: currently we have done a one shot learning. Picked a representative banner with high landing rate. This is good for especially the beginning cold start.
- Prof Sining wants us to run the model in the streaming fashion - but problem with this zero-shot learning: all clicks -> quite a lot of bad banners! 


# LRT method false negative
- first block image -> could be that a wrong image was shown or a bot
- second and third images -> many more users closed the ad than clicked on the ad -> many users closed the advertisement. broken because impending user experience. we can classify this as a broken banner!

# Posters
two methods: focus on the business or on the technique both works, but maybe business is more reasonable
small section in the poster / report for what requirements needed in hardware in CPU/GPU, what would be the memory necessary

# TODO stats approach
- uniform distribution for broken vs uniform distribution for good - which is better?
- how to handle edge cases: let landing rate decide whether it's broken or not for further classify, landing rate decision tree