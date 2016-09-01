# Usage

## Map Overlay
Image that I asked you to locate coffee shops in Tempe given some set of criteria:

* must be on a commercial lot;
* must be within x distance of student housing;
* must be outside of x distance from other coffee shops;
* etc.

One way that you could solve this problem in a GISystem is to use map overlay.  You could gather the necessary layers, ensure they are coregistered (in the same projection), and then perform boolean overlay.  If all of the specififed criteria were true, you would have a potential site for a coffee shop and if any of the criteria were false, you would discount the site.  What happens though if the relationship is not [boolean](https://en.wikipedia.org/wiki/Boolean)?

As an alternative, we could formulate a favorability function ($$F(s)$$).  The boolean decision making process could then be formulated as:

$$\displaystyle F(s) = \prod_{M=1}^{m}X_{M}(s)$$,

where $$s$$ is each location in the study area, $$X_{M}(s)$$ is the coded suitability over the unit, and $$m$$ is the total number of units.  We enforce the following constraint. 

$$
X_{M}(s) = 
\begin{cases}
0, & \text{if the unit is not suitable} \\
1, & \text{if the unit is suitable} 
\end{cases}
$$

How is this formulation an improvement then?  If we relax the constraint such that $$ 0 \leq X_{M}(s) \leq 1$$.  We now no longer have a binary relationship between all of the values.  Using the above example, we could leverage some domain knowledge and assign weights.  The coffee shop must be on commerical land, so we continue to use the binary (boolean) constraint there.  We would like to be near student housing, but it is not critical, so we use an [inverse distance weighted](https://www.e-education.psu.edu/geog486/node/1877) scaling to determine a score for each unit of analysis.  

Extending the above method, we could be in a situation where our domain knowledge is incomplete.  It might be possible to identify the map layers that are of interest, but not to have a handle on what the weightings should be.  In this case, the *weights of evidence* method could be applied.  

The *weights of evidence* method computes $$F(s)$$ as a probability using [Bayes' Theorm](https://en.wikipedia.org/wiki/Bayes%27_theorem).  Bayes' Theorm provides a way to find P(A|B) or the conditional probability that even A occurs given the occurence of event B.  This is formulated as:

$$P(A|B) = P(A)\dfrac{P(B|A)}{P(B)}$$

The *weight of evidence* is the name given to the ratio $$\dfrac{P(B|A)}{P(B)}$$.  If this ratio is > 1 we know that the occurance of B increases P(A).  Conversely, if the ratio < 1 the occurance of B decreases P(B).  

In practice, we can estimate P(A) and P(B) as the proportion of the total areas for which those criteria are true.  We can then estimate P(B|A) as the ratio of the total area that criteria B and criteria A overlap.  Having these values, we can then compute P(A|B) and generate maps of posterior probability of some event given the occurance of some other events.  

Back to the coffee shop example, imagine that we have highly positive values for the success of a coffee shop, P(A|B),  when selecting sites near student housing and only slighlty negative values for P(A|B), when B is nearness to an existing coffee shop.  We could not generate maps with this weighting knowledge.

## Markov Chains
This section provides a high level overview of what a Markov Chain is and what very broad problem types can be represented.  The mathematical formulation to support Markov chains makes uses of matrix operations that will be fully covered later in this text and graph representations that support visualization.  For now, we focus very broadly on the use of probability as one component of a Markov Chain.

Markov chains find use in spatio-temporal analysis.  Imagine that we have fixed areal units (like U.S. states) and longitudinal (time series) data.  If our data ran from 1900 to 2000, we would have 100 element lists of data for each state.  To start simply, let us imagine that we are only interested in Arizona.  Then formally, the data vector (the list, or set $$S$$) could be defined as a Markov chain if we have a sequence of random variables $$X_{0}, X_{1}, X_{2}, \ldots$$ from which future observations $$X_{n+1}, X_{n+2}, \ldots, X_{n}$$ are dependent.  In other words, if we have an observation set of [Gross Domestic Product](https://en.wikipedia.org/wiki/Gross_domestic_product)(GDP) from 1900 to 2000 and we have reason to believe that the GDP of Arizona in $$2001, 2002, \ldots, 2099$$  depends on historical data, we have a Markov chain.  The use of Markov chains makes a few other statistical assumptions that are not to be trivialized, but are also beyond the scope of the underlying mathematics in this text.

Mathematically, we can formulate a Markov Chain as:

$$Pr(X_{n+1} = j | X_{n} = i) = p_{ij}$$,

where $$p_{ij}$$ is a probability matrix.  We will look more deeply at Markov chains when we start to look at matrices, but the basic take away is this:  markov chains are used in the analysis of temporal and spatio-temporal data where the future state is conditionally dependent on the current state.  A transition from the current state to a new state is not guaranteed and some transition probabilities are used.

![](images/markov.png)

Above we see a two state Markov Chain, where a given element can be in either state E or state A.  The current state of the chain is A (indicated by the blue circle).  Notice that each state has two arrows exiting to the other state.  The numbers associated with those arrows are the probabilities of a transition.  For example, is the element is currently in state A, there is a 60% chance that the element remains in state A in the next time step and a 40% chance that the element transitions to state E.
