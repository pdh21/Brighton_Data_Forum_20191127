# Gaussian Process
A Bayesian non-parametric approach or:

"a prior distribution over functions and updating this distribution by conditioning on the data"

Note:
conditioning on data: Likelihood
Properties of the Gaussian distribution and Bayes theorem gives Gaussian process. 


## *a prior distribution over functions*
Use the Gaussian distribution to constrain how function, $\mathbf{y}=f(\mathbf{x})$, behaves

$\Sigma =\begin{pmatrix} \sigma_1^2 & \sigma_{12}^2 \\\ \sigma_{21}^2 & \sigma_{2}^2\end{pmatrix}$


<center>
<video autoplay="true" loop="true" muted="true" width="800">
   <source src="./Slides/assets/Two_points_small_l.mp4" type="video/mp4"> Your browser does not support the video tag.
</video>
</center>


<center>
<video autoplay="true" loop="true" muted="true" width="800">
   <source src="./Slides/assets/Two_points_large_l.mp4" type="video/mp4"> Your browser does not support the video tag.
</video>
</center>


<center>
<video autoplay="true" loop="true" muted="true" width="800">
   <source src="./Slides/assets/manypoints_small_l.mp4" type="video/mp4"> Your browser does not support the video tag.
</video>
</center>


## Covariance functions
Prior on how the functions are allowed to behave.
### Squared Exponential (or RBF)
<center>
<video autoplay="true" loop="true" muted="true" width="800">
   <source src="./Slides/assets/RBF_covfunc.mp4" type="video/mp4"> Your browser does not support the video tag.
</video>
</center>


### Periodic Exponential
<center>
<video autoplay="true" loop="true" muted="true" width="800">
   <source src="./Slides/assets/periodic_exp_covfunc.mp4" type="video/mp4"> Your browser does not support the video tag.
</video>
</center>


### RBF+Periodic Exponential
<center>
<video autoplay="true" loop="true" muted="true" width="800">
   <source src="./Slides/assets/RBF_period_exp_covfunc.mp4" type="video/mp4"> Your browser does not support the video tag.
</video>
</center>


## *conditioning on data*
Monthly Atmospheric CO$_2$ concentration
![](Slides/assets/co2data.png?raw=true)<!-- .element height="70%" width="70%" -->

Note:
Use a covariance function with 
* a long trend, 
* a periodic component that can change and 
* a component for smaller timescale trends


### No data
<center>
<video autoplay="true" loop="true" muted="true" width="800">
   <source src="./Slides/assets/co2_nodata.mp4" type="video/mp4"> Your browser does not support the video tag.
</video>
</center>


### Condition on two data points 
<center>
<video autoplay="true" loop="true" muted="true" width="800">
   <source src="./Slides/assets/co2_twopoints.mp4" type="video/mp4"> Your browser does not support the video tag.
</video>
</center>


### Condition on six data points 
<center>
<video autoplay="true" loop="true" muted="true" width="800">
   <source src="./Slides/assets/co2_fourpoints.mp4" type="video/mp4"> Your browser does not support the video tag.
</video>
</center>


### Condition on all data points
![](Slides/assets/co2fit_and_pred.png?raw=true)

Note:
http://cbl.eng.cam.ac.uk/pub/Public/Turner/News/imperial-gp-tutorial.pdf


## Pros and Cons of GPs
Pros:
* provides well-calibrated predictive uncertainty (decision making)
* big models (even with small data)

Cons:
* Does not scale well due to $\mathcal{O}(n^3)$

Note:
neural networks do not provide well calibrated uncertainty estimates


## Toolkits and resources
* GPy
* Scikit Learn
* GPflow

 [![](data:image/jpeg;base64,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)](http://www.gaussianprocess.org/gpml/)