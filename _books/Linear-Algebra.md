---
title: "Linear Algebra"
collection: books
date: 2025-07-27
permalink: /books/LA
use_math: true
tags:
- Linear Algebra
- Matrix
---

This post illustrates fundamental and most important theory in mathematics : the linear algebra. These notes are based on 선형대수와 군 by 이인석 which is highly intuitive and instructive book for understanding linear algebra.

# Problems of Linear Algebras

Linear Algebra concerns about __Linear Maps on Vector Space__. As many studied the Linear Algebra, usually matrices become the central object. However, matrices and basis are supplementary tools for __understanding Linear Maps__. Matrices and basis are useful for understanding Linear Algebra by __Hands__ but the one who is only used to these __by Hands__ method will fail to understand what really the __Linear Algebra wants to talk about__. However, it is also important to being used to handle matrices.

In this article $F$ stands for __Fields__. So $F = \mathbb{F}_q,\,\mathbb{Q}_p$ fields are also possible. If $F = \mathbb{R}$ or $F = \mathbb{C}$ is needed, then I will clarify it.

The main topics concerning matrices are :
- __Classification of Matrices by Solution space__
- __Classification of Square Matrices by similar relation__

The main topics concerning Linear Algebras are: 
- __Classification of Finite Dimensional Vector Space__
- __Dimension Theorem, Rank Theorem, Perp theorem__
- __Dual Space__
- __Philosophy of Bilinear form and Hermittian form, Quadratic form__
- __Transpose of Linear Map__

In my journey of studying Linear Algebra, at the __first studying__ I learned how to deal with matrices (multiplication, row reduced transform, diagonalization). __Second studying__, I understood linear map is __equivalent__ to matrices. To now the __third studying__ I understood linear map is __not equivalent__ to matrices, rather much abstract and nice concept. Matrices are just useful tool for 'calculating' linear map but linear map and vector space can be handled with much __canonical__ way and beautiful harmony exists.

# Vector Space

### Existence of Basis

__Theorem__. Every non-trivial vector space over $F$ admits basis (proof needs Zorn's lemma)

However, this does not mean basis is constructable. For example, function space $C^0 (\mathbb{R})$ admits basis, but we cannot formulate it.

__Theorem__ (__Basis Extension Theorem__) If $S$ is linearly independent subset of $V$ over $F$ then there exists basis of $V$ that contains $S$.

__Theorem__ If $S$ generates $V$ which $S$ is subset of non-zero vector space $V$, then there exists basis of $V$ that is contained at $S$.

# Linear Transform and Matrix

### Classification of f.d.v.s

__Theorem__. If $V$ is a vector field over $F$ and $dim V = n$, then $V \approx F^n$

Thus, __invariant value__ of equivalence class of finite dimensional vector spaces with relation defined by isomorphism is __dimension__. We can also think any vector space as a representative : $F^n$

### Linear Transform can be represented by Matrix

__Theorem__. Every linear map $L : F^n \rightarrow F^m$ is form of $L_A$. Furthermore, $A$ is unique.

## Dimension Theorem

Dimension Theorem is one __Central Theorem__ of Linear Algebra.

__Theorem (Dimension Theorem)__ If $V$ is f.d.v.s over $F$ and $L: V \rightarrow W$ is linear map, then

$$\mathrm{dim} V = \mathrm{dim} \, \mathrm{ker} L + \mathrm{dim}\,\mathrm{im}L$$


# The Classification of $\mathcal{M}_{m,n}(F)$ : In perspective of Solution Space$

## Rank Theorem

__Theorem (Rank Theorem)__. For $A \in \mathcal{M}_{m,n}(F)$, Row rank (defined by the dimension of row vector space) and Column rank (defined by the dimension of column vector space) are equal.

Proof 1. Suppose $A$ is $m \times n$ matrix. Then if we prove $m = \mathrm{dim} (ker A) + (\mathrm{row \, rank})$ then since $\mathrm{dim} (im A) = (\mathrm{col \, rank})$, proof is over. $m = \mathrm{dim} (ker A) + (\mathrm{row \, rank})$ can be shown by row-reduced echelon form.

Proof 2. If $A$ can be transformed to row-reduced echelon form $R$, then its row rank is invariant. Also, in the row-reduced echelon form $R$, row rank is clearly identical to column rank. Thus, one should prove that column space of $A$ and $R$ have the same rank. Since $EA = R$, $L_A = L_{E}^{-1}\circ L_R$ so $im (L_A) = im(L_E^{-1} \circ L_R) = L_E^{-1} (im (L_R))$. So as the vector space, isomorphism $L_A \approx L_R$ holds. They have the same rank.

### Representative of the classification

__Theorem__ Define $A \asymp B$ for $$A,B \in \mathcal{M}_{m,n}(F)$$ by $B = PAQ$ for some invertible $$P \in \mathcal{M}_{m,m}(F)$$, $$Q \in \mathcal{M}_{n,n}(F)$$. Then $A \asymp B$ if and only if $rank(A) = rank(B)$. Representative form of these equivalence classes is 

$$\begin{pmatrix}
I_r & 0 \\
0 & 0
\end{pmatrix}$$

# The Classification of $\mathcal{M}_{n,n}(F) : In Similar relation$

Here, te equivalence relation is defined by $A \sim B$ if $A = UBU^{-1}$ for some matrix $U \in \mathcal{M}_{n,n}(F)$.

## Triangularization Theorem of $F = \mathbb{C}$

__Theorem__. If $F = \mathbb{C}$ then for linear transform $T$, there exists basis $\mathfrak{B}$ of $V$ such that $[T]_{\mathfrak{B}}^{\mathfrak{B}}$ is a upper-triangular matrix.

More stronger result will be

__Theorem__. (__Schur Decomposition Theorem__) : If $F = \mathbb{C}$, $n \times n$ __complex__ matrix $A$, $A$ can be expressed as
$$ A = QUQ^{-1}$$
for unitary matrix $Q$ and upper triangular matrix $U$. ($F = \mathbb{C}$ is important condition)

However, we want to discuss on the general field $F$.

## Minimal Polynomial

Minimal polynomial is the __minimum degree monic polynomial of annihilator ideal__. For $T$ a linear operator, annihilator ideal $$\mathcal{I}_T = \{f(t) \in F[t] \| f(T) = 0 \}$$. This minimal polynomial $m_T (t)$ generates annihilator ideal.

__Theorem__. Characteristic polynomial $\phi_T (t)$ and minimal polynomial $m_T (t)$ have the same __monic irreducible divisors__ (over field $F$)

Minimal Polynomial admits __Induction__ on matrix size. 

## Primary Decomposition Theorem

__Theorem__. (__Primary Decomposition Theorem__) If $T$ is linear operator (or matrix) then for $\phi_T(t) = p_1(t)^{e_1} p_2(t)^{e_2} \cdots p_k (t)^{e_k}$ and $m_T(t) = p_1(t)^{f_1} p_2(t)^{f_2} \cdots p_k(t)^{f_k}$ ($p_i(t)$ are monic irreducible polynomial)

$$
\begin{aligned}
V &= ker (p_1(T)^{e_1}) \oplus ker(p_2 (T)^{e_2}) \oplus \cdots \oplus ker(p_k (T)^{e_k})\\
    &= ker (p_1(T)^{f_1}) \oplus ker(p_2 (T)^{f_2}) \oplus \cdots \oplus ker(p_k (T)^{f_k})
\end{aligned}    
$$

Moreover, if we let $W_i = ker(p_i(T))^{e_i}$ and $$T_i = T \vert_{W_i}$$, then $\phi_{T_i} (t) = p_i (t)^{e_i}$ and $m_{T_i}(t) = p_i (t)^{f_i}$

If we admit this theorem, for basis $\mathcal{B_i}$ of $W_i$, we have

$$
[T]_{\mathcal{B}}^{\mathcal{B}} =
\begin{pmatrix}
[T_1]_{\mathcal{B}_1}^{\mathcal{B}_1} & 0 & \cdots & 0\\
0 & [T_2]_{\mathcal{B}_2}^{\mathcal{B}_2} & \cdots & 0\\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & [T_k]_{\mathcal{B}_k}^{\mathcal{B}_k}
\end{pmatrix}
$$

This is the consequence of following lemma which is immediate by $d(t) = g_1(t)f_1(t) + \cdots + g_k(t)f_k(t)$ holds for $d(t)$ the greatest common divisor.

__Lemma__. If $f_1(t), \cdots , f_k(t) \in F[t]$ are monic, mutally relative prime and $\xi(t) = f_1(t) f_2(t) \cdots f_k(t) \in \mathcal{I}_T$ then

$$V = ker(f_1(T)) \oplus ker(f_2(T)) \oplus \cdots \oplus ker(f_k(T))$$

## Diagonalizability

__Corollary__. $T$ is diagonalizable if and only if the minimal polynomial $m_T(t)$ can be decomposed into 1st order monic polynomial and does not have multiple root. 

__Thus, diagonalizability is fully determined by 'Minimal Polynomial'__

Also, simiulataneously diagonalizability can be deduced by induction.

__Theorem__ For $$\{T_i\}_{i \in I}$$, If $T_i T_j = T_j T_i$ and $T_i$ are all diagonalizable, then $$\{T_i \}_{i \in I}$$ is simultaneously diagonalizable.

Proof uses induction on dimension of $V$. Fix $$T \in \{T_i\}_{i \in I}$$ and decompose $V = E_{\lambda_1}^T \oplus \cdots \oplus E_{\lambda_k}^T$. Then $E_{\lambda_j}^T$ is $T_i$ invariant space for all $i \in I$. So by induction hypothesis, ${T_i \big\vert_{E_{\lambda_j}^T}}$ are simultaneously diagonalizable with basis $$\{\mathfrak{B}_j \}$$. Now consider $$\mathfrak{B} = \cup_{j=1}^{k} \mathfrak{B}_j$$.

This can be used on finding center of groups, for example $O(n), U(n), SU(n)$.

## $T$-Cyclic Subspace

Furthermore decomposition on linear operator uses $T$-Cyclic subspace terminology.

$$V = F[t] v = \{f(T) v \in V \vert f(t) \in F[t] \}$$

$T$-Cyclic space satisfies $deg (m_T) = dim V$ and $\phi_T (t) = m_T (t)$ (__I think this property, minimal polynomial equals to characteristic polynomial, is very important feature of Cyclic space__) because basis of $F[t] v$ is just $$\mathfrak{B} = \{v, Tv, \cdots , T^{deg(m_T) - 1} v\}$$. For each $T$-Cyclic space, its companion matrix is defined, if $m_T (t) = t^n + a_{n-1} t^{n-1} + \cdots + a_1 t + a_0$ or $T^n + a_{n-1} T^{n-1} + \cdots + a_1 T + a_0 = 0$, companion matrix is

$$\begin{pmatrix}
0 & 0 & 0 & \cdots & 0 & -a_0\\
1 & 0 & 0 & \cdots & 0 & -a_1\\
0 & 1 & 0 & \cdots & 0 & -a_2\\
\vdots & \vdots & \vdots & \ddots & \vdots & \vdots\\
0 & 0 & 0 & \cdots & 0 & -a_{n-2}\\
0 & 0 & 0 & \cdots & 1 & -a_{n-1}
\end{pmatrix}$$

which is just a $[T]_{\mathfrak{B}}^{\mathfrak{B}}$.

For any $T$-invariant space $V$, we can define $T$-cyclic subspace $W$, which is cyclic via $T \vert_W$. If $W = F[t] w$, we notate $m_w(t) = m_{T\vert_W}(t)$. 

## Cyclic Decomposition Theorem

__Theorem__ (__Cyclic Decomposition Theorem__) If $T$ is linear transform and $m_T (t) = p(t)^f$ where $p(t)$ is monic irreducible polynomial. Then

$$V = U_1 \oplus U_2 \oplus \cdots \oplus U_h$$

$U_1, \cdots U_h$ are $T$-Cyclic subspace and for 

$$\phi_{T\vert_{U_j}}(t) = m_{T\vert_{U_j}}(t) = p(t)^{r_j}$$

$$f = r_1 \ge r_2 \ge \cdots \ge r_h \ge 1$$

$h$ and $r_1, \cdots , r_h$ are uniquely determined.

__Thus, $T$-invariant space can be decomposed into direct sum of $T$-cyclic spaces and $h, r_1, \cdots, r_h$ are invariant on decomposition__

## Primary Decomposition Theorem $\oplus$ Cyclic Decomposition Theorem

For $T$, by __Primary Decomposition Theorem__

$$V = W_1 \oplus \cdots \oplus W_k$$

Where $W_i = ker (p_i(T)^{f_i})$. Next, $T_i = T \vert_{W_i}$ can be applied __Cyclic Decomposition theorem__ so

$$W_i = U_{i1} \oplus \cdots \oplus U_{ih_i}$$

Where $f_i = r_{i1} \ge \cdots \ge r_{ih_{i}} \ge 1$ with

$$\phi_{T\vert_{U_{ij}}} (t) = m_{T \vert_{U_{ij}}}(t) = p_i(t)^{r_{ij}}$$

This is the __Best Answer to Decompose arbitrary $$\mathcal{M}_{n,n}(F)$$ Matrix__. Equivalence relation $\sim$ is totally determined by $p_i (t), h_i, r_{ij}$.

## Jordan Canonical Form

__Jordan Canonical Form is Representative Form of $\mathcal{M}_{n,n}(F)$. One assumption that cannot be dropped is that $F$ is Algebraically closed__

After applying Primary Decomposition Theorem, $V = W_1 \oplus \cdots \oplus W_k$ and if we suppose $\phi_T(t)$ is multiple of linear polynomials(__Here the fact that $F$ being algebraically closed is used__) then $\phi_{T_i} (t) = p_i(t)^{e_i}$ and $m_{T_i} (t) = p_i (t)^{f_i}$.

If we apply Cyclic Decomposition Theorem to $N = T - \lambda I$, $W = U_1 \oplus U_2 \oplus \cdots \oplus U_h$ and each $\phi_{N\vert_{U_j}}(t) = m_{N\vert_{U_j}}(t) = t^{r_j}$ so companion matrices last column is zero. 

$$
\begin{aligned}
T\vert_{W_i} &\sim J_{(r_{i1}, r_{i2}, \cdots , r_{i h_i})} \\
&=
\begin{pmatrix}
\lambda_i & 1 & 0 &\cdots & 0 & & & & & &&&&&&\\
0 & \lambda_i & 1 & \cdots & 0 & & & & & &&&&&&\\
0 & 0 & \lambda_i & \cdots & 0 & & & & & &&&&&&\\
\vdots & \vdots & \vdots & \ddots & \vdots & & & & & &&&&&&\\
0 & 0 & 0 & \cdots & \lambda_i & & & & & &&&&&&\\
& & & & & \lambda_i & 1 & 0 &\cdots & 0 &&&&&&\\
& & & & & 0 & \lambda_i & 1 & \cdots & 0 &&&&&&\\
& & & & & 0 & 0 & \lambda_i & \cdots & 0 &&&&&&\\
& & & & & \vdots & \vdots & \vdots & \ddots & \vdots &&&&&&\\
& & & & & 0 & 0 & 0 & \cdots & \lambda_i & &&&&& \\
&&&&&&&&&& \ddots &&&&& \\
&&&&&&&&&&&\lambda_i & 1 & 0 &\cdots & 0\\
&&&&&&&&&&&0 & \lambda_i & 1 & \cdots & 0 \\
&&&&&&&&&&&0 & 0 & \lambda_i & \cdots & 0\\
&&&&&&&&&&&\vdots & \vdots & \vdots & \ddots & \vdots \\
&&&&&&&&&&&0 & 0 & 0 & \cdots & \lambda_i
\end{pmatrix}
\end{aligned}
$$

Each block size is $r_{ij} \times r_{ij}$.

