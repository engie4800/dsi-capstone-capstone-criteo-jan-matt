New method

- KL divergence to compare two images. when you have the assumption that most of the banners are not broken, the summary of the heatmaps should be a representation of what is not broken. 

- Martin used a chi-square test on two different images. original distribution -> probabiility of getting instance distribution. 
- empirical distribution over entire 2D space - intensity (number of clicks) of a bin/pixel sums to 1. 
- calculate likelihood of each click - new click lands on certain location, lkelihood of clicks jjust based on location alone. so if a click landed on an unlikely location, we will get a low likelihood for that click. if you can keep track of the cumulative likelihood and want that cumulative likelihood to go below a certain threshold

- empirical distribution -> use log since probabilities are small -> good sample vs instance - take another instance that was good and compare probability 


possible algorithm:
    log likelihood: outside of 6 sigma -> trigger alarm
    this shd be extremely cheap as linear operations 
    raw data - we have number of clicks 
    when a new click comes in, and given a pixel location, calculate p = likelihood of that click given the binomial distribution for each pixel (parameter theta?)


discussion of adding the timestamp and considering it as a streaming problem 
for each incoming click, set a probability and if it is too low, trigger an alarm


500 banners under one grid ID, one particular grid ID, we want to know which one of the 500 is broken
what we will do is 
- first calculate the summary of the whole grid ID, so in each pixel location we have the number of clicks
- for that particular location, suppose that this location never gets clicked. each pixel (i,j) has $\theta_{i,j}$ that sums to 1. so for a location on a border that shouldn't get any clicks, that theta is small for that location. in the whole image, you have one theta per pixel.
- look at banner 123 (out of 500). first consider that you are working at the company live, location x y at banner 123. when it lands in the location, it is very unlikely (land in pixel with very low theta). theta is the likelihood for that click. when you click on that location u get a very small loglikelihood.
- if banner 123 keeps getting unlikely clicks, then loglikelihood will be really small, whereas a good banner would keep getting good locations.

simplest case -> banner of 2*2, 4 cels, 4 thetas. 97 - 1 - 1 - 1

now you have a banner where you observe 3 consecutive clicks on the lower right.