---
title: "Book Review : Topology from the Differentiable Viewpoint"
collection: books
date: 2025-03-13
permalink: /books/TopfromDiffVeiwpoint
use_math: true
tags:
- John W. Milnor
- Book Review
- Topology
---

Topology from the Differentiable Viewpoint by John W. Milnor analyzes __topological aspects driven from purly differentiable objects of smooth manifolds__.

# Proof of Sard's Theorem

One of my favorite part in this book is the proof of Sard's Theorem. It illustrates how Sard's Theorem can be proved essentially by the __'smooth'__ condition. There are three steps:

Define $C$ a set of critical points of $f:U\subset \mathbb{R}^n \rightarrow \mathbb{R}^p$ and $C_i $ the set of points whose all partial derivatives of order less or equal than $i$ vanishing.

Step 1. $f (C-C_1)$ is measure zero

Step 2. $f(C_i - C_{i+1})$ is measure zero

Step 3. $f(C_k)$ is measure zero for large $k$

Roughly speaking the idea, Step 1, 2 uses change of coordinate charts. Step 3 uses Taylor's theorem so that for large amount of differentiation, the partitioning codomain becomes much larger than possible deviation of functions. 

# Brouwer degree

Chapter 4 and 5 are devoted to the __Brouwer degree__. This concept is the first one that appears by the geometric (local) definition respects topological feature.

Degree of the map $f:M\rightarrow N$ is defined by the sum of the sign of differential of $f$ at regular value's preimage.

$$\mathrm{deg}(f) = \sum_{x \in f^{-1}(y)} \mathrm{sgn} df_x$$

But the degree is in fact, does not depend on the choice of regular value and moreover, __invariant under homotopies!__

# The Poincare Hopf Theorem

Next geometric object is __vector fields__. __Index__ defined on zeros of vector fields which demonstrates local behavior around the zero, also respects the topology of manifold. The beautiful statement is;

$$\sum \iota = \chi (M)$$
 
