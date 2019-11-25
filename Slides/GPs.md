# Gaussian Process

"a prior distribution over functions and updating this distribution by conditioning on the data"

Note:
Properties of the Gaussian distribution and Bayes theorem gives Gaussian process. 


## a prior distribution over functions

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


## conditioning on data
Show fitting a Gaussian process from prior to points (use real world example co2 data?)


## Predictions
conditional distribution

Note:
http://cbl.eng.cam.ac.uk/pub/Public/Turner/News/imperial-gp-tutorial.pdf


## Pros and Cons of GPs
Pros:
* provides well-calibrated predictive uncertainty (decision making)
* big models (even with small data)

Note:
neural networks do not provide well calibrated uncertainty estimates