---
title: 《Introduction to the Theory of Computation》里的自动机部分的定义和定理。
date: 2024-10-21 14:05:17
tags: 可计算性与计算复杂性
---

- [DEFINITION 1.5(finite automaton)](#definition-15finite-automaton)
- [DEFINITION 1.16(regular language)](#definition-116regular-language)
- [DEFINITION 1.23(regular operations)](#definition-123regular-operations)
- [DEFINITION 1.37(A nondeterministic finite automaton)](#definition-137a-nondeterministic-finite-automaton)
- [THEOREM 1.39(DFA equivalent to NFA)](#theorem-139dfa-equivalent-to-nfa)
- [DEFINITION 1.52(regular expression)](#definition-152regular-expression)
- [THEOREM 1.54(regular language is equivalent to language described by regular expression)](#theorem-154regular-language-is-equivalent-to-language-described-by-regular-expression)
- [DEFINITION 1.64(generalized nondeterministic finite automaton)](#definition-164generalized-nondeterministic-finite-automaton)
- [THEOREM 1.70(Pumping lemma)](#theorem-170pumping-lemma)

## DEFINITION 1.5(finite automaton)

A finite automaton is a 5-tuple $\left(Q, \Sigma, \delta, q_0, F\right)$, where

1. $Q$ is a finite set called the states,
2. $\Sigma$ is a finite set called the alphabet,
3. $\delta: Q \times \Sigma \longrightarrow Q$ is the transition function
4. $q_0 \in Q$ is the start state, and
5. $F \subseteq Q$ is the set of accept states.

A string w is accepted by M if M read w, enter accept states.

If A is the set of all strings that machine M accepts, we say that A is the
language of machine M and write L(M ) = A. We say that M recognizes A or
that M accepts A.

```
For every state q in Q and every a in alphabet, exists a next state q'
because domain of transition function is Cartesian product of Q and alphabet
```

```
A string w is rejected iff w is not accepted.
```

## DEFINITION 1.16(regular language)

A language is called a regular language if some finite automatonrecognizes it.

A language is regular if and only if some nondeterministic finite automaton recognizes it.

## DEFINITION 1.23(regular operations)

Let $A$ and $B$ be languages. We define the regular operations union, concatenation, and star as follows:

- Union: $A \cup B=\{x \mid x \in A$ or $x \in B\}$.
- Concatenation: $A \circ B=\{x y \mid x \in A$ and $y \in B\}$.
- Star: $A^*=\left\{x_1 x_2 \ldots x_k \mid k \geq 0\right.$ and each $\left.x_i \in A\right\}$.

the collection of regular languages is closed under all three of the regular operations.

## DEFINITION 1.37(A nondeterministic finite automaton)

A nondeterministic finite automaton is a 5-tuple $\left(Q, \Sigma, \delta, q_0, F\right)$, where

1. $Q$ is a finite set of states,
2. $\Sigma$ is a finite alphabet,
3. $\delta: Q \times \Sigma_{\varepsilon} \longrightarrow \mathcal{P}(Q)$ is the transition function,
4. $q_0 \in Q$ is the start state, and
5. $F \subseteq Q$ is the set of accept states.

## THEOREM 1.39(DFA equivalent to NFA)

Every nondeterministic finite automaton has an equivalent deterministic finite
automaton.

```
two automaton is equivalent iff they recogize same language
```

## DEFINITION 1.52(regular expression)

Say that $R$ is a regular expression if $R$ is

1. $a$ for some $a$ in the alphabet $\Sigma$,
2. $\varepsilon$,
3. $\emptyset$,
4. $\left(R_1 \cup R_2\right)$, where $R_1$ and $R_2$ are regular expressions,
5. $\left(R_1 \circ R_2\right)$, where $R_1$ and $R_2$ are regular expressions, or
6. $\left(R_1^*\right)$, where $R_1$ is a regular expression.

In items 1 and 2 , the regular expressions $a$ and $\varepsilon$ represent the
languages $\{a\}$ and $\{\varepsilon\}$, respectively. In item 3 , the regular expres-
sion $\emptyset$ represents the empty language. In items 4,5 , and 6 , the
expressions represent the languages obtained by taking the union
or concatenation of the languages $R_1$ and $R_2$, or the star of the
language $R_1$, respectively.

L(R) to be the language of R.

## THEOREM 1.54(regular language is equivalent to language described by regular expression)

A language is regular if and only if some regular expression describes it.

## DEFINITION 1.64(generalized nondeterministic finite automaton)

A generalized nondeterministic finite automaton is a 5-tuple, $\left(Q, \Sigma, \delta, q_{\text {start }}, q_{\text {accept }}\right)$, where

1. $Q$ is the finite set of states,
2. $\Sigma$ is the input alphabet,
3. $\delta:\left(Q-\left\{q_{\text {accept }}\right\}\right) \times\left(Q-\left\{q_{\text {start }}\right\}\right) \longrightarrow \mathcal{R}$ is the transition function,
4. $q_{\text {start }}$ is the start state, and
5. $q_{\text {accept }}$ is the accept state.

```
Notice that domain of transition function is Cartesain product.
```

## THEOREM 1.70(Pumping lemma)

Pumping lemma If $A$ is a regular language, then there is a number $p$ (the pumping length) where if $s$ is any string in $A$ of length at least $p$, then $s$ may be divided into three pieces, $s=x y z$, satisfying the following conditions:

1. for each $i \geq 0, x y^i z \in A$,
2. $|y|>0$, and
3. $|x y| \leq p$.
