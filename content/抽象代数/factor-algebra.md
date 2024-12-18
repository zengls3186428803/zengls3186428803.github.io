---
title: 因子群，因子环
date: 2024-11-09 12:53:56
tags:
---

### 因子群

正规子群$N\triangleleft G$的陪集上定义的二元运算：$(aN)(bN)=(ab)N$
这个运算是良定义的。

#### 正规子群的陪集上的二元运算的性质

1. $G/N$上的二元运算会继承群的封闭性
2. $G/N$上的二元运算会继承群的结合律
3. $G/N$上的二元运算会继承群的单位元，即$eN=N$是因子群的单位元
4. $G/N$上的二元运算会继承群的逆元，即$(aN)^{-1}=a^{-1}N$,所以每个陪集都有逆元
5. 如果 G 上有交换律，则$G/N$上的二元运算也会继承群的交换律

### 因子群同构

$\psi:G\rightarrow G'$是群同态映射，即$\psi(ab)=\psi(a)\psi(b)$

$H=Ker(\psi)$，则$H$是$G$的一个正规子群。

H 的所有陪集为$G/H$

定义$G/H$上的二元运算：$(aH)(bH)=(ab)H$

因为同态映射的核是正规子群，所以陪集上的运算是良定义的。

由$G/H$上的二元运算的性质知，$G/H$是一个群

定义$\phi(aH)=\psi(a)$,其中$aH \in G/H$

验证$\phi$是一个是$G/H\rightarrow \psi(G)$的一个同构映射

1. $\phi$是双射
2. $\phi((aH)(bH))=\phi((ab)H)=\psi(ab)=\psi(a)\psi(b)=\phi(aH)\phi(bH)$

### 因子环同构

0 是 R 的加法单位元，0‘ 是 R‘的加法单位元

$\psi:R\rightarrow R'$是一个环同态映射,即$\psi(a+b)=\psi(a)+\psi(b), \psi(ab)=\psi(a)\psi(b)$

$H = Ker(\psi)$，这个核是指加法单位元的在$\psi$下的逆像，即$Ker(\psi)=\psi^{-1}[0']$

$R/H=\{a + H | a ∈ R\}$

现在定义 $G/H$ 上的乘法运算$(a+H)(b+H)=(ab + H)$,加法运算$(a+H)+(b+H)=(a+b)+H$

因为环同态映射的(加法)核是一个理想，所以陪集上的乘法是良定义的。

验证 $R/H$ 是一个环

1. 有群的讨论知：$<R/H,+>$构成一个交换群
2. $(a+H)(b+H)=(ab)+H \in R/H$,乘法的封闭性
3. $((a+H)(b+H))(c+H)=(ab+H)(c+H)=(abc+H)=(a+H)(bc+H)=(a+H)((b+h)(c+H))$,所以$<R/H,\cdot>$是一个半群
4. $(a+H)((b+H)+(c+H))=(a+H)((b+c)+H)=(a(b+c)+H)=((ab+ac)+H)=(ab+H)+(ac+H)=(a+H)(b+H)+(a+H)(c+H)$,所以$<R/H,+,\cdot>$是一个环

定义$\phi(a+H)=\psi(a)$,其中$a+H \in R/H$

验证$\phi$是一个是$R/H\rightarrow \psi(R)$的一个环同构映射

1. $\phi$是双射
2. $\phi((a+H)+(b+H))=\phi((a+b)+H)=\psi(a+b)=\psi(a)+\psi(b)=\phi(a+H)+\phi(b+H)$
3. $\phi((a+H)(b+H))=\phi((ab)+H)=\psi(ab)=\psi(a)\psi(b)=\phi(a+H)\phi(b+H)$

#### 因子环的的性质

1. 如果环有乘法交换律，那因子环也有乘法交换律
2. 如果环有乘法单位元，那因子环也有乘法单位元，$(1+H)(a+H)=(a1+H)=(a+H)$
3. 如果环有乘法逆元，那因子环也有乘法逆元，$(a+H)(a^{-1}+H)=(1+H)$
