# 1.Deepe Insights into Graph Convolutional Networks for Semi-Supervised Learning

## Abstract 

GCN nicely integrate local vertex features and graph topology in the convolutional layers.

GCN的几点基础：
- 1.GCN model is actually a special form of Laplacian smoothing,which is the key reason why GCNs work, but it also brings potential concerns of **oversmoothing** with many convolutional layers.
- 2.to overcomethelimitsoftheGCNmodelwithshallowarchitectures, we propose both co-training and self-training approaches to train GCNs.

Our approaches signiﬁcantly improve GCNs in learning with very few labels, and exempt them from requiring additional labels for validation.

## 1 Introduction 

The GCN model naturally integrates the connectivity patterns and feature attributes of graph-structured data, and outperforms many state-of-the-art methods significantly on some benchmarks.

Nevertheless, it suffers from similar problems faced b yother neural-network-basedmodels. The working mechanisms of the GCN model for semisupervised learning are not clear, and the training of GCNs still requires considerable amount of labeled data for parameter tuning and model selection, 
which defeats the purpose for semi-supervised learning. 

In this paper, we demystify the GCN model for semisupervised learning.

In particular, we show that the graph convolution of the GCN model is simply a special form of Laplacian smoothing, which mixes the features of a vertex and its nearby neighbors.
 
The smoothing operation makes the features of vertices in the same cluster similar, thus greatly easing the classiﬁcation task, which is the key reason why GCNs work so well.
 
However,it also brings potential concerns of over-smoothing. If a GCN is deep with many convolutional layers, the output features may be **oversmoothed** and vertices from different clusters may become **indistinguishable**.
 
 
 To overcome the limits and realize the full potentials of the GCN model, we propose a co-training approach and a self-training approach to train GCNs.
 
 - 1.By co-trainingaGCN with a random walk model, the latter could complement the formerin exploring global graph topology.
 - 2.By self-traininga GCN,we can exploitits feature extraction capability to overcome its localized nature.
 
 Combining both the co-training and self-training approaches can substantially improve the GCN model for semi-supervised learning with very few labels, and exempt it from requiring additional labeled data for validation.
 
 In a nutshell, the key innovations of this paper are:
 - 1.providing new insights and analysis of the GCN model for semi-supervisedlearning
 - 2.proposing solutions to improve the GCN model for semi-supervised learning
 
 ## 2 Preliminaries and Related Works 
 
 $\mathcal{G}=(\mathcal{V}, \mathcal{E})$

无向图

邻接矩阵非负 $A=\left[a_{i j}\right] \in \mathbb{R}^{n \times n}$

degree matrix $D=\operatorname{diag}\left(d_{1}, d_{2}, \ldots, d_{n}\right)$,其中$d_{i}=\sum_{j} a_{i j}$，代表顶点$i$的度。

The graph Laplacian is defined as $L :=D-A$， and the two versions of normalized graph Laplacians are deﬁned as 

$L_{\mathrm{sym}} :=D^{-\frac{1}{2}} L D^{-\frac{1}{2}}$ and $L_{\mathrm{rw}} :=D^{-1} L$ respectively.


### Graph-Based Semi-Supervised Learning 



### Graph Convolutional Networks


There are mainly two types of GCNNs: spatial GCNNs and spectral GCNNs

- Spatial GCNNs view the convolution as “patch operator” which constructs a new feature vector for each vertex using its neighborhood information.
- Spectral GCNNs deﬁne the convolution by decomposing a graph signal  $\mathbf{s} \in R^{n}$   (a scalar for each vertex) on the spectral domain and then applying a spectral ﬁlter $g_{\theta}$   (a function of eigenvalues of $L_{\mathrm{sym}}$) on the spectral components. 

## 3 Analysis 

### 3.1 Why GCNs Work






