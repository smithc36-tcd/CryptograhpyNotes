## Setup
Two public parameters are agreed upon at the start:

- A prime number, p.
- A generator, g, which is a primitive root modulo p.

## Key Exchange Process

1. Each party (say, Alice and Bob) generates a private key. For Alice, let's denote it as a, and for Bob, let's denote it as b. These are chosen randomly and kept secret.
2. Then, they each compute a public key. Alice computes A = g^a mod p and sends A to Bob. Similarly, Bob computes B = g^b mod p and sends B to Alice.
3. Upon receiving the other party's public key, they each compute the shared secret key. Alice computes s = B^a mod p, and Bob computes s = A^b mod p. Due to the properties of modular arithmetic, both computations result in the same value, g^(ab) mod p. This becomes their shared secret key.

## Security
The security of the Diffie-Hellman key exchange comes from the difficulty of the Discrete Logarithm Problem. While it's easy to compute A = g^a mod p, it's computationally infeasible to compute the inverse operation (given A, g and p, find a).

The exchanged keys can then be used as a symmetric key for further secure communication, for example using the [[AES]] encryption algorithm.

Note that while the Diffie-Hellman Key Exchange is secure against eavesdroppers, it does not protect against man-in-the-middle attacks. This is where an attacker intercepts the communication and establishes separate shared keys with Alice and Bob. This problem can be mitigated by using the protocol in conjunction with a public key digital signature system, or by using the variant called Ephemeral Diffie-Hellman which involves public key infrastructure for authentication.
