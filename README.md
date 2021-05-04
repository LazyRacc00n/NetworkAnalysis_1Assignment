# 1. Network Analysis: Assignment 1

## 1.1. Information about the dataset
This dataset consists of 'circles' (or 'friends lists') from Facebook collected from survey participants. The dataset includes node features (profiles), circles, and ego networks. 
An <i> ego network</i>, is a network in which there is one central node known as <i> ego </i>. The network is based off the ego and the nodes directly connected with the ego are colled <i> alters </i>. 
It's been downloaded from [here](https://snap.stanford.edu/data/ego-Facebook.html). </br>
The linked page provides two different dataset:
  - The first contains 10 ego networks, each one has the edge list, a list of clicles (each one constisting of list of nodes), and other features of the network.
  - The second, that is the one used in the assigmentent is a network obtained combing all the ego-networks, including the ego nodes themselves, along with an edge to each of their friends.
$\alpha^2$
## 1.2. Analysis

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

### 1.2.1. Does the graph have the same characteristics of a random or a power-law network?
 </br></br>
  ![alt text](images\degree_distribution.png)
  </br></br>
  Observing the chart of the degree distribution is possible to notice that the degree distribution follows the trend of a <i>power law</i> degree distribution, described by the following equation:
  <!--Poi su git si vede bene -->
  <img src="https://latex.codecogs.com/svg.image?\inline&space;p_k&space;\sim&space;k^{-\gamma}"/>
  </br>
  Since the degree distribution follows a power law, the network is called <i>scale free</i> network, in which fact there are a fraction of nodes with very high degree, that are the hubs.

  </br></br>

### 1.2.2. Which are the most important nodes, with respect to a given centrality measure?

We decide to measure the "importance" of the nodes considering the betweenness and the closeness.

|Betweenness|Closeness|
|--|--|
|<table> <tr><th>Node</th><th>Value</th></tr><tr><td>**107**</td><td>0.480</td></tr> <tr><td>**1684**</td><td>0.337</td></tr> <tr><td>3437</td><td>0.236</td></tr> <tr><td>1912</td><td>0.229</td></tr> <tr><td>1085</td><td>0.149</td></tr> <tr><td>0</td><td>0.146</td></tr> <tr><td>698</td><td>0.115</td></tr><tr><td>567</td><td>0.096</td></tr> <tr><td>**58**</td><td>0.084</td></tr> <tr><td>**428**</td><td>0.064</td></tr> </table>| <table> <tr><th>Node</th><th>Value</th></tr><tr><td>**107**</td><td>0.459</td></tr>  <tr><td>**58**</td><td>0.397</td></tr> <tr><td>**428**</td><td>0.394</td></tr> <tr><td>563</td><td>0.393</td></tr> <tr><td>**1684**</td><td>0.393</td></tr> <tr><td>171</td><td>0.370</td></tr> <tr><td>348</td><td>0.369</td></tr><tr><td>483</td><td>0.369</td></tr> <tr><td>414</td><td>0.369</td></tr> <tr><td>376</td><td>0.366</td></tr></table>|

The table above shows the top 10 nodes with maximum betweeness and the top 10 nodes with maximum closeness and the nodes present in both ranking are highlighted.

The betweeness measures, instead the closeness measures the mean distance from a vertex to the other vertices.

As can be seen from the table the node *107* it has the highest betweeness and the higher closeness, so we can say that such node is very important in the network because ...

The closeness 


  </br></br>
### 1.2.3. Are the paths short with respect to the size of the network?
  </br></br>
### 1.2.4. Is the network dense?
  </br></br>
### 1.2.5. Is the network assortative?
  </br></br>
### 1.2.6. And so on
