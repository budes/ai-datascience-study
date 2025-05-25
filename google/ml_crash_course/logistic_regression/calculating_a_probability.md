- As pointed in the introduction:
	- Logistic Regression estimates a probability
	- After the calculation of the probability, it either returns the result or a filtered answer (calculated by the usage of the probabilities)

> The following was previously analyzed [here](/mathematics_for_deep_learning/pt_3_initialization_activation_and_modification.md), with an greater mathematical 
> emphasis, so i'll go over just as code or in a summarized view
- **Sigmoid Function** -> Tool for keeping the results between 0 to 1 
- $z = b + w_1x_1 + w_2x_2 + ... + w_nx_n$ -> $y = \frac {1}{1 + e^{-z}}$
