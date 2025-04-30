Problems and challenges with neural networks
- **Overfitting** -> Just predict on the training data, but not on the real data
	- Solved by **regularization**
- Computational complexity


# Solving overfitting
- The techniques will apply **regularization**
## Norm Penalties
- $Ĵ(\theta, X, y) = J(\theta, X, y) + \alpha f(\theta)$
	- $\theta$ -> Loss function
	- $X$ -> Train features
	- $y$ -> Target feature
	- $\alpha$ -> The size of the regularization effect

### Types:
- #### L1 (lasso)
	- **L**east **A**bsolute **S**hrinkage and **S**election **O**perator 
	- Definition: $f(\theta) = ||w||_1 = \sum _i |w_i|$
	- The network will try to get a smaller error -> Try to reduce the weights that are related to that error 
	- Can cause to some weights to be zeroed -> **Feature selection**
- #### L2 (ridge)
	- Definition $f(\theta) = \frac{1}{2}||w||^2 _2$
	- Decrease all the weights in order to get zero error
## Early Stopping
- Stop in the point of minimum error at test data
- Train data having smaller and smaller errors is possible, but you need to find the point when the error in the test data starts to rise instead of reducing
- ![mathematics_for_deep_learning](pt_4_train_vs_test_data_sweet_spot.png)

## Dataset Augmentation
- Modifying current train data in order to add more variables
- Training for image recognition
	- Rotating the image
	- Cropping part of it
	- Blurring
	- Adding noise
- Basically generating more diverse train data through the other ones
- "Producing synthetic data"

## Dropout
- Temporarily deactivating (dropping them) some neurons from epoch to epoch will make the network use all neurons
- This would help by avoiding strong connections that tend to obfuscate other connections -> The weight of those going to zero