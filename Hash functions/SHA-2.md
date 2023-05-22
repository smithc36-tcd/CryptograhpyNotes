SHA-2 (Secure Hash Algorithm 2) is actually a family of six hash functions: SHA-224, SHA-256, SHA-384, SHA-512, SHA-512/224, and SHA-512/256. They all use the [[Merkle-Damgård]] construction for iteratively hashing blocks of data, as we discussed earlier.

Here's a simplified explanation of the overall construction of SHA-2, particularly focusing on SHA-256 which is one of the most commonly used variants.

1. Padding: The message is padded so that its length is congruent to 448, modulo 512 (meaning that when the length is divided by 512, the remainder is 448). The padding consists of one '1' bit, followed by necessary '0' bits, and then a 64-bit block which is the length of the original message in binary. This brings the total length of the message to a multiple of 512 bits, which can then be processed in 512-bit blocks.

2. Initialization: A set of initial hash values are defined. These are taken from the fractional parts of the square roots of the first 8 prime numbers.

3. Message schedule: Each 512-bit chunk of the padded message is divided into 16 32-bit words (for SHA-256). Then, 48 additional words are derived from these using a defined operation.

4. Main loop: Each 512-bit chunk is then processed in a loop, which consists of 64 iterations (for SHA-256). In each iteration, a certain mixing operation is performed on the words from the message schedule, and the current values of the working variables (which are initialized to the hash values from the previous chunk or, for the first chunk, the initial hash values). This operation uses logical functions and bitwise operations to mix the input words and working variables.

5. Finalization: After all chunks have been processed, the last set of hash values become the message digest.

These steps provide a very high level of security and resistance to collision attacks. The loop operation is designed to ensure that every bit of input affects every bit of output, and the padding and length encoding in step 1 ensure that different messages cannot produce the same digest, even if they are very similar or differ only in length.

Note that SHA-384, SHA-512, SHA-512/224 and SHA-512/256 work similarly, but use 64-bit words and 80 rounds, and the initialization values and constants are derived from the fractional parts of the cube roots of the first 80 primes, not their square roots. The number of rounds and the size of words are part of what make these SHA-2 variants more secure, but also slower.