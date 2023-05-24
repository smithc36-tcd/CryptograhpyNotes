# Background
There is some background assumed for the course. There is some [[Information Theory]] assumed as well as some background with [[Number Theory]]. Most of which will be covered in the above notes. 

---

# Symmetric-key Cryptography
In [[Symetric-key]], the sender and receiver must both have access to the same secret key, and this key must be securely exchanged and kept secret from all other parties. The security of symmetric key cryptography relies heavily on the secrecy of the key because anyone with access to this key can decrypt the encrypted data.

The main drawback of symmetric key cryptography is the key distribution problem. Because the same key is used for both encryption and decryption, it must be shared somehow between the sender and the receiver. In a large network, distributing secret keys in a secure manner can be challenging and potentially vulnerable to interception. This issue is typically addressed by using asymmetric key cryptography for secure key exchange, then symmetric key cryptography for the actual data encryption.

---

# Hash Functions
A [[Hash functions]] is a deterministic process that takes an input (or 'message') and returns a fixed-size string of bytes. The output, often a 'digest', is ideally unique to each unique input. Hash functions have specific [[Hash properties]]. 

---

# Message Authentication Codes (MACs)
A Message Authentication Code ([[MAC]]) is a short piece of information used to authenticate a message and to provide integrity and authenticity assurances on the message. Integrity assurances detect accidental and intentional message changes, while authenticity assurances affirm the message's origin.

[[HMAC]] is a specific type of message authentication code that uses a cryptographic hash function (like SHA-256) and a secret cryptographic key. It's used to verify both the data integrity and the authenticity of a message.

MACs and HMACs are tools for ensuring message integrity and authenticity. They protect against tampering and forgery by tying a message to a secret key, and are widely used in internet communication protocols like TLS and IPsec.

#### Universal hash function as a MAC
**Theorem:** A $t$-universal hash function $f_\alpha$ for a randomly chosen secret $\alpha$ is an ***unconditionally secure*** MAC, provided that the number of queries is smaller than $t$. 

This assumes that $t$ is $iid$. This can be seen as the OTP equivalent for secrecy, this is the perfect MAC. If it were to be used for $t+1$ messages we could prove it is not a random function. 

---

# Public-Key Cryptography

**Definition:** A [[public-key]] cryptosystem is a tuple (Gen, $E$, $D$) where, 
- Gen is a **probabilistic key generation algorithm** that outputs keypairs ($pk$, $sk$). 
- $E$ is a (possibly probabilistic) **encryption algorithm** that given a public key $pk$ and a message $m$ in the plaintext space $\mathbb{M}_{pk}$ outputs a ciphertext $c$, and 
- $D$ is a **decryption algorithm** that given a secret key $sk$ and a ciphertext $c$ outputs the plaintext $m$. 
such that $D_{sk}(E_{pk}(m)) = m$ for every $(pk, sk)$ and $m \in \mathbb{M}$. 

--- 

# Pseudo-random generators
**Definition:** An efficient algorithm [[PRG]] is a **Pseudo-random generator (PRG)** if there exists a polynomial $p(n) > n$ such that for every polynomial time adversary $A$, if a seed $s \in \{0,1\}^n$ and a random string $u \in \{0,1\}^{p(n)}$ are chosen randomly, then 
$$
|\Pr[A(PRG(s)) = 1] - \Pr[A(u) = 1]|
$$ is negligible. Informally $A$ cannot distinguish PRG(s) from a truly random string in $\{0,1\}^{p(n)}$.\

Hello git