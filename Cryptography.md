# Background
There is some background assumed for the course. There is some [[Information Theory]] assumed as well as some background with [[Elementary Number Theory]]. Most of which will be covered in the above notes. 

# Symmetric-key Cryptography
[[Symetric-key]]


# Hash Functions
A [[Hash functions]] is a deterministic process that takes an input (or 'message') and returns a fixed-size string of bytes. The output, often a 'digest', is ideally unique to each unique input. Hash functions have specific [[Hash properties]]. 


# Message Authentication Codes (MACs)
A Message Authentication Code ([[MAC]]) is a short piece of information used to authenticate a message and to provide integrity and authenticity assurances on the message. Integrity assurances detect accidental and intentional message changes, while authenticity assurances affirm the message's origin.

[[HMAC]] is a specific type of message authentication code that uses a cryptographic hash function (like SHA-256) and a secret cryptographic key. It's used to verify both the data integrity and the authenticity of a message.

MACs and HMACs are tools for ensuring message integrity and authenticity. They protect against tampering and forgery by tying a message to a secret key, and are widely used in internet communication protocols like TLS and IPsec.

#### Universal hash function as a MAC
**Theorem:** A $t$-universal hash function $f_\alpha$ for a randomly chosen secret $\alpha$ is an ***unconditionally secure*** MAC, provided that the number of queries is smaller than $t$. 

This assumes that $t$ is $iid$. This can be seen as the OTP equivalent for secrecy, this is the perfect MAC. If it were to be used for $t+1$ messages we could prove it is not a random function. 

# Public-Key Cryptography

**Definition:** A [[public-key]] cryptosystem is a tuple (Gen, $E$, $D$) where, 
- Gen is a **probabilistic key generation algorithm** that outputs keypairs ($pk$, $sk$). 
- $E$ is a (possibly probabilistic) **encryption algorithm** that given a public key $pk$ and a message $m$ in the plaintext space $\mathbb{M}_{pk}$ outputs a ciphertext $c$, and 
- $D$ is a **decryption algorithm** that given a secret key $sk$ and a ciphertext $c$ outputs the plaintext $m$. 
such that $D_{sk}(E_{pk}(m)) = m$ for every $(pk, sk)$ and $m \in \mathbb{M}$. 



# Pseudo-random generators
TO DO