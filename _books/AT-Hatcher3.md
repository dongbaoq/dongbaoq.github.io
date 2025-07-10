---
title: "Book Review : Algebraic Topology Ch 3"
collection: books
date: 2025-03-14
permalink: /books/AT3
use_math: true
tags:
- Allen Hatcher
- Book Review
- Topology
---


This post illustrates important points in my view of the Allen Hatcher's Algebraic Topology chapter 3.

# Cohomology and Homology

## Intuitive understanding of Cohomology

Cohomology is Quotient group which lies on $C^n (X)$. Cohomology can be realized as a **function** assigning value to each map $\sigma : \Delta^n \rightarrow X$. Cocyle is one of the function that satisfies $\delta \varphi = 0$.

Relative cohomology $H^n (X,A)$ could be realized as some function assigning value to each map that is cocycle and assign 0 to map $\sigma$ whose $Image(\sigma) \subset A$.


## Universal Coefficient Theorem

Universal Coefficient Theorem is useful when we know homology. This sequence splits and also **natural**.

$$ 0 \rightarrow Ext(H_{n-1}(C), G) \rightarrow H^n (C;G) \xrightarrow{h} Hom(H_n(C), G) \rightarrow 0$$

Not all cohomology group can be computed as universal coefficient theorem. Trivial isomorphism 

$$H_n (X ; \mathbb{Z}_2) = H^n (X ; \mathbb{Z}_2)$$

holds. It's because assigning value 1 to $\sigma$ can be interpreted as just adding $\sigma$. Thus one to one correspondence on chain and cochain exists in $\mathbb{Z}_2$ coefficient.


## Similar techniques hold for cohomology

Mayer Vietoris, Excision... also holds for cohomology. Two things are remarkable.

### Naturality of h

This is nontrivial that following diagram is commutative.

$\require{\AMScd}$
$$\begin{CD}
H^n (A;G) @>{\delta}>> H^{n+1}(X,A;G)\\
@VV{h}V @VV{h}V\\
Hom(H_n(A),G) @>{\partial^{*}}>> Hom(H_{n+1}(X,A),G)
\end{CD}$$

Proof is just a diagram chasing but, we can learn what cohomology really is. Realizing as a function assigning values to chain is key ingredient of this proof.

### Cellular cochain is exactly dual to the cellular chain complex

Hatcher Theorem 3.5. Thus we can easily use cellular cochain complex for CW complexes if their cellular chain complex is known.

## Cup Product

### Cup product commutes with induced map

$f : X \rightarrow Y$,

$$f^{*} (\alpha \smile \beta) = f^* (\alpha) \smile f^{*} (\beta)$$

This might be viewed not that powerful, but actually by this property, we can check following diagram is commutative. (This is also a solution for Hatcher exercise 2). Suppose $f : X \rightarrow Y$ that $f(A) \subset C$, $f(B) \subset D$.

$\require{\AMScd}$
$$\begin{CD}
H^{k}(X, A) \times H^{l}(X, B) @>{\smile}>> H^{k+l} (X, A\cup B)\\
@A{f^* \times f^*}AA @A{f^*}AA\\
H^{k}(Y, C) \times H^{l}(Y, D) @>{\smile}>> H^{k+l} (Y, C\cup D)
\end{CD}$$

This is by diagram chasing

$\require{\AMScd}$
$$\begin{CD}
[f^* \phi] \times [f^* \psi] @>{\smile}>> [f^* \phi] \smile [f^* \psi] = [f^* (\phi \smile \psi)]\\
@A{f^* \times f^*}AA @A{f^*}AA\\
[\phi] \times [\psi] @>{\smile}>> [\phi \smile \psi]
\end{CD}$$

### Cup product is skew commutative

$$\alpha \smile \beta = (-1)^{kl} \beta \smile \alpha$$

## Cohomology Ring

Cohomology ring is homotopy invariant, containing a lot of informations.

### Proof detail on cohomology ring of Real projective space

At first glance, I haven't 'really' understand the proof. I'll describe more details on the proof of Hatcher's Theorem 3.12.


## Orientation

### Orientation as homology or as section


Orientation could be understand as a generator of homology $H_{n}(X\|x)$.It may satisfy 'continuity' that for some ball $x \in B$, $H_{n} (X\|A) \rightarrow H_n(X\|x)$ maps generator to generator.

We can think in this way, why Mobius band is not orientable. Following to the circle (deform retraction of Mobius band), generator points opposite way but the same point.

More elegant way to understand this is thinking about covering space $M_R$, topologized by above 'continuity'

$$M_R = \{\mu_x | x \in M, \mu_x \in H_n(X|x;R) \}$$

If $M$ is $R$ orientable then each section will correspond to element of $R$. Identity of $R$ corresponds to $R$-orientation. However, if $M$ is not $R$-orientable, then element in $H_n(X\|x;R)$ need to equal to its minus. Thus $2r = 0$ condition is needed. This fact is illustrated in Theorem 3.26 and Lemma 3.27 of Hatcher's book. Lemma 3.27 is itself useful in many situations.

### Orientation of manifold with boundary

If $M$ is compact manifold with boundary, orientation is defined by orientation of $M - \partial M$.

Existence of collar neighborhood of $\partial M$ gives isomorphism

$$ H_n (M, \partial M ; R) \approx H_n (M-\partial M, \partial M \times (0, \epsilon);R)$$

Since $H_n (M-\partial M, \partial M \times (0, \epsilon);R) = H_n (M-\partial M \| K ; R)$, it can be viewed as orientation of $M$. It means $H_n (M, \partial M ; R)$ represents orientation of $M$.

Crucial fact is that connecting homomorphism maps fundamental class of $M$ into fundamental class of $\partial M$

$$\partial : H_n(M, \partial M) \xrightarrow{\approx} H_{n-1} (\partial M)$$

We can prove this by following method : 

First we prove that $H_n (M) = 0$. There are two maps

$$ i : M - \partial M \times [0, \epsilon] \hookrightarrow M$$

$$ h : M \rightarrow M - \partial M \times [0, \epsilon]$$

Where $h$ follows by proof of existence of collar neighborhood. $M$ is homeomorphic to $M - \partial M \times [0, 3 \epsilon)$. $h$ sends $M - \partial M \times [0,2 \epsilon]$ into itself and $\partial M \times [0, 2\epsilon]$ into projection $\partial M \times {2\epsilon}$.

Then $h \circ i$ and $i \circ h$ is homotopic to identity map. Thus $M$ and $M - \partial M \times [0, \epsilon]$ are homotopy equivalent and later one is noncompact manifold without boundary. Which implies $H_n (M) = 0$.

Now, for the long exact sequence

$$ 0 \rightarrow H_n (M, \partial M) \xrightarrow{\partial} H_{n-1} (\partial M) \rightarrow H_{n-1}(M) $$

We know $M$ is homotopic equivalent to orientable noncompact manifold without boundary so $H_{n-1} (M)$ is free. Thus $\partial$ map must be surjective. That means, $\partial$ map is an isomorphism.

As a corollary we can prove Hatcher Ex. 33. If compact manifold retracts onto its boundary, then $r : M \rightarrow \partial M$ and $i : \partial M \rightarrow M$ satisfies $i \circ r = id$. However for the long exact sequence

$$ H_{n} (M, \partial M) \xrightarrow{\approx} H_{n-1} (\partial M) \xrightarrow{0} H_{n-1}(M)$$

So inclusion map induces zero map in homology. There cannot exist a retraction.

## Diagram chasing within cohomology with compact support

I want to describe diagram chasing that contains cohomology with compact support. 

### Lemma 3.36 from Hatcher

$\require{AMScd}$
$$\begin{CD}
\cdots @>>> H_{c}^{k}(U \cap V) @>>> H_{c}^{k}(U) \oplus H_{c}^{k}(V) @>>> H_{c}^{k} (M) @>>> H_{c}^{k+1} (U \cap V) @>>> \cdots\\
@. @VV{D_{U \cap V}}V @VV{D_U \oplus -D_V}V @VV{D_M}V @VV{D_{U \cap V}}V @.\\
\cdots @>>> H_{n-k}(U\cap V) @>>> H_{n-k}(U) \oplus H_{n-k}(V) @>>> H_{n-k}(M) @>>> H_{n-k-1}(U\cap V) @>>> \cdots\\
\end{CD}$$

First Square: for $K \subset U$ and $L \subset V$ compact,

$\require{AMScd}$
$$\begin{CD}
H^{k} (M | K\cap L) @>>> H^{k} (M|K) \oplus H^{k}(M|L)\\
@VVV @VVV\\
H^{k} (U\cap V |K\cap L) @. H^{k} (U|K) \oplus H^{k}(V|L)\\
@VVV @VVV\\
H_{n-k} (U \cap V) @>>> H_{n-k}(U) \oplus H_{n-k}(V)
\end{CD}$$

for representative cochain $\varphi$

$\require{AMScd}$
$$\begin{CD}
[\varphi] @>>> [(\varphi, -\varphi)]\\
@VVV @VVV\\
[\varphi|_{U\cap V}] @. [(\varphi|_{U}, -\varphi|_{V})]\\
@VVV @VVV\\
[\mu_{K\cap L} \frown \varphi|_{U\cap V}] @>>> 
\end{CD}$$

$$(\mu_K \frown \varphi\big|_{U}, -\mu_{L} \frown \varphi\big|_{V}) = (\mu_{K\cap L} \frown \varphi\big|_{U\cap V}, -\mu_{K\cap L} \frown \varphi\big|_{U\cap V})$$

is what we have to show and it holds because of cap product commutes with induced map.

## Appendix A : Universal Coefficient Theorem

We have two universal coefficient theorems : Universal coefficient theorem for cohomology and Universal coefficient theorem for homology.

Universal coefficient theorem for cohomology states

$$ 0 \rightarrow Ext(H_{n-1}(C), G) \rightarrow H^n(C;G) \rightarrow Hom(H_n(C), G) \rightarrow 0$$

and is split exact, natural.

Universal coefficient theorem for homology states

$$ 0 \rightarrow H_n(C) \otimes G \rightarrow H_n(C;G) \rightarrow Tor(H_{n-1}(C), G) \rightarrow 0$$

and is split exact, natural.

## Appendix B : General Kunneth formula

### Homology as cell of CW complex

In the Appendix B, it introduces how to 'interpret' homology in CW structure. Then, we will be able to define 'product' of cycles. For cohomology, we defined cup product which $\varphi \smile \psi$ applied separately on $\Delta$ - complexes.

The cellular cross product is defined to satisfy $d(e^i \times e^j) = de^i \times e^j + (-1)^i e^i \times de^j$. Which $e^i$, $e^j$ corresponds to $i$ cell and $j$ cell of $X$ and $Y$ respectively. More precisely, these $e^i$ are the generator of $H_i (X^i, X^{i-1})$. However, we need an attention to determine orientation of $e^i$. This orientation is equivalent to linear algebraic orientation. $H_i (I^i, \partial I^i)$ can be determined by orientation of basis elements, which is -1 or 1 according to determinant.

Then, product map of homology is well-defined and cellular maps also satisfies 'good' property. See Lemma 3B.2.

Now we can think of homology for CW complexes that corresponds to one $i$ cells. This gives an easy explanation why $H_n(X\times S^k; \mathbb{Z}) \approx H_n(X;\mathbb{Z}) \oplus H_{n-k} (X; \mathbb{Z})$

### Algebraic Kunneth formula

Algebraic Kunneth formula is formula that determines homology of tensor product of two chains. This applied to homology of CW complexes induce topological Kunneth formula.

### Cohomology as cell of CW complex

Cohomology could be also defined within 'cell' in CW complex. It assigns each $i$ cell a $R$ value. Then as homology does, we can define product of cohomology.

$$(\varphi \times_2 \psi) (e_{\alpha}^k \times e_{\beta}^l) = \varphi(e_{\alpha}^k) \psi(e_{\beta}^l)$$

and assigns 0 to other $k+l$ cells which are not the product of $k$-cell and $l$-cell of $X$ and $Y$.

Important fact of this definition is, this definition of product coincides with product defined by cup product of cohomology.

$$ \varphi \times_1 \psi = p_1^* (\varphi) \smile p_2^* (\psi)$$

## Appendix C : Hopf Algebras

We have looked at interesting algebraic structure on cohomology ring. Within the 'cup product' cohomology ring became graded algebra. If given topological space satisfies additional structure : H-space, then more structure could be induced on cohomology and homology.

### Cohomology : Hopf algebra structure

### Homology : Pontryagin product (Sometimes, Pontryagin ring)
