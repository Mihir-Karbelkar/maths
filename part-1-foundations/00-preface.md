# Part I — Foundations

## Why begin here?

Analytic number theory joins two subjects that initially look unrelated.

Number theory asks discrete questions:

- Which integers are prime?
- How often do primes occur?
- How are primes distributed among residue classes?
- Are there infinitely many twin primes?

Analysis studies limits, continuity, infinite sums, integrals, and functions of real or complex variables. The central surprise of analytic number theory is that questions about indivisible integers can often be translated into questions about continuous or complex-valued functions.

The most famous example is Euler's identity

\[
\sum_{n=1}^{\infty}\frac1{n^s}
=
\prod_p\left(1-\frac1{p^s}\right)^{-1},
\qquad \Re(s)>1.
\]

The left side is an infinite series indexed by every positive integer. The right side is an infinite product indexed only by primes. Unique factorisation is the bridge between them.

Later, this identity becomes the starting point for the Riemann zeta function. Its zeros encode information about the distribution of primes. Dirichlet L-functions extend the method to primes in arithmetic progressions. Sieve theory attacks related questions when no sufficiently useful Euler product is available.

To understand those ideas rather than merely recognise their formulas, we need a foundation in:

1. mathematical logic and proof;
2. sets, functions, and relations;
3. number systems and completeness;
4. sequences, limits, and infinite series;
5. complex numbers and complex analysis;
6. infinite products and elementary number theory.

This part develops those tools deliberately. Every chapter has a future purpose.

## How to read this book

Mathematics is not learned by reading proofs as if they were stories. Pause before each proof and try to discover the argument yourself. Work examples by hand. When a theorem contains several hypotheses, ask what fails if one is removed.

Definitions deserve particular care. A theorem may be difficult, but once proved it becomes available forever. A misunderstood definition corrupts everything built on top of it.

Each chapter therefore uses a recurring structure:

- motivation;
- precise definitions;
- examples and non-examples;
- theorems and derivations;
- common mistakes;
- exercises;
- links to analytic number theory.

## Conventions

We use the following number systems:

\[
\mathbb N=\{1,2,3,\ldots\},\qquad
\mathbb Z=\{\ldots,-2,-1,0,1,2,\ldots\},
\]

\[
\mathbb Q=\left\{\frac ab:a,b\in\mathbb Z,\ b\ne0\right\},
\qquad
\mathbb R,
\qquad
\mathbb C.
\]

Some books include zero in \(\mathbb N\). Whenever that distinction matters, it will be stated explicitly.

The symbol \(p\) usually denotes a prime number. The notation \(p\mid n\) means that \(p\) divides \(n\). The real and imaginary parts of a complex number \(s\) are written \(\Re(s)\) and \(\Im(s)\).

A square at the end of a proof indicates completion:

\[
\square
\]

## The destination

Part I ends with a question that appears elementary:

> Can one build a function whose analytic behaviour reveals how the primes are distributed?

Euler's product says yes. Riemann's continuation of that idea says much more. The rest of the book follows that road while also examining where the method breaks—for example, when we try to detect pairs of primes rather than individual primes.
