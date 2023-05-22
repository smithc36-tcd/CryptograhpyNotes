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

#### Lagrange's Theorem
In the field of group theory, Lagrange's theorem states that for any finite group G, the order (number of elements) of every subgroup H of G divides the order of G. This is a fundamental result in algebra and it has numerous applications, including the theory of polynomial equations.

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