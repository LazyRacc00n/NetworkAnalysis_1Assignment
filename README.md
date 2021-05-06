<center> <h1> Network Analysis: Assignment 1 </h1> </center>
</br>
<h5 style="text-align: right">Simone Campisi s4341240 </h5>
<h5 style="text-align: right">Jacopo Dapueto s4379956 </h5>

## 1. Information about the dataset
This dataset consists of 'circles' (or 'friends lists') from Facebook collected from survey participants. The dataset includes node features (profiles), circles, and ego networks.
It's been downloaded from [here](https://snap.stanford.edu/data/ego-Facebook.html).
The linked page provides two different dataset:
An <i> Ego-centric network</i> (or <i>"ego" networks</i>), is particular type of network in which specifically maps the connections of and from the perspective of a single person (an ego). In fact this networks represent circles of friends of a certains person (ego). 

  - The first contains 10 ego networks, each one has the edge list, a list of clicles (each one constisting of list of nodes), and other features of the network.
  - The second, that is the one used in the assigmentent is a network obtained combing all the ego-networks, including the ego nodes themselves, along with an edge to each of their friends.

 ![Ego Network - Facebook Circles Combined](./images/Facebooks_circles.png) 
## 2. Analysis

| Dataset statistics | Values |
|--------------------|------- |
| Nodes | 4039                |
| Edges | 88234               |
| Average Degree | 43.691     |
| Average clustering | 0.605  |
| Global clustering |    0.51 |
| Nodes giant component| 4039 |
| Diameter |               8  |
| Average shortest path | 3.69|
| Density |         0.01      |
| Assortativity |             |

</br> </br>


### 2.1. Does the graph have the same characteristics of a random or a power-law network?

 </br></br>


  | ![Degree Distribution](./images/degree_distribution.png) |
  |:--: |
  | *Figure 1 - Degree Distribution and fitting of the curve* |
  
  
  | ![Curve Fit](./images/fitted_curve_degree_distribution.png) |
  |:--: |
  | *Figure 2 - Curve fitted plotted in logarithmic scale* |
  
  Observing the chart of the degree distribution ( <i> figure 1 </i>) is possible to notice that the degree distribution follows the trend of a <i>power law</i> degree distribution, described by the following equation:

  
  <center>
  <img src="https://latex.codecogs.com/svg.image?\inline&space;p_k&space;\sim&space;C*k^{-\gamma}"/>
  </center>
  </br>
  
 Hence in the <i> figure 1 </i> is represented the degree distribution in a scatterplot with the curve that represents the trend of the distribution. The curve has been calculated making the fit of the curve, estimating the parameter <i> C </i> and  <img src="https://latex.codecogs.com/svg.image?\inline&space;\gamma"/> of the power law equation. This latest curve allows to prove that the degree destribution is effectively power law, in fact, plotting the curve in logarithmic scale, is possible to notice that the graphic follows a straight line, and this a characteristic of a degree distribution that follows a power law <i> ( figure 2 ) </i>.

 Since the degree distribution follows a power law, the network is called <i>scale free</i> network, in which fact there are a fraction of nodes with very high degree, that are the hubs.

  </br></br>

### 2.2. Which are the most important nodes, with respect to a given centrality measure?

We decide to measure the "importance" of the nodes considering the betweenness and the closeness centrality.

|Betweenness|Closeness|
|--|--|
|<table> <tr><th>Node</th><th>Value</th></tr><tr><td>**107**</td><td>0.480</td></tr> <tr><td>**1684**</td><td>0.337</td></tr> <tr><td>3437</td><td>0.236</td></tr> <tr><td>1912</td><td>0.229</td></tr> <tr><td>1085</td><td>0.149</td></tr> <tr><td>0</td><td>0.146</td></tr> <tr><td>698</td><td>0.115</td></tr><tr><td>567</td><td>0.096</td></tr> <tr><td>**58**</td><td>0.084</td></tr> <tr><td>**428**</td><td>0.064</td></tr> </table>| <table> <tr><th>Node</th><th>Value</th></tr><tr><td>**107**</td><td>0.459</td></tr>  <tr><td>**58**</td><td>0.397</td></tr> <tr><td>**428**</td><td>0.394</td></tr> <tr><td>563</td><td>0.393</td></tr> <tr><td>**1684**</td><td>0.393</td></tr> <tr><td>171</td><td>0.370</td></tr> <tr><td>348</td><td>0.369</td></tr><tr><td>483</td><td>0.369</td></tr> <tr><td>414</td><td>0.369</td></tr> <tr><td>376</td><td>0.366</td></tr></table>|

The table above shows the top 10 nodes with maximum betweeness and the top 10 nodes with maximum closeness and the nodes present in both ranking are highlighted.

The betweeness measures how many short paths pass to, instead the closeness measures the mean distance from a vertex to the other vertices and therefore the nodes with high closeness can have an easy access to information of influence on other nodes.

As can be seen from the table the node *107* it has the highest betweeness and the higher closeness, so we can say that such node is very important in the network and in the main cluster that is in the center of it.

The closeness measures don't change too much from one node to the other, and this can be a 
By constrast the betweeness measures in the ranking dedreases very fast, so there are few nodes which lead the communication between the clusters of the network. In fact it can be seen from the graph above that few nodes connect the cluster to the "center" of the network.
</br>
### 2.3. Are the paths short with respect to the size of the network?
  </br>
  The <i>shortest path (or geodesic path)</i>  between two nodes in a network the number of links. The length of a shortest path is called <i> shortest distance </i>.
  The <i> average shortest path </i>, instead, is the average of the shortest paths between all the pairs nodes, and in the network we are considering is about 3.69. So, is possible to say that in this network there is a <b> small-world effect </b> because the average shortest path is surprisingly short when compared with the numkber of nodes of the network, that are 4039.

### 2.4. Is the network dense?
  </br>
  The <b> density </b> of a network is the defined by the following formula: </br></br> <center> <img src="https://latex.codecogs.com/svg.image?\inline&space;\rho&space;=&space; \frac{L}{\frac{1}{2}N(N-1)"/> </center> </br>, in which L is the total number of links and N is the total number of nodes, represents the total number of edges on the total possible edges, and in this case this values is very small, 0.01, this means that the network is <b> sparse</b>. </br>
### 2.5. Is the network assortative?
  </br></br>
### 2.6. Average clustering

The <i> average clustering </i> is the average of all the <i> clustering coefficients</i>, defined as
 </br> <center> <img src="https://latex.codecogs.com/svg.image?\inline&space;C_i&space;=&space; \frac{k_i}{k_i(k_i-1)"/> </center> </br>, in which <img src="https://latex.codecogs.com/svg.image?\inline&space;L_i"/> is the number of links between the <img src="https://latex.codecogs.com/svg.image?\inline&space;k_i"/> neighbors. This value captures the degree to which the neighbors of a node link to each other, and it is in the range [0,1]. In this case, the mean value in the network is 0.605 and this means that there is in average a 60.5% of probability that a node randomly selected has two neighbors linked.