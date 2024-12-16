---
title: 抽象代数
date: 2024-10-20 14:05:17
tags:
---

《a first course in abstract algebra》里的定理和结论

- [unity](#unity)
- [binary operation](#binary-operation)
- [isomorphism](#isomorphism)
- [group](#group)
- [subgroup and cyclic group](#subgroup-and-cyclic-group)
- [permutations, coset, direct product](#permutations-coset-direct-product)
- [homomorphism and factor groups](#homomorphism-and-factor-groups)
- [group action on set](#group-action-on-set)
- [rings and fields](#rings-and-fields)
- [ideal and factor ring](#ideal-and-factor-ring)

## unity

对于一个代数结构$<A,\sigma>$, 其中$\sigma$是一个二元运算

1. 若 A 的子结构的包含 A 的单位元，则 A 的子结构的单位元等于 A 的单位元
2. $<A,\sigma>$若是一个群，则 A 的子结构的单位元等于 A 的单位元
3. $<A,+,\cdot>$若是一个整环，则 A 的子结构的乘法单位元等于 A 的乘法单位元
4. $<A,+,\cdot>$若是一个除环，则 A 的子结构的乘法单位元等于 A 的乘法单位元

## binary operation

binary operation: a function mapping $S \times S$ to $S$

1. 二元操作里的单位元唯一
2. 一个运算的单位元与这个运算的子运算的单位元不一定相等，除非子运算包含该运算的单位元
3. 二元操作里的逆元唯一

## isomorphism

isomorphism: a bijective function $\phi: S \to S'$,such that $\forall x, y \in S, \phi(x * y) = \phi(x) *' \phi(y)$

1. 同构映射将单位元映射到单位元
2. 同构映射保留交换律
3. 同构映射保留结合律
4. 同构映射保留性质 P:$a*x=b$对于所有的 a，b 有解

## group

group: a set $G$ equipped with a binary operation $*$ satisfying the following axioms:

- (Closure: $\forall a, b \in G, a * b \in G$)
- Associativity: $\forall a, b, c \in G, (a * b) * c = a * (b * c)$
- Identity element: $\exists e \in G, \forall a \in G, e * a = a * e = a$
- Inverse element: $\forall a \in G, \exists b \in G, a * b = b * a = e$

1. 群有左右消去律
2. 群中线性方程$a*x=b$和$y*a=b$有唯一解
3. 群中逆元唯一
4. 群的等价定义：封闭，结合律，左单位元存在，左逆元存在。
5. 1,2,3 阶群唯一
6. 群中幂等元唯一
7. $\forall x \in G, x*x=e$，那么 G 为交换群
8. $a*b*c=e \longrightarrow b*c*a=e$

## subgroup and cyclic group

subgroup:a subset $H \subseteq G$ that is itself a group under the operation of $G$

1. 子群判定：$\forall a,b\in H\subset G, a*b^{-1}\in H$
2. 包含 a 的最小循环子群：$a \in G, H=\{a^n|n\in \mathbb{Z}\}$
3. 同构映射将子群映射到子群
4. 同构映射将循环群映射到循环群
5. 一个群的两个子群的交也是一个子群
6. 循环群是交换群
7. 循环群的子群是循环群
8. 对于一个循环群的任意生成元 a，循环群为有限循环群等价于:$\exist m\in \mathbb{Z}_+,s.t.\ a^m=e$
9. 任何无限循环群都与$<\mathbb{Z},+>$同构；同构映射为$\phi(a^i)\rightarrow i$
10. 任何 n 阶有限循环群都与$<\mathbb{Z}_n,+_n>$同构
11. 对于一个 n 阶循环群 G,$b=a^s$, 则有 b 生成的 G 的（循环）子群含有 gcd(n,s) 个元素
12. 如果一个群只有有限个子群，则这个群只有有限个元素
13. 群 G 同构于 G 的置换群的一个子群
14. 群 G 的最小的包含$\{a_t,t\in T\,a_t\in G\}$的子群$=$$\{a_t,t\in T\,a_t\in G\}$的所有有限个元素的乘积的集合.

## permutations, coset, direct product

permutation of A: a bijective function $\phi: A \to A$

subgroup H of $S_A$ is transitive if for any $a, b \in A$, there exists $\sigma \in H$ such that $\sigma(a) = b$

1. 所有的置换构成一个群，称为对称群
2. 对称群的子群成为置换群
3. 任意一个群 A 都同构于 A 的一个置换群
4. $\{\sigma \in S_A|\sigma[B]=B\}$ 构成一个(置换)群
5. 对于任意 n>=3，对称群 S_n 是非交换群
6. 对于任意 n>=3，对称群 S_n 是非交换群,且只有恒等变换$\sigma$ 满足 for $\forall \gamma ,\sigma \gamma = \gamma \sigma$
7. 对于任意非空有限集合 A，存在一个$S_A$的循环子群 H，使得 H 是 transitive on A, 且|H|=|A|
8. 每一个有限群集合的置换群，都可以表示为多干不相交的 cycles 的并
9. 每一个有限集 A 的置换群都可以表示为若干 transpositions 的乘积
10. $\sigma \in S_n, \tau=(i,j)$,则$\tau \sigma$和$\sigma$的 orbits 数差 1
11. $S_n$的奇置换和偶置换等势
12. 若 H 为$S_n$的子群，则：H 里全是偶置换 或者 H 里的奇置换数量等于偶置换的数量。
13. $a\sim_L b\iff a^{-1}b\in H$ 是一个等价关系
14. lagrange 定理：若 G 为有限群，H 为 G 的子群，则 |H|整除|G|
15. 素数阶的群都为循环群。
16. $K\leq H \leq G$,(G:K) = (G:H) \* (H:K)
17. 任意一个群的子群的左陪集数量与右陪集数量相等。
18. 如果一个子群的陪集的数量为 2,那么每一个左陪集合都是右陪集。
19. 任意有限群的 G, $a^n=e$ for all $a \in G$.
20. n 阶有限循环群 G，若 d|n, 则 G 有唯一阶数为 d 的子群。
21. n 个群的直积是一个群。
22. $Z_m \times Z_n$是循环群且同构于$Z_{mn}$ 当且仅当 m, n 互素。$\prod_{i=1}{n}Z_{m_i}$为循环群且同构于$Z_{m_1m_2...m_n}$ 当且仅当 $m_i$ 两两互素。

## homomorphism and factor groups

a map $\phi$ of group G into G' is a homomorphism if for all $a, b \in G$, $\phi(a * b) = \phi(a) *' \phi(b)$

下面的如果没有加限定，则默认$\phi:G\rightarrow G'$是群同构,$H=Ker(\phi)$，

1. 群同态将单位元映射到单位元
2. 群同态将逆元映射到逆元
3. 群同态将子群映射到子群
4. 子群在群同态下的逆像是子群。
5. 群同态的核 H 是一个群
6. 群同态的核的左陪集等于右陪集，因此可以简称为陪集。
7. $\phi$是一个群同态，$\phi^{-1}[{\phi(a)}]=aH=Ha$,H 为$\phi$的核。
8. 群同态是单射 $\rightleftarrows$ $Ker(\phi)={e}$
9. $\phi(G)$的势等于$G$的核的陪集的集合。
10. 如果 G 是一个有限群，则$|\phi(G)|$整除$|G|$
11. 如果 G’是一个有限群，则$|\phi(G)|$整除$|G'|$
12. 循环群的群同态完全由生成元决定。
13. if |$G$|为素数，则$\phi$要么是 trivial 的，要么是单射。
14. 同态映射的复合为同态映射。
15. $\phi[G]$为交换群$\longleftrightarrow$ $\forall x, y \in G, xyx^{-1}y^{-1}\in Ker(\phi)$
16. H 的所有陪集构成一个群，称为商群(factor group),同构于$\phi[G]$
17. H 是 G 的一个子群，左陪集是良定义的当且仅当 H 是 G 的正规子群。
18. 如果 H 是 G 的一个正规子群，那么 G/H 构成一个群，称为商群或因子群。
19. 若 H 是 G 的一个正规子群，则$\gamma(x)=xH$是一个群同态，且 H 为核。
20. 若 H 是 G 的一个子群，则 xH=H 当且仅当 $x\in H$
21. 群同态基本定理：$\gamma(x)=xH$,$\mu(aH)=\phi(a)$,那么$\phi(x)=\mu(\gamma(x))$
22. 子群 H 为正规子群等价于$gHg^{-1}\in H$
23. 子群的共轭关系为等价关系。
24. 正规子群的所有陪集两两共轭。
25. $m=(G:H)$,则对于任意$a\in G$,都有$a^m\in H$
26. 正规子群的交为正规子群。
27. 如果一个有限群的某个阶的子群只有 1 个，那么这个阶的子群是正规子群。
28. 正规子群 N， 交， 一个子群 H， 是一个 H 的正规子群。
29. 如果存在所有 s 阶子群的交是一个正规子群。
30. 一个群 G 上的所有的自同构在函数复合运算下构成一个群 K，inner automorphism 是 K 的一个正规子群。
31. 使得$i_g$为恒等映射的所有 g 组成的集合是 G 的一个正规子群。
32. $G=H\times K$,$\bar{H}=\{(h,e)|h\in H\}$,则$G/ $\bar{H}$自然地同构于 K
33. 循环群的因子群是循环群。
34. 若 N 是 G 的正规子群，则$\phi[N]$是$\phi[G]$的正规子群，如果 N'是$\phi[G]$的正规子群,N'的逆像也是 G 的正规子群。
35. M 是 G 的极大正规子群$\Longleftrightarrow$G/M 是 simple 的
36. 所有的${aba^{-1}b{-1}}$生成的集合 C 是 G 的一个正规子群。如果 N 是 G 的一个正规子群，那么 G/N 可交换当且仅当$C \leq N$
37. N'是 G 的一个正规子群，则 N‘的逆像是 G 的一个正规子群。
38. G 的中心 Z(G)是 G 的一个正规子群，G 的中心是 H 的可交换子群。
39. G/Z[G]为循环群等价于 G 是交换群。
40. N 是 G 的一个正规子群，H 是 G 的一个子群，则$HN=\{nh|h\in H, n \in N\}$是一个群，且是包含 N 和 H 的最小子群。
41. M 和 N 为 G 的正规子群，则 MN 是 G 的正规子群。
42. 若 H 和 K 是 G 的正规子群且 $H\cap K={e}$,则$hk=kh,\forall h \in H,\forall k \in K$
43. H 是 G 的一个子群，则$aH=bH \Leftrightarrow b\in aH$
44. M 是 G 的正规子群，N 是 G 的子群，且$M<N$,$\phi:G\rightarrow G/M$是经典的同态映射,则$\phi[M]<\phi[N]$
45. 群同构映射将单群映射到单群

## group action on set

1. $\sigma_g=gx$是一个置换。
2. $\phi(g)=\sigma_g$是一个同态映射。
3. 若 X 是一个 G-set,那么$G_x$是一个 G 的子群。
4. $x_1 \sim x_2:\exist g,gx_1=x_2$,是一种等价关系。
5. X 是一个 G-set,Gx 是 x 的轨道，$|Gx| = (G : G_x)$
6. $Y\subset X,G_Y=\{g\in G|gy=y\ for\ all\ y \in Y\}$是 G 的一个子群。

## rings and fields

ring:

- 加法交换群
- 乘法半群
- 乘法对加法有分配律。

环同态：$\phi(a+b)=\phi(a)+\phi(b), \phi(ab)=\phi(a)\phi(b)$

如果没有额外的说明，R 表示环，0 是 R 的加法单位元

交换环：环中乘法有交换律

整环：非零、有乘法单位元、无零因子、交换环

除环:非零、有乘法单位元，每一个非 0 元素都有乘法逆元

field：交换除环

环的特征（charactristic）:环的特征（characteristic）: 对于环 R，如果存在一个最小的正整数 n，使得对于所有 a ∈ R，都有 na = 0，则称 n 为环 R 的特征。如果不存在这样的正整数 n，则称环 R 的特征为 0。

有序环：一个环 R,一个 R 的非空子集 P,满足

- $a,b\in P,a+b\in P,ab\in P$
- $a\in p,a=0,-a\in P$有且只有一个成立。

1. 0a=a0=0
2. a(-b)=(-a)b=-ab, (-a)(-b)=ab
3. 一个环的加法单位元等于乘法单位元$\Longleftrightarrow$ R={0}
4. 环同构是等价关系
5. R 的所有有乘法逆元的元素构成一个群
6. 环有乘法交换律等价于环有平方差公式$a^2-b^2=(a+b)(a-b)$
7. 给一个交换群，对群中的所有元素规定乘法$ab=0$，那么这个交换群和新规定的乘法构成一个环
8. 环中的乘法逆元是唯一的
9. 子环的交是子环，子域的交是子域
10. 环的乘法单位元不一定等于子环的乘法单位元，域中的乘法单位元等于子域中的乘法单位元。
11. 子环的等价定义：对与所有的$a,b\in S$,有$(a-b) \in S; ab \in S$
12. 线性方程组的解$\{x\in R|ax=0\}$是一个 R 的子环
13. 加法群+非 0 元素构成乘法群+乘法对加法有分配律 $\Longrightarrow$ 除环
14. 如果一个环有幂等律$a^2=a$(将这个环称为 Boolean ring),那么这个环是交换环
15. 一个集合上的幂集+对称差（加法）+交（乘法）$\Longrightarrow$ Boolean ring
16. x 是$Z_n$中的零因子$\Longleftrightarrow$x 与 n 不互素.
17. $Z_p$是无零因子环
18. 环无零因子$\Longleftrightarrow$环有（乘法）消去律。
19. 域是整环
20. 有限整环是域
21. $Z_p$是域
22. 一个非零环的特征只看乘法单位元就行。
23. 除环只有 0 和 1 两个幂等元
24. 整环的交是整环
25. 有限非零无零因子环是除环
26. 整环和除环的幂等元只有 0 和 1,即 1 是整环和除环的唯一非零幂等元。因此整环和除环的乘法单位元等于子结构的乘法单位元
27. 整环的特征等于子结构的特征，除环的特征等于子结构的特征。
28. 整环的特征是 0 或素数
29. 费马小定理：$a\in Z$,p is prime not dividing a, then $a^{p-1} \equiv 1 \mod p$.
30. $a^p \equiv a \mod p$, if p is prime
31. Euler's Theorem: For any integer a and a positive integer n that is coprime to a, $a^{\phi(n)} \equiv 1 \mod n$, where $\phi$ is Euler's totient function.
32. 一个整环同构于其商域的一个子环
33. 对于一个包含整环 D 的域 F,则 D 同构与 F 的一个子域
34. 一个环 R 上的多项式集合 R[x]仍然构成一个环，且如果 R 可交换，则 R[x]也可交换,R 非零且有单位元，则 R[x]也有单位元.
35. F 是 E 的一个子域，$\alpha$是 E 的一个元素，定义 evaluation 映射$\Phi_\alpha:F[x]\rightarrow E$, $\Phi_\alpha(f) = f(\alpha)$,估值映射是一个同态映射
36. 如果 D 是一个整环，则 D[x]也是一个整环。D[x]的乘法可逆元素只有$1$
37. R 到 R 上的所有函数组成的集合,再定义加法和乘法：$(f+g)(r)=f(r)+g(r)$，$(f \cdot g)(r) = f(r) \cdot g(r)$,那么$<R^R,+,\cdot>$是一个环
38. 域上多项式的带余数除法：f(x) = q(x)g(x) + r(x)，r(x)的阶小于 g(x)的阶
39. $a\in F$是$f(x)\in F[x]$的零点 $\Longleftrightarrow$ (x-a)是 f(x)的因子
40. 阶数为 n 非零多项式$f(x)\in F[x]$至多有 n 个零点
41. 一个域 F 的非零元素构成的乘法群$<F^*,\cdot>$的有限子群是循环群。
42. 阶数为 2 或 3 的$f(x)\in F[x]$可约等价于 f(x)有零点
43. 有序环 R 中非零元素的平方为正值，R 的 characteristic is 0,R 无零因子
44. 复数环上不能定义序，有限环上不能定义序
45. 序的等价定义：$a<b,a=b,a>b$有且只有一个成立； 如果$a<b$且$b<c$，则$a<c$；$b<c$，则 $a+b<a+c$
46. 同构映射会诱导一个序
47. D 是一个整环，P 是 D 上的正数集合，F 是 D 的商群，那么，$P'=\{x\in F|x=[(a,b)],a,b\in D,and\ ab\in P\}$是良定义的序，且$P'$是$F$上的一个正数集合，且序与 D 上的序一致，且 P'是唯一满足这中性质的序
48. R 上定义一个正数集合，S 是 R 的子环，那么$S\cap P$是子环 R 上的一个正数集合
49. R 是一个有序环，P 是 R 里的正数集，根据 P 定义小于$<$，那么有
    - $a\in P,then\ 0 < a$
    - $a,b \in P,ac=bd$,那么要么$c=d=0$,要么$cd\in P$
    - $a<b\rightarrow -b <-a$
    - $a<0,0<b,\rightarrow ab<0$
    - 如果 R 是域，那么$0<a,0<b\rightarrow 0<a/b$
    - 如果 R 是域，那么$0<a<1\rightarrow 1<1/a$
    - 如果 R 是域，那么$-1<a<0\rightarrow 1/a<-1$

## ideal and factor ring

$$
\phi:R\rightarrow R',homomorphism
$$

M 是极大正规子群$\Leftrightarrow$ 不存在正规子群 N 使得$\{0\}\leq {M} \leq N \leq G$
G 是一个单群 $\Leftrightarrow$ 不存在正规子子群 N 使得$\{0\}<N<G$

- M 是极大正规子群 $\Leftrightarrow$ G/M 是一个单群

M 是一个极大理想$\Leftrightarrow$ 不存在理想 I 使得$\{0\}\leq M < I \leq R$
R 是一个单环$\Leftrightarrow$ 不存在理想 I 使得$\{0\}<I<R$,即 R 没有非平凡的真理想

I 是交换环 R 的真理想,I 是素理想$\Leftrightarrow$ $ab\in I \rightarrow a \in I \vee b \in I$

1. 如果 R 有单位元且$Ker[\phi]$含有 R 的可逆元素,则$Ker[\phi]=R$
2. 从域到环的同态映射，要么是单射，要么同态映射把域中的每个元素映射到环的加法单位元
3. 域 F 的因子环要么是零环，要么和 F 同构
4. 理想的交还是理想
5. 域没有非平凡的真理想，即域是单环
6. 若 R 是一个交换幺环，则 M 是 R 的一个极大理想$\Leftrightarrow$R/M 是一个域
7. 若 R 是一个交换幺环，则 R 是域$\Leftrightarrow$ R 是单环
8. 若 R 是一个交换幺环，N 是 R 的真理想，则 N 是素理想$\Leftrightarrow$$R/N$是整环
9. 若 R 是一个交换幺环, 则 R 的极大理想 M 是素理想
   R 交换幺 $\Rightarrow$ $R/M$是域 $\Rightarrow$ $R/M$ 是整环 $\Rightarrow$ M 是素理想
10. $\phi(n)=n\cdot 1$ 是$Z\rightarrow R$的同态映射
11. 一个幺环的 characteristic n > 1, 则$Z_n$同构与 R 的一个子环，或 n=0,则 $Z$ 同构与 R 的一个子环
12. F 是一个域，要么 F 的 characteristic 是素数，且$Z_p$同构与 F 的一个子环
    要么 F 的 characteristic 是 0，Q 同构与 F 的一个子域
13. 若 F 是一个域，则$F[x]$的理想都是主理想
14. $F[x]$的一个理想$<p(x)>$是极大理想 $\Leftrightarrow$ $p(x)$在 F 上不可约
15. p(x)是 F[x]的不可约多项式，p 整除 r(x)s(x)，则 p(x)整除 r(x)或 p(x)整除 s(x)
16. 交换环 R 上任取一个元素$i$,则集合$\{ir|r\in R\}$是 R 的一个理想
