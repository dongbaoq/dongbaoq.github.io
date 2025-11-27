---
title: "Introduction to Smooth Manifold Ch 11~14"
collection: study
date: 2025-08-17
permalink: /study/SM3
use_math: true
tags:
- Smooth Manifold
- Book Review
- Topology
- Geometry
---

Chapter 11 to 14 considers a basics of tensors defined on manifolds. 

# Chapter 11. Tensors

For vector spaces $V, W$, the map

$$T : V \times \cdots \times V \rightarrow \mathbb{R}$$

is called covariant $k$-tensor if it is multilinear. Then we can define the tensor product which $S \in T^k(V), T \in T^l (V)$ then

$$S \otimes T (X_1, \cdots , X_{k+l}) = S(X_1 ,\cdots, X_k) T(X_{k+1}, \cdots , X_{k+l})$$

$T^k(V)$ has basis elements $\epsilon^{i_1} \otimes \cdots \otimes \epsilon^{i_k}$ which $\epsilon^i$ are dual basis to any basis of $V$.

However, there is a more abstract definition of tensor product of vector spaces. This uses quotient space. Main result of this concept is considering tensor product to satisfy

$$a (v \otimes w) = (av) \otimes w = v \otimes (aw)$$

$$v \otimes w_1 + v \otimes w_2 = v \otimes (w_1 + w_2)$$

$$v_1 \otimes w + v_2 \otimes w = (v_1 + v_2) \otimes w$$

For f.d.v.s $V, W$ then tensor product is __universal__ that for any vector space $X$ with bilinear map $A : V \times W \rightarrow X$, there exists a unique bilinear map $\tilde{A} : V \otimes W \rightarrow X$ that commutes with $A$.

Also one thing to note is that there exists __canonical (do not depend on basis representation)__ isomorphism

$$V^* \otimes W^* \approx B(V,W)$$

$$(\omega, \eta) \longleftrightarrow \bigg((v,w) \mapsto \omega(v)\eta(w)\bigg)$$

thus $T^k(V)$ is canonically isomorphic to tensor product of $k$ copies of $V^*$, so we can define contravariant and mixed tensors by

$$T^k (V) = V^* \otimes \cdots \otimes V^*$$

$$T_k(V) = V \otimes \cdots \otimes V$$

$$T_l^k(V) = V^* \otimes \cdots \otimes V^* \otimes V \otimes \cdots \otimes V$$

## Tensor on Manifolds

Now we can define tensor bundles and its smooth sections

- covariant $k$-tensor bundle

$$T^k M = \coprod_{p \in M} T^k (T_p M)$$

$\mathscr{T}^k (M)$ be its smooth sections. In __local coordinate view__ 

$$\sigma = \sigma_{i_1 \cdots i_k} dx^{i_1} \otimes \cdots \otimes dx^{i_k}$$

- covariant $l$-tensor bundle

$$T_l M = \coprod_{p \in M} T_l (T_p M)$$

$\mathscr{T}_l (M)$ be its smooth sections. In __local coordinate view__ 

$$\sigma = \sigma^{j_1 \cdots j_l} \frac{\partial}{\partial x^{j_1}} \otimes \cdots \otimes \frac{\partial}{\partial x^{j_k}}$$

- mixed $(k,l)$-tensor bundle

$$T^k_l M = \coprod_{p \in M} T_l^k (T_p M)$$

$\mathscr{T}^k_l (M)$ be its smooth sections.

Then, we can define several operations on these tensor bundles and its sections.

- Tensor product
  
$\sigma \in \mathscr{T}^k (M)$, $\tau \in \mathscr{T}^l (M)$ then we can define $\sigma \otimes \tau$

- Pullbacks

$F : M \rightarrow N$ smooth then we can define $F^* : T^k N \rightarrow T^k M$. Since it is $C^{\infty} (M)$ __linear, $F^*$ is a bundle map__.

## Riemannian Metric

Riemannian metric is example of symmetric tensors. Symmetric tensors are covariant $k$ tensor that satisfies

$$T(X_1, \cdots , X_i ,\cdots ,X_j ,\cdots X_k) = T(X_1, \cdots , X_j, \cdots , X_i, \cdots X_k)$$. 

We denote these tensors by $\Sigma^k (V)$. Any tensor can be mapped to symmetric tensor by symmetrization.

__Riemannian Metric__ is __smooth symmetric 2-tensor field that is positive definite at each point__. So each $g_p$ determines inner product on $T_p M$. We can represent in coordinate system, 

$$g = g_{ij} dx^i \otimes dx^j = g_{ij} dx^i dx^j$$

since it is symmetric. Each $g_p$ determining inner product allows us to define norm, angle on $T_p M$. Moreover the length of curve can be defined and importantly, it is independent of parametrization:

$$L_g (\gamma) = \int_a^b |\gamma '(t)|_g dt$$

- Isometry

$F : (M, g) \rightarrow (\tilde{M}, \tilde{g})$ is an isometry if it is diffeomorphism and $F^* \tilde{g} = g$

- Flat

$\forall p \in M$, $\exists U \subset M$ that $(U, g \vert_U)$ isometric to an open subset of $(\mathbb{R}^n, \bar{g})$

Actually, $(M, g)$ to be flat, it is equivalent to following statement:

"Each point of $M$ has a smooth coordinate neighborhood in which the coordinate frame is orthonormal"

Proof is easy : $(U, g\vert_U)$ isomorphic to some $(V, \bar{g}\vert_V )$ of $V \subset \mathbb{R}^n$ open 

$\Leftrightarrow$ $\exists \varphi : U \rightarrow V$ that $\varphi(v_1), \cdots , \varphi(v_n)$ are orthonormal or this coordinate frame $\varphi$ is orthonormal.

<br /> <br />

Interesting properties of riemannian metrics are :

- There exists __Smooth orthonormal frame__ locally. (Gram-Schmidt)

- Distance function $d$ defined by $$d(p, q) = \inf_{\gamma} \{ \gamma : I \rightarrow M \vert \gamma(0) = p, \gamma(1) = q \}$$ induces the same topology with $M$.

- Like as the setting of Whiteney's embedding theorem, for $S \subset M$ a Riemannian submanifold, we can define normal bundle.

$$NS = \coprod_{p \in S} N_p S$$

We can do this by defining $\Phi : \pi_{NS}^{-1} (S \cap U) \rightarrow (S\cap U) \times \mathbb{R}^{n-m}$, $\Phi(a^i E_i \vert_x) = (x, (a^{m+1}, \cdots , a^n))$ where $E_i$ are adapted orthonormal frame. Then its transition matrix is smooth so it is a bundle.

- Tangent-Cotangent Isomorphism

$\tilde{g} : TM \rightarrow T^* M$ bundle map can be defined from the Riemannian metric.

$$\tilde{g}(X_p) (Y_p) = g_p (X_p, Y_p)$$

since $\tilde{g}$ is $C^{\infty}(M)$ linear, $\tilde{g}$ is a bundle map. Moreover clearly $\tilde{g}$ is injective so for dimensionality reason $\tilde{g}$ is bijective so bundle isomorphism.

In coordinate representation, $\tilde{g}(X) = g_{ij} X^i dy^j$ thus it is natural to notate $X_j = g_{ij} X^i$ and say __flat__ : $X \mapsto X^{\flat}$.

Similarly, for $\omega \in \mathscr{T}^* M$, $\tilde{g}^{-1} (\omega) = g^{ij} \omega_j \frac{\partial}{\partial x^i}$ which we notate __sharp__ : $\omega \mapsto \omega^{\sharp}$.

This enables us to define __"gradient"__ as in euclidean space.

$$ \mathrm{grad} f = (df)^{\sharp} $$

Or equivalently,

$$ \langle \mathrm{grad} f, X \rangle_g = Xf $$

More properties of Tangent-Cotangent Isomorphism can be checked on Riemannian Manifold book of Lee.

<br />

Also I want to note from __Problem 11.11__ that generally $TM$ and $T^* M$ are isomorphic vector bundles but this isomorphism is not __canonical__. There does not exist a bundle isomorphism $\lambda_M : TM \rightarrow T^* M$ that is __canonical__. The reason is if the following diagram commutes :

$$\begin{CD}
TM @>{F_*}>> TN\\
@VV{\lambda_M}V @VV{\lambda_N}V\\
T^* M @<{F^*}<< T^* N
\end{CD}$$

then chasing the diagram, one finds $\lambda_N (F_* (v)) (F_* (w)) = \lambda_M (v) (w)$. Fixing $v$, right hand side is linear over $w$ so general relation $\lambda_N (F_* (v)) (F_* (w_1 + w_2) - F_* (w_1) - F_* (w_2)) = 0$ holds, which cannot be true for all diffeomorphism $F$.

- Existence of Riemannian metric Argument

This is from the __Problem 11.22__. Existence proof of Riemannian metric argument can be generalized to general settings, which can be used to prove existence of orientation form, etc.

__Argument__ : For smooth vector bundle $E$ over $M$ and $V \subset E$ an open set that $V \cap E_p$ is __convex__, nonempty. Then there exists a smooth global section whose image lies in $V$.

Proof : For local trivialization $(U_{\alpha}, \Phi_{\alpha})$ there exist local section of $V$, $v_{\alpha}$. Now, for partition of unity $$\{\phi_{\alpha}\}$$ subordinate to $$\{U_{\alpha}\}$$, $\sum \phi_{\alpha} v_{\alpha}$ is it. Here, convexity enables us to ensure summation be possible.

## Notations

$\Lambda^k M$ is vector bundle of alternating $k$ tensors.

$\mathscr{A}^k (M)$ is smooth section of $\Lambda^k M$. We call them __$k$-forms__.

# Chapter 12. Differential Forms

Likewise the symmetric tensors, there exists alternating tensors. Alternating tensors are defined by if vectors permutes, the value changes sign depending on the sign of the permutation. Alternating tensors $\Lambda^k(V)$ have basis $(\epsilon^I)$ where $$I = \{i_1 < i_2 < \cdots < i_k \}$$

Alternating tensors have the __Wedge product__, in Lee's textbook wedge product is defined:

$$ \omega \wedge \eta = \frac{(k+l)!}{k! l!} Alt(\omega \otimes \eta)$$

Then for any multi-indices $I$, $J$ the formula $\epsilon^I \wedge \epsilon^J = \epsilon^{IJ}$ holds. Thus $\epsilon^I = \epsilon^{i_1} \wedge \cdots \wedge \epsilon^{i_k}$.

Alternating tensors with wedge product gives __exterior algebra__

$$\Lambda^* (V) = \bigoplus_{k=0}^{n} \Lambda^k V$$

As we did on the tensor to manifolds, we can define the vector bundle over manifold

$$ \Lambda^k M = \coprod_{p \in M} \Lambda^k (T_p M)$$

Its section is called __differential form__ and notate by $\mathscr{A}^k(M)$. Also, pullback is well defined.

## Exterior Derivatives

Unique property of differential form is that there exists additional operation called __Exterior Derivatives__. Exterior derivative is an unique linear map $d : \mathscr{A}^k (M) \rightarrow \mathscr{A}^{k+1}(M)$ that $df(X) = Xf$ for 0-form $f$, $d(\omega \wedge \eta) = d\omega \wedge \eta + (-1)^k \omega \wedge d\eta$ and $d \circ d = 0$. Following properties holds.

__Lemma 12.16__ If $G: M \rightarrow N$ is a smooth map, then $G^* : \mathscr{A}^k (N) \rightarrow \mathscr{A}^k (M)$ commutes with $d$.

$$ G^* (d\omega) = d(G^* \omega)$$

__Proposition 12.19__ For $\omega \in \mathscr{A}^k(M)$, following formula holds:

$$d\omega (X_1, \cdots , X_{k+1}) = \sum_{1\le i \le k+1}(-1)^{i-1} X_i(\omega(X_1, \cdots, \hat{X_i}, \cdots , X_{k+1})) + \sum_{1\le i < j \le k+1} (-1)^{i+j} \omega([X_i, X_j], X_1, \cdots , \hat{X_i}, \cdots , \hat{X_j}, \cdots , X_{k+1})$$

## Symplectic Forms

Symplectic tensor is a nondegenerate alternating 2-tensor on vector space. We can define symplectic complement for subspace $S \subset V$ by

$$S^{\perp} = \{X \in V : \omega(X,Y) = 0 \,\,\, \forall Y \in S \}$$

Then dimensional reason, $\mathrm{dim} S + \mathrm{dim} S^{\perp} = \mathrm{dim} V$.

We call $S \subset V$ subspace is

- symplectic if $$S \cap S^{\perp} = \{0\}$$ (or equivalently, $\omega \vert_S$ nondegenerate)
- isotropic if $S \subset S^{\perp}$ (or equivalently, $\omega\vert_S = 0$)
- coisotropic if $S \supset S^{\perp}$
- Lagrangian if $S = S^{\perp}$

One important proposition is that there exists a basis that symplectic tensor expressed in canonical form.

__Proposition 12.22__ If $\omega$ is a symplectic tensor on an $m$-dimensional vector space $V$, then $m$ is even and there exists a basis for $V$, $A_1 ,\cdots A_n, B_1 \cdots B_n$ that

$$\omega = \sum_{i=1}^n \alpha^i \wedge \beta^i$$

Using this canonical basis, we can represent subspace of symplectic manifolds as following : 

- symplectic if there exists symplectic basis $(A_i, B_i)$ for $V$ that $S = \mathrm{span}(A_1, B_1,\cdots , A_k, B_k)$
- isotropic if there exists symplectic basis $(A_i, B_i)$ for $V$ that $S = \mathrm{span}(A_1,\cdots , A_k)$
- coisotropic if there exists symplectic basis $(A_i, B_i)$ for $V$ that $S = \mathrm{span}(A_1,\cdots A_n, B_1,\cdots, B_k)$
- Lagrangian if if there exists symplectic basis $(A_i, B_i)$ for $V$ that $S = \mathrm{span}(A_1, \cdots A_n)$

Proofs are easy, think of the basis of $S$ first, then extend it to the basis of $V$ to satisfy symplectic basis conditions.

<br />

Manifold equiped with symplectic form (smooth, closed, nondegenerate 2-form) is symplectic manifold. Symplectic manifold takes advantages of enabling some __geometric argument with differential forms__.

- __Tautological 1-form__

Tautological 1-form is __canonical__ form on cotangent bundle. $$M = T^{*} Q$$ then for the projection map $$\pi : T^{*} Q \rightarrow Q$$, $$\tau \in \Lambda^1 (T^{*} Q)$$ is defined by

$$\tau_{(q,\varphi)} = \pi^{*} \varphi$$

This definition does not depend on the coordinate representation so is canonical.

__Proposition 12.24__ Tautological 1-form is smooth and $\omega = -d\tau$ is a symplectic form on $T^* Q$.

This is by computing on coordinates. If $(x^i)$ a coordinate on $Q$, then standard coordinate on $T^* Q$ is $(x^i, \xi_i)$. (Here, $\varphi = \xi_i dx^i$)

Then $\tau_{(x,\xi)} = \pi^* (\xi_i dx^i) = \xi_i dx^i$ so smooth and $\omega = \sum_i dx^i \wedge d\xi_i$ thus symplectic.

With this tautological 1 form, we can think smooth 1-form in $M$ as an embedding to $T^* M$ and interpret closedness of 1-form into geometry of embedded structure.

__Proposition 12.25__ $\sigma$ be a smooth 1-form on $M$. Then as a smooth map from $M$ to $T^* M$, $\sigma$ is a smooth embedding, and $\sigma$ is closed iff $\sigma(M)$ is a Lagrangian submanifold of $T^* M$.

The argument closedness $\Leftrightarrow$ Lagrangian submanifold comes from the observation :

$$\sigma^* \tau = \sigma^* (\xi_i dx^i) = \sigma_i dx^i = \sigma$$

so $\sigma^* \omega = -\sigma^* d\tau = -d\sigma$.

Generally, let $S$ be an embedded submanifold of $T^* Q$. Then $S$ is the image of a smooth closed 1-form on $Q$ if $S$ is Lagrangian, transverse to the fibers and intersects each fiber in exactly one point.

To see $S$ satisfying Lagrangian, transverse, intersects only one then $S$ is an image of 1-form on $Q$, since $S$ intersects fiber only once, $S$ is a image of (possibly non-continuous at all) section $\sigma$. However we know $S$ is an embedded submanifold and $T_{(p,\varphi)} S + T_{(p,\varphi)} \pi^{-1}(p)$ spans $T_p M$, so $\sigma$ is smooth 1-form and Lagrangian property ensures closedness.

- Geometric interpretation of __Symplectomorphism__ 

For symplectic manifolds $(M, \omega)$ and $(\tilde{M}, \tilde{\omega})$, 2-form $\Omega = \pi^* \omega - \tilde{\pi}^* \tilde{\omega}$ on $M\times \tilde{M}$ is symplectic form. This can be shown if $\Omega(X,Y)=0$ of all $Y$, identifying $Y = Y_1 + Y_2$, each in $T_{\pi(p)}M$ and $T_{\tilde{\pi}(p)}\tilde{M}$, $\omega(X_1, Y_1) = \tilde{\omega}(X_2, Y_2)$ holds for arbitrary $Y_1, Y_2$ which means $X_1 = 0, \, X_2 = 0$

In this analogy, $F : M \rightarrow \tilde{M}$ diffeomorphism is __symplectomorphism if and only if the graph is Lagrangian submanifold of__ $(M \times \tilde{M}, \Omega)$.

The graph $\Gamma(F)$ become Lagrangian submanifold if $\Omega \vert_{\Gamma(F)} = 0$ (since dimensional condition already satisfied). It is equivalent to

$$\Omega \vert_{\Gamma(F)} = 0 \Leftrightarrow i^* \pi^* \omega = i^* \tilde{\pi}^* \tilde{\omega} \Leftrightarrow i^* \pi^* (\omega - F^* \tilde{\omega}) = 0 \Leftrightarrow \omega = F^* \tilde{\omega}$$

- __Symplectic group__

Symplectic group is $\mathrm{Sp}(n, \mathbb{R}) \subset GL(2n, \mathbb{R})$ that makes $\omega = \sum_{i=1}^n dx^i \wedge dy^i$ invariant. $A^* \omega = \omega$.

(a) $A \in \mathrm{Sp}(n, \mathbb{R})$ iff it takes standard basis to a symplectic basis.

This is trivial by the definition of Symplectic group.

(b) $A \in \mathrm{Sp}(n, \mathbb{R})$ iff $A^T JA = J$ where

$$J = \begin{pmatrix}
0 & I_n \\
-I_n & 0
\end{pmatrix}$$

Proof is calculus. Say $A \in \mathrm{Sp}(n, \mathbb{R})$.

$$A = \begin{pmatrix}
A_1 & A_2 \\
A_3 & A_4
\end{pmatrix}$$

Then for the basis $(x^i)$ with $(y^i)$ direct calculation gives
$\sum_{j=1}^n d(\tilde{x})^j \wedge d(\tilde{y})^j$ consist of 
$$\sum_{j=1}^n (A_1)_i^j (A_3)_k^j - (A_1)^j_k (A_3)^j_i dx^i \wedge dx^k $$
and 
$$\sum_{j=1}^n (A_2)_i^j (A_4)_k^j - (A_2)^j_k (A_4)^j_i dy^i \wedge dy^k$$
and 
$$\sum_{j=1}^n (A_1)_i^j (A_4)_k^j - (A_2)_k^j (A_3)_i^j dx^i \wedge dy^k$$.

So the equations being $$\sum_{j=1}^n d(\tilde{x})^j \wedge d(\tilde{y})^j = \sum_{j=1}^n dx^j \wedge dy^j$$ is equivalent to $A_1^T A_3 = A_1 A_3^T$, $A_2^T A_4 = A_2 A_4^T$, $A_4^T A_1 - A_2^T A_3 = I_n$. This is exactly the same formula $A^TJA = J$

(c) $\mathrm{SP}(n, \mathbb{R})$ is embedded Lie subgroup of $\mathrm{GL}(2n, \mathbb{R})$ whose dimension is $2n^2 + n$

$\Phi(A) = A^T JA$ be a map from $\mathrm{GL}(2n, \mathbb{R})$ to itself, we claim $J$ is the regular value. Calculation gives $$(\Phi_*)_A (B) = B^T JA + A^T JB$$ (by the curve $\gamma(t) = A+tB$) so if $B = A$, $(\Phi_*)_A (A) = 2J \neq 0$. Thus $\mathrm{Sp}(n, \mathbb{R})$ is a regular level set, so embedded submanifold. Since $\mathrm{Sp}(n, \mathbb{R})$ is closed under multiplication, it is Lie subgroup.

Now, $$\mathrm{ker}(\Phi_*)_I = \{B \vert B^T J + JB = 0 \}$$ so dimension of $\mathrm{Sp}(n, \mathbb{R})$ is $2n^2 + n$.

(d) The Lie algebra of $\mathrm{Sp}(n, \mathbb{R})$ is by previous calculation

$$\mathfrak{sp}(n, \mathbb{R}) = \{B \in \mathfrak{gl}(2n, \mathbb{R}) \vert B^T J + JB = 0 \}$$

(e) $\mathrm{Sp}(n, \mathbb{R})$ is non compact since following matrices are not bounded.

$$\begin{pmatrix}
kI & I \\
I & \frac{2}{k} I
\end{pmatrix}$$

- __Lagrangian subspaces__

If we denote $\Lambda_n \subset G_n (\mathbb{R}^{2n})$ the set of Lagrangian subspaces, we want to explore manifold structure. Observation gives $\mathrm{Sp}(n, \mathbb{R})$ acts transitively on $\Lambda_n$, which is previous observation. Thus, by __Proposition 9.31__ we can give $\Lambda_n$ a unique smooth manifold structure that action of $\mathrm{Sp}(n, \mathbb{R})$ be smooth. Here, determining the isotropy group

$$\begin{pmatrix}
A & 0 \\
B & (A^{-1})^T 
\end{pmatrix}$$

$A \in \mathrm{GL}(n, \mathbb{R})$ and $B^T A = A^T B$. Isotropy group is closed Lie subgroup and has dimension $n^2 + \frac{1}{2} n(n+1)$ ($A$ has $n^2$ dimension and $B$ has $\frac{1}{2}n(n-1)$ constraints so $\frac{1}{2} n(n+1)$ dimension)

Thus $\mathrm{dim} \Lambda_n = \frac{1}{2} n(n+1)$

Finally $\Lambda_n$ is compact. Since $G_n(\mathbb{R}^{2n})$ is compact, we only need to show closedness.

By coordinate calculation, $V \mapsto V^{\perp}$ the map from $G_n(\mathbb{R}^{2n})$ to itself is continuous. Thus $f : V \mapsto (V, V^{\perp})$ is continuous, so its preimage of diagonal $\Delta$, $f^{-1}(\Delta) = \Lambda_n$ is closed, compact.

# Chapter 13. Orientations

Orientation of manifold is originated from the orientation of vector space. Orientation of vector space is equivalence class of ordered basis. $(E_1, \cdots, E_n)$ and $(\tilde{E}_1, \cdots , \tilde{E}_n)$ are equivalent if the determinant is positive. Also lemma gives vector space $V$ orientation is determined by some nonzero element of $\Lambda^n (V)$. $\Omega \in \Lambda^n (V)$ determines orientation by $\Omega(E_1, \cdots , E_n) > 0$

Orientation of Manifold must be given 'continuity'. Since locally manifold is euclidean space, so is vector space. If two chart $(U_{\alpha},\varphi_{\alpha})$, $(U_{\beta},\varphi_{\beta})$ overlapping area $U_{\alpha} \cap U_{\beta}$ the $\varphi_{\beta} \circ \varphi_{\alpha}^{-1}$ is positive Jacobian then we can say two charts are consistent. If this consistence can be globally defined, we say $M$ is oriented. Analogue of $n$-form determination holds for manifold : $M$ has orientation if and only if there exists nonvanishing $n$-form $\Omega$ on $M$.

As a corollary, parallelizable manifolds are orientable. Thus every __Lie groups are orientable__.

## Orientation Covering

Nonzero $n$ covectors on smooth manifold $M$ is denoted by $$\Lambda_{*}^n M$$. The action $\mathbb{R}^{+}$ on $$\Lambda_{*}^n M$$ is smooth, free, proper (Lemma 13.8) so we can define quotient space $$\hat{M} = \Lambda_{*}^n M / \mathbb{R}^{+}$$.

__Theorem 13.9__ $M$ is smooth connected manifold. $\hat{\pi} : \hat{M} \rightarrow M$ be orientation covering. Then following holds

(2) $\hat{M}$ has a canonical orientation

(4) $\hat{M}$ is connected if and only if $M$ is non-orientable.

Canonical orientation is by the map $$\hat{\pi}_{*} : T_{\hat{q}} \hat{M} \rightarrow T_q M$$. By lifting the orientation of $T_q M$ to the orientation of $T_{\hat{q}} \hat{M}$, it becomes continuous.

## Orientation of Hypersurfaces

In ths section, we want to determine orientability of hypersurface $S \subset M$. To do this, the map $i_X : \Lambda^k (V) \rightarrow \Lambda^{k-1}(V)$ is important.

$$i_X \omega(Y_1, \cdots , Y_{k-1}) = \omega(X,Y_1, \cdots , Y_{k-1})$$

We notate $i_X \omega = X \lrcorner \omega$. The __interior multiplication map plays quite important role on proving crucial equalities on differential forms__

__Lemma 13.11__ $V$ be a f.d.v.s. $X \in V$

(1) $i_X \circ i_X = 0$

(2) If $\omega$ is $k$-covector and $\eta$ is $l$-covector

$$i_X(\omega \wedge \eta) = (i_X \omega) \wedge \eta + (-1)^k \omega \wedge (i_X \eta)$$

To apply interior multiplication to smooth manifold, $X \in \mathscr{T} (M)$ and $\omega \in \mathscr{A}^k (M)$ then applying pointwise, $X \lrcorner \omega$ is $(k-1)$-form.

__Lemma 13.11 (Manifold version)__ $M$ be smooth manifold and $X \in \mathscr{T} (M)$

(1) $i_X : \mathscr{A}^k (M) \rightarrow \mathscr{A}^{k-1} (M)$ is linear over $C^{\infty}(M)$ so is bundle map $i_X : \Lambda^k M \rightarrow \Lambda^{k-1} M$

(2) $i_X \circ i_X = 0$

(3) If $\omega \in \mathscr{A}^k (M)$, $\eta \in \mathscr{A}^l (M)$ then

$$i_X(\omega \wedge \eta) = (i_X \omega) \wedge \eta + (-1)^k \omega \wedge (i_X \eta)$$

Vector space along $S$ is the map $N : S \rightarrow TM$. $N$ is traverse if $N_p$ and $T_p S$ spans $T_p M$.

__Proposition 13.12__ $M$ is oriented smooth $n$-manifold and $S$ is immersed hypersurface of $M$. $N$ is traverse vector field along $S$ then $S$ has a unique orientation where $(N \lrcorner \Omega) \vert_S$ is the orientation form.

## Orientation of Boundary

The same logic can be applied to boundary. In the boundary, we find __traverse vector field to be smooth outward-pointing vector field__

__Lemma 13.16__ $M$ is smooth manifold with boundary. Then there exists smooth outward-pointing vector field along $\partial M$.

As a corollary,

__Proposition 13.17__ $M$ be an oriented smooth manifold with boundary. Then $\partial M$ is orientable.

## The Riemannian Volume Form

In __Orientable Riemannian Manifold__ the Riemannian volume form exists. This is the smooth orientation form $\Omega \in \mathscr{A}^n (M)$ such that

$$\Omega(E_1,\cdots , E_n) = 1$$

for every oriented local orthonormal frame $(E_i)$ for $M$. In local coordinate,

$$dV_g = \sqrt{det(g_{ij})} dx^1 \wedge \cdots \wedge dx^n$$

Hypersurfaces in Riemannian manifold, the Riemannian volume form for hypersurface is determined by ($N$ is smooth unit normal vector field along $S$)

$$dV_{\tilde{g}} = (N \lrcorner dV_g) \vert_S$$

Boundary of Riemannian manifold still holds the same formula. For $N$ the outward unit normal vector field along $\partial M$

$$dV_{\tilde{g}} = (N \lrcorner dV_g ) \vert_{\partial M}$$

# Chapter 14. Integration on Manifolds

I will briefly skip over the defining process of integration. By partition of unity making integration to occur on Euclidean spaces.

One of the most beautiful theorem is __Stoke's Theorem__

__Theorem 14.9 (Stoke's Theorem)__ $M$ be a smooth, oriented $n$-dimensional manifold with boundary, $\omega$ be a compactly supported smooth $(n-1)$-form on $M$. Then

$$\int_M d\omega = \int_{\partial M} \omega$$

## Integration on Riemannian Manifolds

Integration was possible only on $n$ forms. We want to integrate $f : M \rightarrow \mathbb{R}$. But the problem is __there is no consistent transform of 0-form $f$ to $n$-form__. In __Riemannian Manifold we can define consistent transform__. $(M, g)$ be oriented Riemannian Manifold, then $f:M \rightarrow \mathbb{R}$ can be integrated by

$$\int_M f dV_g$$

## The Divergence Theorem

$$* : C^{\infty} (M) \rightarrow \mathscr{A}^n (M)$$ by $$* f = f dV_g$$. Divergence operator is $\mathrm{div}:\mathscr{T}(M) \rightarrow C^{\infty}(M)$ by

$$\mathrm{div}X = *^{-1} d(X \lrcorner dV_g)$$

One application of Stoke's Theorem is

__Theorem 14.23 (The Divergence Theorem)__ $M$ be an oriented Riemannian manifold with boundary. For any compactly supported smooth vector field $X$ on $M$,

$$\int_M (div X) dV_g = \int_{\partial M} \langle X, N \rangle_g dV_{\tilde{g}}$$

## Integration on Lie Groups

Here is 'easy' version of Haar measure existence.

__Proposition 14.25__ $G$ be a compact Lie group endowed with a left-invariant orientation. Then $G$ has a unique left-invariant orientation form $\Omega$ that 

$$\int_G \Omega = 1$$

As an analogue of __consistent transform of 0-form to $n$-form__ on Riemannaian manifold, since above __Haar volume is unique__ $f \rightarrow f dV$ __is consistent transform__.

## Densities

The density originally defined on vector space is a function

$$\mu : V \times \cdots \times V \rightarrow \mathbb{R}$$

satisfying $\mu(TX_1,\cdots , TX_n) = \vert \mathrm{det} T \vert \mu (X_1, \cdots, X_n)$

__Density is not a tensor because nonlinear__. However the space of densities $\Omega(V)$ is 1-dimensional vector space.

Adaptation to manifold is routine process.

$$\Omega M = \coprod_{p \in M} \Omega (T_p M)$$

Then there exists a smooth positive density on $M$.

The purpose of defining density is to integrate by densities. Integration of density in vector space: $\mu = f \vert dx^1 \wedge \cdots \wedge dx^n \vert$

$$\int_D \mu = \int_D f dV$$

__The Riemannian Density__ $(M,g)$ be a Riemannian manifold (with/without boundary). There is a unique smooth positive density $\mu$ on $M$ that for any local orthonormal frame $(E_i)$

$$\mu(E_1, \cdots , E_n) = 1$$

Version of divergence theorem holds for Riemannian densities.

__Theorem 14.34__ $(M,g)$ a Riemannian manifold with boundary. For any compactly supported smooth vector field $X$ on $M$, $dV_g, dV_{\tilde{g}}$ a Riemannian densities

$$\int_M (\mathrm{div} X)dV_g = \int_{\partial M} \langle X, N \rangle_g dV_{\tilde{g}}$$

