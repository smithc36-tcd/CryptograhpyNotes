Substituation-Permuation Networks are a type of Block-Cipher which is built on the principles of **Diffusion** and **Confusion**.

## Construction
The construction of the SPN is  made up of rounds and a Key-Schedule. The Key-Schedule uses a key K to derive the round keys $K_r$ which will be used in each round. 

### Round
1. **Round-Key**: XOR the message with the round key. 
2. **Substituation**: $l$ S-Boxes acting on each $m$-bit word. 
3. **Permutation**: Permutation $\pi_i$ Reordering of each {1, ... , n}  bits. 
