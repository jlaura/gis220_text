# Location and Transportation Problems

## Weber Problem

You may have heard of the Weber problem. It is the traditional location problem, which tries to determine the location of factory that can minimize total transportation cost of raw materials and product. In this case the facility needs two raw materials from separate locations, and it ships the product to single market. Transportation cost is determined as distance, weighted by the amount of material/product being shipped (longer distances with less material are less desirable than shorter distances with the same amount of material). Location of the raw materials sources and the market is given. The facility can be located anywhere in a given area.


$$ D = |(x_{b} - x_{a}) + (y_{b} - y_{a})|$$




$$(x_{r2}, y_{r2})$$ = coordinates of raw material source 2


$$w_{r2}$$ = quantity of raw material 2 needed to be shipped 

$$w_{m}$$ = quantity of produced shipped to market



Or, if we represent two sources and the market using index, $$i = 1,2,3$$, and represent distance like:

$$D_{i} = (|x_{f} - x_{i}| + |y_{f} - y_{i}|)$$


## Generic Transportation Problem

In apple shipment problem, we discussed a transportation problem with single supply source. We can construct an optimization model for multiple supply source and multiple demand nodes. Let say we have $$j$$ supply node and $$i$$ demands. Each demand $$i$$ node needs certain amount of demand, $$D_{i}$$ (Note that demand is being represented using $$D_{i}$$, while above $$D_{i}$$ was distance) but it will be welcome to be provided more than that. The product can be shipped from multiple supply nodes to a single demand node. Each supply node has limited supply capacity, denoted as $$S_{j}$$. Transportation cost from supply $$j$$ to demand $$i$$ is denoted as $$c_{ij}$$.





Minimize $$\sum_{i}\sum_{j}c_{ij}X_{ij}$$



$$\sum_{j}X_{ij} \geq D_{i} \forall i$$ (2)

$$X_{ij} \geq 0 \forall i, j$$ (3)