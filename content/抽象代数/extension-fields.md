---
title: 域拓展
date: 2024-12-11 19:19:16
tags: 域
---

## 定义

$F$和$E$是两个域，且$F\leq E$，$F[x]$是$F$上的多项式环

$\phi_a:F[x]\rightarrow E,a\in E,\phi_a(f(x))=f(a)$为估值同态映射

若$\phi_a(f(x))=f(a)=0$,则称$a$是$f(x)$的零点

可以将域$E$看作向量空间$<F,E>$(E 是交换群，F 是域，数乘运算与$E$上的乘法一致)

称$\alpha\in E$是$F\leq E$的代数元，若存在$F[x]$的非零多项式$f(x)$，使得$f(\alpha)=0$

称$\alpha\in E$是$F\leq E$的超越元，若不存在$F[x]$的非零多项式$f(x)$，使得$f(\alpha)=0$

称$E$是$F$的代数扩张，若$E$中的每一个元素都是$F$上的代数元，

若向量空间$<F,E>$是有限维的，则称$E$是$F$的有限扩域，空间的维数记作$[E:F]$

称$F$为代数闭域，若$F[x]$的每一个非零多项式都有零点

## 性质

1. $F[x]$上的理想都是主理想
2. $F[x]$的理想$<p(x)>$是极大理想 $\Leftrightarrow$ $p(x)$是不可约多项式
3. Kronecker 定理：对于任意一个$f(x)\in F[x]$，存在一个于$E\geq F \wedge a\in E$，使得$\phi_a(f(x))=f(a)=0$，即每一个$f(x)\in F[x]$都存在一个扩域使得$f(x)$有零点
4. $F\leq E \wedge \alpha \in E$,且$\alpha$是$F$上的代数元，存在不可约多项式$p(x)\in F[x]$，使得$p(\alpha)=0$
5. $\alpha \in E \geq F$是超越元 $\Leftrightarrow$ 估值同态映射$\phi_\alpha:F[x]\rightarrow E$是单射
6. 域的单拓展：
   (1) $F\leq E \wedge \alpha \in E$，且$\alpha$是$F$上的代数元，$F(\alpha)=\phi_{\alpha}[F[x]]$是$F$的单拓展
   (2) $F\leq E \wedge \alpha \in E$，且$\alpha$是$F$上的超越元，$F(\alpha)=(\phi_{\alpha}[F[x]]\text{的商域})$是$F$的单拓展
7. $F(\alpha)$的单拓展 $\Rightarrow$ $F(\alpha)$是包含$F$和$\alpha$的最小域
8. $E=F(\alpha) \wedge \alpha$是$F$上的代数元 $\wedge$ $deg(\alpha,F)=n$ $\Rightarrow$ E 中的元素可以唯一表示：$\beta = b_0+b_1\alpha+b_2\alpha^2+\cdots+b_n\alpha^n$，其中$b_i\in F$
9. $E=F(\alpha) \wedge \alpha$是$F$上的代数元,则 $E$是$F$的有限扩域
10. $E=F(\alpha) \wedge \alpha$是$F$上的代数元，且$deg(\alpha,F)=n$,则$E$是一个$n$维的$F$向量空间,基为$\{1,\alpha,\alpha^2,\cdots,\alpha^n\}$,对于任意$\beta\in E$，都有$\beta$是$F$上的代数元，且$deg(\beta,F)\leq n$,更精确地有$deg(\beta,F)\mid deg(\alpha,F)$
11. $[E:F]=1 \Leftrightarrow E=F$
12. 有限扩域都是代数扩域
13. $E$是$F$的有限扩域，$K$是$E$的有限扩域，则$K$是$F$的有限扩域，且$[K:F]=[K:E][E:F]$
14. 设$E$是$F$的代数扩域，则$E=F(\alpha_1,\alpha_2,\cdots,\alpha_n) \Leftrightarrow E$是$F$的有限扩域
15. $E$是$F$的扩域，则$\bar{F}_E=\{a\in E|a\text{是}F\text{上的代数元}\}$是$E$的子域
16. $F$是代数闭域 $\Leftrightarrow$ 每一个$F[x]$的非零多项式都有可以分解成线性因子$(x-a)$的形式
17. 若$F$是代数闭域，$E$是$F$的代数扩域，则$E=F$
18. 每一个域都有一个代数闭包(未证明)
