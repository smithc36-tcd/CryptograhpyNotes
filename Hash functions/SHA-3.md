SHA-3 is the latest member of the Secure Hash Algorithm family and can generate hash values that are 224, 256, 384, and 512 bits in length. Unlike SHA-1 and [[SHA-2]], SHA-3 is not an iterative hash function but is instead based on a new structure called Keccak, a type of "sponge function."

The sponge construction is quite different from the Merkle-Damgård used in [[SHA-2]]. It operates in two phases:

- The "**absorbing**" phase, where input bits are XORed into the state of the function and then transformed with a permutation function.
- The "**squeezing**" phase, where output bits are derived from the state, alternated with the same permutation function.

The important distinction is that sponge functions don't have a length-extension vulnerability that can be found in functions based on the Merkle-Damgård construction.

The primary motivation for the development of SHA-3 was the creation of a hash function that is radically different from and could stand as a backup to SHA-2, in the event that a previously undiscovered vulnerability was found in SHA-2.