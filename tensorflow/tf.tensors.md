# Tensors 
- [_src_](https://www.tensorflow.org/guide/tensor)
- Multidimensional arrays 
	- 0D (scalar), 1D, 2D, 3D, ..., nD
		- 0D -> One value
- Values of the same type -> Dtype
- To create a tensor: 
	- `tf.constant((values0), ..., (valuesn) )`
	- `tf.ones((dimensions))`
	- `tf.zeros((dimensions))`

- **Tensors** ≃ **np.arrays**
	- Can transform into each other
		- `tf.tensor` -> `np.array(tf.tensor)` or `tf.tensor.numpy()` -> `np.array`
			- Most used for visualization
				- `my_tf_tensor = tf.constant((1, 2, 3))`
				- `my_tf_tensor.numpy()` -> "1 2 3"
				- `my_tf_tensor[1:3].numpy()` -> "2 3"
					- ALSO, slicing works normally
		- `np.array` -> `tf.constant(np.array)` -> `tf.tensor`

### Visualizing Tensors
- Example of a 3D tensor of integers:
```
rank_3_tensor = tf.constant([
  [[0, 1, 2, 3, 4],
   [5, 6, 7, 8, 9]],
  [[10, 11, 12, 13, 14],
   [15, 16, 17, 18, 19]],
  [[20, 21, 22, 23, 24],
   [25, 26, 27, 28, 29]],])
```
- The **visualization** of a 3d tensor: ![3dTensor](/tensorflow/Images/tensor_visualization_3d.png)
- **Shape**: $(x, y, z, ...)$
	- `my_tensor.shape` -> `TensorShape` object
	- `tf.reshape(tf.tensor, [dimension, dimension])` -> Returns a similar tensor with this new shape  
		- `tf.reshape(tf.tensor, -1)` -> Whatever fits
			- Mostly used with another dimension defined, so the other is just "whatever fits"
				- Ex: `tf.reshape(tf.ones((3,2,5)), [3, -1])`
			- Keep the order of the axes -> `tf.transpose` doesn't 
	- **Broadcasting** -> The tensor will change dimensions (_stretch_) in order to work in certain operations with other tensors 
	- 
	
- **For indexing**
	- Normal slicing works `my_tensor[1:2]`, `my_tensor[3:]`, `my_tensor[:4]`, `my_tensor[1:2:3]`, etc.
	- Multi-axis indexing
		- Use "," for separation
		- `my_tensor[1:3, 2]`, `my_tensor[1:3, 2:4]`, etc
			- Equivalent to: `my_tensor[1:3][2]`, `my_tensor[1:3][2:4]`
		- It can work for any dimension tensor, as long as they have the amount of dimensions you're indexing

## Operations
- Math operations used for machine learning are implemented in tensors
	- +, -, \*, @
	- `tf.concat()`, [`tf.reduce_sum()`](/tensorflow/tf.reduce_sum.md) 