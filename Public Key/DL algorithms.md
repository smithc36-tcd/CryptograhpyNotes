The algorithms which can be used to calculate the discrete log are 

**Discrete Logarithm Problem**

To understand the following algorithms, it's important to first understand the discrete logarithm problem. This problem involves finding an exponent x given a generator g, an element h of a finite group G, and a prime modulus p, such that g^x = h (mod p). 

# Brute force 

Brute force is simply a brute force search. It has complexity $O(q)$. 

# Shank's baby-step giant-step
Shanks' Baby-Step Giant-Step ([[BSGS]]) is an algorithm in number theory used to solve discrete logarithm problems. It was named after Daniel Shanks who introduced the method in 1971. The algorithm provides a faster, though still exponential, approach than the naive method of brute-forcing the problem.


# Pollard-$\rho$ 
Pollard's rho algorithm ([[Pollard-P]]) is a method for finding the prime factors of a composite integer or solving the discrete logarithm problem. The algorithm's name derives from its use of the Greek letter ρ (rho), whose shape suggests the "cycle detection" used in the algorithm. It was invented by British mathematician John Pollard in 1975.


# Index Calculus
The [[Index Calculus]] algorithm is a powerful method used for solving the discrete logarithm problem (DLP) in certain groups, such as the multiplicative group of integers modulo p, and groups related to certain types of elliptic curves. It was introduced in the late 1970s and early 1980s by Donald Coppersmith. Unlike algorithms such as Pollard's rho or baby-step giant-step, which have a running time dependent on the size of the group, index calculus has a subexponential running time for suitable groups, making it potentially much faster for large inputs.


# Pohlig-Hellman 
The [[Pohlig-Hellman]] algorithm, named after its inventors Stephen Pohlig and Martin Hellman, is a method for solving the discrete logarithm problem when the order of the group in question has only small prime factors. This algorithm, introduced in 1978, illustrates the importance of carefully choosing the parameters of a cryptographic scheme.