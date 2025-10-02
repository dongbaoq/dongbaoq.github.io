---
title: "Probability"
collection: books
date: 2025-10-02
permalink: /books/Probability
use_math: true
tags:
- Probability
- Measure theory
---

This post illustrates fundamental results on Durrett's Probability book.

# Chapter 2. Law of Large Numbers

In this chapter the most important technique is __to convert in probability convergence to almost surely convergence__. I shall build up some major theorems.

__Theorem 2.1.21 (Kolmogorov's Extension Theorem)__ Given probability measures $\mu_n$ on $(\mathbb{R}^n, \mathcal{R}^n)$ that are consistent 

$$\mu_{n+1} ((a_1,b_1] \times \cdots \times (a_n, b_n] \times \mathbb{R}) = \mu_{n} ((a_1,b_1] \times \cdots \times (a_n, b_n])$$

Then there is a unique probability measure on $(\mathbb{R}^{\mathbb{N}}, \mathcal{R}^{\mathbb{N}})$ such that

$$P(w:w_i \in (a_i, b_i], 1\le i\le n) = \mu_n ((a_1,b_1] \times \cdots \times (a_n, b_n])$$

This theorem is important to construct i.i.d variables. Here, $(\mathbb{R}^n, \mathcal{R}^n)$ plays important role, for infinite product of different spaces, such as $\Omega_1 \times \Omega_2 \times \cdots$ Kolmogorov's Extension theorem version does not hold.

- Convergence __in probability__ : $Y_n$ converges to $Y$ in probability if for all $\epsilon > 0$, $P(\vert Y_n - Y\vert>\epsilon) \rightarrow 0$

Basic Weak Law of Large Number theorem is:

__Theorem 2.2.3__ $X_1, X_2, \cdots$ uncorrelated random variables with $\mathbb{E}X_i = \mu$ and $var(X_i)\le C < \infty$. If $S_n = X_1 +\cdots + X_n$ then $S_n /n \rightarrow \mu$ in $L^2$ and in probability.

Now, one of the most important technique follows.

## Truncation

By truncating large values, we can prove __'finite version' of theorem and then send them to infinity__ and complete the argument.

__Theorem 2.2.11__ For each $n$, $X_{n,k}$ are independent $1\le k \le n$. Let $b_n > 0$ with $b_n \rightarrow \infty$ and $$\bar{X}_{n,k} = X_{n,k} 1_{(\vert X_{n,k} \vert \le b_n)}$$. If

(1) $\sum_{k=1}^n P(\vert X_{n,k}\vert >b_n) \rightarrow 0$

(2) $b_n^{-2} \sum_{k=1}^n \mathbb{E} \bar{X}_{n,k}^2 \rightarrow 0$

If $S_n = X_{n,1} + \cdots + X_{n,n}$ and $a_n = \sum_{k=1}^n \mathbb{E} \bar{X}_{n,k}$ then

$$(S_n - a_n)/b_n \rightarrow 0$$

in probability.

This means, if __truncated parts are not large enough (1)__ and __Variance compared to some $b_n$ is small enough (2)__ then untruncated version also holds.

__Theorem 2.2.12 (Weak Law of Large Numbers)__ Let $X_1, X_2, \cdots $ be i.i.d. with 

$$xP(\vert X_i \vert > x) \rightarrow 0$$

as $x \rightarrow \infty$. Let $S_n = X_1 + \cdots + X_n$ and $\mu_n = \mathbb{E}(X_1 1_{(\vert X_1 \vert \le n)})$. Then $S_n / n - \mu_n \rightarrow 0$ in probability.

If $\mathbb{E}\vert X_i \vert < \infty$ then for $\mu = \mathbb{E} X_1$ by above theorem $S_n / n \rightarrow \mu$ in probability holds.

## Borel-Cantelli Lemma

__Borel-Cantelli Lemma is the art of probability measure__.

__Theorem 2.3.1__ If $\sum_{n=1}^{\infty} P(A_n) < \infty$ then

$$P(A_n \; i.o.) = 0$$

Borel Cantelli Lemma is the key converting __in probability argument to almost surely convergence__.

__Theorem 2.3.2__ $X_n \rightarrow X$ in probability if and only if for every subsequence $X_{n(m)}$ there is a further subsequence $X_{n(m_k)}$ that converges almost surely to $X$.

proof constructs sequence of positive numbers $\epsilon_k$ so that

$$\sum_{k=1}^{\infty} P(\vert X_{n(m_k)} - X \vert > \epsilon_k) < \infty$$

By upgrading convergence in probability to convergence almost surely, now we can prove something unnatural to prove when we have only convergence in probability.

__Theorem 2.3.4__ If $f$ is continuous and $X_n \rightarrow X$ in probability then $f(X_n) \rightarrow f(X)$ in probability. If $f$ is bounded then $\mathbb{E}(f(X_n)) \rightarrow \mathbb{E}(f(X))$

The second Borel-Cantelli lemma is opposite argument.

__Theorem 2.3.7 (Second Borel-Cantelli lemma)__ If $A_n$ are independent and $\sum P(A_n) = \infty$ then $P(A_n \; i.o.) = 1$

I want to finally note __this technique__ can be applied to other problem.

__Theorem 2.3.9__ If $A_1, A_2, \cdots$ are pairwise independent and $\sum_{n=1}^{\infty} P(A_n) = \infty$ then

$$\frac{\sum_{m=1}^n 1_{A_m}}{\sum_{m=1}^n P(A_m)} \rightarrow 1 \quad a.s.$$

proof. $X_m = 1_{A_m}$ and $S_n = X_1 + \cdots + X_n$. The Chebyshev inequality gives

$$P(\vert S_n - \mathbb{E}S_n \vert > \delta \mathbb{E}S_n) \le \frac{1}{\delta^2 \mathbb{E}S_n} \rightarrow 0$$

so $S_n / \mathbb{E}S_n \rightarrow 1$ in probability. Now we would change into almost sure convergence. $$n_k = \mathrm{inf} \{n : \mathbb{E}S_n \ge k^2 \}$$ and $T_k = S_{n_k}$. Then using Borel-Cantelli,

$$P(\vert T_k/\mathbb{E}T_k - 1 \vert > \delta \; i.o.) = 0$$

so $T_k / \mathbb{E}T_k \rightarrow 1$ almost surely, and then for such events, using monotonicity

$$\frac{T_k (\omega)}{\mathbb{E}T_{k+1}} \le \frac{S_n(\omega)}{\mathbb{E}S_n}\le \frac{T_{k+1}(\omega)}{\mathbb{E}T_k}$$

so we can interpolate intermediate terms.

## Strong Law of Large Numbers

Strong Law of Large Number uses __Truncation__ and __Borel Cantelli lemma__, as a result induces powerful consequence.

__Theorem 2.4.1 (Strong Law of Large Numbers)__ $X_1, X_2, \cdots$ pairwise independent identically distributed r.v. with $\mathbb{E}\vert X_i \vert < \infty$. Let $\mathbb{E}X_i = \mu$ and $S_n = X_1 + \cdots + X_n$ then $S_n / n \rightarrow \mu$ a.s. as $n\rightarrow \infty$

__Theorem 2.4.5__ Let $X_1, X_2, \cdots $ i.i.d with $\mathbb{E}X_i^{+} = \infty$ and $\mathbb{E}X_i^{-} < \infty$. If $S_n = X_1 + \cdots + X_n$ then $S_n / n \rightarrow \infty$ a.s.

__Theorem 2.4.9 (Glivenko-Cantelli Theorem)__ Let $F$ be the distribution of $X_i$ and $X_1,X_2,\cdots $ i.i.d. If we let $F_n(x) = \frac{1}{n} \sum_{m=1}^n 1_{(X_m \le x)}$ then

$$\mathrm{sup}_x \vert F_n(x) - F(x) \vert \rightarrow 0 \; a.s.$$

## Convergence of Random Series

Here is another approach. Previous section used Borel Cantelli and Truncation but here, __Tail Algebra__ and __Kolmogorov's maximal inequality__ plays the role.

__Tail Algebra__ $\mathcal{T} = \bigcap_n \sigma(X_n, X_{n+1}, \cdots )$ is always probability 0 or 1 (__Kolmogorov's 0-1 law__)

__Theorem 2.5.5 (Kolmogorov's maximal inequality)__ Suppose $X_1, \cdots , X_n$ are independent with $\mathbb{E} X_i = 0$ and $var(X_i) < \infty$. If $S_n = X_1 + \cdots + X_n$ then

$$P(\max_{1\le k \le n} \vert S_k \vert \ge x) \le x^{-2} var(S_n)$$ 

As a corollary, the random series converges with probability one for following situation:

__Theorem 2.5.6__ $X_1, X_2, \cdots $ independent and have $\mathbb{E}X_n = 0$. If 

$$\sum_{n=1}^{\infty} var(X_n) < \infty$$

Then with probability one, $\sum_{n=1}^{\infty} X_n(\omega)$ converges.

For truncated version, here is Kolmogorov's three-series theorem,

__Theorem 2.5.8__ $X_1, X_2, \cdots $ be independent. Let $A>0$ and let $$Y_i = X_i 1_{(\vert X_i \vert \le A)}$$. Then $\sum_{n=1}^{\infty} X_n$ converges a.s. if and only if three holds.

(1) $\sum_{n=1}^{\infty} P(\vert X_n \vert > A) < \infty$

(2) $\sum_{n=1}^{\infty} \mathbb{E} Y_n$ converges

(3) $\sum_{n=1}^{\infty} var(Y_n) < \infty$

I shall prove Exercise 2.5.10 of Durrett Probability. Here is the statement.

__Theorem (P.Levy)__ Let $X_1, X_2, \cdots$ be independent and $S_n = X_1 + \cdots + X_n$. If $\lim_{n\rightarrow \infty} S_n$ exists in probability then it also exists a.s.

This lemma is essential.

__Lemma__ $X_1, X_2, \cdots $ independent and $S_{m,n} = X_{m+1} + \cdots + X_n$ then

$$P(\max_{m<j \le n} \vert S_{m,j} \vert > 2a) \min_{m < k \le n} P(\vert S_{k,n} \vert \le a) \le P(\vert S_{m,n} \vert > a)$$

Proof : $$A_k = \{\omega : \max_{m < j \le n} \vert S_{m,j} \vert = \vert S_{m,k} \vert > 2a, \; \vert S_{m,m+1}\vert, \, \cdots , \vert S_{m, k-1}\vert \le 2a \}$$ then

$$\cup_{k=m+1}^n A_k \cap \{\omega: \vert S_{k,n}\vert \le a \} \subset \{ \vert S_{m,n} \vert > a \}$$

Each event $A_k$ and $\{\omega : \vert S_{k,n} \vert \le a \}$ are independent so Lemma holds.

Now proving the theorem, since $\lim_{n\rightarrow \infty} S_n$ exists in probability,

$$\lim_{n \rightarrow \infty} P(\vert S_n - S\vert > \epsilon)=0$$

so $\lim_{n\rightarrow} \sup_{j \ge 1} P(\vert S_{n+j} - S_n \vert \ge \epsilon) = 0$

$$
\begin{aligned}
P(\max_{1\le j\le k} \vert S_{n+j} - S_n \vert \ge \epsilon) &\le P(\vert S_{n+k}-S_n \vert \ge \epsilon/3) + \sum_{j=1}^{k-1} P((\vert S_{n+k} - S_n \vert < \epsilon/3 )\cap (\vert S_{n+j} - S_n \vert \ge \epsilon, \; \vert S_{n+i} - S_n \vert < \epsilon \; \forall i<j))\\
& \le P(\vert S_{n+k}-S_n \vert \ge \epsilon/3) + \sum_{j=1}^{k-1} P((\vert S_{n+j} - S_n \vert \ge \epsilon, \; \vert S_{n+i} - S_n \vert < \epsilon \forall i<j))P(\vert S_{n+j}-S_{n+k} \vert > \frac{2}{3} \epsilon)\\
& \le P(\vert S_{n+k}-S_n \vert \ge \epsilon/3) + \max_{1\le j\le k-1} P(\vert S_{n+k} - S_{n+j} \vert \ge \frac{2}{3} \epsilon) \\
& \le 3 \max_{0\le j\le k-1} P(\vert S_{n+j} - S_{n+k} \vert \ge \epsilon/3) \rightarrow 0
\end{aligned}$$