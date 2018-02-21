# Mixed Effects Model

Src: https://ourcodingclub.github.io/2017/03/15/mixed-models.html

From the source (a lot of copy-paste):

 - **Fixed effects** are variables that we expect will have an effect on the dependent/response variable. In our case, we are interested in making conclusions about how dragon body length impacts the dragon’s test score. So body length is a fixed effect and test score is the dependent variable.
 
 - **Random effects** (or random factors - as they will be categorical) are usually "grouping factors" which we are trying to control for in terms of their contribution to variation (primarily, so as to isolate contribution to variation of the individual datapoint). A lot of the time we are not specifically interested in their impact on the response (dependent) variable. Additionally, the data for our random effect is just a sample of all the possibilities. Keep in mind that "random" doesn’t have much to do with mathematical randomness. 
 
In the case of the dragon dataset, we are looking to control for the effects of mountain range. We haven’t sampled all the mountain ranges in the world (we have eight) so our data are just a sample of all the existing mountain ranges. We are not really interested in the effect of each specific mountain range on the test score, but we know that the test scores from within the ranges might be correlated so we want to control for that.

# Fixed or Random Effect?

Seems like a philosophical question more than anything else. See a good discussion [link](https://dynamicecology.wordpress.com/2015/11/04/is-it-a-fixed-or-random-effect/)

 - Good decision tree at the bottom of the post.

 - One heuristic: am I interested in this variable (fixed) or is it just a blocking factor/control variable* (random)? The blogger doesn't seem to think that this is a good heuristic; he posits that you can't treat a continuous variable (e.g. age) as a blocking factor. The machine-learning cowboy that I am says that you can still partition the data into age-groups - ta da, categorical variable. 
 
 - A very good discussion on degrees-of-freedom vs. numbers of variable.  There's no point trying to get high-resolution information if there are too few data points per group. 
