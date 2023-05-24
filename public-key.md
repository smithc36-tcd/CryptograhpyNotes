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
Let $f = \{f_\alpha\}$ be ensemble of permutations (bijections). 
- Gen generates a random key-pair $\alpha = (pk, sk)$
- Eval takes $pk$ adn $x$ as input and efficiently evaluates $f_\alpha(x)$
- Invert takes $sk$ and $y$ as input an efficiently evaluates the inverse $f_\alpha^{-1}(y)$

**One-way** if Eval$_{pk}(\cdot)$ is one-way for a random $pk$. 

### Based on proofs of knowledge
Proof of knowledge of exponent is a type of interactive proof system where a prover demonstrates to a verifier that they know a value for a particular mathematical relationship without revealing that value. Also known as Zero-knowledge proofs. 

Zero-knowledge proofs are a type of cryptographic protocol in which one party (the prover) can prove to another party (the verifier) that they know a value or that a certain statement is true, without conveying any other information apart from the fact that they indeed know the value or the statement is true.

There are several properties a zero-knowledge proof must satisfy:

1.  Completeness: If the statement is true and both the prover and verifier follow the protocol correctly, the verifier is convinced of this fact by the end of the protocol.

2.  Soundness: If the statement is false, no cheating prover can convince the verifier that it is true, except with some small probability.

3.  Zero-Knowledge: If the statement is true, the verifier learns nothing other than this fact. This is usually formalized by showing that every verifier has some simulator that, given only the statement to be proved (and no access to the prover), can produce a transcript that looks just like an interaction between the honest prover and the verifier.

[[Schnorr's Protocol]] is one such proof. 

### PKI's (Public-key infrastructure)

#### Signing public-keys of others
Suppose that Alice computes  signature $\sigma_{A,B} = \text{Sig}_{sk_A}(pk_B, BOB)$ of Bobs public key $pk_B$ and his identity and hands it to Bob. Suppsose that Eve holds Alices public-key $pk_A$. Then anyone can hand $(pk_B, \sigma_{A,B})$ directly to Eve and Eve will be convinced that $pk_B$ is Bob's key (Assuming she trusts alice). 

#### Certificates
A **certificate** is a signature of a public-key along with some information on how the key may be used e.g. it may allow the holder to issue certificates. A certificate is valid for a given setting if the signature is valid and the usage information in the certificate matches that of the setting. Some parties must be trusted to issue certificates. These parties are called **Certificate Authorities (CA).**

#### Certificate chains
A CA may be "distributed" using certificate chains. 
- Suppose that Bob holds valid certificates $$
\sigma_{0,1}, \sigma_{1,2}, ..., \sigma_{n-1, n}
$$ 
where $\sigma_{i-1, i}$ is a certificate of $pk_{P_i}$ by $P_{i-1}$. 
