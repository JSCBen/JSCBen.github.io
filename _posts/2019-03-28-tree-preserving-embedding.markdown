---
layout: post
title: "Tree Preserving Embedding"
date: "2019-03-28 20:38:17 +0800"
categories:
- research notes
tags:
- dimensionality reduction
published: false
---

## Motivation

1. Most dimensionality reduction methods fail to preserve clusters, no matter linear or nonlinear methods, due to the crowding problems;
2. Guided by the clusters, embeddings can avoid the crowding problem. However, good clustering is difficult to find;
3. Forced-directed methods such as SNE, t-SNE are proposed to solve the crowding problem, but it's difficult to balance the relative strength of attractive and repulsive forces;

## Contributions
