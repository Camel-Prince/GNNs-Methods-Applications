# GNNs-Methods-Applications

精读GNNs领域的一篇综述性文章。对现有的GNNs模型进行了介绍、系统性地对其应用进行了分类，并提出了四个将来的研究方向。

一、引言

GNNs的动机：

* CNNs：They have the ablity to **extract multi-scale localized spatial features** and **compose them to construct highly expressive representations**, which led to breakthroughs in almost all machine learning areas and started the new era of deep learning.【抽取多尺度的、局部化的空间特征，并把这些特征组合成为表达性极强的表示向量。】But can only operate on these Euclidean data like images and texts. These data can be viewed as instances of graph so it is natural to spread the Convolution to gerneral Graphs!
* Graph Embeddings( Learn to represent the nodes, edges or sub-graphs as low-dimensional vectors ): They based on representation learning, which aim at learning representations of the data that make it easier to extract useful information when building classifiers or other predictors. 代表为：Deep Walk, node2vec, LINE, TADW...  These Graph Embedding methods have two common problems: unshared-params and generalization-inablitiy.


GNNs研究的必要性：

* Nodes of a graph are **naturally unoreded.** If use the CNN and RNN we should traverse all the oreders of nodes. So GNNs must ignore the nodes' order. 【GNN具有节点顺序不变性， invariant for the input order or nodes】
* GNNs are **more Interpretable** than traditional NNs
* GNNs can do propagation guided by the graph structure instead of using it as part of features.


GNN的问题：【详细描述和结局的想法TBD】

* Over-smoothing. 在消息传递机制下，随着GNN的层数增多，每个节点的感受野不断扩大，各节点的聚合操作中用到相同的近邻节点越来越多，从而导致不同节点的特征向量趋于一致。
* Scaling problem.
* Dynamic graphs
* Non-structral sensory data modeling.



二、主流方法

Original GNN：


GCNs:

* Spectral Methods:
  * Spectral Net
  * ChebyNet
  * GCN

> All of these models use the original graph structure to denote relations between nodes. However, there may have implicit relations between different nodes and the Adaptive Graph Convolution Network (**AGCN**) is proposed to learn the underlying relations.

Spectral Methods' main Disadvantage

> However, in all of the spectral approaches mentioned above, the learned fifilters depend on the Laplacian eigenbasis, which depends on the graph structure, that is, a model trained on a specifific structure could not be directly applied to a graph with a different structure.


> 空间方法的挑战：Non-spectral approaches defifine convolutions directly on the graph, operating on spatially close neighbors. The major challenge of non-spectral approaches is defifining the convolution operation with differently sized neighborhoods and maintaining the local invariance of CNNs.

* Spatial Mehtod：

  * Neural FPs：
  * DCNN
  * DGCN
  * PATCHY-SAN
  * LGCN
  * MoNet
  * GraphSage
  * StructureAware Convolutional Neural Networks (SACNNs)
