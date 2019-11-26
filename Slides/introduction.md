# The Gaussian distribution


![](Slides/assets/univariateGaussian.png?raw=true)<!-- .element height="50%" width="50%" -->

$p(x) \sim N(\mu|\sigma^2)$

$p(x) \sim \frac{1}{\sqrt{2\pi\sigma^2}} e^{ -\frac{1}{2}( \frac{x-\mu}{\sigma})^2}$

Note:
Gaussians used for: 
* Very common by nature. Almost all variables are distributed approximately normally.
* Measurement errors in physical experiments are often modeled by a normal distribution
Central limit theorem (CLT): in many situations, when independent random variables are added, their properly normalized sum tends toward a normal distribution (informally a "bell curve") even if the original variables themselves are not normally distributed


## The Multivariate Gaussian
![](Slides/assets/MultivariateGaussian.png?raw=true)<!-- .element height="61%" width="61%" -->


<!-- .slide: data-transition="slide in fade out" -->
$p(\pmb x) \sim N(\pmb \mu|\Sigma)$

$p(\pmb x) \sim \frac{1}{(2\pi)^{d/2} \; |\Sigma|^{1/2}}e^{ -\frac{1}{2}(\pmb x - \pmb \mu)^t \Sigma^{-1}(\pmb x - \pmb \mu)}$

Covariance matrix: $\Sigma =\begin{pmatrix} \sigma_1^2 & \sigma_{12}^2 \\\ \sigma_{21}^2 & \sigma_{2}^2\end{pmatrix}$

$\Sigma_1 =\begin{pmatrix} 1.0 & 0.0 \\\ 0.0 & 1.0\end{pmatrix}$
 <span style="color:red">$\Sigma_2 =\begin{pmatrix} 1.0 & 0.8 \\\ 0.8 & 1.0\end{pmatrix}$</span>


<!-- .slide: data-transition="fade in slide out" -->
$p(\pmb x) \sim N(\pmb \mu|\Sigma)$

$p(\pmb x) \sim \frac{1}{(2\pi)^{d/2} \; |\Sigma|^{1/2}}e^{ -\frac{1}{2}(\pmb x - \pmb \mu)^t \Sigma^{-1}(\pmb x - \pmb \mu)}$

Covariance matrix: $\Sigma =\begin{pmatrix} \sigma_1^2 & \sigma_{12}^2 \\\ \sigma_{21}^2 & \sigma_{2}^2\end{pmatrix}$

![](Slides/assets/heatmap_cov.png?raw=true)


## Bayesian Probability
$P(\theta|D,M) = \frac{P(D|\theta, M)P(\theta|M)}{P(D|M)}$

$Posterior = \frac{Likelihood \times Prior }{Evidence}$

* Transparent way of including model prior information
* Gives full probability distribution


### Why bother with all this Bayesian probabilistic stuff?
* Prior information help us extract more information from data


![](Slides/assets/line_1.png?raw=true)


![](Slides/assets/line_2.png?raw=true)


Have prior information on intercept

$c \sim \mathcal{N}(0.3,0.1)$

![](Slides/assets/line_3.png?raw=true)<!-- .element: class="fragment" data-fragment-index="1" -->


Combination of prior information and data point help constrain slope

![](Slides/assets/line_4.png?raw=true)
