 Gaussian process regression (GPR) (https://arxiv.org/pdf/2009.10862v5)


 * The key is to find the distribution of fitting function (f)
 P(f | X) = N (f | µ, K) 

* The key is to regress the posterior distribution of regression function f, and the practical
 meaning is that once we have f distribution, for any given x*, we can predict mean y* and uncertainty
 y*

 * kernel to discribe the covariance between variables
 * kernel makes the data point smooth
 * kernel is predefined
 * The Gaussian process model is thus a distribution over functions whose shapes (smoothness) are defined by K. 
 * If points xi and xj are considered similar by the kernel, their respective function outputs, f(xi) and f(xj) are expected to be similar too.
 
 * GPy https://gpy.readthedocs.io/en/deploy/; GPyTorch https://gpytorch.ai/; GPflow https://www.gpflow.org/