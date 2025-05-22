Quantization of errors
- **How wrong** the model's guess was from the **label**

Absolute value -> Doesn't matter if the error was from under or above the value predicted, just the distance from the correct answer
- Examples of implementing this:
	- Square of the difference: $(a - b) ^ 2$
	- Absolute of the difference: $|a - b|$


### Types of loss
- L1 loss -> Sum of the absolute differences
- Mean Absolute Error -> The average of L1 (L1/n elements)
- L2 loss -> Sum of the square of the differences
- Mean Squared Error -> The average of L2 (L2/n elements)

Why use any of that?
- MAE -> less towards outliers (lesser noticeable differences)
- MSE -> more towards outliers (greater noticeable differences, as it's the squared value of them)

