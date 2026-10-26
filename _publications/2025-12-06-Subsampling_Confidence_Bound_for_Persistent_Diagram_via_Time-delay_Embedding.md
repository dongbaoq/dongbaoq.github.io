---
title: "Topological Periodicity Test (TopPT) via Confidence Bound of Time-Delay Embeddings"
collection: publications
category: conferences
permalink: /publication/TopPT
excerpt: 
date: 2025-12-06
venue: 'NeurIPS 2026'
slidesurl: 
paperurl: 'https://arxiv.org/abs/2512.06324'
citation: 'Park, Donghyun, An, Junhyun, Kim, Taehyoung, & Kim, Jisu. (2025). "Subsampling Confidence Bound for Persistent Diagram via Time-delay Embedding." <i>arXiv preprint arXiv:2512.06324</i>.'
---

Time-delay embedding is a fundamental technique in Topological Data Analysis (TDA) for reconstructing phase-space dynamics of time-series data, where persistent homology can reveal loops associated with periodicity. However, rigorous statistical uncertainty quantification for these features remains underdeveloped. First, we analyze the topology of time-delay embeddings, showing that the embedded trajectory is homotopy equivalent to a circle (S1) for periodic signals and contractible for non-periodic ones. We also prove a positive lower bound on the embedding reach, ensuring stable topological features. Second, we develop a subsampling approach to construct confidence bounds for persistence diagrams. Under standard manifold regularity conditions, we derive data-dependent bounds with asymptotic guarantees. Finally, we propose Topological Periodicity Test (TopPT), a hypothesis testing framework for periodicity with asymptotically controlled type I and type II error rates. Experiments on bounded-error synthetic data show that raw TDA detects periodic alternatives while avoiding false rejections on structured non-periodic signals, and that the robust rule is conservative after interpolation-error correction. On PhysioNet Fantasia and BIDMC respiratory waveforms, TDA detects most records but only a subset of local windows, unlike scalar periodogram baselines.