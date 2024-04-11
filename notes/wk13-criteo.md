# Comments
- Rendering might be different browsing on the web, the grid type might not be fancy
- For LRT: currently we have done a one shot learning. Picked a representative banner with high landing rate. This is good for especially the beginning cold start.
- Prof Sining wants us to run the model in the streaming fashion - but problem with this zero-shot learning: all clicks -> quite a lot of bad banners! 


# LRT method false negative
- first block image -> could be that a wrong image was shown or a bot
- second and third images -> many more users closed the ad than clicked on the ad -> many users closed the advertisement. broken because impending user experience. we can classify this as a broken banner!