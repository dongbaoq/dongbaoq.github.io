---
title: "Lie Group"
collection: books
date: 2025-11-12
permalink: /books/LieGroup
use_math: true
tags:
- Lie Group
- Lie Algebra
---

This post summarizes the course : Lie Group from SNU 2025 Fall graduate course. Rather than describing details, I want to summarize the story of Lie group theory. References are "Bump, Lie group", "Hall, Lie Groups, Lie Algebras, and Representations", "Knapp, Lie Groups Beyond an Introduction"

# Motivation

In this course, the study of Lie group and Lie algebra came from Homogeneous dynamics. The Iwasawa decomposition and KAK decomposition gives rich view of homogeneous dynamics. The prototype is perhaps $SL_2 \mathbb{Z} \backslash SL_2 \mathbb{R}$.

# Haar Measure

The existence of Haar measure, as we will accept as 'fact'. The statement is:

__Theorem (Haar, 1933)__ Every locally compact Hausdorff topological group has left Haar measure, unique up to constant. Left Haar measure is nonzero positive linear functional over $C_c(G)$, $m:C_c(G) \rightarrow \mathbb{C}$ which is invariant under left-translation $\lambda^{*} (g) m = m$

# Basics of Lie group and Lie algebra

Starting from the smooth manifold, Lie group is defined by smooth manifold with group structure. Lie algebra is defined by vector space of Left invariant vector field over Lie group with bracket operation.

Analyzing with the tool of smooth manifolds, we can analyze some Lie group and Lie algebras. One classical example is $O(n, \mathbb{R})$ and $\mathfrak{o}(n, \mathbb{R})$. We can analyze that the Lie algebra is isomorphic to skew-symmetric Matrix space with bracket operation $[A,B] = AB - BA$

Now we define 'abstract' version of Lie algebra. Lie algebra over field $\mathbb{k}$ is $\mathbb{k}$-vector space with bilinear map $\mathfrak{g} \times \mathfrak{g} \rightarrow \mathfrak{g}$ that satisfies : anti-symmetric, Jacobi Identity:
- $[T_1, T_2] = -[T_2, T_1]$
- $[T_3, [T_1, T_2]] + [T_2, [T_3, T_1]] + [T_1, [T_2, T_3]] = 0$
  
Examples are smooth vector field over smooth manifold $\mathrm{Vect}^{\infty} (M)$, Left invariant smooth vector fields $\mathrm{Vect}^{\infty}(M)^{G}$, Associative $\mathbb{k}$-algebra with $[a,b] = ab - ba$ so for example, space of endomorphisms or derivatives.

## Lie Group and Lie Algebra, some facts

- Hilbert's 5th problem, solved by Gleason, Montgomery, Zippin, Yamabe (1953) : A topological group which is also a topological manifold can be turned into a Lie group in a unique way.
- However, given topological manifold with no smooth structure exists (Kervaire, 1960) and given topological manifold, there can exist non diffeomorphic smooth structure (Milnor, 1956)
- Every Finite dimensional Lie algebra comes from Lie group
- Lie group is not uniquely determined by its Lie algebra. However, simply connected Lie group is uniquely determined by its Lie algebra.
- Closed subgroup of Lie group is Lie group (Cartan Theorem)

# Exponential Map

## Matrix Lie group and Matrix Lie algebra

Matrix Lie group and Matrix Lie algebra has powerful tool : Exponential Map.

Define $X \in \mathcal{M}_{n,n}(F)$. $F = \mathbb{R}, \mathbb{C}$.

$$\mathrm{exp}(X) = \sum_{n=0}^{\infty} \frac{1}{n!} X^n$$

The statement itself is not powerful as expected but important theorem is Baker-Campbell-Hausdorff formula.

$$\mathrm{exp}(X) \mathrm{exp}(Y) = \mathrm{exp}(X + \int_0^1 g(e^{\mathrm{ad}X} e^{\mathrm{ad}(tY)})(Y) dt)$$

We can express $\exp(X) \exp(Y)$ as one exponential. Using Baker-Campbell-Hausdorff formula Critical Theorem holds.

__Theorem__ For $G, H$ matrix Lie group, $\mathrm{Lie}G = \mathfrak{g}$, $\mathrm{Lie}H = \mathfrak{h}$. Assume $G$ simply connected, connected. For $\phi : \mathfrak{g} \rightarrow \mathfrak{h}$ given, there exists unique $\Phi : G \rightarrow H$ such that $\Phi \circ \exp = \exp \circ \phi$.

This theorem is important that we know the converse direction very well : For $\Phi : G \rightarrow H$, we can define $\phi : \mathfrak{g} \rightarrow \mathfrak{h}$ that

$$\begin{CD}
G @>{\Phi}>> H\\
@A{\exp}AA @AA{\exp}A\\
\mathfrak{g} @>>{\phi}> \mathfrak{h} 
\end{CD}$$

## Exponential Map in Lie group, Lie algebra

General exponential map is $\exp_G : \mathfrak{g} \rightarrow G$ for $\mathrm{Lie}G = \mathfrak{g}$ sending $v$ to $\varphi_v(1)$. The flow with initial tangent vector $v$. 

Surjectiveness of exponential map is matter, if $G$ compact connected or compact abelian or $G = GL_n(\mathbb{C})$ then exponential map becomes surjective. Counterexample of exponential map being non surjective even connected group is $SL_2 \mathbb{R}$.

## Adjoint Map

__Adjoint Map__ is core object to understand. I like the view from Fulton-Harris Representation Theory. Viewpoint starts from $\rho : G \rightarrow H$ homomorphism.

$$\begin{CD}
G @>{\rho}>> H\\
@V{m_g}VV @VV{m_{\rho(g)}}V\\
G @>>{\rho}> H 
\end{CD}$$

To look at the tangent space, it is convenient if base point is fixed, so consider conjugate

$$\begin{CD}
G @>{\rho}>> H\\
@V{c_g}VV @VV{c_{\rho(g)}}V\\
G @>>{\rho}> H 
\end{CD}$$

Adjoint representation of Lie group is $\mathrm{Ad} : G \rightarrow GL(\mathfrak{g})$. 

$$\begin{CD}
\mathfrak{g} @>{(d\rho)_e}>> \mathfrak{h}\\
@V{Ad(g)}VV @VV{Ad(\rho(g))}V\\
\mathfrak{g} @>>{(d\rho)_e}> \mathfrak{h} 
\end{CD}$$

Now taking differential again, we get Adjoint Representation of Lie algebra : $\mathrm{ad} : \mathfrak{g} \rightarrow \mathfrak{gl}(\mathfrak{g})$.

$$\begin{CD}
\mathfrak{g} @>{(d\rho)_e}>> \mathfrak{h}\\
@V{ad(g)}VV @VV{ad(\rho(g))}V\\
\mathfrak{g} @>>{(d\rho)_e}> \mathfrak{h} 
\end{CD}$$

which now, respects bracket operation

# Prototype: Representation of $\mathfrak{sl}_2 \mathbb{C}$ and $\mathfrak{sl}_3 \mathbb{C}$

Representation of $\mathfrak{sl}_2\mathbb{C}$ is basic of basic and Representation of $\mathfrak{sl}_3 \mathbb{C}$ will become our blueprint for analyzing general Lie algebras.

Every irreducible finite dimensional representation of $\mathfrak{sl}_2 \mathbb{C}$ is

$$V^{(n)} = V_{-n} \oplus V_{-n+2} \oplus \cdots \oplus V_{n-2} \oplus V_n$$

$$
H = \begin{pmatrix}
1 & 0 \\
0 & -1 
\end{pmatrix}, \quad
X = \begin{pmatrix}
0 & 1\\
0 & 0
\end{pmatrix}, \quad
Y = \begin{pmatrix}
0 & 0\\
1 & 0
\end{pmatrix}
$$

Acts on the representation by $H$ acts on itself, with the eigenvalue in the subindex. (So $V^{(n)}$ as direct sum is actually eigenspace decomposition. Remark : each eigenspace is 1 dimensional). $X$ acts by translating $V_{j}$ to $V_{j+2}$, $Y$ acts by translating $V_{j}$ to $V_{j-2}$.

Representation of $\mathfrak{sl}_3 \mathbb{C}$ is more complex. First define

$$\mathfrak{h} = \{X \in \mathfrak{sl}_3 \mathbb{C} : X \, \mathrm{diagonal}\}$$

We first do the __Root space decomposition__. Which is the special case of representation : $\mathfrak{g} \curvearrowright \mathfrak{g}$ by adjoint action. Then surprisingly, $\mathfrak{g}$ decompose into

$$\mathfrak{g} = \mathfrak{h} \oplus \bigg(\bigoplus_{\alpha} \mathfrak{g}_{\alpha}\bigg)$$

Is eigenspace decomposition of $\mathfrak{h}$ action, where now eigenvalue is not mattering since $\mathfrak{h}$ is two dimensional, but $\alpha \in \mathfrak{h}^{*}$. Adjoint action of $\mathfrak{h}$ acts $\mathfrak{g}_{\alpha}$ to itself, and $\mathfrak{g}_{\alpha}$ acting on $\mathfrak{g}$ is similar to $X, Y$ in $\mathfrak{sl}_2 \mathbb{C}$ which translates $\mathrm{ad}(\mathfrak{g}_{\alpha}): \mathfrak{g}_{\beta} \rightarrow \mathfrak{g}_{\alpha + \beta}$. We call $\alpha$'s __root__

Now back to the irreducible representation $\pi : \mathfrak{g} \curvearrowright V$, eigenspace decomposition of $\mathfrak{h}$ is still valid. $V = \bigoplus_{\alpha} V_{\alpha}$. Also $\pi (\mathfrak{g}_{\alpha}) : V_{\beta} \rightarrow V_{\alpha + \beta}$. Here $\alpha$ is __root__ but $\beta$ is __weight__.

Choose the highest weight vector of $V$ : kernel of $E_{1,2}, E_{1,3}, E_{2,3}$. Then we can identify all irreducible representation of $\mathfrak{sl}_3 \mathbb{C}$. See the figure below.


# Structure Theory
