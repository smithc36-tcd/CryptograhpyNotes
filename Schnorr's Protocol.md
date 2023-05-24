One of the most famous and simplest protocols for proof of knowledge of exponent is Schnorr's protocol. In Schnorr's protocol, a prover demonstrates knowledge of a secret exponent x in relation to public data g (a generator of a group $G_q$) and y (where y = g^x). Here's a basic rundown of how it works:

1. The prover selects a random value r and computes $\alpha = g^r$.
2. The prover sends $\alpha$ to the verifier.
3. The verifier sends a random challenge $c \in \mathbb{Z}_q$  to the prover.
4. The prover computes the response $d = r + c * x\ mod\ q$ and sends it to the verifier.
5. The verifier checks whether g^s equals $\alpha \cdot y^c. 
			($g^r \cdot (g^x)^c = g^{r + c \cdot x}$) 

If the equation holds, the verifier accepts the proof; otherwise, the verifier rejects it. It is computationally infeasible for a dishonest prover to make the verifier accept if the prover does not know the secret exponent x.

Schnorr's protocol is zero-knowledge, meaning it does not leak any information about the secret value x. It is also a sigma protocol, which has desirable properties such as completeness, soundness, and honest verifier zero-knowledge. The security of Schnorr's protocol relies on the Discrete Logarithm Problem (DLP) being difficult to solve.