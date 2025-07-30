---
title: "Book Review : Introduction to Smooth Manifold Ch 7~9"
collection: books
date: 2025-07-27
permalink: /books/SM2
use_math: true
tags:
- Smooth Manifold
- Book Review
- Topology
- Geometry
---

This post illustrates important points (in my view) of the John H.Lee's Introduction to Smooth Manifold Chapter 7 to 8. Chapter 7 to 9 consider 'embeddings'.

# Chapter 7. Submersions, Immersions, and Embeddings

For the map $F : M \rightarrow N$ the map is
- __Submersion__ if $F_*$ is surjective (So, $rank F = dim N$)
- __Immersion__ if $F_*$ is injective (So, $rank F = dim M$)
- __Smooth Embedding__ if $F$ is immersion and is a topological embedding, i.e. $F(M)$ and $M$ are homeomorphic where $F(M)$ induce with __subspace topology__

__Figure Eight__ is important example which is immersion but not smooth embedding. Figure Eight is defined by $\gamma : (-\pi /2, 3\pi /2) \rightarrow \mathbb{R}^2$, $\gamma(t) = (sin(2t), cos(t))$.

__Proposition 7.4__ $F : M \rightarrow N$ is injective immersion. If $M$ is compact or $F$ is proper map (i.e. every preimage of compact set is compact) then $F$ is topological embedding

## Rank Theorem

By the inverse function theorem, we gain powerful theorem that represents submersion, immersion and generally, constant rank maps.

__Theorem 7.13__ (__Representation of Constant Rank Map__) $F:M\rightarrow N$ is constant rank $k$ smooth map. Then for every $p \in M$, there exist smooth coordinates $(x^1 , \cdots ,x^m)$ of $M$ that $F$ has the coordinate representation

$$F(x^1, \cdots , x^k, x^{k+1}, \cdots , x^m) = (x^1, \cdots , x^k, 0, \cdots , 0)$$

Thus, from the Rank theorem, we can figure out if $F : M \rightarrow N$ is smooth constant rank map,
- If $F$ is surjective then it is a submersion
- If $F$ is injective then it is an immersion
- If $F$ is bijective, then it is a diffeomorphism

Moreover, if $\pi : M \rightarrow N$ is submersion then
- $\pi$ is an open map
- If $\pi$ is surjective then it is quotient map

__Quotient Map__ as in point set topology, can induce maps which are impossible at continuous maps.

__Proposition 7.17__ If $\pi : M \rightarrow N$ is surjective submersion (so quotient map) and $F : N \rightarrow P$ be any map. Then $F$ is smooth iff $F \circ \pi$ is smooth.



__Proposition 7.18__ If $\pi : M \rightarrow N$ is surjective submersion (so quotient map) and $F : M \rightarrow P$ be smooth map that is constant on the fibers of $\pi$ then there exist a smooth map $\tilde{F} : N \rightarrow P$ s.t. $\tilde{F} \circ \pi = F$.
