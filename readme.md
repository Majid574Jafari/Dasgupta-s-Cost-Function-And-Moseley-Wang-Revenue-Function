# Hierarchical Clustering Evaluation: Cost and Revenue Functions

In hierarchical clustering, evaluating the quality of a clustering tree is crucial for ensuring that similar data points are grouped together while dissimilar ones are separated effectively. Two complementary measures to assess the quality of such clustering structures are **Dasgupta's cost function** and the **Moseley-Wang revenue function**. Both metrics leverage pairwise similarities between data points and the structure of the clustering tree, but they capture different aspects of clustering quality.

## Dasgupta's Cost Function

Dasgupta's cost function provides a quantitative measure of how well a hierarchical clustering captures the inherent similarity between data points. Consider an undirected graph $G = (V, E)$, where $V$ represents the data points and $E$ contains edges weighted by the similarity $w_{ij}$ between points $i$ and $j$. The cost associated with a clustering tree $T$ (whose leaves correspond to the original data points) is defined as:

![Dasgupta's Cost Function](https://latex.codecogs.com/svg.image?\text{Cost}_{\text{Dasgupta}}(T)=\sum_{i<j}w_{ij}\cdot|T_{ij}|)

Here, $|T_{ij}|$ denotes the number of leaves in the subtree rooted at the lowest common ancestor of $i$ and $j$ in $T$.

## Moseley-Wang Revenue Function

Complementing the cost function, the Moseley-Wang revenue function offers an alternative perspective by rewarding clusterings that efficiently separate dissimilar points. It is given by:

![Moseley-Wang Revenue Function](https://latex.codecogs.com/svg.image?\text{Revenue}_{\text{Moseley-Wang}}(T)=\sum_{i<j}w_{ij}\cdot(n-|T_{ij}|))

In this equation, $n$ denotes the total number of data points, and $|T_{ij}|$ is defined as above.

## A Unified Perspective

By considering both metrics together, one gains a comprehensive understanding of clustering quality:

- **Dasgupta's Cost Function** focuses on **minimizing the cost** by ensuring that similar points are grouped together as early as possible. A lower cost indicates that the clustering effectively captures data similarities.
- **Moseley-Wang Revenue Function** focuses on **maximizing the revenue** by rewarding clusterings that separate dissimilar points early in the hierarchy. A higher revenue signifies that the clustering structure is effective at isolating different groups.

Together, these functions provide complementary insights into the performance of a hierarchical clustering method. They help balance the trade-off between creating tight clusters of similar points and ensuring that distinct clusters are well separated.

In this project, our goal is to implement both the cost and revenue functions in Python, enabling a thorough evaluation of hierarchical clustering results.

## References

- **Dasgupta's Cost Function:**  
  Sanjoy Dasgupta. "[A Cost Function for Similarity-Based Hierarchical Clustering](https://arxiv.org/abs/1510.05043)" (October 20, 2015).

- **Moseley-Wang Revenue Function:**  
  Benjamin Moseley and Y. Wang. "[Hierarchical Clustering with Revenue Maximization](https://arxiv.org/abs/1706.04722)" (2017).
