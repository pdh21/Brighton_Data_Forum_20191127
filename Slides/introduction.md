# The Gaussian distribution


![](Slides/assets/univariateGaussian.png?raw=true)<!-- .element height="50%" width="50%" -->

$p(x) \sim N(\mu|\sigma^2)$

$p(x) \sim \frac{1}{\sqrt{2\pi\sigma^2}} e^{ -\frac{1}{2}( \frac{x-\mu}{\sigma})^2}$

Note:
Gaussians frequently used in statistical/ML modelling: 
* Very common by nature. Almost all variables are distributed in a manner which is approximately normally.
* Measurement errors in physical experiments are often modeled with a normal distribution, mainly because of:
Central limit theorem (CLT): in many situations, when independent random variables are added, their properly normalized sum tends toward a normal distribution (informally a "bell curve") even if the original variables themselves are not normally distributed


## The Multivariate Gaussian
![](Slides/assets/MultivariateGaussian.png?raw=true)<!-- .element height="61%" width="61%" -->

Note:
* The Gaussian distribution can be extended to multiple dimensions
* This triangular plot shows two potential Gaussian distributions, blue and red
* the plots on the diagonal are the 1D histogram, and they are the same for both x1 and x2
* However, when we look at the joint plot, we can see they are different. Blue has no correlation between the two, where as red does.


<!-- .slide: data-transition="slide in fade out" -->
$p(\pmb x) \sim N(\pmb \mu|\Sigma)$

$p(\pmb x) \sim \frac{1}{(2\pi)^{d/2} \; |\Sigma|^{1/2}}e^{ -\frac{1}{2}(\pmb x - \pmb \mu)^t \Sigma^{-1}(\pmb x - \pmb \mu)}$

Covariance matrix: $\Sigma =\begin{pmatrix} \sigma_1^2 & \sigma_{12}^2 \\\ \sigma_{21}^2 & \sigma_{2}^2\end{pmatrix}$

$\Sigma_1 =\begin{pmatrix} 1.0 & 0.0 \\\ 0.0 & 1.0\end{pmatrix}$
 <span style="color:red">$\Sigma_2 =\begin{pmatrix} 1.0 & 0.8 \\\ 0.8 & 1.0\end{pmatrix}$</span>

Note:
* The maths of a Gaussian with multiple dimensional Gaussian can be expressed as follows. 
* The Covariance matrix is the key component that introduces that correlation between variables
* Here are the covariance matrices for the blue and red Gaussians from the previous slide.
* The 1.0s on the diagonal indicate the variance for each dimension, the other diagonal indicates the covariance, which in the case of the red Gaussian is 0.8


<!-- .slide: data-transition="fade in slide out" -->
$p(\pmb x) \sim N(\pmb \mu|\Sigma)$

$p(\pmb x) \sim \frac{1}{(2\pi)^{d/2} \; |\Sigma|^{1/2}}e^{ -\frac{1}{2}(\pmb x - \pmb \mu)^t \Sigma^{-1}(\pmb x - \pmb \mu)}$

Covariance matrix: $\Sigma =\begin{pmatrix} \sigma_1^2 & \sigma_{12}^2 \\\ \sigma_{21}^2 & \sigma_{2}^2\end{pmatrix}$

![](Slides/assets/heatmap_cov.png?raw=true)

Note:
* The covariance matrix will become important in the next couple of slides.
* Another way to visualise the covariance is with a heatmap, which we will use later. These two heatmaps are for the blue and red Gaussians


## Bayesian Probability
$P(\theta|D,M) = \frac{P(D|\theta, M)P(\theta|M)}{P(D|M)}$

$Posterior = \frac{Likelihood \times Prior }{Evidence}$

* Transparent way of including model prior information
* Gives full probability distribution

Note:
* Another useful concept is Bayesian probability
* Subjective. Start with a prior belief that gets updated by observations
* Can be used to provide robust uncertianty measurements


### Why bother with all this Bayesian probabilistic stuff?
* Prior information help us extract more information from data

Note:
Prior information, or domain knowledge is really powerfull. We should be using it where appropriate.
* My fvaourite demonstration of this is fitting a straight line to one data point


![](Slides/assets/line_1.png?raw=true)

Note:
We start of with one datapoint


![](Slides/assets/line_2.png?raw=true)

Note:
If we fit a straight line to this point, the line could be in a variety of positions


Have prior information on intercept

$c \sim \mathcal{N}(0.3,0.1)$

Note:
* What if we had some prior information on the line, i.e. we knew its intercept was roughly around 0.3


![](Slides/assets/line_3.png?raw=true)<!-- .element: class="fragment" data-fragment-index="1" -->

Note:
Now, the possible locations of the straight line are reduced


Combination of prior information and data point help constrain slope

![](Slides/assets/line_4.png?raw=true)

Note: 
* By combining the prior and information and data, we can provide more constraining power.