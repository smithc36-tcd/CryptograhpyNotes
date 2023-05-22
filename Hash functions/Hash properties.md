### One-wayness
Once data has been transformed into a hash, it's practically impossible to retrace back the original input. Even a minor change in the input will cause a drastic, unpredictable change in the output.

### Second Pre-image resistance 
Given an input and its hash, it should be computationally infeasible to find a different input with the same hash. This ensures that a unique input will always produce a unique hash.

### Collision resistance
It should be computationally infeasible to find two different inputs that hash to the same output. This is a stronger property than second preimage resistance.

## Relations for compressing Hash functions
- If a function is not second pre-image resistant, then it is not collision resistant. 
	1. Pick a random $x$. 
	2. Request a second pre-image $x' \neq x$ with $f(x') = f(x)$.
	3. Output $x'$ and $x$. 

- If a function is not one-way, then it is not second pre-image resistant. 
	 1. Given a random $x$, compute $y = f(x)$. 
	 2. Request pre-image of $x' $ of $y$.
