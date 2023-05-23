A [[Hash functions]] is a deterministic process that takes an input (or 'message') and returns a fixed-size string of bytes. The output, often a 'digest', is ideally unique to each unique input. Hash functions have specific [[Hash properties]]. 

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