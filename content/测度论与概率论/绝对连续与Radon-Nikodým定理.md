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
3. 设 $\nu$ 和 $\mu$ 都是 $\mathcal{F}$ 上的有限测度, $\nu \ll \mu$, 且 $\nu \neq 0$, 则存在某个 $\varepsilon > 0$ 和 $A \in \mathcal{F}$, 使得 $\mu(A) > 0$ 且 $A$ 是符号测度 $\nu - \varepsilon\mu$ 的正集.
4. 设 $\nu$ 和 $\mu$ 都是 $\mathcal{F}$ 上的测度, 令
   $$
   \mathcal{H} = \left\{ f \in \mathcal{L}^+ (\Omega, \mathcal{F}) : \text{对任意的 } A \in \mathcal{F} \text{ 都有 } \int_A f \mathrm{d}\mu \leqslant \nu(A) \right\}
   $$
   则
   (i) $\mathcal{H}$ 非空;
   (ii) 对任意的 $\{f_n, n \geqslant 1\} \subset \mathcal{H}$, 都有 $\sup_{n \geqslant 1} f_n \in \mathcal{H}$;
   (iii) 存在 $f \in \mathcal{H}$, 使得 $\int_\Omega f \mathrm{d}\mu = \alpha$, 其中
   $$\alpha = \sup \left\{ \int_\Omega g \mathrm{d}\mu : g \in \mathcal{H} \right\}. $$
