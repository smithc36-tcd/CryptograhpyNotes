The Merkle-Damgård Construction is a method used to build many of these iterated cryptographic hash functions. It was independently invented by Ralph Merkle and Ivan Damgård. This method ensures that the resulting hash function is collision-resistant as long as the underlying compression function used is also collision-resistant.

Here's a simplified description of how the Merkle-Damgård construction works:

1.  **Padding**: The input data is first padded so that its length is a multiple of the block size. Padding typically involves appending a '1' bit, followed by enough '0' bits to nearly fill the last block, and then the length of the original message is appended as a binary number.
2.  **Initialization**: An initial hash value is set, often a fixed constant value.
3.  **Iteration**: The main body of the Merkle-Damgård construction is a loop that processes each block of data. The current block of data and the current hash value are combined and processed through a compression function, producing a new hash value. This new hash value and the next block of data are used in the next iteration of the loop.
4.  **Finalization**: After all blocks have been processed, the final hash value is the output of the hash function.
    
Hash functions built using the Merkle-Damgård construction include the MD5, SHA-1, and SHA-2 families. However, this construction has certain vulnerabilities, and newer designs like SHA-3 use different methods, such as the Sponge construction.