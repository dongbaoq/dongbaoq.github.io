---
title: "Sliding Window for Schwartz Class"
collection: posts
date: 2025-11-14
category: Post
permalink: /posts/Sliding_Window
use_math: true
tags:
---

$f$ be the Schwartz function $\mathcal{S}(\mathbb{R})$. The Sliding Window method is

$$t \rightarrow 
\begin{pmatrix}
f(t) \\
f(t+\tau)\\
\vdots\\
f(t+N\tau)
\end{pmatrix}
$$

Mapping. Sliding window method applied to periodic function and quasi-periodic function is analyzed precisely on [1], [2].

Applying Sliding Window method to Schwartz function can be analyzed with Poisson Sumnmation Formula.

$$\begin{aligned}
\begin{pmatrix}
f(t) \\
f(t + \tau) \\
\vdots \\
f(t + N \tau)
\end{pmatrix} 
&= 
\begin{pmatrix}
\int_{\mathbb{R}} \hat{f} (\xi) e^{2\pi i \xi t} d\xi\\
\int_{\mathbb{R}} \hat{f} (\xi) e^{2\pi i \xi (t+\tau)} d\xi\\
\vdots \\
\int_{\mathbb{R}} \hat{f} (\xi) e^{2\pi i \xi (t+ N\tau)} d\xi
\end{pmatrix} \\
&= \int_{\mathbb{R}} 
\begin{pmatrix}
1\\
e^{2\pi i \xi \tau} \\
\vdots \\
e^{2\pi i \xi N \tau}
\end{pmatrix}
\hat{f} (\xi) e^{2\pi i \xi t} d\xi \\
&= \int_{\mathbb{R}} v(\xi, \tau) \hat{f} (\xi) e^{2\pi i \xi t} d\xi
\end{aligned}
$$

Notice that $v(\xi, \tau) = v(\xi + \frac{1}{\tau}, \tau)$.

$$
\begin{pmatrix}
f(t) \\
f(t + \tau) \\
\vdots \\
f(t + N \tau)
\end{pmatrix} 
= \int_{-\frac{1}{2\tau}}^{\frac{1}{2\tau}} v(\xi, \tau) \sum_{n= -\infty}^{\infty} \hat{f} (\xi + \frac{n}{\tau}) e^{2\pi i (\xi + \frac{n}{\tau})t} d\xi$$

Using Poisson summation formula,

$$
\begin{aligned}
\begin{pmatrix}
f(t) \\
f(t + \tau) \\
\vdots \\
f(t + N \tau)
\end{pmatrix} 
&= \int_{-\frac{1}{2\tau}}^{\frac{1}{2\tau}} v(\xi, \tau) \sum_{n=-\infty}^{\infty} \tau f(t+ n\tau) e^{-2\pi i \xi n\tau}\\
&= \sum_{n = -\infty}^{\infty} \tau f(t + n\tau) \int_{-\frac{1}{2\tau}}^{\frac{1}{2\tau}} v(\xi, \tau) e^{-2\pi i \xi n \tau} d\xi \\
&= \sum_{n = -\infty}^{\infty} \tau f(t + n\tau) \frac{1}{\tau}
\begin{pmatrix}
\delta_{n = 0}\\
\delta_{n = 1}\\
\vdots \\
\delta_{n = N}
\end{pmatrix} \\
&= 
\begin{pmatrix}
f(t) \\
f(t + \tau) \\
\vdots \\
f(t + N \tau)
\end{pmatrix} 
\end{aligned}
$$

Now, I want to study the structure of Sliding Window Image; it'll be a loop. For example the $f(x) = e^{-\pi x^2}$, 

![]({{ site.baseurl }}/assets/images/3D_Trajectory.png)

One method is that the analogous to periodic version analysis, we truncate the Fourier transformed $\hat{f}$. Thus, we have to analyze first for the $\hat{f}$ with compact support.

__References__

[1] Perea, J. A., & Harer, J. (2015). Sliding windows and persistence: An application of topological methods to signal analysis. Foundations of Computational Mathematics, 15(3), 799–838. https://doi.org/10.1007/s10208-014-9206-z

[2] Gakhar, H., & Perea, J. A. (2024). Sliding window persistence of quasiperiodic functions. Journal of Applied and Computational Topology, 8(1), 55–92. https://doi.org/10.1007/s41468-023-00127-9