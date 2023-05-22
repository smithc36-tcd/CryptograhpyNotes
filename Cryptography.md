## Background
There is some background assumed for the course. There is some [[Information Theory]] assumed as well as some background with [[Elementary Number Theory]]. Most of which will be covered in the above notes. 

## Ciphers 
A cipher is a method of disguising and securing communication by transforming the original message (plaintext) into an encoded format (ciphertext) that can only be understood if decrypted. The process of transforming plaintext into ciphertext is called encryption, and the reverse process is called decryption.

There has been a long journey from [[Classical Ciphers]] such as Caeser's cipher to modern day ciphers such as Block Ciphers. 

### Block Ciphers
Block ciphers are a type of symmetric key cipher which operates on fixed-size blocks of plaintext and ciphertext. They use the same key for both encryption and decryption. The key is used to control the transformation of plaintext into ciphertext and vice versa.

Here's a brief description of how block ciphers work:

1. **Encryption**: The plaintext is divided into blocks of a fixed size. If the last block is not long enough to fill the block size, it is padded with extra bits to bring it up to the correct size. Each block is then encrypted using the same key, producing a block of ciphertext of the same size.

2. **Decryption**: The process is reversed to recover the plaintext. Each block of ciphertext is decrypted using the same key, and the padding (if any was added during encryption) is removed to recover the original plaintext.

Block ciphers can be very secure, but their security depends on the size of the key and the security of the encryption algorithm. They are widely used in many different types of cryptographic systems, including secure communication protocols, secure file storage, and digital signatures.

Common examples of block ciphers include [[AES]] (Advanced Encryption Standard) which is a type of [[SPN]], [[DES]] (Data Encryption Standard) which is a type of [[Fesitel Networks]], and Blowfish. Each of these has different properties, including different block sizes and key lengths, and they are suitable for different types of tasks.

### Modes of Operation
In cryptography, the term "[[Modes of Operation]]" refers to the ways in which a block cipher (a type of encryption algorithm that operates on fixed-size blocks of data) can be used. Each mode has different properties and is suitable for different types of tasks. 

### Cryptanalysis
Cryptanalysis is the study of analyzing and breaking cryptographic systems with the intention of decoding encrypted messages without having access to the key used in the encryption process. The goal of cryptanalysis is to find weaknesses in cryptographic algorithms and exploit them to breach the security of a system.

There are a number of [[Types of attacks]]. Two types which apply to block ciphers are Linear and differential attacks. [[Linear and Differential Cryptanalysis]] are two powerful techniques used in the field of cryptanalysis to break cryptographic systems. Both methods aim to find correlations or patterns that can be exploited to discover the secret key used for encryption. They both require a deep understanding of the structure and a large number of plaintext-ciphertext pairs. 

## Hash Functions
A hash function is a deterministic process that takes an input (or 'message') and returns a fixed-size string of bytes. The output, often a 'digest', is ideally unique to each unique input. Hash functions have specific [[Hash properties]]. 

**Universal hash functions** are a method of selecting a hash function from a carefully designed class of hash functions. It is used to minimise the worst-case scenario for a hash-function (collisions). 

### Random Oracle as a hash function
A random oracle is simply a randomly chosen function with appropriate domain and range. A random oracle is the **perfect** hash function. Every input is mapped **independantly** and **uniformly** in the range. // **TO DO ADD IN RO HASH FUNCTION PROPERTIES**

### Iterated Hash functions 
Iterated hash functions process input data in blocks, applying the same transformation to each block in a sequence. They are designed this way because it's often impractical to hash large amounts of data all at once, either due to memory constraints or because the data is being streamed or otherwise incrementally provided. Iterated hash functions allow data to be hashed as it becomes available.

In an iterated hash function, the output from hashing one block of data is used as part of the input to hash the next block of data. This creates a "chain" where each block affects all subsequent blocks, which means that changing any part of the input data will change the resulting hash.

The [[Merkle-Damgård]] is one such iterated hash function. 

### Standardised Hash Functions

Despite the fact that history says it is impossible, in practice people live with fixed hash functions and use them as if they were randomly chosen functions. 

**SHA Family**: The SHA-family of hash functions are functions standardised by NIST. All are iterated hash functions. [[SHA-2]] is a interated hash function which uses the [[Merkle-Damgård]] construction, built from a one-way compression function which used the [David-Meyer](https://en.wikipedia.org/wiki/One-way_compression_function#Davies%E2%80%93Meyer) construction. [[SHA-3]] is different, it uses the sponge construction. 

## Message Authentication Codes (MACs)
A Message Authentication Code ([[MAC]]) is a short piece of information used to authenticate a message and to provide integrity and authenticity assurances on the message. Integrity assurances detect accidental and intentional message changes, while authenticity assurances affirm the message's origin.

[[HMAC]] is a specific type of message authentication code that uses a cryptographic hash function (like SHA-256) and a secret cryptographic key. It's used to verify both the data integrity and the authenticity of a message.

MACs and HMACs are tools for ensuring message integrity and authenticity. They protect against tampering and forgery by tying a message to a secret key, and are widely used in internet communication protocols like TLS and IPsec.

#### Universal hash function as a MAC
**Theorem:** A $t$-universal hash function $f_\alpha$ for a randomly chosen secret $\alpha$ is an ***unconditionally secure*** MAC, provided that the number of queries is smaller than $t$. 

This assumes that $t$ is $iid$. This can be seen as the OTP equivalent for secrecy, this is the perfect MAC. If it were to be used for $t+1$ messages we could prove it is not a random function. 





