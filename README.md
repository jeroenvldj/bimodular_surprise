<p align="center"><img width=60% src="https://github.com/jeroenvldj/bimodular_surprise/blob/master/Images/imt_logo_plus_networks.png"></p>

&nbsp;&nbsp;
![Python](https://img.shields.io/badge/python-3.5%2B-blue.svg)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)

## Detection of Bimodular Network Structures by Surprise 
This code is for the **detection of bimodular structures in networks**, such as *core-periphery* and *bipartite* ones, with the bimodular surprise measure. 
<p align="center"><img width=90% src="https://github.com/jeroenvldj/bimodular_surprise/blob/master/Images/bimodular_structures.png"></p>

## Method
Bimodular surprise provides a measure to detect significant bimodular partitions in *binary*, *directed* and *undirected* networks. It is based on the interplay of edge-densities within the clusters and between the clusters. To this end a hypergeometric distribution function is used in similar fashion to [surprise for traditional community detection](https://www.nature.com/articles/srep01060) on networks. 

### Paper - full details on the method
The details and performance of this method can be found in this open-access [paper](https://arxiv.org/abs/1810.04717). 
[![paper](https://github.com/jeroenvldj/bimodular_surprise/blob/master/Images/arxiv_article2.png)](https://arxiv.org/abs/1810.04717)

## Code
The code for the bimodular surprise calculation and the heuristic for detection is provided in a jupyter notebook (for now) running on Python 3.5. This notebook contains all explanations about the method, the functions and working examples to show how to use the code. 

## Example - Running the code
The provided `jupyter notebook` is written to be self-explanatory and *self-contained*. Once the provided functions in the notebook are loaded, running the detection algorithm on a network is as simple as:
  1. Loading a network/graph, either as the corresponding adjacency matrix in `numpy.array` format or as a `NetworkX.Graph`
```python
G_karate = nx.karate_club_graph() 
```
  2. Running the detection heuristic
```python
revealed_partition, significance = run_surprise(G=G_karate, is_directed=False)
```
  3. The revealed partition can be visualized with (node color indicates the two revealed partitions)
```python
nx.draw(G=G_karate, node_color=revealed_partition)
```
<p align="center"><img width=40% src="https://github.com/jeroenvldj/bimodular_surprise/blob/master/Images/karate.png"></p>

## Notes
Please see the jupyter notebook for more details. 
The extention of this method to weighted networks is in progress. 

MIT © Jeroen van Lidth de Jeude - [IMT School For Advanced Studies Lucca](https://www.imtlucca.it/)

"[*Detectong Core-periphery Structures by Surprise*](https://arxiv.org/abs/1810.04717)" Jeroen van Lidth de Jeude, [Tiziano Squartini](https://www.imtlucca.it/tiziano.squartini), [Guido Caldarelli](http://www.guidocaldarelli.com/), 12 October 2018
