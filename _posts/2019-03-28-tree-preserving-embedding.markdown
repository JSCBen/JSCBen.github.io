---
title: Tree Preserving Embedding
date: 2019-03-28 12:38:17 Z
published: false
categories:
- research notes
tags:
- dimensionality reduction
layout: post
---

## Motivation

1. Most dimensionality reduction methods fail to preserve clusters, no matter linear or nonlinear methods, due to the crowding problems;
2. Guided by the clusters, embeddings can avoid the crowding problem. However, good clustering is difficult to find;
3. Forced-directed methods such as SNE, t-SNE are proposed to solve the crowding problem, but it's difficult to balance the relative strength of attractive and repulsive forces;

## Contributions
