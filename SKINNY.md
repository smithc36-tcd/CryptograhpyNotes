The SKINNY family of ciphers implements parts of the TWEAKEY framework. The initialisation of the SKINNY cipher involves a plain-text message, m, being split
into a 4 × 4 grid of cells. The bit length of each cell is determined by the number of
bits in the block of SKINNY . Each of the cells is initially set to mi, where i < 16. This
construction is useful since the message can at this point be considered a matrix allowing
for linear operations as parts of the encryption funciton.

Each round of encryption in the SKINNY cipher is composed of five transformations:
**SubCells**, **AddConstants**, **AddRoundTweakey**, **ShiftRows** and **MixColumns**. The combination of these steps in this order is of extreme importance for ensuring the security and efficiency of the SKINNY cipher, allowing for both diffusion and confusion.
The final internal state matrix contains the cipher-text of the encrypted plain-text with
cells being unpacked in a similar way to how they were originally initialised.
