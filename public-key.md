## RSA
The [[RSA]] (Rivest-Shamir-Adleman) is a public-key cryptosystem that is widely used for secure data transmission. It is an asymmetric cryptographic algorithm which essentially means it uses two keys. One key can be made public, and while the other remains private. The RSA algorithm first came into existence in 1977 and is named after Ron Rivest, Adi Shamir, and Leonard Adleman, who invented it at MIT.
In an RSA cryptosystem, the encryption key is public and distinct from the decryption key which is kept secret. As a result, it provides a method whereby one person can send another a message in secret, without the need for exchanging keys securely beforehand.

### Rabin
[[Rabin]] is a cryptosystem based of the same principle as RSA, factoring large numbers. The Rabin cryptosystem is an asymmetric cryptographic algorithm named after its inventor, Michael Rabin. Rabin's algorithm was one of the first asymmetric cryptosystems and, like RSA, its security relies on the difficulty of factoring large numbers.

## Diffie-Hellman
The [[Diffie-Hellman Key]] Exchange is a method for securely exchanging cryptographic keys over a public communication channel. This was one of the first public-key protocols as introduced by Whitfield Diffie and Martin Hellman in 1976.

The central idea behind the protocol is the use of exponential functions and the properties of modular arithmetic. These properties ensure that even if an eavesdropper listens to the communication, it will be computationally infeasible for them to determine the exchanged secret key.

### El Gamal
The [[ElGamal]] cryptosystem is an asymmetric key encryption algorithm designed for public-key cryptography. It was described by Taher Elgamal in 1985 and is based on the Diffie-Hellman key exchange. El Gamal is essentially Diffie-Hellman + OTP. 

The ElGamal cryptosystem consists of three components: the key generator, the encryption algorithm, and the decryption algorithm. 

### The Discrete logarithm problem
**Definition:** Let $G$ be the cyclic group of order $q$ and let $g$ be a generator of $G$. Thr **discrete log** of $y \in G$ is the basis $g$ is defined as the unique $x \in \{0,1,...,q-1\}$ such that $$
y = g^x $$
**Definition:** The **Discrete Log (DL) Assumption** in $G$ states that if generators $g_n$ and $y_n$ of $G_{q_n}$ are randomly chosen, then for every polynomial time algorithm A $$
\Pr[D(g_n, y_n) = \log_{g_n} y_n] $$ is neglible. 

**Definition:** Let $g$ be a generator of $G$. The **Decision Diffie-Hellman (DDH) Assumption** in $G$ states that if $a, b, c \in \mathbb{Z}_q$ are randomly chosen, then for every polynomial time algorithm A $$
\left| \Pr[A(g^a, g^b, g^{ab}) = 1] - \Pr[A(g^a, g^b, g^c) = 1] \right| $$ is negligible. 

#### Algorithm to attack the discrete log problem
There a number of algorithms which can be used to calculate the discrete log. They can be found here [[DL algorithms]]. 

## Elliptic Curves 
[[Elliptic Curves]] are another method of generating groups, The best known DL-algorithm in an elliptic  gurve group with prime order $q$ are generic algorithms, i.e. they have arunning time O($\sqrt{q}$). Arguably we can use shorter keys for equivalent bit security compared to RSA keys. 

Elliptic curves are a type of mathematical object defined by a specific type of equation. They are used in a variety of mathematical areas, but in the context of cryptography, they form the basis for elliptic curve cryptography (ECC).

## Signature Schemes 
A digital [[Signature scheme]] is the **public-key** equivalent of a MAC. The reciever verifies the integrity and authenticity of the message. 

### Based on Trapdoor One-way Permutations
TO DO 

### Based on proofs of knowledge
TO DO 

### PKI's 
TO DO 
