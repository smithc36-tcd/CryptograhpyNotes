## Linear

Linear cryptanalysis is a method of attacking symmetric key cryptographic systems, particularly block ciphers, invented by Mitsuru Matsui. It's a [[Types of attacks#Known plaintext attack|Known plaintext attack]], which means the attacker must have access to both the plaintext (original message) and the corresponding ciphertext (encrypted message).

#### Goals of Linear Cryptanalysis

The primary goal of linear cryptanalysis is to find the secret key used in the encryption process. It does this by finding linear approximations to describe the behavior of the block cipher. The more the cipher deviates from a perfect linear random function, the more susceptible it is to linear cryptanalysis.

#### Overview of How Linear Cryptanalysis Works

Linear cryptanalysis attempts to find a linear equation relating plaintext, ciphertext, and key bits that holds with a probability significantly different from 0.5. This is done by constructing a linear approximation table for the cipher's S-boxes (non-linear substitution tables used in block ciphers).

The attacker then uses this table to find a linear approximation of the entire cipher, which can be used to guess bits of the key. Given enough pairs of plaintext and corresponding ciphertext, the secret key can be determined.

#### Detailed Review of How Linear Cryptanalysis Works

1. **Constructing a Linear Approximation Table**: The first step in linear cryptanalysis is to construct a linear approximation table for the cipher's S-boxes. This table contains the probabilities that certain linear expressions of the input and output bits of the S-box will be equal. The expressions that have probabilities farthest from 0.5 are the most useful for the attack.

2. **Finding a Linear Approximation of the Cipher**: Once the linear approximation table has been constructed, it can be used to find a linear approximation of the entire cipher. This is a linear equation relating certain bits of the plaintext, ciphertext, and key. The equation does not hold for all plaintext-ciphertext pairs, but only with a certain probability that is different from 0.5.

3. **Collecting Plaintext-Ciphertext Pairs**: The attacker then needs to collect a large number of plaintext-ciphertext pairs. The number required depends on the bias of the linear approximation (how far its probability is from 0.5). The larger the bias, the fewer pairs are needed.

4. **Guessing Bits of the Key**: For each collected plaintext-ciphertext pair, the attacker computes the value of the linear approximation for the guessed key bits. If the approximation holds (i.e., the computed value is equal to the actual value) more often than would be expected by chance, the guessed key bits are likely to be correct.

5. **Repeating the Process**: The attacker repeats this process, each time guessing different bits of the key, until the entire key has been determined.

Linear cryptanalysis requires a deep understanding of the cipher's structure and a large number of plaintext-ciphertext pairs. It has been used successfully to attack several widely used ciphers, but most modern ciphers are designed to be resistant to this type of attack.

---

## Differential

Differential cryptanalysis is a method of attacking cryptographic schemes, particularly symmetric key ciphers, invented by Eli Biham and Adi Shamir. Like linear cryptanalysis, it's a form of [[Types of attacks#Known plaintext attack|Known plaintext attack]], where the attacker needs access to both the plaintext and its corresponding ciphertext.

#### Goals of Differential Cryptanalysis

The primary goal of differential cryptanalysis is to discover the secret key used for encryption. It does this by studying how differences in the plaintext affect the differences in the ciphertext, aiming to find patterns or characteristics that can be used to deduce information about the key.

#### Overview of How Differential Cryptanalysis Works

Differential cryptanalysis involves choosing pairs of plaintext with a specific difference and studying the difference of the corresponding ciphertexts. The attacker then looks for certain patterns or characteristics that occur more frequently than would be expected by chance. These patterns can provide information about the key.

#### Detailed Review of How Differential Cryptanalysis Works

1. **Choosing Plaintext Pairs**: The attacker chooses pairs of plaintext with a specific difference. This difference is often chosen to satisfy certain properties of the cipher, such as causing certain bits to remain unchanged during encryption.

2. **Computing Ciphertext Differences**: The attacker encrypts each pair of plaintexts and computes the difference of the resulting ciphertexts. This difference is compared to the expected difference based on the properties of the cipher.

3. **Identifying Patterns**: The attacker looks for patterns in the differences between ciphertexts. These patterns can provide information about the key. For example, certain differences might occur more frequently when certain key bits are set to 1.

4. **Guessing the Key**: Based on the patterns identified, the attacker makes educated guesses about the key. This process is repeated with different plaintext pairs and key guesses until the correct key is found.

5. **Confirming the Key**: Once a potential key is found, it can be confirmed by encrypting the plaintext with the guessed key and checking if the resulting ciphertext matches the original ciphertext.

Differential cryptanalysis requires a deep understanding of the cipher's structure and a large number of plaintext-ciphertext pairs. It has been used successfully to attack several widely used ciphers, but most modern ciphers are designed to be resistant to this type of attack. For example, the Advanced Encryption Standard ([[AES]]) was designed with specific measures to resist differential cryptanalysis.