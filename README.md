# Network Analysis: Assignment 1

## Information about the dataset
This dataset consists of 'circles' (or 'friends lists') from Facebook collected from survey participants. The dataset includes node features (profiles), circles, and ego networks.
It's been downloaded from [here](https://snap.stanford.edu/data/ego-Facebook.html).
The linked page provides two different dataset:
An <i> Ego-centric network</i> (or <i>"ego" networks</i>), is particular type of network in which specifically maps the connections of and from the perspective of a single person (an ego). In fact this networks represent circles of friends of a certains person (ego). 

  - The first contains 10 ego networks, each one has the edge list, a list of clicles (each one constisting of list of nodes), and other features of the network.
  - The second, that is the one used in the assigmentent is a network obtained combing all the ego-networks, including the ego nodes themselves, along with an edge to each of their friends.

## Analysis

| Dataset statistics | Values|
|--------------------|-------|
| Nodes | 4039               |
| Edges | 88234              |
| Average Degree | 43.691    |
| Average clustering | 0.605 |
| Global clustering |        |
| Nodes giant component | 4039 |
| Diameter | 8               |
| Average shortest path | 3.69|
| Density |         0.01      |
| Assortativity |            |

</br> </br>

<!-- Uncomment on github ![alt text](https://github.com/LazyRacc00n/NetworkAnalysis_1Assignment/blob/main/images/Facebooks_circles.png) -->
![alt text](images\Facebooks_circles.png)

The network is undirected, is composed by 4039 nodes and 88234. The density </br> <center> <img src="https://latex.codecogs.com/svg.image?\inline&space;\rho&space;=&space; \frac{L}{\frac{1}{2}N(N-1)"/> </center> </br>, in which L is the total number of links and N is the total number of nodes, represents the total number of edges on the total possible edges, and in this case this values is very small, 0.01, this means that the network is sparse. </br>
The <i> average clustering </i> is the average of all the <i> clustering coefficients</i>, defined as
 </br> <center> <img src="https://latex.codecogs.com/svg.image?\inline&space;C_i&space;=&space; \frac{k_i}{k_i(k_i-1)"/> </center> </br>, in which <img src="https://latex.codecogs.com/svg.image?\inline&space;L_i"/> is the number of links between the <img src="https://latex.codecogs.com/svg.image?\inline&space;k_i"/> neighbors. This value captures the degree to which the neighbors of a node link to each other, and it is in the range [0,1]. In this case, the mean value in the network is 0.605 and this means that there is in average a 60.5% of probability that a node randomly selected has two neighbors linked. 

### Does the graph have the same characteristics of a random or a power-law network?
 </br></br>
  ![alt text](images\degree_distribution.png)
  </br></br>
  Observing the chart of the degree distribution is possible to notice that the degree distribution follows the trend of a <i>power law</i> degree distribution, described by the following equation:
  <!--Poi su git si vede bene -->
  <img src="https://latex.codecogs.com/svg.image?\inline&space;p_k&space;\sim&space;k^{-\gamma}"/>
  </br>
  Since the degree distribution follows a power law, the network is called <i>scale free</i> network, in which fact there are a fraction of nodes with very high degree, that are the hubs.

  </br></br>

### Which are the most important nodes, with respect to a given centrality measure?

We decide to measure the "importance" of the nodes considering the betweenness and the closeness centrality.

|Betweenness|Closeness|
|--|--|
|<table> <tr><th>Node</th><th>Value</th></tr><tr><td>**107**</td><td>0.480</td></tr> <tr><td>**1684**</td><td>0.337</td></tr> <tr><td>3437</td><td>0.236</td></tr> <tr><td>1912</td><td>0.229</td></tr> <tr><td>1085</td><td>0.149</td></tr> <tr><td>0</td><td>0.146</td></tr> <tr><td>698</td><td>0.115</td></tr><tr><td>567</td><td>0.096</td></tr> <tr><td>**58**</td><td>0.084</td></tr> <tr><td>**428**</td><td>0.064</td></tr> </table>| <table> <tr><th>Node</th><th>Value</th></tr><tr><td>**107**</td><td>0.459</td></tr>  <tr><td>**58**</td><td>0.397</td></tr> <tr><td>**428**</td><td>0.394</td></tr> <tr><td>563</td><td>0.393</td></tr> <tr><td>**1684**</td><td>0.393</td></tr> <tr><td>171</td><td>0.370</td></tr> <tr><td>348</td><td>0.369</td></tr><tr><td>483</td><td>0.369</td></tr> <tr><td>414</td><td>0.369</td></tr> <tr><td>376</td><td>0.366</td></tr></table>|

The table above shows the top 10 nodes with maximum betweeness and the top 10 nodes with maximum closeness and the nodes present in both ranking are highlighted.

The betweeness measures how many short paths pass to , instead the closeness measures the mean distance from a vertex to the other vertices and therefore the nodes with high closeness can have an easy access to information of influence on other nodes.

As can be seen from the table the node *107* it has the highest betweeness and the higher closeness, so we can say that such node is very important in the network and in the main cluster that is in the center of it.

The closeness measures don't change too much from one node to the other, and this can be a 
By constrast the betweeness measures in the ranking dedreases very fast, so there are few nodes which lead the communication between the clusters of the network. In fact it can be seen from the graph above that few nodes connect the cluster to the "center" of the network.

  </br></br>
### Are the paths short with respect to the size of the network?
  </br></br>
### Is the network dense?
  </br></br>
### Is the network assortative?
  </br></br>
### And so on
