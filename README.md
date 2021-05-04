# Network Analysis: Assignment 1

## Information about the dataset
This dataset consists of 'circles' (or 'friends lists') from Facebook. Facebook data was collected from survey participants. The dataset includes node features (profiles), circles, and ego networks.
It's been downloaded from [here](https://snap.stanford.edu/data/ego-Facebook.html).

## Analysis

| Dataset statistics | Values|
|--------------------|-------|
| Nodes | 4039               |
| Edges | 88234              |
| Average Degree | 43.691    |
| Average clustering | 0.605 |
| Nodes giant component | 4039 |
| Diameter | 8               |
| Average shortest path | 3.69|
| Density |                  |
| Assortativity |            |

</br> </br>

<!-- Uncomment on github ![alt text](https://github.com/LazyRacc00n/NetworkAnalysis_1Assignment/blob/main/images/Facebooks_circles.png) -->
![alt text](images\Facebooks_circles.png)

- Does the graph have the same characteristics of a random or a power-law network?
 </br></br>
  ![alt text](images\degree_distribution.png)
  </br></br>
  Observing the graphic of the degree distribution is possible to notice that the degree distribution follows the trend of a <i>power law</i> degree distribution, described by the following equation:
  <!--Poi su git si vede beene -->
  <img src="https://latex.codecogs.com/svg.image?\inline&space;p_k&space;\sim&space;k^{-\gamma}"/>

  </br></br>

- Which are the most important nodes, with respect to a given centrality measure?

We decide to measure the "importance" of the nodes considering the betweenness and the closeness.

|Betweenness|Closeness|
|--|--|
|<table> <tr><th>Node</th><th>Value</th></tr><tr><td>107</td><td>0.480</td></tr> <tr><td>1684</td><td>0.337</td></tr> <tr><td>3437</td><td>0.236</td></tr> <tr><td>1912</td><td>0.229</td></tr> <tr><td>1085</td><td>0.149</td></tr> <tr><td>0</td><td>0.146</td></tr> <tr><td>698</td><td>0.115</td></tr><tr><td>567</td><td>0.096</td></tr> <tr><td>58</td><td>0.084</td></tr> <tr><td>428</td><td>0.064</td></tr> </table>| <table> <tr><th>Node</th><th>Value</th></tr><tr><td>107</td><td>0.459</td></tr>  <tr><td>58</td><td>0.397</td></tr> <tr><td>428</td><td>0.394</td></tr> <tr><td>563</td><td>0.393</td></tr> <tr><td>1684</td><td>0.393</td></tr> <tr><td>171</td><td>0.370</td></tr> <tr><td>348</td><td>0.369</td></tr><tr><td>483</td><td>0.369</td></tr> <tr><td>414</td><td>0.369</td></tr> <tr><td>376</td><td>0.366</td></tr></table>|

The table above shows the top 10 nodes with maximum betweeness and the top 10 nodes with maximum closeness.
  </br></br>
- Are the paths short with respect to the size of the network?
  </br></br>
- Is the network dense?
  </br></br>
- Is the network assortative?
  </br></br>
- And so on
