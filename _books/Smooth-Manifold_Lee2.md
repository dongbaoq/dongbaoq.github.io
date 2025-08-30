---
title: "Book Review : Introduction to Smooth Manifold Ch 7~10"
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

This post illustrates important points (in my view) of the John H.Lee's Introduction to Smooth Manifold Chapter 7 to 10. Chapter 7 to 9 consider 'embeddings'. Chapter 11 gives an insight to think arbitrary manifold as embedded submanifold of Euclidean space.

# Chapter 7. Submersions, Immersions, and Embeddings

For the map $F : M \rightarrow N$ the map is
- __Submersion__ if $F_{\*}$ is surjective (So, $\mathrm{rank} F = \mathrm{dim} N$)
- __Immersion__ if $F_{\*}$ is injective (So, $\mathrm{rank} F = \mathrm{dim} M$)
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

$$\Phi_{*} B = \frac{d}{dt} \bigg\vert_{t = 0} \Phi (A + tB) = B^T A + A^T B$$

So $\Phi_{\*}$ is surjective, which means $\Phi : GL(n, \mathbb{R}) \rightarrow S(n, \mathbb{R})$ is submersion. Thus $O(n) = \Phi^{-1} (I_n)$ is embedded submanifold, and also subgroup thus Lie subgroup of $GL(n, \mathbb{R})$.

$O(n)$ is thus, $\frac{n(n-1)}{2}$ dimensional Lie group.

Moreover, $T_{I_n} O(n) = \mathrm{Ker}\Phi_{\*}$ by the characterization of tangent space of embedded submanifold, so $$T_{I_n} O(n) = \{ B \in \mathfrak{gl} (n, \mathbb{R}) : B^T + B = 0 \}$$.

$$\mathfrak{o}(n) = \mathrm{Lie}(O(n)) \approx \{ B \in \mathfrak{gl} (n, \mathbb{R}) : B^T + B = 0 \}$$

- $SL(n, \mathbb{R})$

$SL(n, \mathbb{R})$ is level set of $\textrm{det} : GL(n, \mathbb{R}) \rightarrow \mathbb{R}^{\times}$.

$$d (det)_A (B) = (det A) tr(A^{-1} B)$$

so $d (det)_A$ is nonzero, thus $det$ is submersion. This means $SL(n, \mathbb{R})$ is Lie subgroup of dimension $n^2 - 1$.

$$T_{I_n} SL(n, \mathbb{R}) = \mathrm{Ker} (det_{*}) = \{B \in \mathfrak{gl}(n, \mathbb{R}) : tr(B) = 0 \}$$ so we can find

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

# Chapter 9. Lie Group Actions

Lie group actions make us to generate a lot of useful maifolds. __Action__ means $\theta: G \times M \rightarrow M$ with several conditions and action is continuous if $\theta$ is continuous, action is smooth if $\theta$ is smooth.

For smooth acion $\theta$, each $\theta_g$ then playes diffeomorphism on $M$. 

__Theorem 9.7__ (__Equivariant Rank Theorem__) $M, N$ are smooth manifolds and $G$ a Lie group. If $F:M\rightarrow N$ is smooth and __equivariant__ (which means, $F(g \cdot p) = g \cdot F(p)$ holds) w.r.t. __transitive__ smooth action on $M$ and smooth action on $N$. Then $F$ is constant rank so each level sets are closed embedded submanifolds.

Equivariant Rank Theorem is convinient tool of checking the map being constant rank. One should check __equivariantness__ and __transitive__ action on the domain.

__Proposition 9.8__ Lie group homomorphism $F : G\rightarrow H$ is constant rank.

For the proof, define action $G$ on $H$ by $\theta_g (h) = F(g) h$.

- $U(n)$

Define $\Phi : GL(n, \mathbb{C}) \rightarrow \mathcal{M} (n, \mathbb{C})$ by $\Phi(A) = A^{\*} A$. Then $U(n) = \Phi^{-1} (I_n)$.

If we want to prove $U(n)$ is submanifold, we had to prove $I_n$ is regular value. However, with equivariant rank theorem, we can choose alternative way.

Define right action with Lie group $G = GL(n, \mathbb{C})$. This acts on $GL(n, \mathbb{C})$ by $A \cdot B = AB$ and $\mathcal{M}(n, \mathbb{C})$ by $X \cdot B = B^{\*} X B$. Then $\Phi$ is equivariant map and $G$ acts transitively on $GL(n,\mathbb{C})$. Thus $\Phi$ is equivariant map.

As our routine proof, Lie algebra of $U(n)$ can be calculated by

$$\Phi_{*} B = \frac{d}{dt} \bigg\vert_{t = 0} \Phi \circ \gamma (t) = \frac{d}{dt} \bigg\vert_{t = 0} (I+tB)^{*}(I+tB) =  B^* + B$$

So $U(n)$ is $n^2$-dimensional Lie subgroup and

$$\mathfrak{u}(n) = \{ B \in \mathcal{gl}(n, \mathbb{C}) : B^* + B = 0 \}$$

- $SL(n, \mathbb{C})$

$\mathrm{det} : GL(n, \mathbb{C}) \rightarrow \mathbb{C}^{\times}$ is Lie group homomorphism. Thus Proposition 9.8 states $SL(n, \mathbb{C})$ is an embedded Lie subgroup. It's dimension will be $(2n^2 - 2)$.

We have saw that $det_{\*} = tr$ at the identity matrix. Thus,

$$\mathfrak{sl}(n, \mathbb{C}) = \{ A \in \mathfrak{gl}(n, \mathbb{C}) : \mathrm{tr}(A) = 0 \}$$

- $SU(n)$

$SU(n)$ is embedded submanifold of $U(n)$ by restricting domain of $\mathrm{det}$ to $\mathrm{det} \vert_{U(n)} : U(n) \rightarrow \mathbb{C}^{\times}$. Then this map can restrict codomain by $\mathrm{det} \vert_{U(n)} : U(n) \rightarrow \mathbb{S}^1$. Which is Lie group homomorphism and $SU(n)$ is level set.

As a closed submanifold of $U(n)$ and $SL(n, \mathbb{C})$

$$\mathfrak{su}(n) = \mathfrak{u}(n) \cap \mathfrak{sl}(n, \mathbb{C})$$

- Further relationships of $O(n)$, $SO(n)$, $U(n)$, $SU(n)$

(1) $SO(2)$, $U(1)$, $\mathbb{S}^1$ are all isomorphic Lie groups

This is easy when we see these manifolds on algebraic view but more topological perspective exists (from the mathstackexchange answer)

$\phi : U(1) \rightarrow SO(2)$ by 

$$a+bi \longmapsto 
\begin{pmatrix}
a & -b \\
b & a
\end{pmatrix}$$

Then this map is injective and equivariant via $\mathbb{S}^1$ action. It is constant rank and since injective, this is immersion. $U(1)$ is compact so closedness of the map is gauranteed so is embedding. Since codimension is zero and $U(1)$, $SO(2)$ are connected, they are diffeomorphic. Under the map, group operation still holds so is Lie group isomorphism.

(2) $U(1) \times SU(n)$ is diffeomorphic to $U(n)$ but not isomorphic as a Lie group.

Define $U(n) \rightarrow SU(n) \times U(1)$ by

$$A \longmapsto \frac{1}{\sqrt[n]{\mathrm{det}(A)}} A \times \sqrt[n]{\mathrm{det}(A)}$$

Then it is smooth. First think this mapping on $GL(n, \mathbb{C}) \rightarrow GL(n, \mathbb{C}) \times \mathbb{C}^{\times}$. Then restricting to embedded submanifold solves it.

However, these are not isomorphic. It's because they do not have isomorphic centers, for $U(n)$, center is isomorphic to $\mathbb{S}^1$ but $U(1) \times SU(n)$ center is isomorphic to $\mathbb{S}^1 \times \mathbb{Z}_n$.

(3) $SU(2)$ is isomorphic to unit quaternions

Idea is thinking representing 'basis elements'. We can find basis

$$\bigg\{
A_1 = \begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix},
A_2 = \begin{pmatrix}
0 & 1 \\
-1 & 0
\end{pmatrix},
A_3 = \begin{pmatrix}
i & 0 \\
0 & -i
\end{pmatrix},
A_4 = \begin{pmatrix}
0 & i \\
i & 0
\end{pmatrix}
\bigg\}$$

Then one can show that with $a^2 + b^2 + c^2 + d^2 = 1$, $a,b,c,d \in \mathbb{R}$, formula $aA_1 + bA_2 + cA_3 + dA_4$ is exactly the representation of $SU(2)$.

(4) $SO(3)$ is isomorphic to $$SU(2)/\{\pm e\}$$

For unique quaternion $q$, $\rho(q)$ be the matrix representation of $v \mapsto qvq^{\*}$ with respect to $(\mathbf{i}, \mathbf{j}, \mathbf{k})$. Then this map preserves inner product so $\rho(q) \in SO(3)$ and this $\rho$ is surjective with kernel $$\{ \pm 1 \}$$.

(5) $SL(n, \mathbb{R})$ is diffeomorphic to $SO(n) \times \mathbb{R}^{n(n+1)/2 - 1}$. and $SL(n, \mathbb{C})$ is diffeomorphic to $SU(n) \times \mathbb{R}^{n^2 - 1}$.

These arguments are by the $QR$ decomposition. We can show the uniqueness of $QR$ decomposition and its process is smooth (because Gram-Schmidt process) so diffeomorphism established.

## Quotient Manifold

We will look at the quotient manifolds. This __Quotient Manifolds are very very important object on manifolds since it has a lot of applications__. Before that, we need to define __proper action__. __Proper action__ has three equivalent definitions,

- $G \times M \rightarrow M \times M$ by $(g,p) \longmapsto (g \cdot p, p)$ is proper map
- $\forall K \subset M$ compact, $$G_K = \{g \in G : (g \cdot K) \cap K \neq \phi \}$$ compact
- $$\{p_i \}$$ convergent sequence in $M$ and $$\{g_i \cdot p_i \}$$ converges. Then some subsequence of $$\{g_i \}$$ converges.

__Theorem 9.16__ (__Quotient Manifold Theorem__) Lie group $G$ acts __smoothly__, __freely__ ($g \neq e$ then does not fix any point), __properly__ on a smooth manifold $M$. Then $M/G$ the orbit space is a topological manifold and has a unique smooth structure that makes $\pi : M \rightarrow M/G$ be a smooth submersion.

Proof of Quotient Manifold Theorem is lon but instructive. The art of the proof is showing __adapted coordinate chart__. In conclusion, $M$ have an __adapted coordinate chart__ for each point, $(U, (x^1, \cdots , x^k, y^1 \cdots , y^n))$ that
- $\varphi(U) = U_1 \times U_2 \subset \mathbb{R}^k \times \mathbb{R}^n$
- $(\mathrm{Orbit}) \cap U$ is either empty or of form $$\{y^1 = c^1, \cdots , y^n = c^n \}$$.

__Properness__ and __freeness__ really matters in this proof so these two conditions are __Essential__ to make Quotient Manifold Theorem holds.

Quotient Manifold Theorem have a lot of applications.

- __Smooth covering map__

For $\pi : \tilde{M} \rightarrow M$ a smooth covering map, $\mathcal{C}_{\pi} (\tilde{M})$ a covering group is discrete Lie group and its action is smooth, free, proper.

In addition, if $$\mathcal{C}_{\pi} (\tilde{M})$$ is normal, then $M$ is diffeomorphic to $\tilde{M} / \mathcal{C}_{\pi}(\tilde{M})$ by following theorem.

__Theorem 9.19__ $\tilde{M}$ a connected smooth manifold, $\Gamma$ is a discrete group whose action is smooth, free, proper. Then $\tilde{M} / \Gamma$ has a unique smooth structure making $\pi : \tilde{M} \rightarrow \tilde{M}/\Gamma$ to be a smooth normal covering map.

- __Homogeneous Space__

If Lie group action is transitive, we call $M$ a homogeneous $G$-space. Then __Homogeneous Spaces are exactly the Quotient of Lie group by closed Lie subgroup__.

__Theorem 9.22__ If $G$ a Lie group and $H$ closed Lie subgroup, then $G/H$ has a unique smooth structure that makes $\pi : G \rightarrow G/H$ be smooth submersion. Moreover, $G/H$ is homogeneous $G$-space.

__Theorem 9.24__ $M$ be a homogeneous $G$-space. Then for any $p\in M$, $F:G/G_p \rightarrow M$, $F(gG_p) = g\cdot p$ is an equivariant diffeomorphism.

- __Making set to smooth manifold__

__Proposition 9.31__ Suppose $X$ a set and transitive action of Lie group $G$ acts on $X$. Suppose that isotropy group of $p \in X$ is a closed Lie subgroup $G$. Then $X$ has a unique smooth manifold structure making the action smooth.

E.g. __Grassmann manifold__ $G_k(\mathbb{R}^n)$

Initially, defining Grassmann manifold is by following method : 

For $P \in G_k (\mathbb{R}^n)$, write $Q = P^{\perp}$. Define the neighborhood of $P$ by the $k$ dimensional subspaces that $$U_P = \{R \in G_k(\mathbb{R}^n) : R \cap Q = \phi \}$$. Then the map $\varphi : U_P \rightarrow L(P,Q)$ by the inverse map $\psi : L(P,Q) \rightarrow U_P$, $$\psi(A) = \{x + Ax : x \in P \}$$. Then identifying $L(P,Q)$ as $k \times (n-k)$ matrix, Grassmann manifold is smooth manifold under these atlas $$\{(U_P, \varphi_P) \}$$

Another method defining smooth structure on just the 'set' of $k$ dimensional subspaces is using Proposition 9.31. Since the action $GL(n, \mathbb{R})$ acts transitively and its isotropy group is 

$$H = \bigg\{
\begin{pmatrix}
A & B \\
0 & D
\end{pmatrix}
: A \in GL(k, \mathbb{R}), D\in GL(n-k, \mathbb{R})
\bigg\}$$

We can show that two smooth structures are the same by uniqueness argument on Proposition 9.31. We can show that under the original smooth structure, group action is smooth.

Let me describe this more precisely. We need to show the following map is finally smooth.

$$\begin{CD}
\psi (A) = \{x + Ax : x \in P \} \in G_k(\mathbb{R}^n) @>{B \in GL(n, \mathbb{R})}>> B \psi(A) = \{Bx + BAx : x \in P \} \in G_k (\mathbb{R}^n) \\
@AA{\psi}A @VV{\varphi}V\\
A \in L(P,Q) @. A' \in L(P', Q')
\end{CD}$$

Here, $$\{Bx + BAx : x \in P \} = \{ Bx + A'Bx : x \in P \}$$ for some $A'$. We need coordinate of $A'$ are smooth function of $A$. 

$x' \in P$, then $Bx' + A'Bx' = Bx + BAx$ for some $x \in P$. Then $Bx + BAx - Bx' \in Q'$ so if we set $\pi_{P'} : \mathbb{R}^n \rightarrow P'$ a projection, $\pi_{P'} (Bx + BAx - Bx') = 0$ thus $(\pi_{P'} \circ (B + BA))^{-1} (x') = x$ and

$$A' (Bx') = (B + BA) \circ (\pi_{P'} \circ (B+BA))^{-1} (x') - Bx'$$

$$A' = (B+BA) \circ (\pi_{P'} \circ (B+BA))^{-1} \circ B^{-1} - Id$$

This is smooth function of both $A$ and $B$ so smoothness of action is proven.

e.g. Flag manifold $F_K(V)$

Similar to Grassmann manifolds, if $V$ is real vector space and $K = (k_1 , \cdots , k_m)$ is $ 0 < k_1 < \cdots < k_m < n$ integers, then flag manifold is built from the following set :

$$\{ S_1 \subset S_2 \subset \cdots \subset S_m \subset V : \mathrm{dim}(S_i) = k_i \}$$

and give smoothness structure by $GL(V)$ acting transitively on this set.

- __Connectivity of Lie group__

__Proposition 9.34__ Lie group $G$ acts smoothly, freely, properly on a manifold $M$. If $G$ and $M/G$ are connected, then $M$ is connected.

## Representation of Lie group, Lie algebra

A finite dimensional __representation of Lie group__ $G$ is Lie group homomorphism $\rho : G \rightarrow GL(V)$ for finite dimensional real or complex vector space $V$.

If $\rho$ is injective (__faithful__) then we can identify $G$ as Lie subgroup $\rho(G) \subset GL(V)$ or, Lie subgroup of $GL(n, \mathbb{R})$ or $GL(n, \mathbb{C})$.

A finite dimensional __representation of Lie algebra__ $\mathfrak{g}$ is Lie algebra homomorphism $\varphi : \mathfrak{g} \rightarrow \mathfrak{gl}(V)$. Thus, if there exists a representation of Lie group then there exists a representation of Lie algebra of the Lie group. Lie algebra representation is more 'good' than Lie group representation.

__Theorem__ (__Ado's Theorem__) Every finite-dimensional Lie algebra admits a faithful finite-dimensional representation.

One instance of representation method is __Adjoint Representation__. For Lie group $G$, the adjoint representation is 

$$\mathrm{Ad}(g) = (C_g)_{*} : \mathfrak{g} \rightarrow \mathfrak{g}$$

where $C_g(h) = ghg^{-1}$ is conjugation. Then $\mathrm{Ad} : G \rightarrow GL(\mathfrak{g})$ is smooth. (This is shown on Lee's textbook)

However, __Adjoint representation for Lie algebra__ is more subtle but interesting. For Lie algebra (finite-dimensional) $\mathfrak{g}$, define

$$\mathrm{ad}(X) : \mathfrak{g} \rightarrow \mathfrak{g}$$

$$\mathrm{ad}(X)Y = [X,Y]$$

So $\mathrm{ad} : \mathfrak{g} \rightarrow \mathfrak{gl} (\mathfrak{g})$. However, we need to show that this representation is Lie algebra homomorphism... Interestingly, this holds because of __Jacobi Identity__. The problem is, we don't know if

$$\mathrm{ad} ([X,Y]) = \mathrm{ad}(X) \circ \mathrm{ad}(Y) - \mathrm{ad}(Y) \circ \mathrm{ad}(X)$$

But, this equation applied to $Z \in \mathfrak{g}$ became

$$[[X,Y],Z] = [X,[Y,Z]] - [Y,[X,Z]]$$

which is just a Jacobi identity!!



# Chapter 10. Embedding and Approximation Theorems

All of this chapter is saying __Every manifold can be thought as a embedded submanifold of Euclidean space__.

This argument uses __Sard's Theorem__ which is if $F : M \rightarrow N$ is any smooth map then the set of critical values of $F$ is measure zero in $N$.

__Theorem 10.9__ (__Whitney Immersion Theorem__) Every smooth $n$-manifold admits an immersion to $\mathbb{R}^{2n}$.

This theorem uses argument that if we give a little __peturbation__ to a smooth map $F : M\rightarrow \mathbb{R}^m$ then we can get smooth immersion $\tilde{F} : M \rightarrow \mathbb{R}^m$ if $m \ge 2n$ (This argument itself is very interesting, it uses inductive argument, finding little perturbation on little open set). 

Then again inductively constructing 'injectiveness' by finding little perturbation gives the __Whitney Embedding Theorem__.

__Theorem 10.11__ (__Whitney Embedding Theorem__) Every smooth $n$-manifold admits a proper smooth embedding into $\mathbb{R}^{2n+1}$

_Strong Whitney Embedding Theorem and Strong Whitney Immersion Theorem holds for more strict dimension! (Interestingly!) If I study the proof, then I will add the proof in other post._

Second topic is __Any continuous function $F : M \rightarrow N$ can be approximated to smooth function $\tilde{F} : M \rightarrow N$__. This is called __Whitney Approximation Theorem__.

__Theorem 10.16__ (__Whitney Approximation Theorem__) $F : M \rightarrow \mathbb{R}^k$ a continuous function. Then given positive function $\delta : M \rightarrow \mathbb{R}$, there exists smooth function $\tilde{F} : M \rightarrow \mathbb{R}^k$ that is $\delta$-close to $F$. This $\tilde{F}$ could be set relative to closed subset $A \subset M$ if $F$ is smooth on $A$.

## Tubular Neighborhood

What is the advantage of the perspective : $M$ an any smooth manifold can be thought as the embedded submanifold of $\mathbb{R}^k$ ?

Here, the answer is existence of __Tubular Neighborhood__. We can make $M$ inflate slightly so we can imagine some __tube__ wrapping the manifold.

First, we define __Normal Bundle__. 

$$NM = \coprod_{x \in M} N_x M = \{ (x,v) \in T\mathbb{R}^n : x \in M, \, v \in N_x M \}$$

So, Normal bundle is in set view, the subset of tangent bundle of $\mathbb{R}^n$ which is diffeomorphic to $\mathbb{R}^{2n}$. Every element has a representation $(x,v)$.

There exists a smooth structure making $\pi_{NM} : NM \rightarrow M$ surjective submersion. It is __smooth vector bundle__ of rank $n-m$ over $M$, __embedded submanifold__ of $T \mathbb{R}^n$.

Tubular manifold is defined by neighborhood $U$ of $M$ in $\mathbb{R}^n$ which satisfies : for $E : NM \rightarrow \mathbb{R}^n$, $E(x,v) = x+v$

$$E : V \rightarrow U$$

$$V = \{ (x,v) \in NM : \lvert v \rvert < \delta(x) \}$$

is a diffeomorphism.

Not surprisingly, __Every embedded submanifold of $\mathbb{R}^n$ has a tubular neighborhood__. This is very nice. Because tubular neighborhood looks like __tube__, __similar to original manifold__ (Smooth retraction exists). Its application as follows :

__Theorem 10.21__ (__Whitney Approximation on Manifolds__) If $F : N \rightarrow M$ a continuous map, then $F$ is homotopic to smooth map $\tilde{F} : N \rightarrow M$.

Proof idea : Embed $M$ to euclidean space and construct its tubular neighborhood. Then thinking as $F$ mapping to euclidean space, small perturbation makes smooth map's image be totally contained in tubular manifold. Using retraction concludes the proof.

__Proposition 10.22__ If $F, G: M\rightarrow N$ homotopic relative to $A$ (closed subset) then they are smoothly homotopic relative to $A$.

The same idea.

__Problem 10.5__ If $M$ is smooth, compact manifold and admits a nowhere vanishing vector field, then there is a smooth map $F: M\rightarrow M$ that is homotopic to identity and has no fixed points.

Proof idea : Embed $M$ to Euclidean space. Imagine tubular manifold. Now for each point $p \in M$, move $p$ by smooth vector field in euclidean space. Now small move makes is still remain in the tubular manifold (compactness is used) and retract it.