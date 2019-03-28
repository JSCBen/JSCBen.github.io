---
layout: post
title: "Tree Preserving Embedding"
date: "2019-03-28 20:38:17 +0800"
categories:
- research notes
tags:
- dimensionality reduction
published: true
---

## Motivation

1. Most dimensionality reduction methods fail to preserve clusters, no matter linear or nonlinear methods, due to the crowding problems;
2. Guided by the clusters, embeddings can avoid the crowding problem. However, good clustering is difficult to find;
3. Forced-directed methods such as SNE, t-SNE are proposed to solve the crowding problem, but it's difficult to balance the relative strength of attractive and repulsive forces;

## Contributions

Tree preserving embedding (TPE) to preserve both distances and clusters by preserving the single linkage (SL) dendrogram in the embedding, which means that both the data and the embedding have the same SL dendrogram.

Two reasons to using SL:

1. SL is the only dendrogram consistent with the topology of MST. Preserving neighborhood graphs even MST is NP-hard, therefore, pratical methods are usually approximate. However, TPE can preserve SL exactly.
2. SL represents both global and local structure due to its hierarchical nature.

Two advantages of TPE:

1. TPE requires no parameters.
2. TPE inherits the generality of MDS.

![](images/2019-03-28-tree-preserving-embedding-a4dec03b.png)
## Tree Preserving Embedding

TPE is in fact a set of constraints in MDS that preserve the SL dendrogram.

### Algorithm

Given $n \times n$ dissimilarity matrix $D$ fo a set of $n$ objects $S = {1, ..., n}$, MDS finds the embedding $X = {x_i,...,x_n}$ such that:

$$σ(X) = ∑_{x_i, x_j \in X} (d_{i,j}(X) - D_{i,j})^2$$

in which $d_{i,j}(X) = ||x_i - x_j||$.

SL dendrogram is generated from hierarchical clustering algorithm. It is a binary tree with (n-1) depth.

**Definition 1.** Objects $i,j \in S$ are ε-connected if there exists a path $α_1 = i,..., α_m = j \in S$ such that $D_{α_l,α_{l+1}} \le ϵ$ for $l = 1,...,m-1$.

**Definition 2.** Points $x_i, x_j \in X$ are ϵ-connected if there exists a path $x_{α_1} = x_i,...,x_{α_j} \in X$ such that $d_{α_l, α_{l+1}(X)} \le ϵ$ for $l = 1,...,m-1$.

![](images/2019-03-28-tree-preserving-embedding-b95fc965.png)

### Greedy Approximation

The greedy approximation do not change the inter embeddings of prior clusters, and only uses rigid transformations to merge different clusters. Therefore, TPE may not always align the clusters well. For example, if two big clusters with irregular shapes, the merge may causes overlappings.

Another drawback is the time complexity. This algorithm runs with $O(n^3)$. Therefore, this algorithm may be prohibitive for large data.
