---
title: 绝对连续与Radon-Nikodým定理
---

## 前置

-[[测度论与概率论/符号测度]]

## 定义

- 设 $\nu, \varphi$ 都是 $\mathcal{F}$ 上的符号测度.
  - 如果对满足关系式 $\vert{}\varphi\vert{}(A) = 0$ 的每个 $A \in \mathcal{F}$, 都有 $\nu(A) = 0$, 那么称 $\nu$ 关于 $\varphi$ **绝对连续** (absolutely continuous), 记作 $\nu \ll \varphi$;
  - 如果 $\nu \ll \varphi$, 且 $\varphi \ll \nu$, 那么称 $\nu$ 与 $\varphi$ **等价** (equivalent), 记作 $\nu \sim \varphi$.

## 性质

1. 设 $\nu, \varphi$ 为 $\mathcal{F}$ 上二符号测度, 则下列各条等价:
   (i) $\nu \ll \varphi$;
   (ii) $\nu^+ \ll \varphi$, 且 $\nu^- \ll \varphi$;
   (iii) $\vert{}\nu\vert{} \ll \vert{}\varphi\vert{}$.
2. 设 $\nu, \varphi$ 为 $\mathcal{F}$ 上二符号测度, 其中 $\nu$ 有限, 则 $\nu \ll \varphi$ 当且仅当 $\forall \varepsilon > 0, \exists \delta > 0$, 只要 $A \in \mathcal{F}$ 满足 $\vert{}\varphi\vert{}(A) < \delta$, 就有 $\vert{}\nu\vert{}(A) < \varepsilon$.
