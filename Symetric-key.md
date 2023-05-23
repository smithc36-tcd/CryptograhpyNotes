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

There are a number of [[Types of attacks]]. Two types which apply to block ciphers are Linear and differential attacks. [[Lin & Dif Cryptanalysis]] are two powerful techniques used in the field of cryptanalysis to break cryptographic systems. Both methods aim to find correlations or patterns that can be exploited to discover the secret key used for encryption. They both require a deep understanding of the structure and a large number of plaintext-ciphertext pairs. 