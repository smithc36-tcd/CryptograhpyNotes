The Advanced Encryption Standard (AES) is a symmetric block cipher chosen by the U.S. government to protect classified information. It is implemented in software and hardware throughout the world to encrypt sensitive data. It is based on the Rijndael cipher developed by two Belgian cryptographers, Vincent Rijmen and Joan Daemen, who submitted it to the AES selection process.

---

**Structure of AES**

AES operates on a 4x4 column-major order matrix of bytes, termed the state, although some versions may have a larger block size. The AES family of ciphers has three members: AES-128, AES-192, and AES-256. Each AES cipher has a 128-bit block size, with key sizes of 128, 192, and 256 bits, respectively.

The key size used for an AES cipher specifies the number of repetitions of transformation rounds that convert the input (plaintext) into the final output (ciphertext). The number of rounds are as follows:

- 10 rounds for 128-bit keys.
- 12 rounds for 192-bit keys.
- 14 rounds for 256-bit keys.

Each round consists of several processing steps, including substitution, permutation, and mixing of the input plaintext to transform it into the final output of ciphertext. Each of these steps provides a layer of security.

Family of 128-bit block cipher, with varying number of rounds depending on the required security. 
|  Rounds  | 10  | 12  | 14  |
|:--------:|:---:|:---:|:---:|
| Key bits | 128 | 192 | 256 | 

## Construction
Encryption Round: 
1. **SubBytes:** Substitution of Bytes
2. **ShiftRows:** Permutation of Bytes 
3. **MixColumns:** Linear Mapping
4. **AddRoundKey:** XOR with round key
We do not MixColumns for the last round as all it does is permute the output which offers no additional security. 

Decryption Round: 
1. **AddRoundKey:** XOR with round key
2. **InvSubBytes:** Substitution of Bytes
3. **InvShiftRows:** Permutation of Bytes 
4. **InvMixColumns:** Linear Mapping


**Advanced Encryption Standard (AES)**

The Advanced Encryption Standard (AES) is a symmetric block cipher chosen by the U.S. government to protect classified information. It is implemented in software and hardware throughout the world to encrypt sensitive data. It is based on the Rijndael cipher developed by two Belgian cryptographers, Vincent Rijmen and Joan Daemen, who submitted it to the AES selection process.

---

**Structure of AES**

AES operates on a 4x4 column-major order matrix of bytes, termed the state, although some versions may have a larger block size. The AES family of ciphers has three members: AES-128, AES-192, and AES-256. Each AES cipher has a 128-bit block size, with key sizes of 128, 192, and 256 bits, respectively. 

The key size used for an AES cipher specifies the number of repetitions of transformation rounds that convert the input (plaintext) into the final output (ciphertext). The number of rounds are as follows: 

- 10 rounds for 128-bit keys.
- 12 rounds for 192-bit keys.
- 14 rounds for 256-bit keys.

Each round consists of several processing steps, including substitution, permutation, and mixing of the input plaintext to transform it into the final output of ciphertext. Each of these steps provides a layer of security.

---

**The AES Algorithm**

Here's a brief overview of the steps involved in the AES encryption process:

1. **Key Expansion:** The initial key is expanded into an array of key schedule words.

2. **Initial Round:**
    - **AddRoundKey:** Each byte of the state is combined with a block of the round key using bitwise xor.

3. **Rounds:**
    - **SubBytes:** A substitution step where each byte is replaced with another according to a lookup table.
    - **ShiftRows:** A transposition step where each row of the state is shifted cyclically a certain number of steps.
    - **MixColumns:** A mixing operation which operates on the columns of the state, combining the four bytes in each column.
    - **AddRoundKey**

4. **Final Round (no MixColumns):**
    - **SubBytes**
    - **ShiftRows**
    - **AddRoundKey**

The decryption process is the inverse of the encryption process, using inverse functions where necessary.

---

**Strengths and Security**

AES is a very secure encryption algorithm when used correctly. It has a large key size of 128, 192, or 256 bits, which makes it resistant to brute-force attacks. Its design is also resistant to known cryptographic attacks, and it's a well-understood cipher with a clear security profile.

---

**Applications**

AES is widely used across many systems. Internet protocols like HTTPS, SSH, and IPsec use AES for traffic encryption. Disk encryption systems, such as BitLocker and FileVault, use AES to encrypt data at rest. Furthermore, wireless networks, VPNs, and secure file transfer systems all employ AES.

---

**Conclusion**

AES is currently the most prominent symmetric key cipher due to its security, efficiency, and widespread adoption. As of my knowledge cutoff in September 2021, no practical cryptanalytic attacks against AES have been discovered.




