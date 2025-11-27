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

$$\require{amscd}
\begin{CD}
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

Is eigenspace decomposition of $\mathfrak{h}$ action, where now eigenvalue is not mattering since $\mathfrak{h}$ is two dimensional, but $$\alpha \in \mathfrak{h}^{*}$$. 
Adjoint action of $\mathfrak{h}$ acts $\mathfrak{g}_{\alpha}$ to itself, and $\mathfrak{g}_{\alpha}$ acting on $\mathfrak{g}$ is similar to $X, Y$ in $\mathfrak{sl}_2 \mathbb{C}$ which translates $\mathrm{ad}(\mathfrak{g}_{\alpha}): \mathfrak{g}_{\beta} \rightarrow \mathfrak{g}_{\alpha + \beta}$. 
We call $\alpha$'s __root__.

Now back to the irreducible representation $\pi : \mathfrak{g} \curvearrowright V$, eigenspace decomposition of $\mathfrak{h}$ is still valid. $V = \bigoplus_{\alpha} V_{\alpha}$. Also $\pi (\mathfrak{g}_{\alpha}) : V_{\beta} \rightarrow V_{\alpha + \beta}$. Here $\alpha$ is __root__ but $\beta$ is __weight__.

Choose the highest weight vector of $V$ : kernel of $E_{1,2}, E_{1,3}, E_{2,3}$. Then we can identify all irreducible representation of $\mathfrak{sl}_3 \mathbb{C}$. See the figure below.


# Structure Theory : Introduction

Here is now a new Chapter of Lie group, Lie algebra theory. First some definitions

## Simple, Semisimple, Nilpotent

$\mathfrak{g}$ is solvable if $\mathfrak{g}^j = 0$ for some $j$.

$$\mathfrak{g}^j = [\mathfrak{g}^{j-1}, \mathfrak{g}^{j-1}]$$

$\mathfrak{g}$ is nilpotent if $\mathfrak{g}_j = 0$ for some $j$.

$$\mathfrak{g}_j = [\mathfrak{g}_{j-1}, \mathfrak{g}]$$

$\mathfrak{g}$ is simple if $\mathfrak{g}$ is non abelian and has no nontrivial ideal.

$\mathfrak{g}$ is semisimple if it is non abelian and has no nontrivial solvable ideal.

## Three Big Theorems

__(Knapp) Theorem 1.25 (Lie's Theorem)__ $\mathfrak{g}$ be solvable. For finite dimensional representation $\pi : \mathfrak{g} \rightarrow End_{\mathbb{K}} V$, if $\mathbb{K}$ is algebraically closed or more generally, eigenvalues of $\pi(X),\, X \in \mathfrak{g}$ lie in $\mathbb{K}$ then there is a simultaneous eigenvector $v \neq 0$ for all members $\pi(\mathfrak{g})$

So inductively applying Lie's Theorem, representation $\pi : \mathfrak{g} \rightarrow End_{\mathbb{K}}V$ can be seen as flag.

$$ V = V_0 \supset V_1 \supset \cdots \supset V_m = 0$$

Such that each $V_i$ are stable under $\pi(\mathfrak{g})$.

__(Knapp) Theorem 1.35 (Engel's Theorem)__ $V$ a finite dimensional vector space over $\mathbb{k}$. $\mathfrak{g}$ is a Lie algebra of nilpotent endomorphisms of $V$. Then
- $\mathfrak{g}$ is a nilpotent Lie algebra
- There exists $v \in V$ that $X(v) = 0$ for all $X \in \mathfrak{g}$
- With suitable basis of $V$, $\pi(\mathfrak{g})$ is expressed as strictly upper triangular matrix.

As a corollary, the Lie algebra whose $\mathrm{ad} X$ is nilpotent, then Lie algebra itself is nilpotent.

__(Knapp) Theorem 1.45 (Cartan's Criterion for semisimplicity)__ Lie algebra $\mathfrak{g}$ is semisimple if and only if Killing form $B$ is nondegenerate.

These three theorem will give us the starting point of analyzing the structure of Lie group and Lie algebras.

Proof technique is also important, techniques handling Killing form and Bracket operation.

For instance, by these three fundamental theorems we can see:

__(Knapp) Theorem 1.54__ Lie algebra $\mathfrak{g}$ is semisimple if and only if $\mathfrak{g} = \mathfrak{g}_1 \oplus \cdots \oplus \mathfrak{g}_m$ each $\mathfrak{g}_j$ are simple Lie algebra and an ideal.

To go more from semisimple Lie algebras, we look at reductive Lie algebra: The Lie algebra is reductive if $\forall \mathfrak{a} \subseteq \mathfrak{g}$ an ideal then $\exists \mathfrak{b} \subseteq \mathfrak{g}$ that $\mathfrak{g} = \mathfrak{a} \oplus \mathfrak{b}$. Reductive Lie algebra decomposes into

$$\mathfrak{g} = [\mathfrak{g},\mathfrak{g}] \oplus Z_{\mathfrak{g}}$$

$[\mathfrak{g},\mathfrak{g}]$ semisimple part, $Z_{\mathfrak{g}}$ abelian.

## Analytic Subgroup

Analytic group means connected Lie group. One deep result is that for $H$ an analytic subgroup of $G$ and its Lie algebra $\mathfrak{h}$, the correspondence of analytic subgroup and Lie subalgebra is one-to-one onto.

(Analytic Subgroup) <> (Lie subalgebra)

This fact will appear quite often when we analyze Lie algebra precisely, and then lift to the Lie group.

## Root Space Decomposition

We focus on complex semisimple Lie algebras. At the end, we will find out the beautiful classification of complex simple Lie algebras.

__Theorem__ Complex simple Lie algebra is isomorphic to one of the followings:

$$\mathfrak{sl}_n \mathbb{C},\, \mathfrak{so}_{n} \mathbb{C},\, \mathfrak{sp}_{2n} \mathbb{C},\, G_2, F_4, E_6, E_7, E_8$$


Motivation of root space decomposition comes from $\mathfrak{sl}_3 \mathbb{C}$ or more generally, $\mathfrak{sl}_n \mathbb{C}$. We found on $\mathfrak{sl}_3 \mathbb{C}$, adjoint representation gives decomposition of $\mathfrak{sl}_3 \mathbb{R}$ by the eigenspace of 'roots' which lie in $\mathfrak{h}^{*}$. This is indeed true for general semisimple Lie algebra.

__(Knapp) Proposition 2.5__ If $\mathfrak{g}$ is any finite-dimensional Lie algebra over $\mathbb{C}$ and $\mathfrak{h}$ a nilpotent Lie subalgebra then
- $\mathfrak{g} = \bigoplus_{\alpha} \mathfrak{g}_{\alpha}$ the generalized weight space

$$\mathfrak{g}_{\alpha} = \{X \in \mathfrak{g} \mid (\mathrm{ad} H - \alpha(H) 1)^n X = 0 \; \forall H \in \mathfrak{h}\}$$

- $\mathfrak{h} \subseteq \mathfrak{g}_0$
  
- $[\mathfrak{g}_{\alpha}, \mathfrak{g}_{\beta}] \subseteq \mathfrak{g}_{\alpha + \beta}$
  
We call if $\mathfrak{h} = N_{\mathfrak{g}} (\mathfrak{h}) = \mathfrak{g}_0$ then $\mathfrak{h}$ is __Cartan Subalgebra__. For complex Lie algebra, there exists Cartan subalgebra (Knapp, Theorem 2.9) and is unique upto $\mathrm{Int}\mathfrak{g}$. ($\mathrm{Int}$ is analytic subgroup of $\mathrm{Aut}\mathfrak{g}$ whose Lie subalgebra is $\mathrm{ad}\mathfrak{g}$, Knapp Theorem 2.15)

In semisimple Lie algebra, using the Cartan's semisimplicity criteria, the Cartan subalgebra is abelian (Knapp, Proposition 2.10). So $\mathfrak{g}$ semisimple can be written as

$$\mathfrak{g} = \mathfrak{h} \oplus \bigoplus_{\alpha \in \Delta} \mathfrak{g}_{\alpha}$$

We call $\Delta$ roots. Note that if Cartan subalgebra $\mathfrak{h}$ changes, roots will change. However, Cartan subalgebra is unique upto $\mathrm{Int}\mathfrak{g}$ so change of roots will be restricted also.

By Cartan's semismplicity criteria, we can analyze further with the Killing form $B$.

We can know that $B\mid_{\mathfrak{h} \times \mathfrak{h}}$ is nondegenerate and 
$B \vert_{\mathfrak{g}_{\alpha} \times \mathfrak{g}_{-\alpha}}$
 must be nondegenerate for $\alpha \in \Delta$. Thus we can guarantee $\alpha \in \Delta$ then $-\alpha \in \Delta$, moreover $\Delta$ spans $\mathfrak{h}^{*}$.

Moreover, for $\alpha \in \Delta$ we can let $H_{\alpha}$ that $\alpha(H) = B(H, H_{\alpha})$ hold for all $H \in \mathfrak{h}$ (By non-degeneracy of $B\mid_{\mathfrak{h}\times\mathfrak{h}}$) and $E_{\alpha} \in \mathfrak{g}_{\alpha}$ that $[H, E_{\alpha}] = \alpha(H) E_{\alhpa}$ (By Lie's theorem). Then $$\{H_{\alpha}, E_{\alpha}, E_{-\alpha }\}$$ looks like (after some normalization) $\mathfrak{sl}_2 \mathbb{C}$.

This introduces the terminology 'root string' and 'root reflection'

## Abstract Root System

From the motivation of studying root system of complex semisimple Lie algebra, we define an abstract root system for general finite dimensional real inner product space $V$,

- $\Delta$ spans $V$.
- $s_{\alpha} (\varphi) = \varphi - \frac{2\langle \varphi, \alpha \rangle}{\mid \alpha \mid^2} \alpha$ sends $\Delta$ to itself
- $\frac{2\langle \beta, \alpha \rangle}{\mid \alpha \mid^2}$ is an integer

Connection of abstract root system to Lie algebra is that: $\mathfrak{g}$ a complex semisimple Lie algebra has abstract reduced root system if and only if $\mathfrak{g}$ is simple. So finding all simple Lie algebras (complex) is now become the problem finding all abstract reduced root system.

This problem is combinatoric. First define 'positivity' of roots and define atomic positive element : 'simple root'. Now abstract root system correspond to 'Cartan Matrix' and expressing as graph, the 'Dynkin diagram'. Thus, classification of complex simple Lie algebra is now established.

## Weyl Group

On going from abstract reduced root system to abstract Cartan matrix, we need an ordering of roots (or positivity). The uniqueness matter of ordering is expressed as the Weyl group, defined $W(\Delta)$ a group generated by reflections of roots $s_{\alpha}$.

# Compact Lie Group, Compact Lie Algebra

To go on the deep structure theories, we need 'Compact Lie Algebras'. The fact that analytic subgroup is one to one onto correspondence of Lie subalgebra; when does the analytic subgroup become compact?

$\mathfrak{g}$ is compact __real__ Lie algebra if $\mathrm{Int}\mathfrak{g}$ is compact. (Recall $\mathrm{Int}\mathfrak{g}$ is analytic subgroup of $Aut_{\mathbb{R}} \mathfrak{g}$ whose Lie algebra is $\mathrm{ad}\mathfrak{g}$)

__(Knapp) Corollary 4.25__ $G$ a compact Lie group then its Lie algebra is reductive

__(Knapp) Proposition 4.27__ If the Killing form of a real Lie algebra $\mathfrak{g}$ is negative definite then $\mathfrak{g}$ is compact Lie algebra.

By the analysis of compact Lie algebras, we can find the structure of Compact Lie group.

__(Knapp) Theorem 4.29__ $G$ a compact, connected Lie group. Center be $Z_G$ and $G_{ss}$ an analytic subgroup of Lie algebra $[\mathfrak{g},\mathfrak{g}]$ then $G_{ss}$ has finite center and

$$G = (Z_G)_{0} G_{ss}$$

as a commuting product of closed subgroups $(Z_G)_0$ and $G_{ss}$.

We define Maximal tori of compact connected Lie group by maximal torus subgroup. This definition correspond to: analytic subgroup correspond to maximal abelian subalgebra of $\mathrm{Lie} G = \mathfrak{g}_0$. (Knapp, Proposition 4.30). Complexification of $\mathfrak{t}_0, \mathfrak{g}_0$, since $T$ is torus group, $\mathfrak{t} = \mathfrak{t}_0^{\mathbb{C}}$ gives analogy of root space decomposition.

(Technically, we only know well about root space decomposition for complex semisimple Lie algebras. So we decompose $\mathfrak{t}$ into terms on centralizer $Z_{\mathfrak{g}}$ and semisimple part $[\mathfrak{g},\mathfrak{g}]$ and combine result)

$$\mathfrak{g} = \mathfrak{t} \oplus \bigoplus_{\alpha \in \Delta(\mathfrak{g}, \mathfrak{t})} \mathfrak{g}_{\alpha}$$

From the root space decomposition,

__(Knapp) Theorem 4.34__ For compact connected Lie group $G$, two maximal abelian subalgebras of $\mathfrak{g}_0 = \mathrm{Lie}G$ are conjugate via $\mathrm{Ad}(G)$.

Moreover, every element belong to maximal torus;

__(Knapp) Theorem 4.36__ For compact connected Lie group $G$, maximal torus $T$, each element of $G$ is conjugate to element of $T$.

This simple looking theorem is hard to proof : the hardest part is while lifting the Lie algebra analysis to Lie group level.

## Weyl group

We defined Weyl group in terms of Lie algebra : $W(\Delta(\mathfrak{g},\mathfrak{h}))$ was the group generated by root reflections.

For compact connected Lie group $G$ and maximal torus $T$, define analytic Weyl group:

$$W(G,T) = N_G (T) / Z_G (T)$$

This version of Weyl group can also act on Lie algebra $\mathfrak{t}_{\mathbb{R}}^{*}$ by $\mathrm{Ad}$ action. The thing is that

__(Knapp) Theorem 4.54__ For a compact connected Lie group $G$ with maximal torus $T$, the analytically defined Weyl Group $W(G,T)$ acting on $\mathfrak{t}_{\mathbb{R}}^{*}$ coincides with Weyl Group $W(\Delta(\mathfrak{g}, \mathfrak{t}))$