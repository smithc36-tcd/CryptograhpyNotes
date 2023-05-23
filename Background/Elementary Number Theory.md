Some important definitons

**Greatest Common Divisor:** The GCD of two integers $m$ and $n$ is a common divisor $d$ such that every common divisor $d'$ divides $d$.

#### The Euclidean algorithm
The Euclidean Algorithm is an efficient method for computing the greatest common divisor (GCD) of two integers. The GCD of two integers a and b is the largest number that divides both of them without leaving a remainder.

The algorithm is based on the principle that the GCD of two numbers a and b (where a > b) is equal to the GCD of b and a mod b. This process is repeated, reducing the problem to a pair of smaller numbers each time, until it reaches a pair where the smaller number is 0. The GCD is the remaining non-zero number.

#### Stein's Algorithm (Binary GCD)
Stein's Algorithm, also known as the binary GCD algorithm, is an algorithm that computes the GCD of two integers. Stein's algorithm uses simpler arithmetic operations than the conventional Euclidean algorithm; it replaces division with arithmetic shifts, comparisons, and subtraction.

The binary GCD algorithm is based on the following facts:

-   If u and v are both even, then gcd(u, v) = 2·gcd(u/2, v/2),
-   If u is even and v is odd, then gcd(u, v) = gcd(u/2, v),
-   If both are odd, and u ≥ v, then gcd(u, v) = gcd((u - v)/2, v),
-   If both are odd and u < v, then gcd(u, v) = gcd((v - u)/2, u).

#### Bezout's Lemma
Bezout's Lemma (also known as Bezout's Identity) states that if a and b are integers with greatest common divisor d, then there exist integers x and y such that ax + by = d. Moreover, d is the smallest positive integer that can be written in this form.

#### The Extended Euclidean Algorithm 
The Extended Euclidean Algorithm is a version of the Euclidean Algorithm that also finds the coefficients of Bezout's identity (those integers x and y).

This algorithm is particularly useful in modular arithmetic and cryptography, because one of the coefficients (which can be calculated efficiently using the Extended Euclidean Algorithm) is the modular multiplicative inverse of a given number modulo another number. That is, given numbers a and m, the algorithm finds number x such that (ax) mod m = 1.

#### Chinese Remainder Theorem
The Chinese Remainder Theorem is a result in number theory that gives a solution to simultaneous linear congruences. If you have several numbers which leave different remainders when divided by several different divisors, and if these divisors are pairwise coprime (the GCD of each pair is 1), then there is a unique solution to this system of simultaneous congruences modulo the product of these divisors.

**Theorem:** Let $\{n_1, ..., n_k\}$ be positive pairwise coprime integers and let $a_1, ..., a_k$ be integers. Then the equation system 

$$
\begin{align*}
x &= a_1\ mod\ n_1 \\
x &= a_2\ mod\ n_2 \\
x &= a_3\ mod\ n_3 \\
\quad\ \vdots \\
x &= a_k\ mod\ n_k \\
\end{align*}
$$
has a unique solution in $\{ 0, ..., \Pi_i(n_{i-1})\}$ . 

#### Lagrange's Theorem
In the field of group theory, Lagrange's theorem states that for any finite group G, the order (number of elements) of every subgroup H of G divides the order of G. This is a fundamental result in algebra and it has numerous applications, including the theory of polynomial equations.

**Theorem:** If $H$ is a subgroup of a finite group $G$, then $|H|$ divides $|G|$ .

#### Eulers Totient Function
In number theory, Euler's totient function counts the positive integers up to a given integer n that are relatively prime to n. In other words, φ(n) is the number of integers k in the range 1 ≤ k ≤ n for which the greatest common divisor gcd(n, k) is equal to 1.

For example, φ(9) = 6 because there are six numbers relatively prime to 9 in the range from 1 to 9: 1, 2, 4, 5, 7 and 8.

#### Fermat's little theorem and Eulers Theorem
Fermat's Little Theorem states that if p is a prime number, then for any integer a, the number ap − a is an integer multiple of p. In the notation of modular arithmetic, this is expressed as:
$$
a^p \equiv a \quad (mod\ p)
$$
Euler's theorem is a generalization of Fermat's Little Theorem. It states that if a and n are coprime positive integers, then:
$$
a^{(\phi(n))} ≡ 1 \quad (mod\ n)
$$

#### Prime Number Theorem
**Theorem:** Let $\pi(m)$ denote the number of primes $0 < p \leq m$, then
$$
\lim_{m \to \infty} \dfrac{\pi(m)}{\tfrac{m}{\ln(m)}} = 1
$$

#### Legendre Symbol 
Legendre symbol is a mathematical function that gives information about whether a number is a quadratic residue modulo a prime. In simpler terms, it tells us if a given number has a square root modulo a prime number.

Given an integer a and an odd prime number p, the Legendre symbol (a/p) is defined as follows:

1. (a/p) = 0 if a is a multiple of p.
2. (a/p) = 1 if a is not a multiple of p and there exists an integer x such that x^2 ≡ a (mod p). In other words, if a has a square root modulo p (i.e., a is a quadratic residue modulo p).
3. (a/p) = -1 if a is not a multiple of p and there does not exist such an integer x. That is, if a is a quadratic non-residue modulo p.

To calculate the Legendre symbol, we typically use properties of the symbol, including its multiplicativity and periodicity, and Euler's Criterion, which provides a formula for the Legendre symbol in terms of exponentiation modulo p.

The Legendre symbol is used in many areas of number theory, including the law of quadratic reciprocity, which provides a formula for the product of the Legendre symbols (a/p) and (p/a).

It's important to note that the Legendre symbol (a/p) is only defined when p is a prime number. For general odd integers, we use the Jacobi symbol instead, which is a generalization of the Legendre symbol.

#### Jacobi Symbol 
The Jacobi symbol is an extension of the Legendre symbol, which is defined for all positive odd integers, not just for prime numbers. The Jacobi symbol is denoted as (a/n) where a is an integer and n is a positive odd integer.

When n is a prime number, the Jacobi symbol and the Legendre symbol are the same. However, when n is a composite number, the Jacobi symbol can be defined, while the Legendre symbol cannot.

The Jacobi symbol (a/n) is defined as the product of the Legendre symbols for each of the prime factors of n.

In other words, if n is factored into primes as $n = p_1^{e_1} * p_2^{e_2} * ... * p_k^{e_k}$, then the Jacobi symbol is given by:
$$
(\frac{a}{n}) = (\frac{1}{p1})^{e_1} * (\frac{a}{p2})^{e_2} * ... * (\frac{a}{pk})^{e_k}
$$
Each term (a/pi)^ei is a Legendre symbol and can be evaluated as described in the previous response.

It's important to remember that while the Legendre symbol gives meaningful information about whether a number is a quadratic residue modulo a prime (that is, whether it has a square root), the Jacobi symbol does not necessarily provide this information when n is composite. For example, (a/n) = 1 does not guarantee that a has a square root modulo n.

The Jacobi symbol is used in many areas of number theory, including algorithms for primality testing and integer factorization. For example, the Solovay-Strassen primality test uses the Jacobi symbol to probabilistically determine whether a number is prime or composite.
