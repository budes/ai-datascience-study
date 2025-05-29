## Analyzing data
- `dataset[index].max()` -> Maximum value inside said dataset
- `dataset[index].mean()` -> Return the mean of the values in it
- `dataset[index].nunique()` -> Number of unique values in it
	- `np.unique(dataset[index])` -> The unique values in it
- `dataset[index].value_counts()` -> Returns a table like structure of values and how many times they appear
- `dataset[index].idxmax()` -> Returns the index with the greatest value in it in said structure
- `dataset[index].isnull()` -> Returns an array-like structure with each index pointing out if it is null or not

## Correlation Matrix
- [About correlation coefficients](/topics/correlation_coefficient.md)
- Basically we will build a matrix around correlation coefficients of each value in order to visualize the relation each feature has on the label in analysis
- Important to note:
	- Greater absolute value -> Greater relation
	- Thus 0 -> No linear relation at all between those variables
- `dataset.corr()` -> Generate a correlation matrix of all the n features 
	- Size is $n \cdot n = n²$ 
- `sns.pairplot(training_df, x_vars=["FARE", "TRIP_MILES", "TRIP_SECONDS"], y_vars=["FARE", "TRIP_MILES", "TRIP_SECONDS"])`
	- Show the relation between variables and values for each pair