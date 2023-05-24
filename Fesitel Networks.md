**Feistel Network**

A Feistel network is a structure used in the construction of block ciphers, named after the German-born physicist and cryptographer Horst Feistel who did pioneering research while working for IBM (USA). Feistel networks are used in many popular symmetric key algorithms such as DES (Data Encryption Standard), Blowfish, and others.

---

**Structure of Feistel Network**

A typical Feistel network involves splitting the block of plaintext to be encrypted into two equal halves, that are processed separately and then swapped. Each half goes through the same set of transformations (referred to as a round), and these rounds are performed multiple times to enhance the security of the resultant cipher. 

Here are the primary steps:

1. **Splitting:** The plaintext block is divided into two equal halves, denoted as L (left) and R (right).

2. **Processing (Feistel function):** The right half (R) of the data is processed with a round function, F, using a subkey generated from the original encryption key. This function can be any deterministic function - typically a complex mix of substitutions and permutations. The output of this round function is then combined with the left half (L) of the data, typically using XOR operation. 

3. **Swapping:** After processing, the two halves of the data are swapped, unless it's the last round.

4. **Iterative Rounds:** Steps 2 and 3 are repeated a number of times to increase security. Each iteration is known as a round and uses a different subkey, generated from the original encryption key. 

5. **Final Combination:** The two halves are combined to give the ciphertext block.

The decryption process in a Feistel network is essentially the same as the encryption process, but the subkeys are applied in the reverse order.

---

**Encryption**
The encrytion of a given round can be defined as, 
$$
\begin{align*}
L_{i+1} &= R_i \\ 
R_{i+1} &= L_i + F_{k_i}(R_i) 
\end{align*}
$$
**Decryption**
The decryption of a given round is given as, 
$$
\begin{align*}
L_{i-1} &= R_i + F_{k_i}(L_{i-1}) \\ 
R_{i-1} &= L_i
\end{align*}
$$
---

**Features of Feistel Network**

1. **Versatility:** One of the significant advantages of the Feistel structure is its versatility. The exact operations used in the round function, F, can be varied without changing the overall structure of the algorithm. This makes Feistel networks suitable for constructing a wide variety of block ciphers.

2. **Simplicity of Inversion (Decryption):** Despite the complex structure, Feistel networks are straightforward to invert, which means decryption is relatively simple. The same algorithm can be used for both encryption and decryption.

3. **Security:** With enough rounds, a sufficiently complex round function, and secure key generation, Feistel ciphers can achieve high levels of security.

---

**Conclusion**

Feistel networks have proved to be a fundamental building block in creating symmetric key algorithms. Their flexibility, simplicity, and security have made them popular for designing various encryption algorithms.

**References**
1. Schneier, Bruce. Applied Cryptography: Protocols, Algorithms, and Source Code in C. John Wiley & Sons, 1996.
2. Stallings, William. Cryptography and Network Security: Principles and Practice. Pearson, 2017.