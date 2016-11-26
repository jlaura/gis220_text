# The Huff Model and Distance Decay

The Huff Model is a gravity model that seeks to answer the question: How likley is some consumer to visit a retail location.  The Huff model is available within the ArcGIS software application and the description of how the Huff model functions is well documented.  Please see: [The Original Huff Model](http://desktop.arcgis.com/en/arcmap/10.3/tools/business-analyst-toolbox/how-original-huff-model-works.htm).

The formulation is unfortunately small on that page.  The equation is:

$$P_{ij} = \dfrac{W_{i}/D_{ij}^{a}}{\sum_{i=1}^{n}(W_{i}/D_{ij}^{a})}$$, 

with all variables defined in the above link.

A key componnt of the Huff model (and many other interaction models) is the concept of distance decay.  Please read:

[Distance Decay Models](http://www.spatialanalysisonline.com/HTML/index.html?distance_decay_models.htm).