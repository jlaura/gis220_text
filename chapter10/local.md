# Location and Transportation Problems

## Weber Problem

You may have heard of the Weber problem. It is the traditional location problem, which tries to determine the location of factory that can minimize total transportation cost of raw materials and product. In this case the facility needs two raw materials from separate locations, and it ships the product to single market. Transportation cost is determined as distance, weighted by the amount of material/product being shipped (longer distances with less material are less desirable than shorter distances with the same amount of material). Location of the raw materials sources and the market is given. The facility can be located anywhere in a given area.
For simplicity, distance is measured by rectilinear distance (or so called [Manhattan distance](https://en.wikipedia.org/wiki/Taxicab_geometry)). In rectilinear distance (1-norm distance), distance between two points $$a (x_{a}, y_{a})$$ and $$b (x_{b}, y_{b})$$ is measured:

$$ D = |(x_{b} - x_{a}) + (y_{b} - y_{a})|$$
Like its name, movement in rectilinear distance metric is restricted to 90-degree turns. 
Let’s start from decision variables. Here, decision variables are location of facility in terms of x and y coordinates: $$(x_{f}, y_{f})$$.Location (coordinates) of raw material source 1, 2, and the market is given. For this hypothetical problem, we don’t have actual number, but we can say:$$(x_{m} , y_{m})$$ = coordinates of the market
$$(x_{r1}, y_{r1})$$ = coordinates of raw material source 1 

$$(x_{r2}, y_{r2})$$ = coordinates of raw material source 2
Amount of raw materials and product to be shipped:$$w_{r1}$$ = quantity of raw material 1 needed to be shipped 

$$w_{r2}$$ = quantity of raw material 2 needed to be shipped 

$$w_{m}$$ = quantity of produced shipped to market
Objective of this problem is to minimized transportation cost, which is translated as sum of weighted distance. Transportation cost of raw material 1 to the facility is:$$w_{r1}(|x_{f} - x_{r1}| + |y_{f} - y_{r1}|)$$
and then the objective function isMinimize: $$ w_{r1}(|x_{f} - x_{r1}| + |y_{f} - y_{r1}|) + w_{r2}(|x_{f} - x_{r2}| + |y_{f} - y_{r2}|) + w_{m}(|x_{f} - x_{m}| + |y_{f} - y_{m}|)$$

Or, if we represent two sources and the market using index, $$i = 1,2,3$$, and represent distance like:

$$D_{i} = (|x_{f} - x_{i}| + |y_{f} - y_{i}|)$$
Then objective function can be rewritten as:Minimize $$\sum_{i=1}^{3} w_{i}D_{i}$$This is nonlinear problem, as distance function has the absolute value operator. So we will not see how to solve the Weber problem, but as it is traditional and a great exercise in formulation.

## Generic Transportation Problem

In apple shipment problem, we discussed a transportation problem with single supply source. We can construct an optimization model for multiple supply source and multiple demand nodes. Let say we have $$j$$ supply node and $$i$$ demands. Each demand $$i$$ node needs certain amount of demand, $$D_{i}$$ (Note that demand is being represented using $$D_{i}$$, while above $$D_{i}$$ was distance) but it will be welcome to be provided more than that. The product can be shipped from multiple supply nodes to a single demand node. Each supply node has limited supply capacity, denoted as $$S_{j}$$. Transportation cost from supply $$j$$ to demand $$i$$ is denoted as $$c_{ij}$$.
$$S_{j}$$ = the supply at node $$j$$
$$D_{i}$$ = the demand at node $$i$$$$c_{ij}$$ = the unit cost of shipping from supply node $$j$$ to demande node $$i$$
Decision variable is amount of product for each demand node.$$X_{ij}$$ = the amount shipped from supply node $$j$$ to demand node $$i$$
The objective is also to minimize total transportation cost:

Minimize $$\sum_{i}\sum_{j}c_{ij}X_{ij}$$
In this case, constraints are capacity limitation of each supply and minimum requirement of each demand node.
Subject to:$$\sum_{i}X_{ij} \leq S_{j} \forall j$$ (1)

$$\sum_{j}X_{ij} \geq D_{i} \forall i$$ (2)

$$X_{ij} \geq 0 \forall i, j$$ (3)Constraint (1) is supply capacity restriction. For each supply node $$j$$, total sum of shipped product to demand nodes cannot be more than $$S_{j}$$. Likewise, in constraint (2), for each demand node $$i$$, total sum of supply must be greater than or equal to $$D_{i}$$.