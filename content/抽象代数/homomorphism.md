---
title: 同态映射
date: 2024-11-08 20:46:35
tags:
---

## 同态映射

$\phi:A\rightarrow A'$
$\phi(ab) = \phi(a)\phi(b)$

### 同态映射的性质

同态映射“保留”某性质含义为在 $A$ 中成立的性质在$\phi[A]$也成立

1. 同态映射保留交换律
2. 同态映射保留结合律
3. 同态映射保留单位元
   这个单位元是$\phi[A]$的单位元，不一定是$A'$的单位元，而且$A'$不一定有单位元。
4. 同态映射保留逆元
   这里可逆也是在$\phi[A]$里讨论
5. 同态映射保留子集的封闭性
   即，$a',b'\in \phi[G']\Rightarrow a'b'\in \phi[G']$

### 同态映射的逆像的性质

1. 同态映射的逆像保留子集的封闭性
   即，$a,b\in \phi^{-1}[H'],H' \sub A' \Rightarrow ab\in \phi^{-1}[H']$

## 群同态映射

$\phi:G\rightarrow G'$
$\phi(ab) = \phi(a)\phi(b)$

1. 群同态映射把子群映射到子群
   $H \leq G \Rightarrow \phi[H] \leq G'$
   等价于$H \leq G \Rightarrow \phi[H] \leq \phi[G]$，因为子群的概念只于子群本身有关，与子群的环境无关。
   证明：同态映射保留封闭性、结合律、单位元、逆元。
2. 群同态映射的逆像保留逆元的存在性
   $a\in \phi^{-1}[H'] \wedge H'\leq G \Rightarrow a^{-1}\in \phi^{-1}[H']$
3. 群同态映射把子群逆像到子群
   $H' \leq G' \Rightarrow \phi^{-1}[H'] \leq G$
4. 群同态映射保留把正规子群映射到正规子群
   $H \triangleleft G \Rightarrow \phi[H] \triangleleft \phi[G]$
5. 群同态映射的逆像保留正规子群的性质
   $H' \triangleleft G' \Rightarrow \phi^{-1}[H'] \triangleleft G$

### 环同态映射

$\phi:R\rightarrow R'$
$\phi(a+b) = \phi(a)+\phi(b)$
$\phi(ab) = \phi(a)\phi(b)$

1. 环同态映射把子环映射到子环
   $H \leq R \Rightarrow \phi[H] \leq R'$
   $H \leq R \Rightarrow \phi[H] \leq \phi[R]$
   证明：同态映射把子群映射到子群、同态映射保留交换律(加法)、同态映射保留封闭性(乘法)、同态映射保留结合律(乘法)、继承环的分配律(乘法对加法)
2. 环同态映射把子环逆像到子环
   $H' \leq R' \Rightarrow \phi^{-1}[H'] \leq R$
   证明：同态映射把子群逆像到子群、继承环的加法交换律、同态映射的逆像保留子集的封闭性(乘法)、子环继承环的分配律(乘法对加法)、子环继承环的结合律(乘法)
3. 环同态映射把理想映射到理想
   $I \triangleleft R \Rightarrow \phi[I] \triangleleft \phi[R]$
   证明：$\phi(i)\phi(r)=\phi(ir)\in \phi[I]$
   只需证明理想的吸收律,因为同态映射把子环映射到子环
4. 环同态映射把理想逆像到理想
   $I' \triangleleft R' \Rightarrow \phi^{-1}[I'] \triangleleft R$
   证明：$\phi(ir) = \phi(i)\phi(r)\in I' \Rightarrow ir\in \phi^{-1}[I']$
   只需证明理想的吸收律，因为同态映射把子环逆像到子环
