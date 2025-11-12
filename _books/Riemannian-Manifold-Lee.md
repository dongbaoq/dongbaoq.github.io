---
title: "Riemannian Manifold"
collection: books
date: 2025-09-06
permalink: /books/RM
use_math: true
tags:
- Riemannian Manifold
- Book Review
- Topology
- Differential Geometry
---

This post summarizes Lee's Riemannian Manifold.

# Chapter 2. Review of Tensors, Manifolds, and Vector Bundles

I will cover small portion of this chapter, since a lot of things are precisely explained at Smooth Manifold book.

__Lemma 2.1__ Let $V$ be a finite-dimensional vector space. There is a __natural__ isomorphism between $T_{l+1}^k (V)$ and $$\mathrm{Multi}(V^{*} \times \cdots \times V^{*} \times V \times \cdots \times V, V)$$. Here $$V^{*}$$ appears $l$ times and $V$ appears $k$ times.

For $k = 1$ and $l = 0$, we can let $\Phi : End(V) \rightarrow T_1^1 (V)$ by

$$(\Phi(A))(\omega, X) = \omega(AX)$$

This map sends endomorphism $A$ to multilinear map. Also, it is vector space isomorphism thus to show injectiveness, if $\Phi(A) = 0$ then it is trivial that $A = 0$. To show surjectiveness, with any basis $$\{e^i \}$$ and its dual $$\{E_i \}$$, for $F \in T_1^1 (V)$ we can let $A_i^j = F(E_i, e^j)$.

Similarly, we can set

$$\Phi : \mathrm{Multi}(V^{*} \times \cdots \times V^{*} \times V \times \cdots \times V, V) \rightarrow T_{l+1}^k (V)$$

$$\Phi(A) (\omega^1, \cdots, \omega^{l+1}, X_1, \cdots , X_k) = \omega^{l+1} (A(\omega^1, \cdots , \omega^l , X_1, \cdots, X_k))$$

We can define __Trace__ operator.

$$tr : T_{l+1}^{k+1} \rightarrow T_{l}^{k}(V)$$

$$(tr \, F) (\omega^1, \cdots , \omega^l , V_1, \cdots , V_k) = tr(F(\omega^1, \cdots, \omega^l, \cdot , V_1, \cdots, V_k, \cdot))$$

where right hand side trace operator is trace defined on endomorphism.

Tensor defined on manifold is defined by vector bundle over a manifold. We call this a __Tensor Bundle__. Following __Tensor Characterization Lemma__ states tensor field can be characterized by showing $C^{\infty}(M)$ linearity.

__Lemma 2.4__ A map

$$\tau : \mathscr{T}^1 (M) \times \cdots \times \mathscr{T}^1(M) \times \mathscr{T}(M) \times \cdots \times \mathscr{T}(M) \rightarrow C^{\infty}(M)$$

is induced by a $(k,l)$ tensor field if and only if it is multilinear over $C^{\infty}(M)$.

# Chapter 3. Riemannian Metrics

$g$ is Riemannian metric if it is element of $\mathscr{T}^2 (M)$ and symmetric positive definite. Simple definitions are:

- Isometry if $\varphi : (M, g) \rightarrow (\tilde{M}, \tilde{g})$ and $$\varphi^{*} \tilde{g} = g$$
- $\mathcal{J}(M)$ be isometry group of $M$.
- In local frame (not essentially coordinate chart)

$$g = g_{ij} \varphi^i \otimes \varphi^j$$

- Induced Metric. For $i : M \hookrightarrow (\tilde{M}, \tilde{g})$ then we can define riemannian metric on $M$ by $$g = i^{*} \tilde{g}$$
- Product Manifold. We can define natural Riemannian metric on $M_1 \times M_2$ where $(M_1, g_1)$, $(M_2, g_2)$ are Riemannian manifolds. Natural isomorphism $T_{(p_1, p_2)} (M_1 \times M_2) \approx T_{p_1}M_1 \oplus T_{p_2}M_2$ exists so we can define $g = g_1 \oplus g_2$
- Covering space. For $\pi : \tilde{M} \rightarrow (M, g)$ a covering map, we can define $$\tilde{g} = \pi^{*} g$$. Then for covering transform $\varphi : \tilde{M} \rightarrow \tilde{M}$, $$\varphi^{*} \tilde{g} = \varphi^{*} \pi^{*} g = \pi^{*} g = \tilde{g}$$ holds. Converse also holds that if $\pi : (\tilde{M}, \tilde{g}) \rightarrow M$ is smooth covering map that $\tilde{g}$ is invariant under all covering transformations then there exists $g$ that is $\pi$ related to $\tilde{g}$

## Raising and Lowering Indices

We define Flat and Sharp operation.

$$\flat : TM \rightarrow T^{*}M$$

$$X^{\flat} (Y) = g(X,Y)$$

In local coordinate $X_j = g_{ij} X^i$ for $X^{\flat} = X_j dx^j$.

$$\sharp : T^{*}M \rightarrow TM$$

In local coordinate $\omega^i = g^{ij} \omega_j$ where $g^{ij}$ is $ij$ component of $g^{-1}$.

## Inner product of Tensors

This is quite stunning result. __Riemann Metric naturally induces fiber metric on arbitrary dimensional tensor bundles__

__Lemma 3.1__ Let $g$ be a Riemannian metric on a manifold $M$. There is a unique fiber metric on each tensor bundle $T_l^k M$ that if $(E_1, \cdots , E_n)$ is an orthonormal basis for $T_p M$ and $(\varphi^1, \cdots , \varphi^n)$ is dual basis then $E_{j_1} \otimes \cdots \otimes E_{j_l} \otimes \varphi^{i_1} \otimes \cdots \otimes \varphi^{i_k}$ forms orthonormal basis for $T_l^k (T_p M)$

We prove it by defining inner product by

$$\langle F, G \rangle = g^{i_1 r_1} \cdots g^{i_k r_k} g_{j_1 s_1} \cdots g_{j_l s_l} F_{i_1\cdots i_k}^{j_1 \cdots j_l} G_{r_1 \cdots r_k}^{s_1 \cdots s_l}$$

And we will show this definition satisfies orthonormal property.

$$
\begin{align*}
&\langle E_{j_1}\otimes \cdots E_{j_l}\otimes \varphi^{i_1} \otimes \cdots \otimes \varphi^{i_k}, E_{\tilde{j}_1}\otimes \cdots \otimes E_{\tilde{j}_l} \otimes \varphi^{\tilde{i}_1} \otimes \cdots \otimes \varphi^{\tilde{i}_k} \rangle \\
&= E_{j_1}^{r_1} \cdots E_{j_l}^{r_l} (E^{-1})_{s_1}^{i_1} \cdots (E^{-1})_{s_k}^{i_k} E_{\tilde{j}_1}^{\tilde{r}_1} \cdots E_{\tilde{j}_l}^{\tilde{r}_l} (E^{-1})_{\tilde{s}_1}^{\tilde{i}_1} \cdots (E^{-1})_{\tilde{s}_k}^{\tilde{i}_k} g^{s_1\tilde{s}_1} \cdots g^{s_k \tilde{s}_k} g_{r_1 \tilde{r}_1} \cdots g_{r_l \tilde{r_l}}\\
&=(E_{j_1}^{r_1}E_{\tilde{j}_1}^{\tilde{r}_1} g_{r_1 \tilde{r}_1}) \cdots (E_{j_l}^{r_l} E_{\tilde{j}_l \tilde{r}_l} g_{r_l \tilde{r}_l}) ((E^{-1})_{s_1}^{i_1} (E^{-1})_{\tilde{s}_1}^{\tilde{i}_1} g^{s_1 \tilde{s}_1}) \cdots ((E^{-1})_{s_k}^{i_k} (E^{-1})_{\tilde{s}_k}^{\tilde{i}_k} g^{s_k \tilde{s}_k})\\
&= \langle E_{j_1}, E_{\tilde{j}_1} \rangle_g \cdots \langle E_{j_l}, E_{\tilde{j}_l} \rangle_g  \langle (\varphi^{i_1})^{\sharp} , (\varphi^{\tilde{i}_1})^{\sharp} \rangle_g \langle (\varphi^{i_k})^{\sharp} , (\varphi^{\tilde{i}_k})^{\sharp} \rangle_g \cdots \\
&= \delta_{j_1 \tilde{j}_1} \cdots \delta_{j_l, \tilde{j}_l} \delta_{i_1 \tilde{i}_1} \cdots \delta_{i_k \tilde{i}_k}
\end{align*}
$$

Moreover, we can know that if $\omega, \eta$ are covariant 1 tensors, then

$$\langle \omega, \eta \rangle = \langle \omega^{\sharp}, \eta^{\sharp} \rangle$$

## The Volume Form

There exists a unique $n$-form $dV$ on oriented Riemannian Manifold such that for orthonormal basis(oriented) $(E_1, \cdots, E_n)$, $dV(E_1, \cdots , E_n) = 1$

## Model Spaces of Riemannian Geometry

### Euclidean space

$V$ be an f.d.v.s with inner product then defining $g(X,Y) = \langle X, Y \rangle$ is Riemannian metric.

### Spheres

$S_R^n$ is sphere with radius $R$ in $R^{n+1}$. Equipped with the induced Riemannian metric $\overset{\circ}{g_R}$. Here are the properties

- Homogeneous: Sphere admits Lie group to act smoothly and transitively by isometries
- Isotropic: Exists a Lie group acting smoothly such that the isotropy subgrouop acts transitively on $T_p M$

Actually, the Lie group is $O(n+1)$. Identifying $T_p S_R^n$ to subspace of $T_p R^{n+1}$, $O(n+1)$ is the group taking $$(p/R, \{E_i \})$$ to $$(\tilde{p}/R, \{\partial_i \})$$

- $$S_R^n - \{p\}$$ conformally equivalent to $R^n$. 
  
Here, conformal equivalence is defined: for $(M, g)$ and $(\tilde{M}, \tilde{g})$, diffeomorphism $\varphi : M \rightarrow \tilde{M}$ exists that $$\varphi^{*} \tilde{g} = fg$$, $f \in C^{\infty} (M)$. Or, it just preserves angles.

Calculation by stereographic projection. In differential geometry, __calculation__ is important. We know the stereographic projection formula. $$\sigma : S_R^n - \{N\} \rightarrow R^n$$ is defined

$$\sigma (\xi, \tau) = \frac{R\xi}{R-\tau}$$

$$\sigma^{-1} (u) = \bigg( \frac{2R^2 u}{\vert u \vert^2 + R^2}, \frac{\vert u \vert^2 - R^2}{\vert u \vert^2 + R^2} R \bigg)$$

### Hyperbolic spaces

There exists three different models for hyperbolic space.

__Hyperboloid Model__ $$H_R^n = \{(\xi^1, \cdots , \xi^n, \tau) \vert \tau > 0, \, \tau^2 - \vert \xi \vert^2 = R^2 \}$$ with the metric $$h_R^1 = i^{*} m$$. Where $i : H_R^n \rightarrow R^{n+1}$ is inclusion, $m = (dx^1)^2 + \cdots + (dx^n)^2 - (dy)^2$

__Poincare Ball Model__ $B_R^n$ is the ball of radius $R$ in $R^n$ with the metric

$$h_R^2 = 4R^4 \frac{(du^1)^2 + \cdots + (du^n)^2}{(R^2 - \vert u \vert^2)^2}$$

__Poincare Half-Space Model__ $U_R^n$ is the upper half space in $R^n$ with the metric

$$h_R^3 = R^2 \frac{(dx^1)^2 + \cdots + (dx^{n-1})^2 + dy^2}{y^2}$$

It is quite a huge calculation to prove these models are isometric.

<br />

__Hyperbolid Model__ $\Leftarrow$ __Poincare Ball Model__

$$\pi (\xi, \tau) = \frac{R}{R+\tau} \xi$$

$$\pi^{-1}(u) = \bigg(\frac{2R^2 u}{R^2 - \vert u \vert^2}, \frac{R^2 + \vert u \vert^2}{R^2 - \vert u \vert^2} R \bigg)$$

$\pi$ is a diffeomorphism. Remaining is $$(\pi^{-1})^{*} h_R^1 = h_R^2$$.

For $V \in T_q B_R^n$, $$(\pi^{-1})^{*} h_R^1(V,V) = m(\pi_{*}^{-1} V, \pi_{*}^{-1} V)$$. Calculation gives

$$V\xi^j = \frac{2R^2 V^j}{R^2 - \vert u \vert^2} + \frac{4R^2 u^j (\sum V^i u^i)}{(R^2 - \vert u \vert^2)^2}$$

$$V\tau = \frac{4R^3 (\sum V^i u^i)}{(R^2 - \vert u \vert^2)^2}$$

$$m(\pi_{*}^{-1} V, \pi_{*}^{-1} V) = \sum_{j=1}^m (V\xi^j)^2 - (V\tau)^2 = \frac{4R^4 |V|^2}{(R^2 - \vert u \vert^2)^2} = h_R^2 (V,V)$$

<br />

__Poincare Ball Model__ $\Leftarrow$ __Poincare Half Plane Model__

$$\kappa(u, v) = \bigg(\frac{2R^2 u}{\vert u \vert^2 + (v-R)^2}, \frac{R^2 - \vert u \vert^2 - v^2}{\vert u \vert^2 + (v-R)^2} R \bigg)$$

$$\kappa^{-1} (x,y) = \bigg(\frac{2R^2 x}{\vert x \vert^2 + (y+R)^2}, \frac{\vert x \vert^2 + y^2 - R^2}{\vert x \vert^2 + (y+R)^2} R \bigg)$$

For $V \in T_p B_R^n$ we calculate $$\kappa_{*} V$$

<br />

Now, $H_R^n$ have symmetry group $O_{+}(n, 1)$ this group preserves Minkowski metric and taking $\tau > 0$ to itself. This group action gives $H_R^n$ be homogeneous and isotropic.

Let $p \in H_R^n$ and $$\{E_i \}$$ orthonormal basis, $$\{E_1 , \cdots , E_n, E_{n+1} = p/R \}$$ is a basis to $R^{n+1}$. We claim

$$m = (\varphi^1)^2 + \cdots + (\varphi^n)^2 - (\varphi^{n+1})^2$$

If we set $(x^1, \cdots , x^{n+1})$ a coordinate of $R^{n+1}$,

$$(E_1 ,\cdots, E_{n+1})^T = A (\partial_1, \cdots , \partial_{n+1})^T$$

for the matrix $A$

$$A = \begin{pmatrix}
a_1^1 & \cdots & a_1^{n+1} \\
\vdots & \ddots & \vdots \\
p^1 /R & \cdots & p^{n+1} / R
\end{pmatrix}$$

$$(\varphi^1, \cdots, \varphi^{n+1})^T = (A^{-1})^T (dx^1, \cdots , dx^{n+1})^T$$

Now, $$(\varphi^1)^2 + \cdots + (\varphi^n)^2 - (\varphi^{n+1})^2 = (dx^1, \cdots , dx^{n+1}) A^{-1} \begin{pmatrix} I & 0 \\ 0 & -1 \end{pmatrix} (A^{-1})^T (dx^1, \cdots , dx^{n+1})^T$$ and explicit calculation gives

$$A^{-1} \begin{pmatrix} I & 0 \\ 0 & -1 \end{pmatrix} (A^{-1})^T = \begin{pmatrix} I & 0 \\ 0 & -1 \end{pmatrix}$$

So $m = (\varphi^1)^2 + \cdots + (\varphi^n)^2 - (\varphi^{n+1})^2$
