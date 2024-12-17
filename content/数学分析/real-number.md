---
title: 实数构造与度量空间完备化
date: 2024-12-15 14:32:59
tags: 数学分析
---

假设人类已经学会了朴素自然数和朴素集合论

- [皮亚诺公理(Peano Axioms)](#皮亚诺公理peano-axioms)
    - [皮亚诺公理](#皮亚诺公理)
    - [自然数加法](#自然数加法)
    - [自然数的上的偏序关系](#自然数的上的偏序关系)
      - [强归纳法](#强归纳法)
    - [自然数乘法](#自然数乘法)
    - [自然数整数次幂](#自然数整数次幂)
    - [总结](#总结)
    - [自然数是一个良序性](#自然数是一个良序性)
- [整数](#整数)
    - [整数加法](#整数加法)
    - [整数乘法](#整数乘法)
    - [整环](#整环)
    - [有序环](#有序环)
- [有理数](#有理数)
    - [有理数加法](#有理数加法)
    - [有理数乘法](#有理数乘法)
    - [有序域](#有序域)
    - [有理数中定义范数(绝对值)、距离度量](#有理数中定义范数绝对值距离度量)
- [实数](#实数)
    - [有理数中的柯西列](#有理数中的柯西列)
    - [实数加法](#实数加法)
    - [实数乘法](#实数乘法)
    - [有序域](#有序域-1)

## 皮亚诺公理(Peano Axioms)

#### 皮亚诺公理

- $0$ is a natural number.
- If $n$ is a natural number, then $n++$ is also a natural number.
- $0$ is not the successor of any natural number; i.e., we have $n++ \neq 0$ for every natural number $n$.
- Different natural numbers must have different successors; i.e., if $n, m$ are natural numbers and $n \neq m$, then $n++ \neq m++$. Equivalently, if $n++ = m++$ then we must have $n = m$.
- Principle of mathematical induction. Let $P(n)$ be any property pertaining to a natural number $n$. Suppose that $P(0)$ is true, and suppose that whenever $P(n)$ is true, $P(n++)$ is also true. Then $P(n)$ is true for every natural number $n$.

自然数集$\mathbb{N}=\{n \mid n \text{ is a natural number}\}$

$\textbf{Recursive definitions}$. Suppose for each natural number $n$, we have some function $f_n : \mathbb{N} \to \mathbb{N}$ from the natural numbers to the natural numbers. Let $c$ be a natural number. Then we can assign a unique natural number $a_n$ to each natural number $n$, such that $a_0 = c$ and $a_{n++} = f_n (a_n)$ for each natural number $n$.

证明：

首先，对于$n\not=0$,根据 Peano 公理有$n++\not=0$,所以$a_0$没有被重新定义，即$a_0$唯一

其次，设$a_n$唯一，若$a_{n++}$不唯一，即$m++ = n++$,根据 Peano 公理有$m=n$，所以$a_{n++}$唯一

最后，根据数学归纳法，对所有的自然数$n$，$a_n$唯一

#### 自然数加法

自然数加法$f(n,m):\mathbb{N}\times \mathbb{N}\to \mathbb{N}$,将$f(n,m)$记作$n+m$

- $\textbf{Addition of natural numbers}$. Let $m$ be a natural number. To add
  zero to $m$, we define $0 + m := m$. Now suppose inductively that we have defined how
  to add $n$ to $m$. Then we can add $n++$ to $m$ by defining $(n++) + m := (n + m)++$.

说明:

对与任意一个自然数 $m$

首先，我们定义了 $f(0,m)=m$,根据 Peano 公理有$n++ \not= 0$，所以$f(0,m)$唯一

其次假设我们已经唯一定义了$f(n,m)$,那么我们定义$f(n++,m)=(f(n,m))++$，假设定义不唯一，根据 Peano 公理有$n++=m++$，所以$n=m$，所以$f(n++,m)$被唯一定义

最后，根据数学归纳法，对所有的自然数 $n$，$f(n,m)$被唯一定义。

$\textbf{Lemma}$. For any natural number $n$, $n + 0 = n$. 可对$n$使用数学归纳法证明。

$\textbf{Lemma}$. For any natural numbers $n$ and $m$, $n + (m++) = (n + m)++$.
证明：

对$n$使用数学归纳法

$n=0$,$f(0,m++)=m++=f(0,m)++$

假设$f(n,m++)=f(n,m)++$成立

那么$f(n++,m++)=f(n,m++)++=(f(n,m)++)++=f(n++,m)++$

根据数学归纳法，对所有的自然数都有$f(n,m++)=f(n,m)++$成立

$\textbf{Lemma}$. For any natural numbers $n$ and $m$, $n + m = m + n$. 可固定其中一个数，对另一个数使用数学归纳法。

$\textbf{Lemma}$. For any natural numbers $a$, $b$, $c$, we have $(a + b) + c = a + (b + c)$. 可对$c$使用数学归纳法证明。

$\textbf{Lemma}$. Let $a$, $b$, $c$ be natural numbers such that $a + b = a + c$. Then we have $b = c$. 可对$a$使用数学归纳法证明。

$\textbf{Definition}$. A natural number $n$ is said to be positive iff it is not equal to 0.

$\textbf{Proposition}$. If $a$ is a positive natural number, and $b$ is a natural number, then $a + b$ is positive. 对$b$使用数学归纳法证明。

$\textbf{Corollary}$. If $a$ and $b$ are natural numbers such that $a + b = 0$, then $a = 0$ and $b = 0$.

$\textbf{Lemma}$. Let $a$ be a positive number. Then there exists exactly one natural number $b$ such that $b++ = a$.

令$P(n):(n\not=0)\rightarrow (\text{存在唯一的自然数}b\text{使得}b++=a)$

$n = 0$ 时， $P(0)$空真

假设 $P(n)$成立，即存在唯一的自然数$b$使得$b++=a$

那么$n++$时，假设$c++=a++$（$c$的存在性显然，因为$a++=a++$）,则有$a++=c++=(b++)++$,根据 Peano 公理有$c=b++$，所以存在唯一的自然数$b++$使得$b++=a++$

根据数学归纳法，P(n)对所有自然数 n 成立

#### 自然数的上的偏序关系

$\textbf{Ordering of the natural numbers}$. Let $n$ and $m$ be natural numbers. We say that $n$ is greater than or equal to $m$, and write $n \geq m$ or $m \leq n$, iff we have $n = m + a$ for some natural number $a$. We say that $n$ is strictly greater than $m$, and write $n > m$ or $m < n$, iff $n \geq m$ and $n \not= m$.

$\textbf{Proposition}$. Let $a, b, c$ be natural numbers. Then

- (Order is reflexive) $a ≥ a$.
- (Order is transitive) If $a ≥ b$ and $b ≥ c$, then $a ≥ c$.
- (Order is antisymmetric) If $a ≥ b$ and $b ≥ a$, then $a = b$.
- (Addition preserves order) $a ≥ b$ if and only if $a + c ≥ b + c$.
- $a < b$ if and only if $a++ ≤ b$.
- $a < b$ if and only if $b = a + d$ for some positive number $d$.
- $a <= b$ and $c < d$ $\Rightarrow$ $a+c < b+d$

可以根据定义和上面已有的性质证明。

$\textbf{Proposition}$. Let $a$ and $b$ be natural numbers. Then exactly one of the following statements is true: $a < b$, $a = b$, or $a > b$.

证明：对$b$使用数学归纳法 $P(b):$假设$a<b$和$a=b$都不成立，我们证明一定有$a>b$

$b=0$时，$a=a+0$，所以$a\geq0$,根据假设$a\not=0$，所以$a>0$

假设$b=n$时,$P(b)$成立

$b=n++$时，因为$a>b$,所以$a\geq n++$,根据假设有$a\not=n$，所以$a>n$

根据数学归纳法，对所有的自然数$b$，$P(b)$成立

##### 强归纳法

$\textbf{Lemma}$.$n++>n$. 因为 $n++=n+++0=(n+0)++=n+(0++)$

$\textbf{Lemma}$ 不存在自然数 m 和 n，使得$n<m<n++$

反证，若$n<m$,则$m = n + d = (n++) + e$,其中 $d>0$,$e \leq 0$,所以$m>n++$

与自然数上的偏序关系的三分性矛盾

$\textbf{Strong principle of induction}$. Let $m_0$ be a natural number, and let $P(m)$ be a property pertaining to an arbitrary natural number $m$. Suppose that for each $m \geq m_0$, we have the following implication: if $P(m')$ is true for all natural numbers $m_0 \leq m'  < m$, then $P(m)$ is also true. (In particular, this means that $P(m_0)$ is true, since in this case the hypothesis is vacuous.) Then we can conclude that $P(m)$ is true for all natural numbers $m \geq m_0$.

定义 $Q(n)$：$P(m)$ is true for all $m_0 \leq m < n$

当$n\leq m_0$是，Q(n)空真，因此 Q(0)成立

假设$Q(n)$成立，即$P(m)$对所有$m_0 \leq m < n$成立

根据强归纳法的条件（if $P(m')$ is true for all natural numbers $m_0 \leq m'  < m$, then $P(m)$ is also true.）有$P(n)$成立

集合$A=\{m\in \mathbb{N}\mid m_0 \leq m < n++\}=\{m\in \mathbb{N}\mid m_0 \leq m < n\}\cup\{n\}$

根据强归纳法的条件，P(m)对所有$m\in A$成立

根据数学归纳法，Q(n)对所有自然数$n$成立

#### 自然数乘法

$g(n,m): \mathbb{N}\times \mathbb{N}\to \mathbb{N}$，将$g(n,m)$记作$n\times m$或$nm$或$n\cdot m$

$\textbf{Multiplication of natural numbers}$. Let $m$ be a natural number. To multiply zero to $m$, we define $0 \times m := 0$. Now suppose inductively that we have defined how to multiply $n$ to $m$. Then we can multiply $n++$ to $m$ by defining $(n++) \times m := (n \times m) + m$

$\textbf{Lemma}$. For any natural number $n$, $n \times 0 = 0$. 可对$n$使用数学归纳法证明。

$\textbf{Lemma}$. For any natural numbers $n$ and $m$, $n \times (m++) = (n \times m) + n$. 可对$n$使用数学归纳法证明。

$\textbf{Lemma}$. Let $n, m$ be natural numbers. Then $n \times m = m \times n$. 可固定$m$对$n$使用数学归纳法证明。

$\textbf{Lemma}$. Let $n, m$ be natural numbers. Then $n \times m = 0$ if and only if at least one of $n, m$ is equal to zero. In particular, if $n$ and $m$ are both positive, then $nm$ is also positive.

$\Rightarrow$使用反证法

$\Leftarrow$使用定义

$\textbf{Proposition}$. For any natural numbers $a, b, c$, we have $a(b + c) = ab + ac$ and $(b + c)a = ba + ca$. 可对$a$使用数学归纳法证明。

$\textbf{Proposition}$. For any natural numbers $a, b, c$, we have $(a \times b) \times c = a \times (b \times c)$. 可对$c$使用数学归纳法证明。

$\textbf{Proposition}$. If $a, b$ are natural numbers such that $a < b$, and $c$ is positive, then $ac < bc$. 使用定义证明。

$\textbf{Corollary}$. Let $a, b, c$ be natural numbers such that $ac = bc$ and $c$ is non-zero. Then $a = b$. 使用上面的命题证明。

$\textbf{Proposition}$. Let $n$ be a natural number, and let $q$ be a positive number. Then there exist natural numbers $m, r$ such that $0 \leq r < q$ and $n = mq + r$. 并且$m$和$r$唯一。

存在性对$n$使用数学归纳法

唯一性的证明,设$n=m_1q+r_1=m_2q+r_2$,对$r_1$和$r_2$分类讨论

若$r_1 = r_2$,则根据加法消去律，有$m_1q=m_2q$，$q\not=0$，根据乘法消去律有$m_1=m_2$

若$r_1 = r_2$,不妨设$r_1 < r_2$，则$r_2 = r_1 + d$,其中$d\not=0$，则有$m_1q+r_1=m_2q+r_1+d$，根据加法消去律有$m_1q=m_2q+d$，所以$m_1q > m_2q$，因为$q\not=0$，根据乘法消去律有$m_1>m_2 \Leftarrow$ $m_1 \geq (m_2++)$

$n=m_1q + r_1 > (m_2++)q + r_1 = m_2q + r_1 + q > m_2q + r_2 = n$,矛盾

#### 自然数整数次幂

$\textbf{Definition}$. Let $m$ be a natural number. To raise $m$ to the power $0$, we define $m^0 := 1$; in particular, we define $0^0 := 1$. Now suppose recursively that $m^n$ has been defined for some natural number $n$, then we define $m^{n++} := m^n \times m$.

#### 总结

由以上讨论知：

- 自然数加法有结合律，自然数乘法有结合律
- 自然数乘法对加法有分配律
- 自然数加法有单位元$0$，乘法有单位元$1=(0++)$

因此自然数加法为交换幺半群，自然数乘法为乘法幺半群

$<\mathbb{N},+,\cdot>$不构成一个环

#### 自然数是一个良序性

$\textbf{Lemma}$. 对于任意$n \in \mathbb{N},S=\{m \in \mathbb{N}|m \leq n\}$，$S$为有限集

$n=0$时，$S=\{0\}$，是有限集

假设$n=k$时，$S$为有限集

则$n=k++$时，$S=\{m \in \mathbb{N}|m \leq k\} \cup \{k++\}$，是有限集

根据数学归纳法，对于任意$n \in \mathbb{N},S=\{m \in \mathbb{N}|m \leq n\}$，$S$为有限集

$\textbf{Lemma}$. $\mathbb{N}$中不存在无穷严格递减序列。由$S=\{m \in \mathbb{N}|m \leq n\}$为有限集易得。

$\textbf{Lemma}$. $\mathbb{N}$为良序集。

由$<$的三分性可得$\mathbb{N}$是全序集

假设$\mathbb{N}$不是良序集，则$\mathbb{N}$中存在无穷严格递减序列，矛盾。

## 整数

$A = \mathbb{N}\times \mathbb{N}$

在$A$上定义关系$(a,b)\sim _- (c,d)$当且仅当$a+d=b+c$

$\textbf{Lemma}$. $\sim _-$是等价关系. 使用定义证明等价关系的自反性、对称性和传递性

等价关系的所有等价类组成的集合是$\mathbb{N}$的一个划分，记作$\mathcal{A}$

$(a,b)$的等价类记作$[(a,b)]$,简记为$[a,b]$

#### 整数加法

在等价类上定义加法

$[a,b] + [c,d] = [a+c,b+d]$

在集类(集合的集合)上定义加法需要说明良定义性，即等价类之间的运算不依赖与等价类的表示方式，只依赖与集合内包含哪些元素。

假设$(e,f)\sim _- (a,b)$和$(g,h)\sim _- (c,d)$，需要证明$[e+g,f+h]= [a+c,b+d]$，可以根据定义证明。

根据上述加法的定义，可以证明上述加法具有以下性质

- 加法结合律
- 加法交换律
- 加法单位元$[0,0]$
- 加法逆元$[a,b]$的加法逆元为$[b,a]$

因此$<\mathcal{A},+>$构成一个交换群

note: 需要验证加法逆元的良定义性，若$[a,b]=[c,d]$,则$[b,a]=[d,c]$,即若两个数表示的等价类相等，则它们的加法逆元表示的等价类也相等

#### 整数乘法

在等价类上定义乘法

$[a,b] \times [c,d] = [ac+bd,ad+bc]$

在集类上定义乘法需要说明良定义性，即等价类之间的运算不依赖与等价类的表示方式，只依赖与集合内包含哪些元素。

假设$(e,f)\sim _- (a,b)$和$(g,h)\sim _- (c,d)$，需要证明$[ac+bd,ad + bc] = [eg+fh,eh+fg]$

提示：证明 $[a,b] \times [c,d] = [ac+bd,ad+bc] = [ec+fd,ed+fc] = [e,f] \times [c,d]$ When $[a,b]= [e,f]$，另一侧的良定义性同理。

#### 整环

根据定义可以证明上述乘法具有以下性质

- 乘法结合律
- 乘法交换律
- 乘法单位元$[1,0]=[0++,0]$
- 乘法对加法的分配律

$\textbf{Lemma}$. $<\mathcal{A},+,\times>$构成一个交换幺环

$\textbf{Proposition}$. (Integers have no zero divisors) Let a and b be integers such that
ab = 0. Then either a = 0 or b = 0 (or both).

$\textbf{Lemma}$. $\mathcal{A}$中任意元素都可以写为$[(a,0)]$或$[(0,a)]$的形式，$a$为自然数

证明：

对于任意$[c,d]$，分类讨论，若$c\geq d$，则$c=d+e$，$e$为自然数，则$[c,d]=[d+e,d]=[e,0]$. 若$c<d$，则$d=c+e$，$e$为自然数，则$[c,d]=[c,c+e]=[0,e]$

将$[a,0]$记作$a$，将$[0,a]$记作$-a$，将$[0,0]$记作$0$，则$\mathcal{A}$中的元素可以表示为$a$或$-a$，其中$a$为自然数

$\textbf{Definition}$. $i(n):N \to \mathcal{A}$，$i(n)=[n,0]$

$i(m+n)=[m+n,0]=[m,0]+[n,0]=i(m)+i(n)$

$i(mn)=[mn,0]=[m,0][n,0]=i(m)i(n)$

因此$i$是$\mathbb{N}$到$\mathcal{A}$的同态映射

若$i(m)=i(n)$，则$[m,0]=[n,0]$，即$m=n$，因此$i$是单射

因此$i$是$\mathbb{N}$到$\mathcal{A}$的子集$\{[n,0] \mid n \in \mathbb{N}\}$的同构映射

$\textbf{Proposition}$. (Integers have no zero divisors) Let a and b be integers such that
$ab = 0$. Then either $a = 0$ or $b = 0$ (or both).

反证：$[a,b]\not=[0,0]$且$[c,d]\not=[0,0]$时，$[a,b][c,d]=[0,0]$

$[a,b][c,d]=[ac+bd,ad+bc]=[0,0] \Rightarrow ac+bd=0 \text{且} ad+bc=0$

因此$ac=bd=ad=bc=0$，因此有 $(a(c+d)=b(c+d))$

$c\not=d \Rightarrow c+d\not= 0 $, 所以使用消去律得到$ a=b=0$

$\textbf{Lemma}$. $<\mathcal{A},+,\times>$构成一个整环(非零+无零因子+交换+幺环)

使用加法逆元定义减法

$[a,b]-[c,d]=[a,b]+[d,c]=[a+d,b+c]$

(抽象代数)环有以下性质

- $0a=a0=0$
- $a(-b)=(-a)b=-ab, (-a)(-b)=ab$
- 一个环的加法单位元等于乘法单位元$\Longleftrightarrow$ R={0}
- R 的所有有乘法逆元的元素构成一个群
- 无零因子环有消去律

至此将$<\mathcal{A},+,\times>$记作$<\mathbb{Z},+,\times>$

#### 有序环

$\textbf{Proposition}$. (Trichotomy of integers). Let x be an integer. Then exactly one of the following three statements is true: (a) x is zero; (b) x is equal to a positive natural number n; or (c) x is the negation −n of a positive natural number n.

根据三分性和整数加法与乘法的定义，我们可以构造一个有序环。

首先规定一个正数(positive integer)集合$P=\{x \in \mathbb{Z} \mid \text{存在非零自然数n使得}x=[n,0]\}$

容易验证 P 满足有性质

- $\forall x,y \in P, x+y \in P,xy \in P$
- $\forall x \in \mathbb{Z}, x \in P, x=0 , -x \in P$三者有且只有一个成立

根据抽象代数里有序环的性质，我们可以定义偏序关系$x < y \Leftrightarrow y-x \in P$, 可以证明$<$有如下性质

- Trichotomy: $x < y, x=y, x>y$三者有且只有一个成立
- Transitivity: $x<y,y<z \Rightarrow x<z$
- Addition preservation: $x<y \Rightarrow x+z<y+z$
- Multiplication preservation: $x<y,z>0 \Rightarrow xz<yz$
- Negation reverses order: $a > b \Rightarrow -a < -b$

$\textbf{Lemma}$. $n++=n+(0++)=n+1$

$\textbf{Lemma}$. $x\in P \Rightarrow x >= 1=0++$

$\textbf{Definition}$. 若一个有序环$R$满足如下性质则称该环为 Archimedean(阿基米德)环

- 对任意$x,y \in R$，$x>0,y>0 \Rightarrow \exists n \in \mathbb{Z} \text{使得} nx>y$

$\textbf{Lemma}$. $\mathbb{Z}$是 Archimedean 环

反证法：假设对任意$x,y \in \mathbb{Z}$，$x>0,y>0 \Rightarrow \neg \exists n \in \mathbb{Z} \wedge n>0 \text{使得} nx>y$

即对$\forall n \in \mathbb{Z} \wedge n>0$，$nx< y$ or $nx=y$

若对于某个$n$, nx=y,则$(n+1)x=nx+x=y+x>y$, 矛盾

因此必须有$nx<y$对所有$n\in \mathbb{Z} \wedge n>0$成立

但是 $y-yx=y(1-x)\leq 0$，即$n=y$使得$nx\geq y$，矛盾

$\textbf{Lemma}$. 若$n,m \in \mathbb{N}$，$n>m$，则$i(n)=[n,0]>[m,0]=i(m)$

$\textbf{Lemma}$. 非空$X\subseteq \mathbb{Z}$且$X$在$\mathbb{Z}$中的有下界，则$X$中不存在无穷严格递减序列

假设$X$存在无穷严格递减序列$x_0>x_1>x_2>\cdots \geq m$,$m$ 为$X$的一个下界

使用数学归纳法可证明对于任意的$n\in \mathbb{Z} \wedge n \geq 0$，有$x_0>m+n$

因为$Z$是阿基米德环，所以存在$k\in Z \wedge k > 0$使得 $k > max(x_0,m)$

$k$ 可以表示为$k=m+d$,$d\in \mathbb{Z} \wedge d>=0$, 矛盾。

$\textbf{Lemma}$. 非空$X\subseteq \mathbb{Z}$且$X$在$\mathbb{Z}$中的有下界，则$X$中存在最小元素, 否则$X$中存在无穷严格递减序列

## 有理数

因为$\mathbb{Z}$是整环，所以我们可以构造一个整环的商域(The Field of Quotients of an Integral Domain)

$B = \mathbb{Z}\times (\mathbb{Z}\setminus \{0\}) = \{(a,b) \mid a,b \in \mathbb{Z}, b\not=0\}$

在$B$上定义$(a,b)\sim_{/} (c,d)$当且仅当$ad=bc$

$\textbf{Lemma}$. $\sim_{/}$是等价关系

等价关系$\sim_{/}$的所有等价类组成的集合是$\mathbb{Z}$的一个划分，记作$\mathcal{B}$

类似于构造整数的过程，$(a,b)$的等价类记作$[(a,b)]$，简记为$[a,b]$，这里的$a$和$b$是整数而不是自然数

#### 有理数加法

在等价类上定义加法

$[a,b] + [c,d] = [ad+bc,bd]$

因为$b$和$d$不为零，所以$bd$不为零，因此$[ad+bc,bd]$是$\mathcal{B}$中的元素

在集类上定义加法需要说明良定义性，即等价类之间的运算不依赖与等价类的表示方式，只依赖与集合内包含哪些元素。

假设$(e,f)\sim_{/}(a,b)$和$(g,h)\sim_{/}(c,d)$，需要证明$[ad+bc,bd]=[eg+fh,fh]$

容易验证按上述方式定义的加法具有如下性质：

- 加法交换律
- 加法结合律
- 加法单位元$[0,1]=[0,b]$，$1$为整环的乘法单位元,$b$为整环中的非零元素
- 加法逆元$[a,b]$的加法逆元为$[-a,b]$

因此$<\mathcal{B},+>$构成一个交换群

note: 需要验证逆元的良定义性，即若两个数表示的等价类相等，则它们的逆元表示的等价类也相等

#### 有理数乘法

在等价类上定义乘法

$[a,b] \times [c,d] = [ac,bd]$

验证良定义：假设$(e,f)\sim_{/}(a,b)$和$(g,h)\sim_{/}(c,d)$，需要证明$[ac,bd]=[eg,fh]$，可按定义证明。

容易验证按上述方式定义的乘法具有如下性质：

- 乘法交换律
- 乘法结合律
- 乘法单位元$[1,1]=[c,c]$，$1$为整环的乘法单位元,$c$为整环中的非零元素
- 乘法逆元，若$[a,b]\not=[0,1]$，则$[a,b]$有乘法逆元$[b,a]$
- 乘法对加法的分配律

因此$<\mathcal{B},+,\times>$构成一个交换除环，即域。

note: 需要验证逆元的良定义性，即若两个数表示的等价类相等，则它们的逆元表示的等价类也相等

$\textbf{Definition}$. 令$i(n):N \to \mathcal{A}$，$i(n)=[n,1]$

$i(m+n)=[m+n,1]=[m,1]+[n,1]=i(m)+i(n)$

$i(mn)=[mn,1]=[m,1][n,1]=i(m)i(n)$

因此$i$是$\mathbb{N}$到$\mathcal{B}$的同态映射

若$i(m)=i(n)$，则$[m,1]=[n,1]$，即$m=n$，因此$i$是单射

因此$i$是$\mathbb{N}$到$\mathcal{B}$的子集$\{[n,1] \mid n \in \mathbb{N}\}$的同构映射

#### 有序域

$\textbf{Lemma}$. $[a,b]=[-a,-b]$

$\textbf{Lemma}$. $\mathcal{B}$中任意元素都可以写为$[a,b]$的形式，其中$a,b$为整数，$b>0$.

$\textbf{Definition}$. $P=\{x \in \mathcal{B} \mid \exists a,b \in \mathbb{Z}, a,b>0 \text{使得} x=[a,b]\}$

容易验证$P$满足如下性质

- $\forall x,y \in P, x+y \in P,xy \in P$
- $\forall x \in \mathcal{B}, x \in P, x=0 , -x \in P$三者有且只有一个成立

$\textbf{Lemma}$. 域是环

根据抽象代数里有序环的性质，我们可以定义偏序关系$x < y \Leftrightarrow y-x \in P$, $<$有如下性质

- Trichotomy: $x < y, x=y, x>y$三者有且只有一个成立
- Transitivity: $x<y,y<z \Rightarrow x<z$
- Addition preservation: $x<y \Rightarrow x+z<y+z$
- Multiplication preservation: $x<y,z>0 \Rightarrow xz<yz$
- Negation reverses order: $a > b \Rightarrow -a < -b$

因为$\mathcal{B}$是域，所以有以下性质

- $a>0 \Leftrightarrow a^{-1}>0$
- $0<a,0<b\rightarrow 0<a/b$
- $0<a<1\rightarrow 1<1/a$
- $-1<a<0\rightarrow 1/a<-1$

至此将$<\mathcal{B},+,\times>$记作$<\mathbb{Q},+,\times>$

$\textbf{Lemma}$. $[a,1] \geq [a,b]$ for $a,b \in Q \wedge a,b > 0$

$\textbf{Lemma}$. 对于任意一个 Q 中的正数，都可以找到一个 Z 中的正数，使得

$\textbf{Lemma}$. $\mathbb{Q}$是一个 Archimedean 环，即对任意$x,y \in \mathbb{Q}$，$x>0,y>0 \Rightarrow \exists n \in \mathbb{Z} \wedge n>0 \text{使得} nx>y$

假设对任意$x,y \in \mathbb{Q}$，$x>0,y>0 \Rightarrow \neg \exists n \in \mathbb{Q} \wedge n>0 \text{使得} nx>y$

即对$\forall n \in \mathbb{Q} \wedge n>0$，$nx< y$ or $nx=y$

若对于某个$n$, $nx=y$,则$(n+1)x=nx+x=y+x>y$, 矛盾

因此必须有$nx<y$对所有$n\in \mathbb{Q} \wedge n>0$成立

但是 $y-(yx^{-1})x=y-y=0$，即$n=yx^{-1}$使得$nx\geq y$，矛盾

因此，对任意$x,y \in \mathbb{Q}$，$x>0,y>0 \Rightarrow \exists n \in \mathbb{Q} \wedge n>0 \text{使得} nx>y$

根据$\mathbb{Z}$的 Archimedean 性，可以找到一个$\mathbb{Z}$中的正数$m$，使得$m=m1>n$,易得$[m,1]>[n,1]$

因此对于任意一个正有理数$[a,b]$,存在一个$\mathbb{Z}$中的正数$s$使得$[s,1] > [a,1] \geq [a,b]$

所以$[s,1]x = sx > nx \geq y$. 证毕。

$\textbf{Lemma}$. 若$n,m \in \mathbb{Z}$，$n>m$，则$i(n)=[n,1]>[m,1]=i(m)$

#### 有理数中定义范数(绝对值)、距离度量

$\textbf{Definition}$. (Absolute value) If $x$ is a rational number, the absolute value $|x|$ of $x$ is defined as follows. If $x$ is positive, then $|x| := x$. If $x$ is negative, then $|x| := −x$. If $x$ is zero, then $|x| := 0$.

上面定义绝对值有以下性质

- 非负性：$|x| \geq 0$，且$|x|=0 \Leftrightarrow x=0$
- $|-x|=|x|$
- $x\leq |x|$
- 三角不等式：$|x+y| \leq |x|+|y|$
- 我们有不等式 $-y \leq x \leq y$ 当且仅当 $y \geq |x|$. 特别地，我们有 $-|x| \leq x \leq |x|$.
- 乘法性质：$|x y| = |x| |y|$. 特别地，$|-x|=|x|$

$\textbf{Definition}$. (Distance) Let $x$ and $y$ be rational numbers. The quantity $|x − y|$ is called the distance between $x$ and $y$ and is sometimes denoted $d(x, y)$, thus $d(x, y) := |x − y|$.

上面定义的距离有以下性质

- 非负性：$d(x, y) \geq 0$，且$d(x, y) = 0 \Leftrightarrow x = y$
- 对称性：$d(x, y) = d(y, x)$
- 三角不等式：$d(x, z) \leq d(x, y) + d(y, z)$

$\textbf{Lemma}$. (Interspersing of integers by rationals). Let $x$ be a rational num-ber. Then there exists an integer $n$ such that $n \leq x < n + 1$. In fact, this integer is unique (i.e., for each $x$ there is only one $n$ for which $n \leq x < n + 1$). In particular, there exists a natural number $N$ such that $N > x$ (i.e., there is no such thing as a rational number which is larger than all the natural numbers).

提示：$\mathbb{Z}$中的非空子集若有下界，则该子集有最小元素。

$\textbf{Proposition}$. (Interspersing of rationals by rationals). If $x$ and $y$ are two rationals such that $x < y$, then there exists a third rational $z$ such that $x < z < y$.

令$2=1 + 1$,$1$ 是整环$\mathbb{Z}$ 的乘法单位元

(1/2) + (1/2) = [1,1+1] + [1,1+1]=[1+1+1+1,1+1+1+1]=[1,1]

$x = x/2 + x/2 < x/2 + y/2 < y/2 + y/2 = y$

令$z=(x+y)/2 = x/2 + y/2$即可。

## 实数

#### 有理数中的柯西列

$\textbf{Definition}$. (Sequences). Let $m$ be an integer. A sequence $(a_n)_{n=m}$ of rational numbers is any function from the set $\{n \in \mathbb{Z} : n \geq m\}$ to $\mathbb{Q}$, i.e., a mapping which assigns to each integer $n$ greater than or equal to $m$, a rational number $a_n$. More informally, a sequence $(a_n)_{n=m}$ of rational numbers is a collection of rationals $a_m, a_{m+1}, a_{m+2}, \cdots$.

$\textbf{Definition}$. (Cauchy sequences). A sequence $(a_n)_{n=m}$ of rational numbers is said to be a Cauchy sequence iff for every $\epsilon > 0$, there exists an $N \geq 0$ such that $d(a_j, a_k) \leq \epsilon$ for all $j, k \geq N$.

$\textbf{Definition}$. (Bounded sequences). Let $M \geq 0$ be rational. A finite sequence $a_1, a_2, \cdots, a_n$ is bounded by $M$ iff $|a_i| \leq M$ for all $1 \leq i \leq n$. An infinite sequence $(a_n)_{n=m}$ is bounded by $M$ iff $|a_i| \leq M$ for all $i \geq m$.

$\textbf{Lemma}$. Finite sequences are bounded

$\textbf{Lemma}$. $|x-y|<=M \Rightarrow |x|<=|y|+M$

$\textbf{Lemma}$. (Cauchy sequences are bounded). Every Cauchy sequence $(a_n)_{n=m}$ is bounded.

$\textbf{Lemma}$. $n \in \mathbb{N} \wedge x \in \mathbb{Q} \Rightarrow nx=\sum_{i=1}^{n}x$, 提示：自然数到整数的同构映射、整数到有理数的同构映射、数学归纳法

令$C=\{x \in \prod_{i\in \mathbb{N}} \mathbb{Q} \mid x_i \text{ is a Cauchy sequence}\}$，即由$\mathbb{N}$索引的$\mathbb{Q}$的笛卡尔积。

定义$C$上的一种关系$\sim_c$，$x \sim_c y$当且仅当对于任意$\epsilon \in \mathbb{Q} \wedge \epsilon > 0$，存在$N \in \mathbb{N}$，使得对于任意$n \geq N$，有$|x_n-y_n| \leq \epsilon$

$\textbf{Lemma}$. $\sim_c$是等价关系

$\sim_c$在$C$上的所有等价类所构成的集合为 $\mathcal{C}$，$\mathcal{C}$中的元素记作$[(a_n)_{n=0}]$，简记为$[a_n]$

#### 实数加法

$\textbf{Lemma}$. if $(a_n)_{n=0}$ and $(b_n)_{n=0}$ are Cauchy sequences, then $(a_n+b_n)_{n=0}$ is also a Cauchy sequence

在$\mathcal{C}$上定义**加法**

$[(a_n)_{n=0}]+[(b_n)_{n=0}]=[(a_n+b_n)_{n=0}]$

简记为$[a_n]+[b_n]=[a_n+b_n]$

容易验证上述定义的加法是良定义的

上述定义的加法具有以下性质

- 加法交换律
- 加法结合律
- 加法单位元$[0_n]$，$0_n$为$\mathbb{Q}$中的零序列
- 加法逆元$[(a_n)_{n=0}]+[(-a_n)_{n=0}]=[(a_n-a_n)_{n=0}]=[0_n]$

因此$<\mathcal{C},+>$构成一个交换群

note: 需要验证逆元的良定义性，即若两个数表示的等价类相等，则它们的逆元表示的等价类也相等

#### 实数乘法

$\textbf{Lemma}$. if $(a_n)_{n=0}$ and $(b_n)_{n=0}$ are Cauchy sequences, then $(a_n b_n)_{n=0}$ is also a Cauchy sequence

证明：by definition

任取一个$\epsilon \in \mathbb{Q} \wedge \epsilon > 0$

因为柯西列都是有界，所以$|a_n| \leq M_1$，$|b_n| \leq M_2$，因此它们有共同上界$M = max(M_1,M_2)$

对于$\epsilon_a= \epsilon/(2M)$，存在$N_a$，使得对于任意$n,m \geq N_a$，有$|a_n - a_m| \leq \epsilon_a$

对于$\epsilon_b= \epsilon/(2M)$，存在$N_b$，使得对于任意$n,m \geq N_b$，有$|b_n - b_m| \leq \epsilon_b$

取$N = max(N_a,N_b)$，对于任意$n,m \geq N$，有

$|a_n b_n - a_m b_m| = |a_n b_n - a_n b_m + a_n b_m - a_m b_m| = |a_n||b_n - b_m| + |b_m||a_n - a_m|\leq M|b_n - b_m| + M|a_n - a_m| \leq \epsilon_a + \epsilon_b = \epsilon$

在$\mathcal{C}$上定义**乘法**

$[(a_n)_{n=0}] \times [(b_n)_{n=0}] = [(a_n b_n)_{n=0}]$

简记为$[a_n] \times [b_n] = [a_n b_n]$

容易验证上述定义的乘法是良定义的

$\textbf{Definition}$. (Sequences bounded away from zero). A sequence $(a_n)_{n=0}$ of rational numbers is said to be bounded away from zero iff there exists a rational number $c > 0$ such that $|a_n| \geq c$ for all $n \geq 0$.

$\textbf{Lemma}$. Let $x$ be a non-zero real number. Then $x = [(a_n)_{n=0}]$ for some Cauchy sequence $(a_n)_{n=0}$ which is bounded away from zero.

证明：
由$x = [b_n] \not = [0_n]$,存在$\epsilon \in \mathbb{Q} \wedge \epsilon > 0$，使得对于任意$N$, 都存在$n_0>N$,使得$|b_{n_0}| \geq \epsilon$

因为$x$是柯西列，所以存在$N_1$，使得对于任意$n,m \geq N_1$，有$|b_n - b_m| \leq \epsilon/2$

取$N=max(N_1,n_0)$，对于任意$n \geq N$，有$|b_{n_0} - b_n| \leq \epsilon/2$，因此$|b_n| \geq |b_{n_0}| - |b_{n_0} - b_n| \geq \epsilon - \epsilon/2 = \epsilon/2$

构造一个新的数列$a_i=b_{n_0},i<n_0$，$a_i=b_i,i\geq n_0$

易得$[a_n]=[b_n]=x$,且$|a_n| \geq \epsilon/2$

即$(a_n)_{n=0}$是bounded away from zero的cauchy sequence

$\textbf{Lemma}$. 若$a_n$是bounded away from zero的cauchy sequence，则$1/a_n$也是cauchy sequence. 按柯西列的定义证明

$\textbf{Lemma}$. 若$a_n \sim_{c} b_n$，且$a_n,b_n$都是bounded away from zero的cauchy sequence，则$1/a_n \sim_{c} 1/b_n$，即逆元是良定义的。

上述定义的乘法具有以下性质

- 乘法交换律
- 乘法结合律
- 乘法单位元$[1_n]$，$1_n$为$\mathbb{Q}$中的单位序列
- 乘法逆元，若$[a_n] \not= [0_n]$，且$(a_n)_{n=0}$是bounded away from zero的cauchy sequence，则$[a_n]$有乘法逆元$[b_n]$，其中$b_n = \frac{1}{a_n}$
- 乘法对加法的分配律

因此$<\mathcal{C},+,\times>$构成一个交换除环，即域

$\textbf{Definition}$. $i(n): \mathbb{Q} \to \mathcal{C}$，$i(q)=[q_n]$，$\forall q_i=q$

$i(q_1 + q_2) = [(q_1+q_2)_n]=[(q_1)_n] + [(q_2)_n]$

$i(q_1q_2)$ = $[(q_1q_2)_n]=[(q_1)_n] [(q_2)_n]$

若$i(q_1) = i(q_2)$，$[(q_1)_n] = [(q_2)_n] \Rightarrow q_1 = q_2$，因此$i$是单射

因此$i$是$\mathbb{Q}$到$\mathcal{C}$的同构映射

#### 有序域

$\textbf{Definition}$. Let $(a_n)_{n=0}$ be a sequence of rationals. We say that this sequence is positively bounded away from zero iff we have a positive rational $c > 0$ such that $a_n \geq c$ for all $n \geq 0$ (in particular, the sequence is entirely positive). The sequence is negatively bounded away from zero iff we have a positive rational $c > 0$ such that $a_n \leq -c$ for all $n \geq 0$ (in particular, the sequence is entirely negative).

$\textbf{Definition}$. A real number $x$ is said to be positive iff it can be written as $x = [(a_n)_{n=0}]$ for some Cauchy sequence $(a_n)_{n=0}$ which is positively bounded away from zero. （$x$ is said to be negative iff it can be written as $x = [(a_n)_{n=0}]$ for some Cauchy sequence $(a_n)_{n=0}$ which is negatively bounded away from zero.）

$P = \{x \in \mathcal{C} \mid x \text{ is positive}\}$

可以验证$P$满足如下性质

- $\forall x,y \in P, x+y \in P,xy \in P$
- $\forall x \in \mathcal{C}, x \in P, x=0 , -x \in P$三者有且只有一个成立

因此$<\mathcal{C},+,\times>$构成一个有序域，即$<\mathbb{R},+,\times>$

可以定义$<$为$x<y \Leftrightarrow y-x \in P$

(抽象代数)有序域(环)上的性质对$<\mathcal{C},+,\times>$都成立

- Trichotomy: $x < y, x=y, x>y$三者有且只有一个成立
- Transitivity: $x<y,y<z \Rightarrow x<z$
- Addition preservation: $x<y \Rightarrow x+z<y+z$
- Multiplication preservation: $x<y,z>0 \Rightarrow xz<yz$
- Negation reverses order: $a > b \Rightarrow -a < -b$
- $a>0 \Leftrightarrow a^{-1}>0$
- $0<a,0<b\rightarrow 0<a/b$
- $0<a<1\rightarrow 1<1/a$
- $-1<a<0\rightarrow 1/a<-1$

$\textbf{lemma}$. $x,y \in \mathbb{Q} \wedge x<y \Rightarrow i(x)<i(y)$,即$i(q)=[(q_n)_n]$是从$\mathbb{Q}$到$\mathcal{C}$的一个子集的序同构

至此将$<\mathcal{C},+,\times>$记作$<\mathbb{R},+,\times>$,简记为$\mathbb{R}$

$\textbf{Proposition}$. Let $a_0,a_1,a_2,...$ be a Cauchy sequence of non-negative rational numbers. Then $[(a_n)_{n=0}]$ is a non-negative real number.

$\textbf{Corollary}$. Let $(a_n)_{n=0}$ and $(b_n)_{n=0}$ be Cauchy sequences of rationals such that $a_n \geq b_n$ for all $n \geq 0$. Then $[(a_n)_{n=0}] \geq [(b_n)_{n=0}]$.

$\textbf{Proposition}$. Let $x$ be a positive real number. Then there exists a positive rational number $q$ such that $q \leq x$, and there exists a positive integer $N$ such that $x \leq N$.

$\textbf{Corollary}$. Let $x$ be a real number, and let $\epsilon$ be a positive real number. Then there exists a positive integer $M$ such that $M\epsilon > x$.

$\textbf{Proposition}$. Given any two real numbers $x < y$, we can find a rational number $q$ such that $x < q < y$.

$\textbf{Definition}$. $|x|=x$ if $x \geq 0$, else $|x|=-x$

(抽象代数)有序环上的绝对值有以下性质

1. $|x| \geq 0$
2. $|-x|=|x|$
3. $|x|=0 \Leftrightarrow x=0$
4. $x<|x|$
5. $|x+y| \leq |x|+|y|$
6. $|xy|=|x||y|$

用绝对值定义距离$d(x,y)=|x-y|$，则有以下性质

1. $d(x, y) \geq 0$. Also, $d(x, y) = 0$ if and only if $x = y.$
2. $d(x, y) = d(y, x)$.
3. $d(x, z) \geq d(x, y) + d(y, z)$.

$\textbf{Definition}$. (Upper bound). Let $E$ be a subset of $\mathbb{R}$, and let $M$ be a real number. We say that $M$ is an upper bound for $E$, iff we have $x \leq M$ for every element $x$ in $E$.

$\textbf{Definition}$. (Least upper bound). Let $E$ be a subset of $\mathbb{R}$, and $M$ be a real number. We say that $M$ is a least upper bound for $E$ iff (a) $M$ is an upper bound for $E$, and also (b) any other upper bound $M$ for $E$ must be larger than or equal to $M$.

$\textbf{Proposition}$. Let $E$ be a subset of $\mathbb{R}$. Then $E$ can have at most one least upper bound.

$\textbf{Theorem}$. (Existence of least upper bound). Let $E$ be a non-empty subset of $\mathbb{R}$. If $E$ has an upper bound, (i.e., $E$ has some upper bound $M$), then it must have exactly one least upper bound.

