---
title: Advanced Group Theory
date: 2024-12-12 16:59:23
tags: 群
---

## 同构定理(Isomorphism Theorems)

#### 第一同构定理(First Isomorphism Theorem)

设 $\phi: G \to G'$ 是群 $G$ 到 $G'$ 的同态，则$G/\ker [\phi] \cong \phi(G)$

#### 引理 1

$N\triangleleft G, \gamma: G \to G/N$为经典同态映射，$A=\{L\triangleleft G \mid N \leq L\},B=\{L' \triangleleft (G/N)\}$，则$\phi: A \to B = \gamma[L]$为双射

#### 引理 2

$HN = \{hn \mid h \in H, n \in N\}$
$H\vee N = \bigcap \{E\leq G \mid HN \subseteq E\}$,$H\vee N$为包含$HN$的最小子群

$N\triangleleft G,H\leq G$,则$H\vee N = HN = NH$，且若$H\triangleleft G$，则$H\vee N = HN = NH \triangleleft G$

#### 第二同构定理(Second Isomorphism Theorem)

$N \triangleleft G,H\leq G$,则$(HN)/N \cong H/(H\cap N)$

#### 第三同构定理(Third Isomorphism Theorem)

$K \triangleleft H \triangleleft G$,则$G/H \cong (G/K)/(H/K)$

#### 一些性质

$N\triangleleft G,H\leq G \Rightarrow (H\cap N) \triangleleft H$

## Series of Groups

$I=\{0,1,2,\cdots,n\}$是一个有限的指标集

称$\mathcal{G}=\{G_i \mid i \in I \wedge G_i \leq G_{i+1} \wedge G_0 = \{e\} \wedge G_n = G\}$为$G$的群列(Series of Groups)

称$\mathcal{G}=\{G_i \mid i \in I \wedge G_i \triangleleft G_{i+1} \wedge G_0 = \{e\} \wedge G_n = G\}$为$G$的次正规群列(Subnormal Series of Groups)

称$\mathcal{G}=\{G_i \mid i \in I \wedge G_i \triangleleft G \wedge G_0 = \{e\} \wedge G_n = G\}$为$G$的正规群列(Normal Series of Groups)

若$\mathcal{G_1} \subseteq \mathcal{G_2}$，则称$\mathcal{G_2}$为$\mathcal{G_1}$的加细(Refinement)

称两个次正规群列$\mathcal{G}=\{G_i\}$和$\mathcal{H}=\{H_i\}$是同构的，若存在双射$\sigma: I \to I$，使得$H_{i}/H_{i-1} \cong G_{\sigma(i)}/G_{\sigma(i) - 1}$

#### zassenhaus 引理(butterfly lemma)

$H^*$ 为 $H$ 的正规子群，$K^*$ 为 $K$ 的正规子群，则有

- $H^*(K\cap H) / H^*(H\cap K^*) \cong K^*(H\cap K) / K^*(H^*\cap K) \cong (H\cap K)/(H^* \cap K) (H \cap K^*)$

![butterfly](butterfly.jpg)

#### Schreier 定理

一个群$G$两个次正规群列有一个同构的加细

#### Jordan-Hölder 定理

称群$G$的一个次正规群列$\mathcal{G}=\{G_i\}$为合成列(Composition Series)，若$G_{i+1}/G_i$为单群
(即$G_i$是$G_{i+1}$的极大正规子群)

称群$G$的一个正规群列$\mathcal{G}=\{G_i\}$为主列(principal series,chief series)，若$G_{i+1}/G_i$为单群(simple group)

称群$G$是可解列，若$G$有一个合成列$\mathcal{G}=\{G_i\}$，且$G_{i+1}/G_{i}$为交换群

Jordan-Hölder 定理：一个群的两个合成列(主列)同构

若$G$有一个合成列(主列)，$N$是$G$的正规子群，则$G$有一个包含$N$的合成列(主列)
