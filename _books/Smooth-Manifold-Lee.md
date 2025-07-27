---
title: "Book Review : Introduction to Smooth Manifold"
collection: books
date: 2025-07-27
permalink: /books/SM
use_math: true
tags:
- Smooth Manifold
- Book Review
- Topology
- Geometry
---


This post illustrates important points in my view of the John H.Lee's Introduction to Smooth Manifold.

# Chapter 1. Smooth Manifold

__"Smooth Manifold"__ is __"Topological manifold"__ with some __"Smoothness"__. "Topological manifold" satisfies : Hausdorff, Second Countable, Locally Euclidean (which is homeomorphism)

Major properties of Topological Manifolds are :
- Have countable basis of precompact balls
- Countable components
- Countable fundamental group $\pi_1 (M)$

"Smoothness" structure is given by transition of two coordinate charts. Since we only know "smoothness" on "Euclidean spaces", we define smoothness by smoothness of transition of coordinate charts. Manifold with "Smooth structure" is topological manifold given with maximal smooth atlas.

One useful thing is that every smooth atlas is contained in unique maximal smooth atlas. Thus, if we want to build some __'strange'__ smooth structure, we should figure some atlas! and argue that this atlas expands to smooth structure.

# Chapter 2. Smooth Maps

__"Diffeomorphism"__ is $F:M \rightarrow N$ that is bijective, smooth and satisfying $F^{-1}$ smooth.

__"Lie group"__ is a smooth manifold $G$ that has group structure, satisfying $m : G \times G \rightarrow G$, $i : G\rightarrow G$ are smooth. One must not confuse with the definition of __"Lie Algebra"__.

__"Smooth Covering Map"__ is $\pi : \tilde{M} \rightarrow M$ that is smooth, surjective and similar to topological covering map, some neighborhood's inverse image is component-wisely "diffeomorphism".

If $M$ is smooth manifold and there exists topological covering map, then we can give smooth structure to $\tilde{M}$ to make $\pi$ smooth covering map. This type of __"Assigning Smooth Structure to satisfy smoothness of some map"__ argument is Very Very important.

For Lie group $G$, there exists a Universal smooth covering map $\pi : \tilde{G} \rightarrow G$ (Theorem 2.13)

__"Proper Map"__ is the map that satisfies : Any preimage of compact set is compact. It is useful that __proper continuous map is closed__ and closed continuous map with (1) injectiveness, (2) surjectiveness, (3) bijectiveness satisfies (1) topological embedding, (2) quotient map, (3) homeomorphism respectively.

__Partition of Unity__ : Since every topological manifolds are paracompact, any smooth manifold with arbitrary open cover gains smooth partition of unity subordinate to the open cover.

# Chapter 3 : Tangent Vectors

We defined smooth manifold or just topological manifold as some "patches" of Euclidean spaces. This means the definition of manifold is independent to its embedding on larger Euclidean space. This is the bottleneck defining tangent vector : since our intuition considers some embedded manifolds.

__Tangent Vector is defined as the Derivation__. For $C^{\infty}(M)$ a smooth real valued function on $M$, tangent vectors are __Derivations__. $X(fg) = f(a) X(g) + g(a) X(f)$

__Pushforward__ is defined by $F_* (X) (f) = X(f \circ F)$. Notice that pushforward in terms of derivation.

__Representation of Tangent vector in coordinate system__ is interesting since coordinate system is local, but tangent vectors are defined on global smooth functions.

Idea is to pushforward by chart map. $(U, \varphi)$ be the chart then $\varphi_* : T_p M \rightarrow T_{\varphi(p)} \mathbb{R}^n$ is an isomorphism. Since Euclidean spaces, $\frac{\partial}{\partial x^i}\big\vert_{p}$ are basis, its pushforward becomes basis.

In this coordinate, $F:M \rightarrow N$ pushforward $F_*$ is represented by jacobian matrix of $\hat{F} = \psi \circ F \circ \varphi^{-1}$.

__Calculation by Curve__ : If $\gamma$ curve satisfies $\gamma (0) = p$, $\gamma' (0) = X$ then $F_* (X) = (F \circ \gamma)' (0)$.

# Chapter 4 : Vector Fields 

__Tangent Bundle__. Tangent bundle is originally set $TM = \coprod_{p \in M} T_p M$. However, this set can be given topology and smooth structure so that $TM$ is smooth manifold and $\pi : TM \rightarrow M$ is smooth map. Its coordinate representation is useful that for $(U, (x^1, \cdots , x^n))$ chat for $M$, $TM$ coordinate is represented with $(x^1(p), \cdots , x^n(p), v^1, \cdots, v^n)$.

__Smooth Vector Field__ is __rough vector field__ endowed with smoothness. Rough vector field is just a section of $\pi : TM \rightarrow M$. "Smoothness" is smoothness of the section as map of $M$ to $TM$.
- If $Y_p = Y^i (p) \frac{\partial}{\partial x^i} \big\vert_p$, then $Y$ is smooth iff $Y^i$ are smooth.
- $Y$ is smooth iff $\forall f \in C^{\infty} (U)$, $Yf$ is smooth.

Smooth Vector Field can be used in two different ways.
- __Module over ring__ $C^{\infty} (M)$ : $(f \cdot Y)_p = f(p) Y_p$ which is multiplying tangent vectors with scalar function values.
- __Derivation__ and thus mapping $Y : C^{\infty} (M) \rightarrow C^{\infty}(M)$.

__Pushforward of Vector Field__ : $F: M \rightarrow N$ generally does not induce pushforward of vector field since if $F$ is not surjective or not injective, well-definedness might fail. One sufficient condition is diffeomorphism. __Pushforward of Vector Field, to be well-defined needs diffeomorphim__.

## Lie Brackets