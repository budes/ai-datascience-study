***OBJECTIVE*** -> Find the relationship between variables, such as **features** <-> **label**, but not limited to just those

Formula ([similar to](mathematics_for_deep_learning/pt_2_types_of_neurons.md)):
$y' = b + w_1 x_1$
- $y'$ -> label analyzed
- $b$  -> bias        -> ==Defined on training==
- $w_1$ -> weight  -> ==Defined on training==
- $x_1$ -> feature analyzed

It can be extended to more and more features, by adding those features values and their weights to the calculation, like:
$y' = b + w_1 x_1 + w_2 x_2 + ... + w_n x_n$ on the analysis of $n$ features.

Can be used to estimate the weights of a network by the pattern observed.
![chart example](/google/ml_crash_course/Images/linear_regression_chart.png)

Our **label** ($y'$) would be miles per gallon, as $b$ is independent from x, we can find it by estimating the 0 of the function, as we can observe, it is 30 on the 0.
So: $y' = 30 + w_1x_1$
$w_1$ could be defined by the angular coefficient of this function in specific, so we can predict the relation of the **feature** ($x_1$) Pounds in 1000s to the label analyzed.
As $y'$ goes to 12 when $x$ gets to 5, we can establish that $w_1$ is -3.6.

So our linear regression function to predict the behavior of this set of data could be represented by:
$y' = 30 - 3.6x_1$

