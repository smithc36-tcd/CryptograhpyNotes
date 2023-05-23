
## Overview

In an RSA cryptosystem, the encryption key is public and distinct from the decryption key which is kept secret. As a result, it provides a method whereby one person can send another a message in secret, without the need for exchanging keys securely beforehand.

The RSA algorithm involves three steps: key generation, encryption, and decryption.

1. **Key Generation:** The key generation involves choosing two large prime numbers and calculating a modulus for the keys, by multiplying these prime numbers together. The public key pair (e, n) is generated where 'n' is the modulus and 'e' is the public exponent (commonly chosen as 65537). The private key 'd' is the modular multiplicative inverse of 'e' modulo φ(n), where φ is Euler's totient function.

2. **Encryption:** The sender, upon receiving the public key (e, n), can encrypt a message M into ciphertext C using the formula C = M^e mod n.

3. **Decryption:** The receiver, using their private key 'd', can recover the original message using the formula M = C^d mod n.

This system works because of the mathematical properties of modular arithmetic and the difficulty of factoring the product of two large prime numbers.

## Detailed Description

### Key Generation
The steps involved in the generation of RSA keys are:

1. Choose two distinct large random prime numbers $p$ and $q$. For security purposes, the integers $p$ and $q$ should be chosen at random and should be similar in magnitude but differ in length by a few digits to make factoring harder. Prime integers can be efficiently found using a primality test.

2. Compute $n = pq$. $n$ is used as the modulus for both the public and private keys. Its length, typically expressed in bits, is the key length.

3. Compute the Carmichael's totient function $λ(n)$, where $λ$ is Carmichael's totient. If $p$ and $q$ are prime, $λ(n) = \text{lcm}(p − 1, q − 1)$, and $\gcd(λ(n), e) = 1 ; 1 < e < λ(n)$. In this step, it is ensured that 'e' which is the public exponent, is a valid number i.e., it is less than $λ(n)$ and co-prime to $λ(n)$. 

4. Determine $d$ as $d ≡ e⁻¹ (mod λ(n))$; i.e., $d$ is the modular multiplicative inverse of $e (modulo λ(n))$. This means that $d \cdot e ≡ 1 (mod λ(n))$. 

5. Public key is $(e, n)$ and private key is $(d, n)$.

### Encryption
The encryption of a plaintext m is done using the formula:
$$
c ≡ m^e (mod\ n)
$$
Here, m is the plaintext message that an outside party is encrypting and c is the resultant ciphertext.

### Decryption
The decryption of the ciphertext c is done using the formula:
$$
m ≡ c^d (mod\ n)
$$
Here, m is the plaintext message after decrypting c.

## Security of RSA
RSA's security comes from the fact that, while it is easy (on the order of operations proportional to the number of digits in the common modulus n) to multiply two large prime numbers and create the public modulus, it is computationally infeasible (on the order of operations proportional to an exponential in the number of digits in n) to factor a composite number if its prime factors are sufficiently large.

Furthermore, RSA is considered secure against a chosen plaintext attack as long as padding is used. RSA without padding is not secure.

### Factoring
The obvious way to break RSA is to factor the public modulus $N$ and recover the prime factors $q$ and $p$. 
- The number field sieve factors $N$ in time $$
O(e^{(1.92 + O(1))((\ln N)^{1/3} + (\ln \ln N)^{2/3})})
$$
- The elliptic curve method factors $N$ in time $$
	O(e^{(1 + O(1))\sqrt{2\ln p \ln \ln p}})
	$$
#### Small Encryption exponents

- **Small messages:** If $m$ is small, then $m^e < N$. Thus, no reduction takes place and $m$ can be computed in $\mathbb{Z}$ by taking the eth root. 
- **Identical Plaintext:** If a message $m$ is encrypted under moduli $N_1,\ N_2,\ N_3,\ \&\ N_4$ as $c_1,\ c_2\, c_3\ \&\ c_4$ then CRT implies a $c \in \mathbb{Z}^*_{N_1,N_2,N_3,N_4}$ such that $c = c_i\ \mod N_i$ and $c = m^e\ \mod N_1N_2N_3N_4$ with $m < N_i$. 
