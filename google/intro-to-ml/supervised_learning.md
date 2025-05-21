## Data
Data can have a lot of details to be understood before you mess with it.

A dataset is constituted by many **examples** of **features**, all that details the concept we want to analyze in order to establish our model's behavior, using of the **labels** to define the correct answer for it.

What i have said quotes many elements of a dataset that are of great emphasis. 
- **examples** -> An example of a correct analysis, used on supervised learning to establish a previous relation between data and result
- **features** -> Elements of the context in which we define the element we want to find through our model's analysis
	- Example: features we could analyze in order to define if it's raining or not is humidity, temperature, place in earth we are, day of the year, etc.
- **labels** -> The correct answer. 

- **SIZE** and **DIVERSITY** are the key factors to make a better model
- More data, and more diverse data will cover more and more cases for our model -> Prevents **overfitting** (as established on [this](/mathematics_for_deep_learning/pt_4_avoiding_overfitting.md), there are other ways to avoid this problem)
## Model

### Training
By using default [initial weight parameters](/mathematics_for_deep_learning/pt_3_initialization_activation_and_modification.md) that can be defined by other functions or randomly, it will go through those values and try to compare to the label.
As our model do mistakes, it will be applied a learning factor, using a loss function, in order to change how our model is visualizing everything.
The factor can't be too much, in order to make it do smoother adjustments, and not over adjust it.

### Evalutation
Our model will be put through new testing data, or just to evaluate it's precision with the previous defined data.
The step that does the analysis of how precise our model really is.

