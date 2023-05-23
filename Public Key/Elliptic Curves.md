An elliptic curve is defined by an equation of the form:
$$
y² = x³ + ax + b
$$
For some numbers a and b. The solutions to this equation, together with a special "point at infinity," form the elliptic curve.

The set of points on an elliptic curve, together with the operation of "point addition," forms what's known as an abelian group. This is a mathematical structure that behaves in some ways like the familiar operation of addition on numbers.

In the context of ECC, the abelian group structure of an elliptic curve is used to construct cryptographic systems. In particular, it's used to construct systems for public key cryptography, which are systems where each user has a pair of keys - a public key, which can be freely shared and used by anyone to encrypt messages, and a private key, which is kept secret and used to decrypt messages.

The security of ECC comes from the fact that, while it's relatively easy (computationally) to perform point addition and to multiply a point by an integer, it's very hard to reverse these operations - that is, given a point P and a point Q = nP, it's hard to find the integer n.

## Singular points
**Definition:** A point (u, v) $\in E(\mathbb{E})$, with $\mathbb{E}$ an extenstion field of $\mathbb{F}$ is singular if 

$$
\frac{\delta g(x, y)}{\delta x}(u,v) = \frac{\delta g(x, y)}{\delta y}(u,v) = 0
$$
**Definition:** A plane cubic curve is **smooth** if $E(\bar{\mathbb{F}})$ contains no singular points. 


## Other important points 

Elliptic curves are a fundamental concept in number theory and algebraic geometry, and they have significant applications in cryptography. Here are some key concepts when defining and working with elliptic curves:

1.  **Curve Definition**: An elliptic curve over a field is defined by the equation y² = x³ + ax + b, where 4a³ + 27b² ≠ 0 (to avoid singularities). The points (x,y) satisfying this equation, together with an extra point called "the point at infinity," form the elliptic curve.

2.  **Point Addition**: An important operation on the elliptic curve is point addition. If you take two points P and Q on the curve, you can "add" them together to get a third point R. This is done by drawing a line through P and Q, and finding where it intersects the curve a third time, then reflecting that point in the x-axis. This operation gives the elliptic curve a group structure, which is fundamental to its use in cryptography.
   
3.  **Point Doubling**: Point doubling is a special case of point addition where P=Q. Instead of drawing a line through two different points, we take the tangent to the curve at P, and see where it intersects the curve again.
   
4.  **Scalar Multiplication**: This involves adding a point P on the curve to itself n times. Scalar multiplication is used extensively in the elliptic curve version of the Diffie-Hellman protocol and other cryptographic schemes.
   
5.  **Elliptic Curve Discrete Logarithm Problem (ECDLP)**: This is the problem of finding a number n given points P and Q=nP. This is considered computationally difficult, and is the basis for the security of most elliptic curve cryptography.
   
6.  **Choice of Field**: The choice of the field over which the elliptic curve is defined matters a lot. For cryptographic applications, we usually consider elliptic curves over finite fields, particularly those of large prime order or those that are powers of 2. The specific properties of these fields can make computations more efficient and can also impact the security of the cryptographic schemes.
   
7.  **Curve Selection**: Selecting an appropriate elliptic curve for cryptographic use involves various considerations, including security and performance. Some curves are known to have vulnerabilities that can be exploited by certain attacks, so these must be avoided.
   
8.  **Point at Infinity**: This is an abstract element added to the elliptic curve to serve as the identity element for the group operation. In the geometric interpretation, it's the point where vertical lines "meet," making the curve complete.
   
9.  **Endomorphisms**: These are functions from the curve to itself that respect the curve's group structure. Some curves have non-trivial endomorphisms, which can be used to speed up scalar multiplication operations, a key operation in elliptic curve cryptography.