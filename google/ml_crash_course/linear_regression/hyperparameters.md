Those are the variables that **we** control.

They define the environment in which the model is developing on itself.

The hyperparameters are:
- Learning rate
- Batch size
- Epochs

## Analyzing each hyperparameter
### Learning rate
- How much it will try to change itself after each iteration
- It's like a "step distance"
	- Too low, it will take too long to converge
	- Too high, it will always go past the point
- Multiplicative with the gradient

### Batch size
- The number of attempts before changing the parameters
- Too low -> More room for outliers\will not reflect the model's real performance
- Too high -> More computational resources and time spent
- Ways to optimize the usage of greater batch sizes
	- **Stochastic Gradient Descent (SGD)**
		- Single example per iteration
		- Can be very noisy -> As it's kind of random
	- **Mini-batch Stochastic Gradient Descent (Mini-batch SGD)**
		- Choose from N random points to create a mini-batch that's easier to calculate
		- The mini batch can be any number between 1 and N.
		- Averages the results
		- Less noisy, but more intense than **SGD**
- Noise can help in the development process as it generates more randomness

### Epochs
- The number of runs on the batch size it will have
- The number of times it analyzed all examples within the batch size number and then repeated the process
- Greater numbers can help introducing more attempts to reach the correct point
	- But it can also lead to overfitting.
- 