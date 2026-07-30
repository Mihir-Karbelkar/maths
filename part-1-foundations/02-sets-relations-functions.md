# Chapter 2 — Sets, Relations, and Functions

## 2.1 Sets as collections

A **set** is a collection of distinct objects. The objects are called its **elements**.

If \(x\) is an element of a set \(A\), we write

\[
x\in A.
\]

If it is not, we write \(x\notin A\).

Examples:

\[
A=\{1,2,3\},
\qquad
B=\{n\in\mathbb Z:n\text{ is even}\}.
\]

The first uses **roster notation**. The second uses **set-builder notation**.

Order and repetition do not matter:

\[
\{1,2,3\}=\{3,2,1,1\}.
\]

The set containing no elements is the **empty set**, denoted \(\varnothing\).

## 2.2 Equality and subsets

Two sets are equal when they have exactly the same elements:

\[
A=B
\iff
\forall x\,(x\in A\iff x\in B).
\]

A set \(A\) is a **subset** of \(B\), written \(A\subseteq B\), when every element of \(A\) belongs to \(B\):

\[
A\subseteq B
\iff
\forall x\,(x\in A\implies x\in B).
\]

Every set is a subset of itself, and the empty set is a subset of every set.

### Theorem 2.1

For any sets \(A,B\),

\[
A=B
\iff
A\subseteq B\text{ and }B\subseteq A.
\]

### Proof

If \(A=B\), then every element of either set belongs to the other, so both inclusions hold.

Conversely, suppose \(A\subseteq B\) and \(B\subseteq A\). If \(x\in A\), then \(x\in B\); if \(x\in B\), then \(x\in A\). Thus the sets have exactly the same elements, so \(A=B\). \(\square\)

This is the standard method for proving set equality: prove two inclusions.

## 2.3 Basic operations on sets

The **union** is

\[
A\cup B=\{x:x\in A\text{ or }x\in B\}.
\]

The **intersection** is

\[
A\cap B=\{x:x\in A\text{ and }x\in B\}.
\]

The **difference** is

\[
A\setminus B=\{x:x\in A\text{ and }x\notin B\}.
\]

Given a universal set \(U\), the complement of \(A\subseteq U\) is

\[
A^c=U\setminus A.
\]

De Morgan's laws for sets are

\[
(A\cup B)^c=A^c\cap B^c,
\qquad
(A\cap B)^c=A^c\cup B^c.
\]

They follow directly from the logical De Morgan laws.

### Example: residue classes

Let

\[
E=\{n\in\mathbb Z:2\mid n\},
\qquad
M_3=\{n\in\mathbb Z:3\mid n\}.
\]

Then \(E\cap M_3\) is the set of integers divisible by both \(2\) and \(3\), hence divisible by \(6\).

This elementary observation anticipates sieve theory, where unions and intersections describe divisibility constraints.

## 2.4 Indexed families

For a family of sets \(\{A_i\}_{i\in I}\), define

\[
\bigcup_{i\in I}A_i
=
\{x:\exists i\in I,\ x\in A_i\},
\]

\[
\bigcap_{i\in I}A_i
=
\{x:\forall i\in I,\ x\in A_i\}.
\]

The difference between “there exists” and “for every” is built directly into union and intersection.

For example, let

\[
A_p=\{n\in\mathbb N:p\mid n\}
\]

for each prime \(p\le z\). Then

\[
\bigcup_{p\le z}A_p
\]

is the set of integers divisible by at least one prime not exceeding \(z\). Removing this union is the basic act of sieving.

## 2.5 Power sets

The **power set** of \(A\), written \(\mathcal P(A)\), is the set of all subsets of \(A\).

If \(A=\{a,b\}\), then

\[
\mathcal P(A)=\{\varnothing,\{a\},\{b\},\{a,b\}\}.
\]

### Theorem 2.2

If \(A\) has \(n\) elements, then \(\mathcal P(A)\) has \(2^n\) elements.

### Reason

For each element of \(A\), a subset makes one of two choices: include it or exclude it. The choices are independent, giving

\[
2\cdot2\cdots2=2^n
\]

possible subsets.

A full proof may be written using induction.

## 2.6 Cartesian products

The ordered pair \((a,b)\) remembers order. Usually

\[
(a,b)\ne(b,a).
\]

The **Cartesian product** is

\[
A\times B=\{(a,b):a\in A,\ b\in B\}.
\]

If \(|A|=m\) and \(|B|=n\), then

\[
|A\times B|=mn.
\]

The plane \(\mathbb R^2\) is \(\mathbb R\times\mathbb R\). The complex plane can be constructed from ordered pairs of real numbers equipped with special addition and multiplication.

## 2.7 Relations

A **binary relation** from \(A\) to \(B\) is a subset of \(A\times B\). A relation on \(A\) is a subset of \(A\times A\).

If \((a,b)\in R\), we often write

\[
aRb.
\]

Examples:

- equality on \(\mathbb Z\);
- divisibility: \(aRb\) when \(a\mid b\);
- order: \(aRb\) when \(a\le b\);
- congruence modulo \(m\): \(aRb\) when \(m\mid(a-b)\).

A relation may have the following properties.

- **Reflexive:** \(aRa\) for every \(a\).
- **Symmetric:** \(aRb\implies bRa\).
- **Antisymmetric:** \(aRb\) and \(bRa\implies a=b\).
- **Transitive:** \(aRb\) and \(bRc\implies aRc\).

Equality is reflexive, symmetric, and transitive. The order relation \(\le\) is reflexive, antisymmetric, and transitive, but not symmetric.

## 2.8 Equivalence relations

An **equivalence relation** is reflexive, symmetric, and transitive.

### Congruence modulo \(m\)

For a fixed positive integer \(m\), define

\[
a\equiv b\pmod m
\iff
m\mid(a-b).
\]

### Theorem 2.3

Congruence modulo \(m\) is an equivalence relation on \(\mathbb Z\).

### Proof

Reflexivity: \(a-a=0\), and \(m\mid0\).

Symmetry: if \(m\mid(a-b)\), then \(a-b=mk\) for some integer \(k\). Hence

\[
b-a=-mk=m(-k),
\]

so \(m\mid(b-a)\).

Transitivity: if \(m\mid(a-b)\) and \(m\mid(b-c)\), write

\[
a-b=mr,
\qquad
b-c=ms.
\]

Adding gives

\[
a-c=m(r+s),
\]

so \(m\mid(a-c)\). \(\square\)

An equivalence relation partitions a set into disjoint **equivalence classes**.

The class of \(a\) modulo \(m\) is

\[
[a]_m=\{n\in\mathbb Z:n\equiv a\pmod m\}.
\]

There are exactly \(m\) classes:

\[
[0]_m,[1]_m,\ldots,[m-1]_m.
\]

This becomes central in the study of primes in arithmetic progressions. For instance, every odd prime lies in one of the classes \([1]_4\) or \([3]_4\).

## 2.9 Partitions and quotient sets

A **partition** of a set \(A\) is a family of nonempty subsets whose union is \(A\) and whose distinct members are disjoint.

Every equivalence relation on \(A\) produces a partition into equivalence classes. Conversely, every partition defines an equivalence relation by declaring two elements equivalent when they lie in the same block.

The set of equivalence classes is called a **quotient set** and is denoted

\[
A/{\sim}.
\]

The integers modulo \(m\) form

\[
\mathbb Z/m\mathbb Z.
\]

This quotient is not merely notation. Addition and multiplication descend to equivalence classes and create a finite algebraic system.

## 2.10 Functions

A **function** \(f:A\to B\) assigns to every element \(a\in A\) exactly one element \(f(a)\in B\).

The set \(A\) is the **domain**. The set \(B\) is the **codomain**. The actual values obtained form the **image** or **range**:

\[
f(A)=\{f(a):a\in A\}\subseteq B.
\]

The rule alone does not fully determine a function; domain and codomain matter.

For example,

\[
f(x)=x^2
\]

may define different functions:

\[
f:\mathbb R\to\mathbb R,
\qquad
f:[0,\infty)\to[0,\infty),
\qquad
f:\mathbb C\to\mathbb C.
\]

These functions have different invertibility properties.

## 2.11 Injective, surjective, and bijective maps

A function \(f:A\to B\) is **injective** if

\[
f(a_1)=f(a_2)\implies a_1=a_2.
\]

Different inputs cannot produce the same output.

It is **surjective** if

\[
\forall b\in B\;\exists a\in A:\ f(a)=b.
\]

Every element of the codomain is attained.

It is **bijective** if it is both injective and surjective.

### Example

The function

\[
f:\mathbb Z\to\mathbb Z,
\qquad
f(n)=2n
\]

is injective but not surjective, because no odd integer is in its image.

The same rule regarded as

\[
f:\mathbb Z\to2\mathbb Z
\]

is bijective.

This demonstrates why codomains cannot be ignored.

## 2.12 Composition and identity

If \(f:A\to B\) and \(g:B\to C\), their composition is

\[
(g\circ f)(a)=g(f(a)).
\]

Composition is associative:

\[
h\circ(g\circ f)=(h\circ g)\circ f.
\]

The identity function on \(A\) is

\[
\operatorname{id}_A(a)=a.
\]

It satisfies

\[
f\circ\operatorname{id}_A=f,
\qquad
\operatorname{id}_B\circ f=f.
\]

## 2.13 Inverse functions

A function \(f:A\to B\) has an inverse \(f^{-1}:B\to A\) when

\[
f^{-1}\circ f=\operatorname{id}_A
\]

and

\[
f\circ f^{-1}=\operatorname{id}_B.
\]

### Theorem 2.4

A function has an inverse if and only if it is bijective.

### Proof

Suppose \(f\) has an inverse. If \(f(a_1)=f(a_2)\), applying \(f^{-1}\) gives \(a_1=a_2\), so \(f\) is injective. For every \(b\in B\), take \(a=f^{-1}(b)\); then \(f(a)=b\), so \(f\) is surjective.

Conversely, suppose \(f\) is bijective. For every \(b\in B\), surjectivity gives at least one \(a\in A\) with \(f(a)=b\), and injectivity makes that \(a\) unique. Define \(f^{-1}(b)=a\). The two inverse identities follow. \(\square\)

## 2.14 Images and preimages

For \(S\subseteq A\), the image is

\[
f(S)=\{f(s):s\in S\}.
\]

For \(T\subseteq B\), the preimage is

\[
f^{-1}(T)=\{a\in A:f(a)\in T\}.
\]

This notation does not require \(f\) to be invertible.

Preimages preserve unions, intersections, and complements exactly:

\[
f^{-1}(U\cup V)=f^{-1}(U)\cup f^{-1}(V),
\]

\[
f^{-1}(U\cap V)=f^{-1}(U)\cap f^{-1}(V),
\]

\[
f^{-1}(B\setminus U)=A\setminus f^{-1}(U).
\]

Images preserve unions but may fail to preserve intersections unless the function is injective.

## 2.15 Finite and infinite sets

Two sets have the same **cardinality** when a bijection exists between them.

A set is **countably infinite** when it is in bijection with \(\mathbb N\).

The integers are countable. One possible enumeration is

\[
0,1,-1,2,-2,3,-3,\ldots
\]

The rational numbers are also countable, despite appearing much denser than the integers. Fractions can be arranged in a two-dimensional grid and enumerated diagonally, skipping repetitions.

## 2.16 Cantor's diagonal argument

### Theorem 2.5

The interval \((0,1)\) is uncountable.

### Proof idea

Assume every number in \((0,1)\) can be listed:

\[
x_1=0.a_{11}a_{12}a_{13}\ldots,
\]

\[
x_2=0.a_{21}a_{22}a_{23}\ldots,
\]

and so on.

Construct a new decimal

\[
y=0.b_1b_2b_3\ldots
\]

by choosing \(b_n\) different from \(a_{nn}\), for example

\[
b_n=
\begin{cases}
1,&a_{nn}\ne1,\\
2,&a_{nn}=1.
\end{cases}
\]

Then \(y\) differs from \(x_n\) in the \(n\)-th decimal place. Therefore \(y\) is not equal to any number in the list, contradicting the claim that the list contained all numbers in \((0,1)\). \(\square\)

The digits \(1\) and \(2\) avoid the ambiguity of decimals ending in repeating \(9\)s.

Thus infinite sets come in different sizes.

## 2.17 Functions in analytic number theory

An **arithmetic function** is a function

\[
f:\mathbb N\to\mathbb C.
\]

Examples include:

- the divisor-counting function \(d(n)\);
- Euler's totient \(\varphi(n)\);
- the Möbius function \(\mu(n)\);
- the von Mangoldt function \(\Lambda(n)\).

The prime-counting function is

\[
\pi(x)=\#\{p\le x:p\text{ prime}\}.
\]

The twin-prime counting function is

\[
\pi_2(x)=\#\{p\le x:p\text{ and }p+2\text{ prime}\}.
\]

Both are perfectly well-defined functions. The difficulty is not defining or computing them for a fixed \(x\), but proving useful global descriptions of their growth.

A function can encode a set through its **indicator function**:

\[
\mathbf 1_A(n)=
\begin{cases}
1,&n\in A,\\
0,&n\notin A.
\end{cases}
\]

For primes,

\[
\pi(x)=\sum_{n\le x}\mathbf 1_{\mathbb P}(n).
\]

For twin primes,

\[
\pi_2(x)=\sum_{n\le x}\mathbf 1_{\mathbb P}(n)\mathbf 1_{\mathbb P}(n+2).
\]

The product of indicators exposes the central difficulty: twin primes require a correlation between primality at two shifted inputs.

## 2.18 Exercises

1. Prove \(A\cap(B\cup C)=(A\cap B)\cup(A\cap C)\).
2. Prove both De Morgan laws for sets by element chasing.
3. Show that \(A\setminus(B\cup C)=(A\setminus B)\cap(A\setminus C)\).
4. Find \(\mathcal P(\{1,2,3\})\).
5. Prove by induction that an \(n\)-element set has \(2^n\) subsets.
6. Determine which properties—reflexive, symmetric, antisymmetric, transitive—hold for divisibility on \(\mathbb N\).
7. Prove that equality is an equivalence relation.
8. Prove that equivalence classes are either identical or disjoint.
9. List the equivalence classes modulo \(5\).
10. Prove that addition modulo \(m\) is well-defined on equivalence classes.
11. Determine whether \(f:\mathbb R\to\mathbb R\), \(f(x)=x^3\), is injective, surjective, or bijective.
12. Answer the same question for \(f(x)=x^2\) under several choices of domain and codomain.
13. Prove that the composition of injective functions is injective.
14. Prove that the composition of surjective functions is surjective.
15. Show that if \(g\circ f\) is injective, then \(f\) is injective.
16. Show that if \(g\circ f\) is surjective, then \(g\) is surjective.
17. Give examples showing that the converses of Exercises 15 and 16 need not hold.
18. Prove the preimage identities in Section 2.14.
19. Find an example where \(f(S\cap T)\ne f(S)\cap f(T)\).
20. Construct an explicit bijection between \(\mathbb N\) and \(\mathbb Z\).
21. Explain carefully why the rational numbers are countable.
22. Use Cantor's argument to prove that the set of all infinite binary sequences is uncountable.
23. Express the set of composite numbers using a union of divisibility sets.
24. Write \(\pi(x)\) as a sum involving an indicator function.
25. Write a counting function for prime pairs separated by a fixed even integer \(h\).

## 2.19 Chapter summary

Sets provide the language of collections. Relations describe comparisons and equivalences. Functions encode dependence, transform objects, and turn sets into quantities that analysis can study.

The most important ideas for later chapters are:

- set operations and indexed unions;
- equivalence classes and modular arithmetic;
- domains, codomains, and images;
- injective, surjective, and bijective maps;
- countability;
- arithmetic and counting functions;
- indicator functions and correlations.

The next chapter constructs and compares the major number systems, culminating in the completeness of the real numbers and the algebra of the complex numbers.
