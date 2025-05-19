
`tf.math.reduce_sum(tf.tensor, axis = None, keepdims = False, name = None)

Reduces a tensor to a certain shape and sums the others that are over the limit to the values inside the determined size.
`mytensor = tf.constant([1, 2], [3, 4])`

This would be structured as:
$1 \ 2$
$3 \ 4$

If we `reduce_sum` without a defined value for axis it will reduce it to a scalar tensor, which means, a single value
`tf.reduce_sum(mytensor)` -> `[10]`

BUT, if we define an axis it will try to keep the reduction to that index as specified
If its 0 -> Rows
If its 1 -> Columns

And so on.
Based on that
`tf.reduce_sum(mytensor, 0)` -> `[4 6]`
Because it will associate the index with it's parallel indexes on the other rows.

1  2 
\+ \+
3  4

And 
`tf.reduce_sum(mytensor, 1)` ->`[3 7]`
Because

1 + 2
3 + 4