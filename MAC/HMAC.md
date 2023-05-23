The construction of HMAC affects the security properties of the underlying hash function in a positive way. For example, HMAC doesn't suffer from the length-extension attacks that can affect hash functions. In simple terms, if someone has the hash of a message, they can't generate the hash of the message plus some additional content without knowing the secret key.

The process of HMAC generation involves the following steps:

1. The key is first padded with zeros to the block size of the underlying hash function (for instance, 64 bytes for SHA-256).
2. The padded key is then XORed with the iPad value (a repeated byte value of 0x36) and the message is appended. The hash of this is calculated.
3. The original padded key is XORed with the opad value (a repeated byte value of 0x5C) and the hash result from step 2 is appended. The hash of this is calculated.
4. The result of step 3 is the HMAC value.