---
title: "Book Review : Introduction to Smooth Manifold Ch 1~6"
collection: books
date: 2025-07-27
permalink: /books/SM1
use_math: true
tags:
- Smooth Manifold
- Book Review
- Topology
- Geometry
---


This post illustrates important points (in my view) of the John H.Lee's Introduction to Smooth Manifold Chapter 1 to 6. Chapter 1 to 6 considers basic definition of manifolds, smoothness, vector field and covector field.

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

Lie bracket is operator from two vector fields to vector field. $[V,W] = VW - WV$ become 'derivation'.

## Lie Algebra

For Lie group $G$, $L_g (h) = gh$ and $R_g(h) = hg$ are diffeomorphism. (As a composition $G \xrightarrow{i_g} G \times G \xrightarrow{m} G$)

So, Lie group can be __systematically map any point to any other by a global diffeomorphism__.

Lie Algebra is defined in algebraic sense : Real vector space $\mathfrak{g}$ with bracket operation $[, ] : \mathfrak{g} \times \mathfrak{g} \rightarrow \mathfrak{g}$ satisfying
- $[aX+bY, Z] = a[X,Z] + b[Y,Z]$, $[Z, aX+bY] = a[Z,X] + b[Z,Y]$
- $[X,Y] = -[Y,X]$
- $[X,[Y,Z]]+[Y,[Z,X]]+[Z,[X,Y]] = 0$

For Lie group $G$, left invariant vector fields are Lie algebra $Lie(G)$. For Lie group, $Lie(G)$ is completely determined by tangent vector at $e \in G$. 

__Theorem 4.20__ $G$ be Lie group. Then the evaluation map $\epsilon : Lie(G) \rightarrow T_e (G)$ is vector space isomorphism.

Idea is using global diffeomorphism $L_g$ and $Lie(G)$ is defined by left-invariant vector fields.

Moreover, from this evaluation map we can find that __Lie group homomorphism induces Lie algebra homomorphism__.

__After several chapters, we will determine many Lie algebras of Lie groups__. First one to figure out is Lie algebra of $GL(n, \mathbb{R})$

__Proposition 4.23__ $Lie(GL(n, \mathbb{R})) \rightarrow \mathfrak{gl}(n, \mathbb{R})$ is Lie algebra isomorphism. (Here, $\mathfrak{gl}(n, \mathbb{R})$ is the matrix algebra, vector space $\mathcal{M}(n, \mathbb{R})$ with $[A,B] = AB - BA$)

# Chapter 5 : Vector Bundles

Viewing manifolds as vector bundle from the base space is powerful in some situations.

__Smooth Vector Bundle__ is $M, E$ smooth manifolds with $\pi : E \rightarrow M$ a smooth map satisfying
- $\forall p \in M$, $E_p = \pi^{-1}(p)$ is $k$ dimensional vector space.
- $\forall p \in M$, $\exists U \in M$, $\exists \Phi : \pi^{-1}(U) \rightarrow U \times \mathbb{R}^k$ is a diffeomorphism and sends each fiber $E_q$ into $\{q \} \times \mathbb{R}^k$ (Local trivialization)

One example is Tangent Bundle $TM$.

Vector Bundles admits __sections__ and __frames__. One idea of understanding vector bundle is to understand __Local trivialization and Local Frame are identical__. Local frame induces Local trivialization and vice versa. In this viewpoint, __Tangent Bundle is unique vector bundle over $M$ that all coordinate vector fields be smooth local sections__

- Lie Group is parallelizable. Thus $TG$ is trivial bundle.
- $\mathbb{S}^3$ is parallelizable. We can find $i : \mathbb{S}^3 \hookrightarrow \mathbb{R}^4$ related vector fields

$$ X_1 = -x^2 \frac{\partial}{\partial x^1} + x^1 \frac{\partial}{\partial x^2} + x^4 \frac{\partial}{\partial x^3} - x^3 \frac{\partial}{\partial x^4} $$

$$ X_2 = -x^3 \frac{\partial}{\partial x^1} - x^4 \frac{\partial}{\partial x^2} + x^1 \frac{\partial}{\partial x^3} + x^2 \frac{\partial}{\partial x^4} $$

$$ X_3 = -x^4 \frac{\partial}{\partial x^1} + x^3 \frac{\partial}{\partial x^2} - x^2 \frac{\partial}{\partial x^3} + x^1 \frac{\partial}{\partial x^4} $$

Also in the above viewpoint, __Bundle Map of the same base space is mapping of smooth sections which is linear over $C^{\infty}(M)$__.
$\pi : E \rightarrow M$, $\pi' : E' \rightarrow M$ then smooth bundle map $F : E \rightarrow E'$ over $M$ associates with $\mathcal{F} : \mathcal{E} (M) \rightarrow \mathcal{E}'(M)$ by $\mathcal{F} (\sigma) = F \circ \sigma$

Final gist to point out is __Vector Bundle Construction Lemma__. It is highly technical lemma but useful to prove whether following space is vector bundle. This requires :

- $E_p$ a real vector space for $p \in M$.
- $$\{U_{\alpha} \}_{\alpha \in A}$$ an open cover
- Local trivialization-like bijective map $\Phi_{\alpha} : \pi^{-1} (U_{\alpha}) \rightarrow U_{\alpha} \times \mathbb{R}^k$ which sends $E_p$ to $$\{p\} \times \mathbb{R}^k$$
- A smooth transition map $\tau_{\alpha \beta} : U_{\alpha} \cap U_{\beta} \rightarrow GL(k, \mathbb{R})$ that $\Phi_{\alpha} \circ \Phi_{\beta}^{-1} (p, v) = (p, \tau_{\alpha \beta} (p) v)$.

# Chapter 6 : The Cotangent Bundle

__Cotangent Bundle__ is $T^* M = \coprod_{p\in M} T_p^* M$. Standard coordinate for cotangent bundle is dual of $\frac{\partial}{\partial x^i}$, $\lambda^i$ thus $(x^i, \lambda^i)$.

Smooth covector field is just a section of Cotangent bundle. One good thing is that __Pullback of smooth covector field always exist__. $(F^* \omega) (X) = \omega(F_* (X))$. This is different from vector fields, which such a  diffeomorphism condition is needed.

One type of smooth covector field is __differential__. For $f : M \rightarrow \mathbb{R}$, $df$ is defined by $df_p (X_p) = X_p f$. Or, in curve view, $(f \circ \gamma)'(t) = df_{\gamma(t)} (\gamma' (t))$. Its pullback is easy to compute : $G^* (df) = d (f \circ G)$.

# Calculation Formula of pushforward, pullback

__It is useless to know sophisticated formulas but don't know the method calculating pushforward and pullback__. Every instances requires calculations so we need to handle computations easily.

__Pushforward__

$$ F_* \frac{\partial}{\partial x^i} \bigg\vert_p = \frac{\partial \hat{F^j}}{\partial x^i} (\hat{p}) \frac{\partial}{\partial y^j} \bigg\vert_{F(p)}$$

e.g. $F(t) = (cos(t), sin(t))$ then 

$$F_* \bigg(\frac{\partial}{\partial t}\bigg) = \frac{\partial (cos(t))}{\partial t} \frac{\partial}{\partial x} + \frac{\partial sin(t)}{\partial t} \frac{\partial}{\partial y} = -y \frac{\partial}{\partial x} + x \frac{\partial}{\partial y}$$

__Change of basis__

$$X = X^i \frac{\partial}{\partial x^i} \bigg\vert_p = \tilde{X^j} \frac{\partial}{\partial \tilde{x^j}} \bigg\vert_p$$

$$\tilde{X^j} = \frac{\partial \tilde{x^j}}{\partial x^i} (\hat{p}) X^i$$

__Lie Bracket__

$$[V,W] = (VW^j - WV^j) \frac{\partial}{\partial x^j}$$

e.g.

$$X = y \frac{\partial}{\partial z} - z \frac{\partial}{\partial y}$$

$$Y = z \frac{\partial}{\partial x} - x \frac{\partial}{\partial z}$$

$$
\begin{aligned}
[X, Y] &= (X(z) - Y(0)) \frac{\partial}{\partial x} + (X(0) - Y(-z)) \frac{\partial}{\partial y} + (X(-x) - Y(y)) \frac{\partial}{\partial z} \\
&= y \frac{\partial}{\partial x} + (-x) \frac{\partial}{\partial y} + (0-0) \frac{\partial}{\partial z} = y\frac{\partial}{\partial x} - x\frac{\partial}{\partial y}
\end{aligned}
$$

__Pullback__

$$G^* \omega = (\omega_j \circ G) d(y^j \circ G)$$

e.g. $G(x,y,z) = (x^2 y, y sin(z))$ and $\omega = u dv + v du$

$$
\begin{aligned}
G^* (\omega) &= (y sin(z)) d(x^2 y) + (x^2 y) d(y sin(z)) \\
&= (y sin(z)) (2xy dx + x^2 dy) + (x^2 y)(sin(z) dy + y cos(z) dz) \\
&= 2xy^2 sin(z) dx + 2 x^2 y sin(z) dy + x^2 y^2 cos(z) dz
\end{aligned}
$$

__Line Integral__

$$\int_{\gamma} \omega = \int_{a}^{b} \omega_{\gamma(t)} (\gamma'(t)) dt$$

e.g. $\omega = \frac{x dy - y dx}{x^2 + y^2}$ and $\gamma(t) = (cos(t), sin(t))$

$$\int_{\gamma} \omega = \int_0^{2\pi} (-sin(t)) \cdot (-sin(t)) + (cos(t)) \cdot (cos(t)) dt = 2\pi$$
