# MVLR Production

[W10_MVLR_DataMean.pdf](MVLR%20Production%200b8223dd22984ed98e541949a2ef3e3a/W10_MVLR_DataMean.pdf)

# Choice of this model

**Multi Variate:** We will be inserting multiple features

**Linear Regression:** We are trying to predict/forecast an array of values.

It's fairly straight forward what this model does with the data, so we have a good grip on the model while tweaking it. If we are working with an LSTM, we will lose that grip. So this will be a good benchmark for the final model.

# Form of the model (scalar)

- $y_i$ : the ground truth
- $b_0$ : The intercept
- $p$ : The amount of features
- $b_i$ : The feature's slope
- $x_{ij}$: The feature value
- $e_i$ : The [error function](https://en.wikipedia.org/wiki/Error_function) 
(probability of Y falling in the range [-x,x]) ← something I don't fully comprehend.

$$y_i = b_0 + \sum_{j=1}^{p} b_j \cdot x_{ij} + e_i$$

The dataset used looks like this, s_delta is the production variable that is our target.

![MVLR%20Production%200b8223dd22984ed98e541949a2ef3e3a/Untitled.png](MVLR%20Production%200b8223dd22984ed98e541949a2ef3e3a/Untitled.png)

The model was trained on 10 months of data and is predicting 10 days of the validation set

![MVLR%20Production%200b8223dd22984ed98e541949a2ef3e3a/Untitled%201.png](MVLR%20Production%200b8223dd22984ed98e541949a2ef3e3a/Untitled%201.png)

Looking at the $R^2$ it seems like the model is doing a pretty good job!

![MVLR%20Production%200b8223dd22984ed98e541949a2ef3e3a/Untitled%202.png](MVLR%20Production%200b8223dd22984ed98e541949a2ef3e3a/Untitled%202.png)