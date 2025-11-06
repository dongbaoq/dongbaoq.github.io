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

# Chapter 3. Central Limit Theorems

We move on our interest into __converge in distributions (or Weak convergence)__. In this perspective, the __characteristic function__ is important object.

## Weak Convergence

Weak convergence is defined: for sequence of distribution functions $F_n$ converges weakly to a limit $F$ if $F_n(y) \rightarrow F(y)$ for all $y$ a continuity points of $F$.

There are some equivalent statements of weak convergence.

- $X_n \Rightarrow X_{\infty}$ iff every bounded continuous function $g$, $\mathbb{E}g(X_n) \rightarrow \mathbb{E}g(X_{\infty})$
- $X_n \Rightarrow X_{\infty}$ iff $\forall G$ open, 

$$\mathrm{liminf}_{n\rightarrow \infty} P(X_n \in G) \ge P(X_{\infty} \in G)$$

- $X_n \Rightarrow X_{\infty}$ iff $\forall K$ closed, 

$$\mathrm{limsup}_{n\rightarrow \infty} P(X_n \in K) \le P(X_{\infty} \in K)$$

- $X_n \Rightarrow X_{\infty}$ iff $\forall A$ Borel set with $P(X_{\infty} \in \partial A) = 0$,

$$\mathrm{lim}_{n\rightarrow \infty} P(X_n \in A) = P(X_{\infty} \in A)$$

All these proofs use that we can construct $Y_n$ with distribution $F_n$ such that $Y_n \rightarrow Y_{\infty}$ almost surely, with $Y_{\infty}$ has distribution $F_{\infty}$.

## Tightness

In the series of distribution functions, __tightness__ condition is important to guarantee that the series converge into distribution again. If not, the general theorem "Helly's selection theorem" holds.

__Theorem 3.2.12 (Helly's selection theorem)__ For every sequence $F_n$ of distribution functions, there exists a subsequence $F_{n(k)}$ and right continuous nondecreasing $F$ that $$\mathrm{lim}_{k \rightarrow \infty} F_{n(k)} (y) = F(y)$$ at continuity points of $F$.

To guarantee that this limit is again a distribution function, 

__Theorem 3.2.13__ Every subsequential limit is the distribution function if and only if $F_n$ is __tight__. There exists $M$ for each $\epsilon > 0$ such that

$$\mathrm{limsup}_{n \rightarrow \infty} 1- F_n(M_{\epsilon}) + F_n (-M_{\epsilon}) \le \epsilon$$

## Characteristic Functions

__Characteristic Function__ is like a __key__ of distribution functions. This function __Encodes__ the distribution function and formulates problem into much easier object to handle.

First of all, the definition of the characteristic function is 

$$\varphi(t) = \mathbb{E} e^{itX}$$

We can recover the distribution function from teh characteristic function by the inversion formula.

__Theorem 3.3.11 (The Inversion Formula)__ If $a < b$ then

$$\lim_{T \rightarrow \infty} \frac{1}{2\pi} \int_{-T}^T \frac{e^{-ita} - e^{-itb}}{it} \varphi(t) dt = \mu (a,b) + \frac{1}{2} \mu (\{a, b\})$$

Or, if $\varphi$ is good : 

__Theorem 3.3.14__ If $\int \vert \varphi(t) \vert dt < \infty$, then measure $\mu$ has bounded continuous density

$$f(y) = \frac{1}{2\pi} \int e^{-ity} \varphi(t) dt$$

## Weak Convergence in Characteristic function

__This theorem is the heart of Chapter 3. Weak convergence can be encoded as function limit__

__Theorem 3.3.17 (Continuity Theorem)__ Let $\mu_n$ probability measures with characteristic functions $\varphi_n$

(1) If $\mu_n \Rightarrow \mu_{\infty}$, then $\varphi_n (t) \rightarrow \varphi_{\infty}(t)$ for all $t$.

(2) If Characteristif functions $\varphi_n(t)$ converges pointwise to a limit $\varphi(t)$ (Do not know it is characteristic funciton) and $\varphi(t)$ is continuous at 0, then $\mu_n$ __is tight and converges weakly to a measure $\mu$ which has a characteristic funtion__ $\varphi$

proof. Using the identity

$$\int_{-u}^{u} 1-e^{itx} dt = 2u - \frac{2 sin(ux)}{x}$$

$$\frac{1}{u} \int_{-u}^{u} (1-\varphi_n(t))dt = 2 \int \bigg(1-\frac{sin(ux)}{ux}\bigg) \mu_n (dx)$$

Left hand side converges as $n\rightarrow \infty$ to $\frac{1}{u} \int_{-u}^{u} 1-\varphi(t) dt$. Right hand side, when integrated on $\vert x \vert \ge 2/u$ is bigger than $$\mu_n (\{x : \vert x\vert >2/u \})$$

$$\frac{1}{u} \int_{-u}^u (1-\varphi_n (t)) dt \ge \mu_n \{x : \vert x \vert > 2/u \}$$

Now, continuity of $\varphi$ at 0 is used to bound

$$\frac{1}{u} \int_{-u}^u (1-\varphi(t))dt \rightarrow 0$$

So tightness can be shown.

Here in the proof, __smoothness of the characteristic function at 0 gives impact on the decay of distribution function__. This idea can be also found on Fourier analysis. For instance, $f$ is $C^k$ then $\hat{f}(n) = o(\vert n\vert^{-k})$.

__Theorem 3.3.18__ If $\int \vert x \vert^n \mu(dx) < \infty$ then $\varphi$ is $C^n$ with 

$$\varphi^{(n)} (t) = \int (ix)^n e^{itx} \mu(dx)$$

## Polya's Criteria

Special case of Ch.f. is when the Density function is 

$$f(x) = \frac{1-cos(x)}{\pi x^2}$$

$$\varphi(t) = (1-\vert t\vert )^+$$

Using this distribution we can verify __when does the given function $\varphi(t)$ becomes Characteristic function of some distribution__.

__Theorem 3.3.22. (Polya's criterion)__ If $\varphi(t)$ real nonnegative, $\varphi(0)=1$, $\varphi(-t) = \varphi(t)$ and $\varphi$ decreasing convex on $(0,\infty)$.

$$\lim_{t\downarrow 0} \varphi(t) = 1$$

$$\lim_{t\uparrow \infty} \varphi(t) = 0$$

Then there is a probability measure on $(0,\infty)$ so that

$$\varphi(t) = \int_{0}^{\infty} \bigg(1-\bigg\vert \frac{t}{s}\bigg\vert\bigg)^{+} \mu (ds)$$

Thus, as a continuous sum (or integral) of Ch.f.s in above formula $\varphi$ is characteristic function.

A big application of the Polya's criterion is, for the function 

$$\varphi(t) = \exp(-\vert t\vert^{\alpha})$$

__It is a characteristic function if $0 < \alpha \le 2$ but not a characteristic function if $\alpha > 2$__

Now, we shall seek on the application of characteristic functions.


## Momentum Problem

If we have all the values of $\int x^k dF(x)$ $k = 1,2,\cdots$. Then can we find $F$?

In general, the answer is no.

Counterexapmle 1, suggested by Heyde (1963) was lognormal density

$$f_0(x) = (2\pi)^{-1/2} x^{-1} \exp(-(\log x)^2/2)$$

Then $f_a(x) = f_0(x) (1+a \sin(2\pi \log x))$ have the same moments for $-1 \le a \le 1$

In this case moments are $\mathbb{E} X^n = \exp(n^2/2)$.

Counterexample 2. For $\lambda \in (0,1)$ and $-1\le a\le 1$

$$f_{a,\lambda} (x) = c_{\lambda} \exp(-\vert x\vert^{\lambda})\{1+a\sin(\beta \vert x\vert^{\lambda} \mathrm{sgn}(x))\}$$

$\beta = \tan(\lambda \pi/2)$ and $c_{\lambda}$ normalizing constant, have the same moments. In this case, moments are approximately size of $\mathbb{E} X^n \asymp \Gamma (\frac{n-\lambda-1}{\lambda})$

Here, $ln(\Gamma(z)) \sim z ln(z) -z$ so 

$$\Gamma \bigg(\frac{n}{\lambda}\bigg)^{1/n} = \exp\bigg(\frac{1}{n} ln(\Gamma(\frac{n}{\lambda}))\bigg) \sim \exp\bigg(\frac{1}{\lambda}ln(n)\bigg) = n^{1/\lambda}$$

$$\sum_{k=1}^{\infty} \frac{1}{\mathbb{E}(X^{2k})^{1/2k}} \sim \sum_{k=1}^{\infty} \frac{1}{(2k)^{1/\lambda}} < \infty$$

The criteria is determined by this formula. Which is __Carleman's condition__.

__Theorem__ If $\sum_{k=1}^{\infty} \frac{1}{\mu_{2k}^{1/2k}} = \infty$ then there is at most one distribution function $F$ with $\mu_k = \int x^k dF(x)$.

## The Central Limit Theorem

Now we are ready to focus on the central limit theorem. By our previous works, central limit theorem is an easy consequence by study of characteristic functions. __Theorem 3.3.17__ is again very powerful theorem.

__Theorem 3.4.1__ $X_1, X_2, \cdots$ i.i.d with $\mathbb{E} X_i = \mu$ and $var(X_i) = \sigma^2 \in (0,\infty)$. If $S_n = X_1 + \cdots +X_n$ then

$$(S_n - n\mu)/\sigma n^{1/2} \Rightarrow \chi$$

the standard normal distribution.

proof) Assume $\mu = 0$. $\varphi_{X_i}(t) = 1 - \frac{\sigma^2 t^2}{2} + o(t^2)$ so $\varphi_{S_n/\sigma n^{1/2}}(t) = \bigg(1-\frac{t^2}{2n} +o(n^{-1})\bigg)^n \rightarrow exp(-t^2/2)$. Which is continuous at $0$ and $exp(-t^2/2)$ is characteristic function of standard normal distribution.

As we did on the law of large numbers, we can __truncate__ the series of random variables to obtain general results.

__Theorem 3.4.10 (The Lindeberg-Feller theorem)__ $X_{n,m}$ for $1\le m\le n$ are independent r.v.s with $\mathbb{E}X_{n,m} = 0$. Suppose

(1) $\sum_{m=1}^n \mathbb{E}X_{n,m}^2 \rightarrow \sigma^2 > 0$

(2) $\forall \epsilon > 0, \, \lim_{n\rightarrow \infty} \sum_{m=1}^n \mathbb{E}(\vert X_{n,m} \vert^2 ; \vert X_{n,m} \vert > \epsilon) = 0$

Then $S_n = X_{n,1} + \cdots +X_{n,n} \Rightarrow \sigma \cdot \chi$

Remark. $X_{n,m} = X_m / n$ deduces into C.L.T theorem

proof) Again we are doing on the characteristic functions. $\varphi_{n,m}(t)$ be the characteristic function of $X_{n,m}$.

By the accurate examination formula

$$\bigg\vert e^{ix} - \sum_{m=0}^n \frac{(ix)^m}{m!} \bigg\vert \le \min \bigg(\frac{\vert x\vert^{n+1}}{(n+1)!}, \frac{2\vert x\vert^n}{n!}\bigg)$$

$$\vert \varphi_{n,m}(t) - (1-t^2 \sigma^{2}_{n,m}/2)\vert \le \mathbb{E}(\vert tX_{n,m}\vert^3 \wedge 2\vert tX_{n,m}\vert^2 ) \le \epsilon t^3 \mathbb{E}X_{n,m}^2 + 2t^2 \mathbb{E}(\vert X_{n,m}\vert^2;\vert X_{n,m}\vert > \epsilon)$$

Giving us

$$\limsup_{n \rightarrow \infty}\sum_{m=1}^n \vert \varphi_{n,m}(t) - (1-t^2 \sigma^{2}_{n,m}/2)\vert \le \epsilon t^3 \sigma^2$$

So 

$$\prod_{m=1}^n \varphi_{n,m}(t) - exp(-t^2 \sigma^2/2) \rightarrow 0$$

Using this truncation technique, we can handle infinite variance cases. See Example 3.4.13 of Durrett's Probability book.

So when does the truncation technique can be used on? Gnedenko and Kolmogorov found the necessary and sufficient condition.

__Theorem 3.4.14__ $X_1, X_2, \cdots$ be i.i.d. $S_n = X_1 + \cdots + X_n$. There exists $a_n, b_n > 0$ that $(S_n - a_n)/b_n \Rightarrow \chi$ if and only if as $y \rightarrow \infty$

$$\frac{y^2 P(\vert X_1 \vert > y)}{\mathbb{E}(\vert X_1 \vert^2 ; \vert X_1 \vert \le y)} \rightarrow 0$$

## Local Limit Theorem

We can classify characteristic functions into three classes.

(1) $\varphi \equiv 1$ : point mass

(2) $\vert \varphi(\lambda) \vert = 1$ for some $\lambda$ but not all : Lattice distribution

(3) $\vert \varphi \vert <1$

In the case of lattice distribution, we can argue on the all supports ; lattices that probability distribution of $S_n$ converges to normal distribution.

__Theorem 3.5.3__ If $X_1, X_2, \cdots $ i.i.d with $\mathbb{E} X_i = 0$, $\mathbb{E} X_i^2 = \sigma^2 \in (0,\infty)$ having a common lattice distribution $X_i \in b + h\mathbb{Z}$. Then for $p_n(x) = P(S_n / \sqrt{n} = x)$ the discrete probability whose support being $$\{(nb+hz)/\sqrt{n}: z\in \mathbb{Z}\}$$ converges uniformly to normal distribution probability density : $n(x) = \frac{1}{\sqrt{2\pi} \sigma} exp(-x^2 /2\sigma^2)$

$$\sup_{x \in \{(nb+hz)/\sqrt{n} : z\in\mathbb{Z}\}} \bigg\vert \frac{\sqrt{n}}{h} p_n(x) - n(x) \bigg\vert \rightarrow 0$$

Actually, the same holds for non-lattice case.

# Chapter 4. Martingales

