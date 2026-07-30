# Chapter 1 — Logic and Mathematical Proof

## 1.1 Mathematics begins with statements

A **statement** or **proposition** is a sentence that is either true or false.

Examples:

1. \(2+3=5\).
2. Every even integer greater than \(2\) is the sum of two primes.
3. There are infinitely many prime numbers.

The first and third statements are true. The second is Goldbach's conjecture: it has a definite truth value, but that truth value is not presently known.

Questions and commands are not propositions:

- “Is \(7\) prime?”
- “Find all solutions.”
- “This sentence is false.”

The last example is not an ordinary mathematical proposition because assigning either truth value creates a paradox.

A statement containing an unspecified variable is called an **open statement** or **predicate**. For example,

\[
P(n): n^2\ge n
\]

is not true or false until a domain and a value of \(n\) are supplied. If the domain is \(\mathbb N\), then \(P(n)\) is true for every \(n\). If the domain is \(\mathbb R\), it is false for values such as \(n=\tfrac12\).

This illustrates an essential rule:

> A mathematical statement cannot be understood without knowing the domain of its variables.

## 1.2 Logical connectives

Let \(P\) and \(Q\) be propositions.

### Negation

The negation of \(P\), written \(\neg P\), means “not \(P\).”

If

\[
P: 7\text{ is prime},
\]

then

\[
\neg P: 7\text{ is not prime}.
\]

### Conjunction

The conjunction \(P\land Q\) means “\(P\) and \(Q\).” It is true only when both statements are true.

### Disjunction

The disjunction \(P\lor Q\) means the inclusive “or”: at least one of \(P,Q\) is true, possibly both.

### Implication

The implication

\[
P\implies Q
\]

means “if \(P\), then \(Q\).” It is false only when \(P\) is true and \(Q\) is false.

This convention may feel strange when \(P\) is false. For example,

> If \(10\) is odd, then \(2+2=5\)

is formally true as an implication because its hypothesis is false. The implication promises only that whenever the hypothesis occurs, the conclusion follows. It says nothing about cases in which the hypothesis fails.

In theorem proving, we usually care about implications whose hypotheses can actually hold.

### Biconditional

The biconditional

\[
P\iff Q
\]

means both

\[
P\implies Q
\quad\text{and}\quad
Q\implies P.
\]

It is read “\(P\) if and only if \(Q\).”

The phrase “\(P\) is sufficient for \(Q\)” means \(P\implies Q\). The phrase “\(P\) is necessary for \(Q\)” means \(Q\implies P\).

## 1.3 Truth tables

A truth table records the value of a compound proposition for every possible assignment of truth values.

| \(P\) | \(Q\) | \(P\land Q\) | \(P\lor Q\) | \(P\implies Q\) | \(P\iff Q\) |
|---|---|---:|---:|---:|---:|
| T | T | T | T | T | T |
| T | F | F | T | F | F |
| F | T | F | T | T | F |
| F | F | F | F | T | T |

Two expressions are **logically equivalent** when they have the same truth value in every case.

Important equivalences include

\[
P\implies Q
\equiv
\neg P\lor Q,
\]

and De Morgan's laws,

\[
\neg(P\land Q)
\equiv
(\neg P)\lor(\neg Q),
\]

\[
\neg(P\lor Q)
\equiv
(\neg P)\land(\neg Q).
\]

The implication \(P\implies Q\) has three related statements:

- converse: \(Q\implies P\);
- inverse: \(\neg P\implies\neg Q\);
- contrapositive: \(\neg Q\implies\neg P\).

An implication is logically equivalent to its contrapositive, but not generally to its converse or inverse.

Example:

\[
4\mid n \implies 2\mid n.
\]

The contrapositive is

\[
2\nmid n \implies 4\nmid n,
\]

which is also true. The converse,

\[
2\mid n \implies 4\mid n,
\]

is false: \(n=6\) is a counterexample.

## 1.4 Quantifiers

The **universal quantifier** \(\forall\) means “for every.”

\[
\forall n\in\mathbb N,\quad n^2\ge n.
\]

The **existential quantifier** \(\exists\) means “there exists at least one.”

\[
\exists p\in\mathbb N\quad\text{such that}\quad p\text{ and }p+2\text{ are prime}.
\]

The statement above is easy: \(p=3\) works. The twin-prime conjecture makes the stronger claim that infinitely many such \(p\) exist.

The order of quantifiers matters. Compare

\[
\forall x\in\mathbb R\;\exists y\in\mathbb R:\ y>x
\]

with

\[
\exists y\in\mathbb R\;\forall x\in\mathbb R:\ y>x.
\]

The first is true: for each \(x\), take \(y=x+1\). The second is false: no real number exceeds every real number.

### Negating quantified statements

Negation swaps the quantifier and negates the predicate:

\[
\neg(\forall x\,P(x))
\equiv
\exists x\,\neg P(x),
\]

\[
\neg(\exists x\,P(x))
\equiv
\forall x\,\neg P(x).
\]

Thus the negation of

> Every integer greater than \(1\) is prime

is not

> No integer greater than \(1\) is prime.

The correct negation is

> There exists an integer greater than \(1\) that is not prime.

A single example, such as \(4\), proves the negation.

## 1.5 Definitions, theorems, and conjectures

A **definition** assigns precise meaning to a term.

> An integer \(n\) is even if there exists \(k\in\mathbb Z\) such that \(n=2k\).

Definitions are neither proved nor disproved. They are judged by usefulness, consistency, and clarity.

An **axiom** is accepted as a starting assumption within a formal system.

A **theorem** is a proposition proved from definitions, axioms, and previously established results.

A **lemma** is a theorem used mainly to prove another theorem. A **corollary** follows with little additional work from a theorem. A **conjecture** is a proposition believed to be true but not yet proved.

Examples:

- Euclid's theorem: infinitely many primes exist.
- Riemann hypothesis: every nontrivial zero of \(\zeta(s)\) has real part \(\tfrac12\).
- Twin-prime conjecture: infinitely many primes \(p\) have \(p+2\) prime.

Computation may support a conjecture, but no finite computation proves a universal statement about infinitely many integers.

## 1.6 Direct proof

To prove

\[
P\implies Q
\]

directly, assume \(P\) and deduce \(Q\).

### Theorem 1.1

The sum of two even integers is even.

### Proof

Let \(a,b\in\mathbb Z\) be even. By definition, there exist integers \(r,s\) such that

\[
a=2r,
\qquad
b=2s.
\]

Therefore

\[
a+b=2r+2s=2(r+s).
\]

Since \(r+s\in\mathbb Z\), the integer \(a+b\) is divisible by \(2\), hence even. \(\square\)

Notice the proof's structure:

1. unpack the hypothesis using the definition of evenness;
2. perform algebra;
3. match the result to the definition of evenness.

### Theorem 1.2

If \(m\mid n\) and \(n\mid r\), then \(m\mid r\).

### Proof

Because \(m\mid n\), there exists \(a\in\mathbb Z\) such that \(n=ma\). Because \(n\mid r\), there exists \(b\in\mathbb Z\) such that \(r=nb\). Substitution gives

\[
r=nb=(ma)b=m(ab).
\]

Since \(ab\in\mathbb Z\), we have \(m\mid r\). \(\square\)

## 1.7 Proof by contrapositive

Sometimes \(P\implies Q\) is awkward to prove directly, while

\[
\neg Q\implies\neg P
\]

is simple.

### Theorem 1.3

If \(n^2\) is even, then \(n\) is even.

### Proof

We prove the contrapositive: if \(n\) is odd, then \(n^2\) is odd.

If \(n\) is odd, then \(n=2k+1\) for some \(k\in\mathbb Z\). Hence

\[
n^2=(2k+1)^2=4k^2+4k+1=2(2k^2+2k)+1.
\]

Thus \(n^2\) is odd. Therefore, by contraposition, if \(n^2\) is even then \(n\) is even. \(\square\)

## 1.8 Proof by contradiction

To prove \(P\), assume \(\neg P\) and derive an impossibility.

### Theorem 1.4

The number \(\sqrt2\) is irrational.

### Proof

Assume, for contradiction, that \(\sqrt2\) is rational. Then

\[
\sqrt2=\frac ab
\]

for integers \(a,b\) with \(b\ne0\), chosen so that \(a/b\) is in lowest terms. Squaring gives

\[
2=\frac{a^2}{b^2},
\qquad
 a^2=2b^2.
\]

Thus \(a^2\) is even. By Theorem 1.3, \(a\) is even, so \(a=2k\) for some integer \(k\). Substituting,

\[
(2k)^2=2b^2,
\qquad
4k^2=2b^2,
\qquad
b^2=2k^2.
\]

Therefore \(b^2\), and hence \(b\), is even. Both \(a\) and \(b\) are divisible by \(2\), contradicting the assumption that \(a/b\) was in lowest terms. Therefore \(\sqrt2\) is irrational. \(\square\)

The contradiction did not show that irrational numbers are mysterious. It showed that representing \(\sqrt2\) as a reduced fraction forces that fraction not to be reduced.

## 1.9 Proving existence

An existential statement has the form

\[
\exists x\in D:\ P(x).
\]

A **constructive proof** supplies an explicit witness.

Example:

\[
\exists n\in\mathbb N:\ n^2-n-6=0.
\]

Taking \(n=3\) proves the statement.

A **nonconstructive proof** establishes existence without identifying a specific witness. Such proofs are legitimate, though in applications a construction may be more useful.

### Example: an irrational power with a rational value

We claim that there exist irrational positive numbers \(a,b\) such that \(a^b\) is rational.

Consider

\[
x=(\sqrt2)^{\sqrt2}.
\]

If \(x\) is rational, choose \(a=b=\sqrt2\). If \(x\) is irrational, choose

\[
a=x,
\qquad
b=\sqrt2.
\]

Then

\[
a^b
=
\left((\sqrt2)^{\sqrt2}\right)^{\sqrt2}
=
(\sqrt2)^2
=2.
\]

In either case, suitable irrational \(a,b\) exist. The argument does not need to determine whether \(x\) is rational.

## 1.10 Proving uniqueness

To prove that exactly one object satisfies a property, establish both:

1. existence;
2. uniqueness.

A standard uniqueness argument assumes two objects satisfy the required property and proves they are equal.

### Theorem 1.5

The additive identity in \(\mathbb Z\) is unique.

### Proof

Existence is clear because \(0+n=n+0=n\) for every integer \(n\).

For uniqueness, suppose \(e\) and \(f\) are both additive identities. Since \(f\) is an identity,

\[
e+f=e.
\]

Since \(e\) is an identity,

\[
e+f=f.
\]

Therefore \(e=f\). \(\square\)

## 1.11 Disproof by counterexample

A universal statement

\[
\forall x\in D:\ P(x)
\]

is disproved by finding one \(x\in D\) for which \(P(x)\) is false.

Claim:

> Every prime number is odd.

Counterexample: \(2\) is prime and even.

A common mistake is to give many confirming examples for a universal claim. One million successful tests do not prove a statement about all integers. One failed test disproves it.

## 1.12 Mathematical induction

Induction proves statements indexed by natural numbers. Suppose we want to prove \(P(n)\) for all \(n\ge n_0\).

The method has two parts:

1. **Base case:** prove \(P(n_0)\).
2. **Inductive step:** assume \(P(k)\) for an arbitrary \(k\ge n_0\), and prove \(P(k+1)\).

The assumption \(P(k)\) is the **induction hypothesis**.

### Theorem 1.6

For every \(n\in\mathbb N\),

\[
1+2+\cdots+n=\frac{n(n+1)}2.
\]

### Proof

For \(n=1\),

\[
1=\frac{1(1+1)}2,
\]

so the base case holds.

Assume for some \(k\ge1\) that

\[
1+2+\cdots+k=\frac{k(k+1)}2.
\]

Then

\[
1+2+\cdots+k+(k+1)
=
\frac{k(k+1)}2+(k+1).
\]

Factor \(k+1\):

\[
\frac{k(k+1)}2+(k+1)
=
(k+1)\left(\frac k2+1\right)
=
\frac{(k+1)(k+2)}2.
\]

This is exactly the desired formula with \(n=k+1\). Therefore the identity holds for every positive integer \(n\). \(\square\)

### Why induction works

The base case establishes the first link. The inductive step proves that whenever one link holds, the next holds. Hence all later links follow.

Induction is not circular. We do not assume the theorem for every \(n\); we assume it for one arbitrary index \(k\) solely to prove the next case.

## 1.13 Strong induction

In **strong induction**, the inductive hypothesis assumes

\[
P(n_0),P(n_0+1),\ldots,P(k)
\]

and uses all these cases to prove \(P(k+1)\).

### Theorem 1.7

Every integer \(n\ge2\) is either prime or a product of primes.

### Proof

For \(n=2\), the statement is true because \(2\) is prime.

Assume the statement holds for every integer from \(2\) through \(k\). Consider \(k+1\).

If \(k+1\) is prime, we are done. If it is composite, then

\[
k+1=ab
\]

for integers \(a,b\) satisfying

\[
2\le a,b\le k.
\]

By the strong induction hypothesis, each of \(a,b\) is prime or a product of primes. Therefore \(k+1=ab\) is a product of primes. \(\square\)

This proves existence of prime factorisations. It does not yet prove uniqueness; that requires additional work.

## 1.14 Minimal counterexample arguments

The well-ordering principle states:

> Every nonempty subset of \(\mathbb N\) has a least element.

It is closely related to induction. To prove a statement for every natural number, one may assume counterexamples exist, choose the smallest counterexample, and show that a smaller counterexample must then exist—a contradiction.

This style becomes important in number theory, where descent arguments repeatedly replace a hypothetical solution by a smaller one.

## 1.15 Necessary discipline in writing proofs

A correct proof should make clear:

- what is assumed;
- what must be shown;
- where each object comes from;
- why each inference is valid;
- where the argument ends.

Avoid statements such as “obviously” when the omitted step contains the heart of the argument. Conversely, do not bury a simple idea beneath pages of algebra.

Variables should be introduced with their domains:

> Let \(n\in\mathbb Z\).

rather than merely

> Let \(n\).

Do not infer a biconditional after proving only one direction. Do not divide by an expression before establishing that it is nonzero. Do not assume that a pattern seen in examples continues forever.

## 1.16 How logic enters analytic number theory

The major conjectures of analytic number theory differ sharply in logical strength.

The statement

\[
\exists p:\ p,p+2\text{ are prime}
\]

is proved by the witness \(p=3\).

The statement

\[
\forall N\;\exists p>N:\ p,p+2\text{ are prime}
\]

asserts infinitely many twin primes. Here the quantifier order is crucial: no matter how large \(N\) is chosen, a twin-prime pair must occur beyond it.

Similarly, saying that prime gaps are bounded infinitely often means

\[
\exists B\;\forall N\;\exists\text{ primes }p<q
\quad	ext{with}\quad
p>N,
\quad q-p\le B.
\]

The Maynard–Tao bounded-gaps theorem has this logical form for some finite \(B\). The twin-prime conjecture asks whether one may take \(B=2\).

A proposed reformulation of a conjecture is useful only if it introduces new structure. If statement \(A\) is merely equivalent to the original conjecture \(B\), then proving \(A\) may be exactly as difficult as proving \(B\). Establishing equivalence is still valuable because a new formulation may suggest tools unavailable in the old language.

## 1.17 Worked proof analysis: infinitely many primes

### Theorem 1.8 — Euclid

There are infinitely many primes.

### Proof

Assume, for contradiction, that only finitely many primes exist. List them:

\[
p_1,p_2,\ldots,p_n.
\]

Form the integer

\[
N=p_1p_2\cdots p_n+1.
\]

Since \(N>1\), Theorem 1.7 implies that \(N\) has a prime divisor; call it \(q\). By assumption, \(q\) must equal one of the listed primes, say \(q=p_j\).

Because \(q\mid p_1p_2\cdots p_n\) and \(q\mid N\), it follows that \(q\) divides their difference:

\[
N-p_1p_2\cdots p_n=1.
\]

No prime divides \(1\), a contradiction. Therefore infinitely many primes exist. \(\square\)

### What the proof does not say

It does not claim that

\[
p_1p_2\cdots p_n+1
\]

is always prime. For the first six primes,

\[
2\cdot3\cdot5\cdot7\cdot11\cdot13+1=30031=59\cdot509.
\]

The argument needs only a prime divisor not contained in the original finite list.

### Logical anatomy

The theorem has the form

\[
\forall n\;\exists p>n:\ p\text{ is prime}.
\]

Euclid proves it indirectly by denying infinitude, converting that denial into a supposedly complete finite list, and constructing an integer whose prime divisor lies outside the list.

This construction—encode all known objects into one object and then alter it by \(+1\)—reappears throughout mathematics.

## 1.18 Common logical errors

### Affirming the consequent

From

\[
P\implies Q
\]

and \(Q\), one cannot generally conclude \(P\).

Example: if a number is divisible by \(4\), it is even. The number \(6\) is even, but not divisible by \(4\).

### Denying the antecedent

From \(P\implies Q\) and \(\neg P\), one cannot generally conclude \(\neg Q\).

### Circular reasoning

A proof is circular when it assumes the result it is meant to establish, possibly in disguised form.

### Confusing evidence with proof

Checking the first trillion cases is evidence, not a proof of a universal statement.

### Proving examples instead of the theorem

A variable in a proof must remain arbitrary. Showing that a claim works for \(n=5,6,7\) does not establish it for all \(n\).

### Negating incorrectly

The negation of “all” is “at least one not,” not “none.” The negation of “there exists” is “for all, not.”

## 1.19 Exercises

### Basic logic

1. Decide which of the following are propositions:
   - \(5<9\);
   - \(x+2=7\);
   - “Close the door”;
   - every prime greater than \(2\) is odd.
2. Write the negation of each proposition:
   - every integer is positive;
   - some prime is even;
   - for every real \(x\), there exists a real \(y>x\).
3. Construct truth tables for:
   - \(\neg(P\land Q)\);
   - \((P\implies Q)\land P\);
   - \((P\implies Q)\iff(\neg Q\implies\neg P)\).
4. Determine whether each implication is true for all integers \(n\):
   - \(6\mid n\implies3\mid n\);
   - \(3\mid n\implies6\mid n\);
   - \(n^2\text{ odd}\implies n\text{ odd}\).

### Direct proof and contraposition

5. Prove that the sum of two odd integers is even.
6. Prove that the product of two odd integers is odd.
7. Prove that if \(a\mid b\), then \(a\mid bc\) for every integer \(c\).
8. Prove that if \(n^2\) is odd, then \(n\) is odd.
9. Prove that if \(3\nmid n\), then \(3\nmid n^2\).
10. Prove that the square of any integer is congruent to \(0\) or \(1\pmod4\).

### Contradiction and irrationality

11. Prove that \(\sqrt3\) is irrational.
12. Prove that no largest integer exists.
13. Prove that there is no rational number whose square is \(2\).
14. Show that if \(r\in\mathbb Q\) and \(x\notin\mathbb Q\), then \(r+x\) is irrational.
15. Determine what additional condition is needed in Exercise 14 to guarantee that \(rx\) is irrational.

### Induction

16. Prove

\[
1+3+5+\cdots+(2n-1)=n^2.
\]

17. Prove

\[
1^2+2^2+\cdots+n^2=\frac{n(n+1)(2n+1)}6.
\]

18. Prove that \(2^n\ge n+1\) for every integer \(n\ge0\).
19. Prove that \(7^n-1\) is divisible by \(6\) for every positive integer \(n\).
20. Prove that a set with \(n\) elements has \(2^n\) subsets.
21. Use strong induction to prove that every integer \(n\ge2\) can be written as a product of primes.
22. Prove that every amount of postage of at least \(12\) units can be formed using stamps worth \(4\) and \(5\) units.

### Proof diagnosis

23. Find the error in the following argument:

\[
a=b
\implies a^2=ab
\implies a^2-b^2=ab-b^2
\implies(a-b)(a+b)=b(a-b)
\implies a+b=b.
\]

24. Explain why verifying the twin-prime conjecture up to \(10^{20}\) would not prove it.
25. Compare the logical forms:

\[
\forall N\;\exists p>N:\ p,p+2\text{ prime},
\]

and

\[
\exists N\;\forall p>N:\ p,p+2\text{ prime}.
\]

26. Rewrite “there are arbitrarily large prime numbers” using quantifiers.
27. Rewrite “prime gaps are unbounded” using quantifiers.
28. Negate the Riemann hypothesis in precise logical form, assuming the terms “nontrivial zero” and \(\Re(s)\) are already defined.

## 1.20 Chapter summary

A proof is a finite chain of justified inferences. The essential tools introduced in this chapter are:

- propositions and predicates;
- logical connectives;
- universal and existential quantifiers;
- direct proof;
- contraposition;
- contradiction;
- construction and uniqueness;
- counterexamples;
- induction and strong induction;
- minimal-counterexample reasoning.

These are not preliminary formalities. Later arguments about primes, convergence, analytic continuation, and zeros of L-functions depend on handling hypotheses and quantifiers precisely.

The next chapter develops the language in which mathematical objects and mappings between them are organised: sets, relations, and functions.
