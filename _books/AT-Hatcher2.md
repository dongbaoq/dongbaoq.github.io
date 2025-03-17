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

Homology : definition and technique
========

## Relative Homology

Relative homology defined as $H_n (X,A)$ is interpreted as following:

It is represented by relative cycle $\varphi \in C_n (X)$ that $\partial \varphi \in C_n (A)$. So draw an image cycle whose boundary belongs to $A$.

This relative cycle is trivial if $\varphi = \partial \psi + \varphi^{A}$ where $\psi \in C_{n+1} (X)$, $\varphi^{A} \in C_{n} (A)$.

Homology is hard to imagine what it states for. It's because homology is the form $ker \partial / im \partial$. We need to imagine homology by specific cycle which is much easier to believe. Only aware of the fact that there are several other cycles that match with the cycle by equivalent class.

## Techniques for Calculating Homology

Calculation of homology depends on some techniques. Major one is 'Mayer Vietoris'

### Mayer Vietoris

Mayer Vietoris argument is useful because **We know all maps in exact sequence**

$$ \cdots H_n (A \cap B) \xrightarrow{(i_{1*}, i_{2*})} H_n (A) \oplus H_n (B) \xrightarrow{j_{1*} - j_{2*}} H_n (X) \xrightarrow{\partial_{*}} H_n (A \cap B) \cdots $$