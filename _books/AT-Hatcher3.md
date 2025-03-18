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

$$M_R = \{\mu_x | x \in M, \mu_x \in H_n(X\|x;R) \}$$

If $M$ is $R$ orientable then each section will correspond to element of $R$. Identity of $R$ corresponds to $R$-orientation. However, if $M$ is not $R$-orientable, then element in $H_n(X\|x;R)$ need to equal to its minus. Thus $2r = 0$ condition is needed. This fact is illustrated in Theorem 3.26 and Lemma 3.27 of Hatcher's book. Lemma 3.27 is itself useful in many situations.




