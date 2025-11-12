---
title: "Introduction to Smooth Manifold Ch 17~19"
collection: books
date: 2025-10-04
permalink: /books/SM4
use_math: true
tags:
- Smooth Manifold
- Book Review
- Topology
- Geometry
---

Chapter 17 to 19 gives new insight to understand vector fields. Moreover, this insight provides new view of Lie bracket operation.

# Chapter 17. Integral Curves and Flows

__Integral curve__ of $V$ smooth vector field on $M$ is smooth curve $\gamma : J \rightarrow M$ such that

$$\gamma'(t) = V_{\gamma(t)}$$

for all $t \in J$.

## The fundamental theorem of flows

__Theorem 17.8__ Let $V$ be a smooth vector field on a smooth manifold $M$. There is a unique maximal smooth flow $\theta : \mathcal{D} \rightarrow M$ whose infinitesimal generator is $V$. This flow has the following properties:

(1) For each $p \in M$ the curve $\theta^{(p)} : \mathcal{D}^{(p)} \rightarrow M$ is the unique maximal integral curve of $V$ starting at $p$.

(2) If $s \in \mathcal{D}^{(p)}$, then $\mathcal{D}^{\theta(s,p)}$ is the interval $\mathcal{D}^{(p)} - s$

(3) For each $t \in \mathbb{R}$ the set $$M_t = \{p \in M : (t,p) \in \mathcal{D} \}$$ is open in $M$ and $\theta_t : M_t \rightarrow M_{-t}$ is a diffeomorphism with inverse $\theta_{-t}$

(4) For each $(t,p) \in \mathcal{D}$, $$(\theta_t)_{*} V_p = V_{\theta_t (p)}$$


The proof uses ODE theorem.

(1) __Existence__ : $U \subset \mathbb{R}^n$ be an open set, $V : U\rightarrow \mathbb{R}^n$ is Lipshitz continuous. Let $(t_0 , x_0) \in \mathbb{R}\times U$ given. There exist an open interval $J_0 \subset \mathbb{R}$ containing $t_0$, an open set $U_0 \subset U$ containing $x_0$, and for each $x \in U_0$ a $C^1$ curve $\gamma:J_0 \rightarrow U$ satisfies

$$(\gamma^i)'(t) = V^i (\gamma(t))$$

$$\gamma^i (t_0) = x^i$$

(2) __Uniqueness__ : $U \subset \mathbb{R}^n$ an open set, and $V : U \rightarrow \mathbb{R}^n$ is Lipschitz continuous. For any $t_0 \in \mathbb{R}$, any two solutions to initial value problem are equal on theeir common domain.

(3) __Smoothness__ $U \subset \mathbb{R}^n$ is an open set and $V : U\rightarrow \mathbb{R}^n$ is Lipschitz continuous. $U_0 \subset U$ is an open set, $J_0 \subset \mathbb{R}$ is an open interval containing $t_0$, and $\theta: J_0 \times U_0 \rightarrow U$ is a map that $\gamma(t) = \theta(t,x)$ solves the initial value problem for each $x \in U_0$. If $V$ is $C^k$ for some $k \ge 0$, then $\theta$ is $C^k$.

Proof of the ODE theorem is important enough. It can be compared to the proof of implicit function theorem and inverse function theorem.

Proof Ideas:

(1) __Existence__ : Define iteration 

$$I_{\gamma}(t) = x + \int_{t_0}^t V(\gamma(s)) ds$$

by finding complete metric space and proving $I$ is contraction, fixed point is the solution

(2) __Uniqueness__ : Is direct application of the comparison lemma

(3) __Smoothness__ : Triky part. First is showing $\theta$ continuous. This is by comparison lemma. Applying comparison lemma gives jointly continuity.

Next is $C^1$. Nicely, by initial value problem statement,

$$\frac{\partial \theta^i}{\partial t} (t,x) = V^i (\theta(t,x))$$

so $\frac{\partial \theta^i}{\partial t}$ exists and continuous. Remaining part is showing $\frac{\partial \theta^i}{\partial x^j}$ exists and continuous.

First define $1\le i,j \le n$, $(\Delta_h)_j^i : \bar{J}_1 \times \bar{U}_1 \rightarrow \mathbb{R}$ be

$$(\Delta_h)_j^i (t,x) = \frac{\theta^i(t,x+he_j) - \theta^i (t,x)}{h}$$

By proving $(\Delta_h)_j^i$ converges uniformly on $\bar{J}_1 \times \bar{U}_1$ as $h \rightarrow 0$, $C^1$ version will be proved.

Taylor formula gives $t \in \bar{J}_1$, $y \in \bar{U}_1$, $v \in \bar{B}_r(0)$

$$V^i(y+v) = V^i (y) + v^k \frac{\partial V^i}{\partial y^k} (y) + v^k G_k^i (y,v)$$

then

$$\frac{\partial}{\partial t} (\Delta_h)_j^i (t,x) = \bigg(\frac{\partial V^i}{\partial y^k} (\theta(t,x)) + G_k^i (y,v) \bigg) (\Delta_h)_j^k(t,x)$$

$$\left\vert \frac{\partial}{\partial t} (\Delta_h (t,x) - \Delta_{\tilde{h}} (t,x)) \right\vert \le \mathrm{sup} \vert DV \vert \cdot \vert \Delta_h (t,x) - \Delta_{\tilde{h}}(t,x) \vert + 2\epsilon n e^{CT}$$

Now $C^k$ version is induction. $\frac{\partial \theta^i}{\partial t}$ clearly holds. Using the derivative by $t$, smoothness can be easily interpreted as new system of ODE.

## Complete Vector Field

When does the flow is global? That means, $\mathcal{D}^{(p)}$ is $\mathbb{R}$.

__Lemma 17.10 (Escape Lemme)__ $V$ be a smooth vector field on a smooth manifold $M$. If $\gamma$ is an integral curve of $V$ whose maximal domain is not all of $\mathbb{R}$, then the image of $\gamma$ cannot lie in any compact subset of $M$.

The flow need to __'Escape'__ when it is not global.

## Canonical coordinate of vector field

$V$ be a vector field on $M$, $p \in M$ is a singular point if $V_p = 0$ and regular point otherwise. If we start from singular point, $\theta^{(p)}$ will be constant curve. If we start from regular point, then $\theta^{(p)} : \mathcal{D}^{(p)} \rightarrow M$ is an immersion.

__Theorem 17.13__ Let $V$ be a smooth vector field on a smooth manifold $M$, and $p \in M$ be a regular point for $V$. There exist smooth coordinates $(u^i)$ on some neighborhood of $p$ which $V$ has the coordinate representation $\frac{\partial}{\partial u^1}$

Idea is, by choosing smooth coordinates $(x^1, \cdots, x^n)$ centered at $p$, $\theta : \mathcal{D} \rightarrow U$ the flow of $V$, the new coordinate is

$$\psi (t,u^2, \cdots, u^n) = \theta_t (0, u^2, \cdots , u^n)$$

This $\psi$ will satisfy

$$\psi_{*} : \bigg(\frac{\partial}{\partial t}\bigg\vert_{(0,0)}, \frac{\partial}{\partial u^2}\bigg\vert_{(0,0)}, \cdots, \frac{\partial}{\partial u^n}\bigg\vert_{(0,0)} \bigg) \rightarrow \bigg(V_p, \frac{\partial}{\partial x^2}\bigg\vert_{p}, \cdots, \frac{\partial}{\partial x^n}\bigg\vert_{p}\bigg)$$

## Time Dependent Vector Fields

Time Dependent Vector Field version still holds.

__Theorem 17.15 (Flows of Time-Dependent Vector Fields)__ $M$ be a smooth manifold, $V : J \times M \rightarrow TM$ be a smooth time-dependent vector field on $M$. There exist an open set $\mathcal{E} \subset J \times J \times M$ and smooth map $\theta : \mathcal{E} \rightarrow M$ such that $s \in J$ and $p \in M$, the set $$\mathcal{E}^{(s,p)} = \{t \in J : (t,s,p) \in \mathcal{E} \}$$ containing $s$ the smooth curve $\gamma : \mathcal{E}^{(s,p)} \rightarrow M$ by $\\gamma(t) = \theta(t,s,p)$ is the unique maximal solution to

$$\gamma'(t) = V(t,\gamma(t))$$

$$\gamma(s) = p$$

The proof is minor modification of proof of time independent vector field.

## Classification of 1-manifolds

Using the flow of vector fields, we can prove the classification of 1 manifolds.

