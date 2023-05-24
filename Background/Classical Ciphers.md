**Caesar Cipher**

Named after Julius Caesar, who reportedly used it for his private correspondence, the Caesar cipher is one of the simplest and most widely known encryption techniques. It's a type of substitution cipher in which each letter in the plaintext is 'shifted' a certain number of places down the alphabet. For example, with a shift of 3, A would be replaced by D, B would become E, and so on.

---

**Affine Cipher**

The Affine cipher is a type of monoalphabetic substitution cipher, where each letter in an alphabet is mapped to its numeric equivalent, encrypted using a simple mathematical function, and then converted back to a letter. The mathematical function for encryption in an affine cipher is a linear equation of the form `(ax + b) mod m`, where `a` and `b` are constants, `x` is the numerical equivalent of a plaintext letter, `m` is the size of the alphabet, and `mod` denotes the modulus operation.

---

**Substitution Cipher**

A substitution cipher is a method of encryption by which units of plaintext are replaced with ciphertext, according to a regular system; the "units" may be single letters (the most common), pairs of letters, triplets of letters, mixtures of the above, and so forth. The receiver deciphers the text by performing the inverse substitution. The most famous example of a substitution cipher is the Caesar Cipher.

---

**Vigenère Cipher**

The Vigenère cipher is a method of encrypting alphabetic text by using a series of interwoven Caesar ciphers based on the letters of a keyword. It's a simple form of polyalphabetic substitution. Essentially, it uses multiple Caesar ciphers to encrypt the text, changing the cipher for each letter based on a repeating keyword. This means that the same plaintext letter could be encrypted to different ciphertext letters, making frequency analysis much more difficult. However, it is vunerable to [[Types of attacks#Known plaintext attack|Known Plaintext Attacks]].

---

**Hill Cipher**

The Hill cipher is a polygraphic substitution cipher based on linear algebra. Invented by Lester S. Hill in 1929, it uses matrix theory to encrypt and decrypt messages. Each letter is represented by a number modulo 26. A block of letters in the plaintext is converted to a vector of numbers and is dotted with a matrix. The result is then converted back to letters to form the ciphertext.

---

**Permutation Cipher**

A permutation, or transposition cipher, is a method of encryption in which the positions held by plaintext are shifted according to a regular system. In other words, the plaintext is reordered. The key to a permutation cipher is the permutation used, and both sender and receiver must know and use the same secret permutation. For example, a simple columnar transposition cipher could rearrange the letters in a plaintext by writing them out in rows, then combining the letters in each column together, perhaps with a specific order to the columns.
