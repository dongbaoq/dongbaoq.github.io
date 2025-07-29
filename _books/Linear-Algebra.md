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

# Existence of Basis

__Theorem__. Every non-trivial vector space admits basis (proof needs Zorn's lemma)

However, this does not mean basis is constructable. For example, function space $C^0 (\mathbb{R})$ admits basis but we cannot formulate it.

__Theorem__ (__Basis Extension Theorem__) If $S$ is linearly independent subset of $V$ then there exists basis of $V$ that contains $S$.

__Theorem__ If $S$ generates $V$ which $S$ is subset of non-zero vector space $V$, then there exists basis of $V$ that is contained at $S$.

# Basis, Rank, Linear Transform

## Classification of f.d.v.s

__Theorem__. If $dim V = n$ then $V \approx F^n$

Thus, __invariant value__ of equivalence class of finite dimensional vector spaces with relation defined by isomorphism is __dimension__

## Linear Transform equals Matrix

__Theorem__. Every linear map $L : F^n \rightarrow F^m$ is form of $L_A$. Furthermore $A$ is unique.

## Row Rank equals Column Rank

__Theorem__. Row rank (defined by the dimension of row vector space) and Column rank (defined by the dimension of column vector space) are equal.

Proof 1. Suppose $A$ is $m \times n$ matrix. Then if we prove $m = dim (ker A) + (rowrank)$ then since $dim (im A) = (colrank)$, proof is over. $m = dim (ker A) + (rowrank)$ can be shown by row-reduced echelon form.

Proof 2. If $A$ can be transformed to row-reduced echelon form $R$, then its row rank is invariant. Also, in the row-reduced echelon form $R$, row rank is clearly identical to column rank. Thus, one should prove that column space of $A$ and $R$ have the same rank. Since $EA = R$, $L_A = L_{E}^{-1}\circ L_R$ so $im (L_A) = im(L_E^{-1} \circ L_R) = L_E^{-1} (im (L_R))$. So as the vector space, isomorphism $L_A \approx L_R$ holds. They have the same rank.

## Rank is invariant value of similar matrices

__Theorem__ Define $A \asymp B$ for $A,B \in \mathbf{M}_{m,n}(F)$ by $B = PAQ$ for some invertible $P \in \mathbf{M}_{m,m}(F)$, $Q \in \mathbf{M}_{n,n}(F)$. Then $A \asymp B$ if and only if $rank(A) = rank(B)$. Representive form of these equivalence class is 

$$\begin{pmatrix}
I_r & 0 \\
0 & 0
\end{pmatrix}$$

# Triangularization Theorem 

__Theorem__. (__Schur Decomposition Theorem__) : For $n \times n$ __complex__ matrix $A$, $A$ can be expressed as
$$ A = QUQ^{-1}$$
for unitary matrix $Q$ and upper triangular matrix $U$. ($F = \mathbb{C}$ is important condition)


# Minimal Polynomial

Minimal polynomial is the __minimum degree monic polynomial of annihilator ideal__. For $T$ a linear operator, annihilator ideal $\mathcal{I}_T = \{f(t) \in F[t] \| f(T) = 0 \}$. This minimal polynomial $m_T (t)$ generates annihilator ideal.

__Theorem__. Characteristic polynomial $\phi_T (t)$ and minimal polynomial $m_T (t)$ have the same __monic irreducible divisors__ (over field $F$)

Minimal Polynomial admits __Induction__ on matrix size. 

# Primary Decomposition Theorem

__Theorem__. (__Primary Decomposition Theorem__) If $T$ is linear operator (or matrix) then for $\phi_T(t) = p_1(t)^{e_1} p_2(t)^{e_2} \cdots p_k (t)^{e_k}$ and $m_T(t) = p_1(t)^{f_1} p_2(t)^{f_2} \cdots p_k(t)^{f_k}$ ($p_i(t)$ are monic irreducible polynomial)

$$
\begin{aligned}
V &= ker (p_1(T)^{e_1}) \oplus ker(p_2 (T)^{e_2}) \oplus \cdots \oplus ker(p_k (T)^{e_k})\\
    &= ker (p_1(T)^{f_1}) \oplus ker(p_2 (T)^{f_2}) \oplus \cdots \oplus ker(p_k (T)^{f_k})
\end{aligned}    
$$

Moreover, if we let $W_i = ker(p_i(T))^{e_i}$ and $T_i = T \|_{W_i}$, then $\phi_{T_i} (t) = p_i (t)^{e_i}$ and $m_{T_i}(t) = p_i (t)^{f_i}$

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

# Diagonalizability

__Corollary__. $T$ is diagonalizable if and only if the minimal polynomial $m_T(t)$ can be decomposed into 1st order monic polynomial and does not have multiple root. 

(__Thus, diagonalizability is fully determined by 'Minimal Polynomial'__)



# Diagonalization Theorem

For linear operator $T : V \rightarrow W$, there exists adjoint linear operator $T^* : W \rightarrow V$ satisfying $<T(x), y>_W = <x, T^* (y)>_V$. Assurance that $V, W$ being __finite dimensional inner product space__ is essential.

- __Normal Operator__ satisfies $T T^* = T^* T$ for $T : V \rightarrow V$.
-  __Hermitian Operator__ satisfies $T = T^*$.
-  __Unitary Operator__ satisfies $T^* T = I$.
-  __Orthogonal Operator__ satisfies $T^t T = I$ for real vector field.

# Spectral Theorem