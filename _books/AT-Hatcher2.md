---
title: "Book Review : Algebraic Topology Ch 2"
collection: books
date: 2025-03-14
permalink: /books/AT2
use_math : true
tags:
- Allen Hatcher
- Book Review
- Topology
---

# Homology : definition and technique

## Relative Homology

Relative homology defined as $H_n (X,A)$ is interpreted as following:

It is represented by relative cycle $\varphi \in C_n (X)$ that $\partial \varphi \in C_n (A)$. So draw an image cycle whose boundary belongs to $A$.

This relative cycle is trivial if $\varphi = \partial \psi + \varphi^{A}$ where $\psi \in C_{n+1} (X)$, $\varphi^{A} \in C_{n} (A)$.

Homology is hard to imagine what it states for. It's because homology is the form $ker \partial / im \partial$. We need to imagine homology by specific cycle which is much easier to believe. Only aware of the fact that there are several other cycles that match with the cycle by equivalent class.

## Techniques for Calculating Homology

Calculation of homology depends on some techniques. Long exact sequence is the main one. Mayer Vietoris argument is another.

### Mayer Vietoris

Mayer Vietoris argument is useful because **We know all maps in exact sequence**

$$ \cdots H_n (A \cap B) \xrightarrow{(i_{1*}, i_{2*})} H_n (A) \oplus H_n (B) \xrightarrow{j_{1*} - j_{2*}} H_n (X) \xrightarrow{\partial_{*}} H_n (A \cap B) \cdots $$

Note that third map is quite clear. Cycle of $X$ can be decomposed into sum of chain in $A$ and chain in $B$ by barycentric subdivision. These two chain cancels, $\varphi = \varphi_A + \varphi_B$ then $0 = \partial \varphi_A + \partial \varphi_B$. So third map sends $\varphi$ into $\partial \varphi_A = -\partial \varphi_B$.

### Excision

Excision is an isomorphism but its fundamental is from **inclusion map**.
$i : (X-Z, A-Z) \hookrightarrow (X,A)$ induces $H_n (X-Z, A-Z) \xrightarrow{i_*} H_n (X, A)$.

This fact may be important if excision relates to naturality. 

Another thing to note is the proof technique. Constructing chain homotopy yields the same induced map is crucial component in chain argument.

$ \partial P + P \partial = f_* - g_*$
then $f, g$ generates the same induced map.

## Naturality

Naturality states if $f : (X,A) \rightarrow (Y,B)$ then

$\require{\AMScd}$
$$\begin{CD}
\cdots @>>> H_n(A) @>{i_*}>> H_n(X) @>{j_*}>> H_n(X,A) @>{\partial}>> H_{n-1}(A) @>>> \cdots\\ 
@. @VV{f_*}V {\circlearrowleft} @VV{f_*}V {\circlearrowleft} @VV{f_*}V {\circlearrowleft} @VV{f_*}V\\
\cdots @>>> H_n(B) @>{i_*}>> H_n(Y) @>{j_*}>> H_n(Y,B) @>{\partial}>> H_{n-1}(B) @>>> \cdots
\end{CD}$$

Third commutative diagram is important. Induced map commutes with boundary map is key of naturality.

## Cellular Homology

### Mapping Telescope Argument

Hatcher Lemma 2.34 uses mapping telescope argument for infinite dimensional CW complex. I haven't seen this type of argument applied to other situation but following proof was interesting.

### Cellular Boundary Map

Strength of cellular homology is that it is able to compute explicitly the boundary map. Understanding following diagram is important.

$\require{\AMScd}$
$$\begin{CD}
H_n (D_{\alpha}^n, \partial D_{\alpha}^n) @>{\partial}>> \tilde{H}_{n-1} (\partial D_{\alpha}^n) @>{\Delta}_{\alpha\beta *}>> \tilde{H}_{n-1} (S_{\beta}^{n-1}) \\
@VV{\Phi_{\alpha *}}V @VV{\varphi_{\alpha *}}V @AA{q_{\beta *}}A\\
H_n (X^n, X^{n-1}) @>{\partial_n}>> \tilde{H}_{n-1} (X^{n-1}) @>{q_*}>> \tilde{H}_{n-1} (X^{n-1}/X^{n-2}) \\
@. @VV{j_{n-1}}V @VV{\approx}V\\
@. H_{n-1}(X^{n-1}, X^{n-2}) @>{\approx}>> H_{n-1}(X^{n-1}/X^{n-2}, X^{n-2}/X^{n-2})
\end{CD}$$

Cellular boundary map sends $H_n (X^n, X^{n-1})$ to $H_{n-1}(X^{n-1}, X^{n-2})$. We need to see how actually each class send to others.

$\require{\AMScd}$
$$\begin{CD}
[D_{\alpha}^n] @>{\partial}>> [\partial D_{\alpha}^n] @>{\Delta}_{\alpha\beta *}>> [d_{\alpha\beta} e_{\beta}^{n-1}] \\
@VV{\Phi_{\alpha *}}V @VV{\varphi_{\alpha *}}V @AA{q_{\beta *}}A\\
[e_{\alpha}^n] @>{\partial_n}>> [*] @>{q_*}>> [\sum_{\beta} d_{\alpha\beta} e_{\beta}^{n-1}] \\
@. @VV{j_{n-1}}V @|\\
@. [\sum_{\beta} d_{\alpha\beta} e_{\beta}^{n-1}] @= [\sum_{\beta} d_{\alpha\beta} e_{\beta}^{n-1}]
\end{CD}$$

Therefore, the formula holds.

### Application

Applying cellular homology to various CW complexes are remarkable. Len's space, Real and Complex Projective space... and exercises of chapter 2.2

## Homology is an abelianization of fundamental group

The statement that homology is an abelianization of fundamental group is itself useful but I want to point out that this statement helps us to realize what homology represents.

Like example 2A.2. on Algebraic hatcher, we can express first homology group as 'loops'. Also, by calculation on fundamental group, we can identify whether two loops determine the same homology group.

## Simplicial Approximation theorem of CW complex

Proof of simplicial approximation theorem is quite hard. I want to describe details of the proof.

The main bottleneck is that ordinary mapping cone does not apply to simplicial objects. Building mapping cylinder for simplicial map is as following:

- First remark that $f:K \rightarrow L$ simplicial map can be extended to $f:K' \rightarrow L$ where $K'$ is barycentric subdivision of $K$. This is by choosing 'lowest index' for each barycentric division. In the proof, we want to make $M(f)$ that has retraction onto $L$ with $r_1 \| K' =f$. Right hand side $f$ mean $f$ applyed to $K'$.

- First construct $M(f|K^0)$. $K^0$ maps into $L^0$ by $f$ so connect those points by $\Delta^1$.

  $$M(f\|K^0) = L \cup \cup_{K^0} \Delta^1$$

- Existing $M(f\|K^{n-1})$, $n$-simplex $\sigma$ of $K$ and $\tau = f(\sigma)$. Then within the barycentric subdivision of $\sigma$, $M(f:\sigma \rightarrow \tau)$ can be think of cone whose vertex is barycenter and underlying space $M(f:\partial \sigma \rightarrow \tau)$. Note that $f$ extended to barycenter of $\sigma$ sends barycenter to one of the 0 simplex of $L$. Thus, cone is perfectly defined.

- Attach $M(f:\sigma \rightarrow \tau)$ to $M(f|K^{n-1})$. Then we obtain $M(f\|K^n)$ that deformation retracts to $M(f\|K^{n-1})$. Here, deformation retract is defined for the 'realization' of mapping cylinders.

- Thus there can occur the problem that deformation retract does not equal $f$. However, this can be corrected by linear homotopy.
