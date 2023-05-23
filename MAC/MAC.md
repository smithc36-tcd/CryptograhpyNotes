A MAC algorithm, sometimes called a keyed (cryptographic) hash function, accepts as input a secret key and an arbitrary-length message to be authenticated, and outputs a MAC (the authentication tag). The receiver of the message then recomputes the MAC using the same key and checks if the computed MAC matches the received MAC. If they're the same, the message is authenticated.

### Security of MACs

MACs are used for ensuring integrity and authenticity of messages in the presence of an adversary. They are designed to withstand various types of security attacks:

1. Existential Forgery: This attack occurs when an attacker is able to create a valid MAC for a message without knowing the secret key. A secure MAC is resistant to existential forgery under chosen plaintext attacks.

2. Selective Forgery: This attack occurs when an attacker can create a valid MAC for a specific message of the attacker's choice without knowing the secret key.

3. Universal Forgery: This attack occurs when an attacker can create a valid MAC for any message without knowing the secret key.