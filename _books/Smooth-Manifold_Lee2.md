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
- __Submersion__ if $F_{\*}$ is surjective (So, $rank F = dim N$)
- __Immersion__ if $F_{\*}$ is injective (So, $rank F = dim M$)
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

# Chapter 8. Submanifolds

With the knowledge of submersions, immersions we can define 'submanifolds'.

__Embedded Submanifold__ is if $\forall p \in S$, there exists chart $(U, \varphi)$ such that $U\cap S$ is $k$ slice of $U$. Then $S$ with subspace topology is topological manifold and have unique smooth strucutre on $S$ such that $S \hookrightarrow M$ is a smooth embedding. Converse is also true. Therefore, __Embedded Submanifolds are exactly the image of Smooth Embedding__.

__Immersed Submanifold__ is $S \subset M$ with $k$ manifold topology (__Do not need to be subspace topology__) with smooth structure that makes $S \hookrightarrow M$ be smooth immersion. Similar to embedded submanifolds, __Immersed Submanifolds are exactly the image of Injective Immersions__. One significant example is __Figure Eight__. However, not always given subset cannot be an immersed submanifold, the example __Cusp $x^3 = y^2$__ is it.

Interestingly, immersed submanifold can have more than one topology and smooth structure to be immersed submanifold. However, if __Topology is given then there exists only one smooth structure__. In other words, (Top1, Smooth1), (Top2, Smooth2) ... can exist but if (Top, Smooth1) and (Top, Smooth2) are two structures then Smooth1 = Smooth2. (Exercise 8.12)

## Level Set being embedded submanifolds

__Theorem 8.8__ (__Constant Rank Level Set Theorem__) If $\Phi : M \rightarrow N$ be smooth map with constant rank $k$. Then each level set of $\Phi$ is a __closed embedded submanifold__ of codimension $k$

Here, __constant rank__ condition can be weakened in some situations

__Corollary 8.9__. If $\Phi$ is a submersion then each level set is closed embedded submanifold.

__Corollary 8.10__ (__Regular Level Set Theorem__) Each regular level set ($\Phi_{\*} : T_p M \rightarrow T_{\Phi(p)}N$ is surjective for every level set) is a __closed embedded submanifold__ of codimension equal to $\mathrm{dim} N$.

Moreover, Proposition 8.12 states __Every embedded submanifold is locally, level set of some submersion__. As a consequence, we can __characterize the tangent space of an embedded submanifold__. 

__Lemma 8.15__ (__Characterization of tangent space__) If $S \subset M$ is an embedded submanifold and $\Phi : U \rightarrow N$ is any local defining map for $S$ ($U \subset M$ and $U \cap S$ become regular level set of $\Phi$) then

$$T_p S = \textrm{Ker} \Phi_{*} : T_p M \rightarrow T_{\Phi(p)} N$$

## Restricting to Submanifolds

Nice property of immersed submanifolds or embedded submanifolds are __these submanifolds enables restrict domain or codomain of smooth map__.

- If $F : M \rightarrow N$ is smooth map and $S \subset M$ is an (immersed or embedded) submanifold then $F \vert_{S} : S \rightarrow N$ is smooth.
- If $F : M \rightarrow N$ is smooth map and $F(M) \subset S$ which is immersed or embedded submanifold of $N$. If $F : M \rightarrow S$ is continuous, then $F : M \rightarrow S$ is smooth. (__Restricting codomain is more tricky__)

Also, we can restrict vector fields and covector fields
- If $S \subset M$ is an immersed submanifold, $Y$ is tangent vector field of $M$ is also tangent to $S$ then there exists unique smooth vector field $Y\vert_S$ which is $i$-related to $Y$.
- Since every pullback of covector field is well-defined, $\omega \vert_S$ exists, which is $i^{\*} \omega$.

## Lie Subgroups

Lie subgroup is very important topic. We originally know Lie group $GL(n, \mathbb{R})$ and it has $\mathfrak{gl} (n, \mathbb{R})$ as a Lie algebra.

Proposition 8.30 enables discussion of Lie group can be hung with embedded submanifold. __$G$ be a Lie group and $H \subset G$ is subgroup and embedded submanifold. Then $H$ is closed Lie subgroup of $G$__.

Thus, we can just check __(1) Subgroup condition__ and __(2) Embedded submanifold (Level set or ...)__ to figure various Lie groups.

__Identification of Lie algebra of a Lie subgroup__. Lie algebra of a Lie subgroup can be identified as : for $H \subset G$ is Lie subgroup,

$$\tilde{\mathfrak{h}} = \{ X \in \mathrm{Lie}(G) : X_e \in T_e H\}$$

is canonically isomorphic to $\mathrm{Lie}(H)$. This is because Lie algebra of Lie subgroup is totally defined by tangent vector at identity.

- $O(n)$ 

$O(n)$ is level set of $\Phi : GL(n, \mathbb{R}) \rightarrow S(n, \mathbb{R})$

$$\Phi (A) = A^T A$$

$\Phi_{\*} : T_A GL(n, \mathbb{R}) \rightarrow T_{\Phi(A)} S(n, \mathbb{R})$ can be calculated by curve $\gamma(t) = A + tB$, 

$$\Phi_{\*} B = \frac{d}{dt} \bigg\vert_{t = 0} \Phi (A + tB) = B^T A + A^T B$$

So $\Phi_{\*}$ is surjective, which means $\Phi : GL(n, \mathbb{R}) \rightarrow S(n, \mathbb{R})$ is submersion. Thus $O(n) = \Phi^{-1} (I_n)$ is embedded submanifold, and also subgroup thus Lie subgroup of $GL(n, \mathbb{R})$.

$O(n)$ is thus, $\frac{n(n-1)}{2}$ dimensional Lie group.

Moreover, $T_{I_n} O(n) = \mathrm{Ker}\Phi_{\*}$ by the characterization of tangent space of embedded submanifold, so $T_{I_n} O(n) = \{ B \in \mathfrak{gl} (n, \mathbb{R}) : B^T + B = 0 \}$.

$$\mathfrak{o}(n) = \mathrm{Lie}(O(n)) \approx \{ B \in \mathfrak{gl} (n, \mathbb{R}) : B^T + B = 0 \}$$

- $SL(n, \mathbb{R})$

$SL(n, \mathbb{R})$ is level set of $\textrm{det} : GL(n, \mathbb{R}) \rightarrow \mathbb{R}^{\times}$.

$$d (det)_A (B) = (det A) tr(A^{-1} B)$$

so $d (det)_A$ is nonzero, thus $det$ is submersion. This means $SL(n, \mathbb{R})$ is Lie subgroup of dimension $n^2 - 1$.

$T_{I_n} SL(n, \mathbb{R}) = \mathrm{Ker} (det_{\*}) = \{B \in \mathfrak{gl}(n, \mathbb{R}) : tr(B) = 0 \}$ so we can find

$$\mathfrak{sl}(n,\mathbb{R}) = \mathrm{Lie}(sl(n,\mathbb{R})) = \{B \in \mathfrak{gl}(n, \mathbb{R}) : tr(B) = 0\}$$

- $SO(n)$

$SO(n)$ is open subset of $O(n)$ thus Lie group. Also since $SO(n)$ is open in $O(n)$, Lie algebra are identical.

$$\mathfrak{so}(n) = \mathfrak{o}(n)$$

- $GL(n, \mathbb{C})$

By $\beta : GL(n, \mathbb{C}) \rightarrow GL(2n, \mathbb{R})$ that

$$
\beta
\begin{pmatrix}
a_1^1 + ib_1^1 & \cdots & a_1^n + i b_1^n \\
\vdots & \ddots & \vdots \\
a_n^1 + ib_n^1 & \cdots & a_n^n + i b_n^n
\end{pmatrix}
=
\begin{pmatrix}
a_1^1 & -b_1^1 & \cdots & a_1^n & -b_1^n \\
b_1^1 & a_1^1 & \cdots & b_1^n & a_1^n \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
a_n^1 & -b_n^1 & \cdots & a_n^n & -b_n^n \\
b_n^1 & a_n^1 & \cdots & b_n^n & a_n^n
\end{pmatrix}
$$

becomes injective Lie group homomorphism. So $GL(n, \mathbb{C})$ can be thought of embedded submanifold of $GL(2n, \mathbb{R})$.

$\beta_{\*} : \mathrm{Lie}(GL(n,\mathbb{C})) \rightarrow \mathrm{Lie}(GL(2n, \mathbb{R}))$ is Lie algebra homomorphism. Using $\beta_{\*}$, one can find the map

$$\mathrm{Lie}(GL(n, \mathbb{C})) \xrightarrow{\epsilon} T_{I_n} GL(n, \mathbb{C}) \xrightarrow{\varphi} \mathfrak{gl}(n, \mathbb{C})$$

which is originally vector space isomorphism becomes Lie algebra isomorphism (Here, we need to prove $\varphi \circ \epsilon$ preserves bracket operation).

- $\mathbb{S}^3$

Define $\mathbb{H} = \mathbb{C} \times \mathbb{C}$ and bilinear product $(a,b)(c,d) = (ac - \bar{d}b, da + b\bar{c})$ for $a,b,c,d \in \mathbb{C}$. This is __quaternion algebra__.

Its basis $(\mathbf{1}, \mathbf{i}, \mathbf{j}, \mathbf{k})$ are $\mathbf{1} = (1,0)$, $\mathbf{i} = (i, 0)$, $\mathbf{j} = (0,1)$, $\mathbf{k} = (0,i)$. It satisfies

$$\mathbf{ij} = -\mathbf{ji} = \mathbf{k}$$
$$\mathbf{jk} = -\mathbf{kj} = \mathbf{i}$$
$$\mathbf{ki} = -\mathbf{ik} = \mathbf{j}$$
$$\mathbf{i}^2 = \mathbf{j}^2 = \mathbf{k}^2 = -\mathbf{1}$$

Quaternion multiplication is associative but not commutative, and we can define norm and inner product on quaternions. $ \langle p, q\rangle = \frac{1}{2} (p^{\*}q + q^{\*}p)$ .

Then unit quaternions is Lie group. This is because first, $\mathbb{H}$ multiplication map and inverse map is smooth, by calculation formula via its basis. Unit quaternions are subgroup. Additionally, it is embedded submanifold as a view of level set $\lVert \cdot \rVert : \mathbb{H} \rightarrow \mathbb{R}$. Thus restricting domain and codomain of multiplication map and inverse map gives $m \vert_{\mathcal{S}}$ and $i \vert_{\mathcal{S}}$ are smooth. Its smooth structure is diffeomorphic to $\mathbb{S}^3$ if we identify $\mathbb{H}$ as $\mathbb{R}^4$.

In this point of view, the statement $\mathbb{S}^3$ can be parallelizable is easy to show. Since vector fields $X_1 \vert_q = q \mathbf{i}$, $X_2 \vert_q = q\mathbf{j}$, $X_3 \vert_q = q\mathbf{k}$ are non vanishing tangent vector fields, $\mathbb{S}^3$ diffeormorphic to unit quoternions is parallelizable.

Same logic can be applied to __octonions__. However after __sedenions__, parallelizable argument does not applied becaus __division algebra__ condition brokes down. ($X_i \vert_q = q e_i$ nonvanishing argument depends the fact that if $pq = 0$, $p =0$ or $q = 0$, but after sedenions, this does not hold)