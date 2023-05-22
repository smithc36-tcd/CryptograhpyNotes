The Advanced Encryption Standard, also known as Rijndael. Chosen as the new standard by competition in 2000. The main goal of AES was to create a successor to DES, that was secure and fast. AES is an SP-network.
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





