# Construction 
## Key Generation

1.  Select two large distinct prime numbers p and q, such that p ≡ q ≡ 3 (mod 4). This condition ensures that each quadratic congruence modulo p and q has exactly one solution which will be required during decryption.

2.  Compute N = p*q. n is the modulus for both the public and the private keys.

3.  The public key is N, and the private key is (p, q).


## Encryption

Suppose Bob wants to send Alice a message. Bob converts the plaintext message M into an integer m such that 0 ≤ m < N.

The encryption function is simple squaring: c = m² mod N. Bob sends the ciphertext c to Alice.

## Decryption

Alice receives the ciphertext c and wants to recover the plaintext message m. Here are the decryption steps:

1.  Compute mp = c^(p+1)/4 mod p and mq = c^(q+1)/4 mod q. These are the four square roots of c modulo p and q.

2.  Use the Chinese Remainder Theorem to find the four square roots modulo N.

3.  Among the four roots, one is the original plaintext message m. The correct m can be found by additional error detection/correction information added during encryption or by context of the communication.

# Security:

The security of the Rabin cryptosystem is based on the computational difficulty of the integer factorization problem, similar to RSA. However, unlike RSA, Rabin cryptosystem has been proven to be as hard as factoring, under certain conditions.

While the encryption process in the Rabin cryptosystem is simpler than RSA (squaring vs. exponentiation), decryption is more complicated due to the need to find square roots modulo n. Moreover, for every ciphertext, there are four possible plaintexts, which requires additional information to disambiguate.

**Theorem:** Breaking Rabin is equivalent to factoring. 
1. Choose a random element $r$. 
2. Hand $r^2\ mod\ N$ to the Adversary
3. Consider outputs $r'$ from the adversary such that $(r')^2 = r^2\ mod\ N$. Then $r' \neq \pm\ r\ mod\ N$ with probability 1/2, in which case gcd($r' - r, N$) gives a factor of N.   




