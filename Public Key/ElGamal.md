# Construction
## Key Generation

1. Choose a large prime number p and a generator g of the multiplicative group of integers modulo p. These are the system's parameters.
2. Choose a secret key x from the set {1,..., p-2}.
3. Compute the public key y = g^x mod p.

The pair (g, p) is the public key, and x is the private key.

## Encryption

To encrypt a message m (where m is an integer in the range 0 through p-2), do the following:

1. Choose a random integer k from the set {1,..., p-2}.
2. Compute c1 = g^k mod p.
3. Compute c2 = m * y^k mod p.

The ciphertext is the pair (c1, c2).

## Decryption

To decrypt the ciphertext (c1, c2), do the following:

1. Compute s = c1^x mod p.
2. Compute m = c2 * (s^-1) mod p where s^-1 is the multiplicative inverse of s modulo p.

The plaintext message m is now recovered.

# Security

The ElGamal encryption is considered secure against chosen plaintext attacks. The hardness of the discrete logarithm problem is the basis for the security of ElGamal encryption. It is computationally infeasible to compute x given g, p, and g^x mod p, even when g and p are public.

However, ElGamal encryption is not semantically secure because it is deterministic. Semantic security can be achieved by introducing random padding.

Finally, the ElGamal encryption is also malleable. This means that an attacker can transform a ciphertext into another valid ciphertext which decrypts to a related plaintext. 

- Finding the secret key is equivalent to the DL problem. 
- Finding the plaintext from the ciphertext and the public key is equivalent to the DH problem. 
- The CPA security of El Gamal is equivalent to the DDH problem