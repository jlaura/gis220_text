# Spatial Regression Models
This section is definitely not intended to be a substitute for a true course on spatial regression, in fact, the goal is simply to illustrate the use of spatial weights objects (and by extension matrix operations) within the context of GIScience.  Therefore, this section is intentionally broad.

Assume that we have a traditional Ordinary Least Squares (OLS) regression model:

$$y = x\beta + \epsilon$$

The above model makes a few assumptions that will fail if we are using spatial data.  This is primarily due to the assumption that $$\epsilon$$ is identically and independently distributed.  Therefore, different spatially aware regression models have been proposed.  We will look at two of these, the spatial autoregressive model (SAR) and the spatial error model (SEM).

## Spatial Autoregressive Model (Spatial Lag Model)
This model is appropriate when the focus of the analysis is the existance and strength of spatial interaction (Anselin, 2003 - *A Companion to Theoretical Econometrics*) and is formulated as:

$$y = \rho W y + X\beta + \epsilon$$,

where $\rho$ is a scalar spatial autoregressive coefficient (that in and of itself receives huge attention, but is (un)fortunately not the focus of this section), $$\mathbf{W}$$ is the spatial weights object, $$y$$ is the dependent variable (so $$\mathbf{Wy}$$ is the spatially lagged dependent variable), and $$\epsilon$$ is the error term.  Our interest is in $$\mathbf{W}y$$.


#### Supplemental Video
[![Spatial Lag](http://img.youtube.com/vi/zWXnOM3_lJI/0.jpg)](https://www.youtube.com/watch?v=zWXnOM3_lJI)

So what exactly is the spatial lag model trying to capture by placing $$y$$ on both sides of the equality?  $$\rho \mathbf{W} y$$ is a predictor, in addition to $$\beta X$$ and spatially lagging the dependent variable seeks to account for the spatial interaction.  That interaction is not simplistic.  For example, city A does not influence city B without city B somehow influencing city A.  While I do not recall where I read the analogy, this is akin to dropping a rock into a pond with a few reeds.  The ripples expand out from where the rock was dropped and bounce off the reeds causing secondary ripples.  Those ripples bounce around and interact again, and again, and again creating a highly complex system.  Spatial interactions are analoguous.