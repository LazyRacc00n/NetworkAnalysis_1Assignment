<center> <h1> Network Analysis: Assignment 1 </h1> </center>
</br>
<h5 style="text-align: right">Simone Campisi s4341240 </h5>
<h5 style="text-align: right">Jacopo Dapueto s4345255 </h5>

## 1. Information about the dataset

This dataset we choose consists of 'circles' (or 'friends lists') from Facebook collected from survey participants. The dataset includes node features (profiles), circles, and ego networks.
It's been downloaded from [Stanford Network Analysis Project](https://snap.stanford.edu/data/ego-Facebook.html).
The linked page provides two different dataset:

- The first contains 10 ego networks, each one has the edge list, a list of circles (each one consisting of list of nodes), and other features of the network. An <i> Ego-centric network</i> (or <i>"ego" networks</i>)consist of a focal node ("ego") and the nodes to whom ego is directly connected to (these are called "alters"). In fact this networks represent circles of friends of a certain person (ego).
- The second is the one used in the assignment and it is obtained combining all the ego-networks, including the ego nodes themselves along with an edge to each of their friends.

To visualize the network we used <b>Gephi</b> which provides functionalities to process networks, especially for very large networks. 

One of them identifies the <i>communities</i> through the <i>modularity</i> measure and to each of them is assigned a different color. In the image below there are both densely connected communities and sparsely connected ones. So this is a good way to represent the ego network, because is possible to see better the circles of friends.

<div align="center">
  <figure>
  <img src="./images/Facebooks_circles.png" height="75%" width="75%" />
  </figure>
</div>

## 2. Analysis

The following table shows the global statistics we used to analyze the network in the following chapters, it includes the number of nodes and edges, the average clustering and the global clustering etc. The entire network is connected so exist a path for each pair of nodes.

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
| Assortativity |     0.06    |

</br> </br>


### 2.1. Does the graph have the same characteristics of a random or a power-law network?

To answer to the question we first visualize the degree distribution together with the fitted curve. 
Each dot represent a degree and the frequency it appears in the dataset.
 </br></br>



<div align="center" style="border: solid">
<figure>
<img src="./images/degree_distribution.png" height="80%" width="80%" />
<figcaption> <i>Figure 1 - Degree Distribution and fitting of the curve</i> </figcaption>
</figure>
</div>

</br></br> 
  
  At the first sight it seems that the chart in <i> figure 1 </i> shows the degree distribution following the trend of a <i>power law</i> and the fittd curve is described by the equation <img src="https://latex.codecogs.com/svg.image?\inline&space;p_k&space;\sim&space;C*k^{-\gamma}"/>.
 
  </br>

  

<div align="center">
<figure>
<img src="./images/fitted_curve_degree_distribution.png" height="80%" width="80%" />
<figcaption> <i>Figure 2 - Curve fitted plotted in logarithmic scalee</i> </figcaption>
</figure>
</div>
  
   
  
 Hence the <i> figure 1 </i> represent the degree distribution in a scattershot along with with the curve that represents the trend of the distribution. The curve has been computed fitting the power law function, estimating the parameter <i> C </i> and  <img src="https://latex.codecogs.com/svg.image?\inline&space;\gamma"/>. This latest curve allows to prove that the degree distribution is effectively a power law, in fact showing the curve in logarithmic scale is possible to observe that the green line is a straight one, and this is a characteristic of a degree distribution that follows a power law <i> ( figure 2 ) </i>.
 
 
 What can be further observed in the figure 2, is that our network doesn't have a degree distribution that follows a pure power law. In fact real networks rarely display a degree distribution following a pure power law, instead real systems display a shape similar to what is show in the figure 2 that share some common features:
 - **Low-degree saturation** that is shown in the initial flatten <img src="https://latex.codecogs.com/svg.image?\inline&space;P_k&space;"/> region. This happen when the network have  fewer small degree nodes than expected for a pure power law.
 - **High-degree cutoff** appears as a rapid drop in <img src="https://latex.codecogs.com/svg.image?\inline&space;P_k&space;"/> : which means that the network has fewer high-degree nodes than expected in a pure power law, and also limiting the size of the hubs. This happens when there is a limitation in the number of links a node can have. Since our system is taken from a social network, is cutoff may be a due to the fact that one person can hardly maintain a deep and meaningful relation with a lot of people.

 The degree distribution follows a power law distribution but it's not a <i>scale free</i> network, as can be observed in the plot above there are a few hubs (already described as **High-degree cutoff**) and this suggests that the second moment of the degree distribution doesn't diverge. 
 We tried to simulate the behavior of the average path length as the network grows: starting from a random set of nodes, nodes and edges are added step by step so that the network remains connected.
 The following image shows the tendency of the distance, since the first nodes are randomly selected the distance doesn't follow one of the highlighted curves but then after some steps it converges to the <img src="https://latex.codecogs.com/svg.image?\inline&space;\frac{\ln{N}}{\ln{\ln{N}}}&space;"/> one. 
 

<div align="center">
<figure>
<img src="./images/grow_network.png" height="80%" width="80%" />
<figcaption> <i>Figure 3 - average shortest path as the number of nodes increases</i> </figcaption>
</figure>
</div>

</br></br>
 
This result suggests that the <img src="https://latex.codecogs.com/svg.image?\inline&space;\gamma"/> might be equal to 3, which is the critical point between the *Ultra-small world* and the *Small world* regimes where the hubs are still enough to shrinks the distances compared to a random network of similar size.
However we cannot be sure about that because of the limited dimension of the dataset.
  </br></br>

### 2.2. Which are the most important nodes, with respect to a given centrality measure?

We decide to measure the "importance" of the nodes considering the betweenness, the closeness centrality and the degree.


|Betweenness|Closeness|Degree|
|--|--|--|
|<table> <tr><th>Node</th><th>Value</th></tr><tr><td>**107**</td><td>0.480</td></tr> <tr><td>**1684**</td><td>0.337</td></tr> <tr><td>3437</td><td>0.236</td></tr> <tr><td>1912</td><td>0.229</td></tr> <tr><td>1085</td><td>0.149</td></tr> <tr><td>0</td><td>0.146</td></tr> <tr><td>698</td><td>0.115</td></tr><tr><td>567</td><td>0.096</td></tr> <tr><td>58</td><td>0.084</td></tr> <tr><td>428</td><td>0.064</td></tr> </table>| <table> <tr><th>Node</th><th>Value</th></tr><tr><td>**107**</td><td>0.459</td></tr>  <tr><td>58</td><td>0.397</td></tr> <tr><td>428</td><td>0.394</td></tr> <tr><td>563</td><td>0.393</td></tr> <tr><td>**1684**</td><td>0.393</td></tr> <tr><td>171</td><td>0.370</td></tr> <tr><td>348</td><td>0.369</td></tr><tr><td>483</td><td>0.369</td></tr> <tr><td>414</td><td>0.369</td></tr> <tr><td>376</td><td>0.366</td></tr></table>| <table> <tr><th>Node</th><th>Value</th></tr><tr><td>**107**</td><td>1045</td></tr>  <tr><td>**1684**</td><td>782</td></tr> <tr><td>1912</td><td>792</td></tr> <tr><td>3437</td><td>547</td></tr> <tr><td>0</td><td>347</td></tr> <tr><td>2543</td><td>294</td></tr> <tr><td>2347</td><td>291</td></tr><tr><td>1888</td><td>254</td></tr> <tr><td>1800</td><td>245</td></tr> <tr><td>1663</td><td>235</td></tr></table>

The table above shows the top 10 nodes with maximum betweenness and the top 10 nodes with maximum closeness together with the nodes and their degree: the nodes present in all the ranking are highlighted.

The betweenness measures how many short paths pass to a certain node, instead the closeness measures the mean distance from a vertex to the other vertices and therefore the nodes with high closeness can have an easy access to information of influence on other nodes.

As can be seen from the table the node *107* it has the highest betweenness and the higher closeness, so we can say that such node is very important in the network and it is in the main cluster.

The closeness measures don't vary too much from one node to the other, and this can be due to the logarithmic growth of shortest paths.
By contrast the betweenness measures in the ranking decreases very fast, so there are few nodes which lead the communication between the clusters of the network. In fact it can be seen from the graph above that few nodes connect the pheriperical clusters to the "center" of the network.
</br>
### 2.3. Are the paths short with respect to the size of the network?
  </br>
  The <i> average shortest path </i> is the average of the shortest paths between all the pairs nodes, the average on this network is about 3.69. So, is possible to say that in this network there is a <b> small-world effect </b> because the average shortest path is surprisingly short comparing it with the total number of nodes of the network. Also considering the diameter equal to 8 which means that the longest path is made up of 8 nodes.

### 2.4. Is the network dense?
  </br>
  The <b> density </b> of a network is the defined by the following formula:
  </br></br>
  <center> <img src="https://latex.codecogs.com/svg.image?\inline&space;\rho&space;=&space;\frac{L}{\frac{1}{2}N(N-1)"/> </center> 
  
  </br>,in which L is the total number of links and N is the total number of nodes, it is the number of edges in the network over maximum number of possible edges in the network. On our network the value is 0.01, this means that the network is particularly <b> sparse</b>. </br>
### 2.5. Is the network assortative?

  In a network can be measured the assortative mixing according to the degree distribution and:
  - In an **assortative network** high-degree nodes tend to stick together and the structure of the network is characterized by a *core* of high-degree nodes. Hence hubs tend to link to each other and avoid linking to small-degree nodes meanwhile small-degree nodes tend to connect to other small-degree nodes avoiding hubs.
  - In a **disassortative network** hubs avoid linking each other, and tends to link to small-degree nodes. The network result in a hub-and-spoke topology.
 
 The pearson correlation coefficient of our network is 0.06, which means that the network is non-assortative and there is no a particular correlation between the degrees.
 It can be understood looking at the image of the network: the network is made up of clusters where some of them seems to be a hub-and-spoke topology and the others seems to have a *core* of high-degree nodes surrounded by a sparser periphery. So there isn't a dominant mixing.
  </br></br>
### 2.6. Average clustering

The <i> average clustering </i> is the average of all the <i> local clustering coefficients</i>, defined as
 
 <center> <img src="https://latex.codecogs.com/svg.image?\inline&space;C_i&space;=&space;\frac{L_i}{k_i(k_i-1)"/> </center>
 
 , in which <img src="https://latex.codecogs.com/svg.image?\inline&space;L_i"/> is the number of links between the <img src="https://latex.codecogs.com/svg.image?\inline&space;k_i"/> neighbors. It captures the density of links in i’s immediate neighborhood, and it is in the range [0,1]. In this case the mean value of the network is 0.605, it means that on average a node has his 60% of neighbors connected to each other so *structural holes* doesn't seem to be a problem in such network.
 
 On the other hand the global clustering is 0.51 and this could be due to the different local topologies in the networks, in particular there are components that seems to be densely connected and others components in a hub-and-spoke topology.
