---
title: zorn引理
date: 2024-11-28 21:54:01
tags: 集合论
---

### 前置概念

偏序集、链(全序子集)、极大元、上界、严格上界

- 偏序关系：一个集合 $X$ 上的关系 $\leq$，如果满足自反性、反对称性、传递性，则称 $\leq$ 为 $X$ 上的偏序关系。
- 偏序集：一个集合 $X$ 和一个偏序关系 $\leq$ 组成的二元组 $(X, \leq)$，简记为 $X$。
- 可比较：$x$ 和 $y$ 是可比较的，如果 $x \leq y$ 或 $y \leq x$。
- 严格小于：$x < y$ 表示 $x \leq y$ 且 $x \neq y$。
- 全序：一个偏序集合 $X$ 是全序集合，如果 $X$ 中的任意两个元素都是可比较的。
- 链：偏序集的全序子集
- 极大元：称 $m \in X$ 是 $X$ 的极大元，若对于 $x \in X \wedge x \geq m \Rightarrow x = m$。
- 极小元：称 $m \in X$ 是 $X$ 的极小元，若对于 $x \in X \wedge x \leq m \Rightarrow x = m$。
- 上界：称 $u\in X$ 是 $B\subseteq X$ 的上界，若对于 $\forall x \in B$,如果 $x$ 和 $u$ 可比较，则 $x \leq u$。
- 严格上界：称 $u \in X$ 是 $B\subseteq X$ 的严格上界，若对于 $\forall x \in B$,如果 $x$ 和 $u$ 可比较，则 $x < u$。
- 良序集：一个偏序集 $X$ 是良序集，如果 $X$ 是全序集，且 $X$ 的任意非空子集都有极小元。
- 选择公理：设 $X$ 是一个集合，对于 $X$ 的任意非空子集 $Y$，都存在一个函数 $f: \mathcal{P}(X) \to X$，使得 $f(Y) \in Y$

### 前置概念的性质

- 良序集的子集也是良序集。
- 良序集合的交集是良序集合，因为良序集的交是良序集的子集。

### zorn 引理

$\textbf{Zorn's Lemma (Hausdorff Maximal Principle).}$ Suppose that $\leqslant$ is a partial order in a set $X$ and that every chain in $X$ has an upper bound. Then $X$ has a maximal element.(对于任意偏序集 $X$，如果 $X$ 的每个链都有上界，则 $X$ 有极大元。)

### 证明

待补充
