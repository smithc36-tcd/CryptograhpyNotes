### Important Terms 
- **Memoryless source over finite alphabet:** A source produces symbols from a $\Sigma = \{a_1, ..., a_n\}$. Each symbol generated is independantly distributed. 
- **Binary Channel:** A binary channel can only send bits. 
- **Entropy:** $H(\mathbb{X}) = - \Sigma_{x \in \mathbb{X}} P_X(x)\log P_X(x)$
- **Conditional Entropy:** $$
	 \begin{align*}
	 H(X|y) &= - \Sigma_x P_{X|Y} \log P_{X|Y}(x|y) \\
	 H(X|Y) &= \Sigma_y (y) H(X|y)
	 \end{align*}
	$$
