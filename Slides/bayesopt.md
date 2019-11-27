## Ambiental: Automate the calibration of flood models?
* Flood models for a specific catchment need calibrating
* Unknown parameters such as groundwater level, rock porosity etc
* Running a model can take a long time
* model is black box (don't know gradients)


![](Slides/assets/flowchart_ambiental.png?raw=true)


This is an optimisation problem! 

![](Slides/assets/BO_1.png?raw=true)


## Solutions:
* Grid search?
* Gradient descent?
* MCMC?

Note: 
* Grid search appropriate resolution? exponential with dimensions, lots of call to model
* Gradient descent not applicable,  assumes optimisation function is convex
* MCMC far too many calls to model


## Bayesian Optimisation
*a sequential design strategy for global optimization of black-box functions that doesn't require derivatives* 
* incorporates __prior__ belief about optimisation function
* updates the prior with samples drawn from function to get a posterior that better approximates optimisation function


* __Surrogate model__: approximates the optimisation function.
* __acquisition function__ decides where best to sample function


## BO in 1D
![](Slides/assets/BO_1.png?raw=true)


![](Slides/assets/BO_2.png?raw=true)


![](Slides/assets/BO_3.png?raw=true)


![](Slides/assets/BO_5.png?raw=true)


![](Slides/assets/BO_6.png?raw=true)


![](Slides/assets/BO_7.png?raw=true)


## autocal: Ambiental
* Automating the calibration of flood models with Bayesian optimisation

![](Slides/assets/non_opt_anim.gif?raw=true)![](Slides/assets/opt_anim.gif?raw=true)


## Pros and Cons:
* Efficient in number of samples required
* Better than other alternatives

* Limited in number of dimensions (e.g. 10s)
* Difficult to parallize ( though progress is being made)


## Other Applications
* Experimental Design [e.g. reducing drag](http://auai.org/uai2018/proceedings/papers/362.pdf)![](Slides/assets/drag_example.png?raw=true)


* A/B testing [e.g. Facebook](https://research.fb.com/blog/2018/09/efficient-tuning-of-online-systems-using-bayesian-optimization/)
* Hyperparameter tuning [e.g. Amazon](https://docs.aws.amazon.com/sagemaker/latest/dg/automatic-model-tuning-how-it-works.html)
* [Synthetic Gene Design](https://arxiv.org/abs/1505.01627)
* many more

Note:
* Emulator - Simulator - Physical system
* A/B testing: Optimize the web design to maximize sign-ups, downloads, purchases, etc
* Deep learning , reinforcment learning, 
* use a Gaussian process model to emulate the behavior of the cell, 


## Toolkits
* [Emukit](https://amzn.github.io/emukit/): Developed by Amazon research team
* [Ax and BOTorch](https://ax.dev/): Developed by Facebook research team
* [scikit optimize](https://scikit-optimize.github.io/notebooks/bayesian-optimization.html)
and more...