## Ambiental: Automate the calibration of flood models?
* Flood models for a specific catchment need calibrating
* Unknown parameters such as groundwater level, rock porosity etc
* Running a model can take a long time
* model is black box (don't know gradients)


![](Slides/assets/flowchart_ambiental.png?raw=true)

Note:
The challenge is finding parameters that provide the best fit to the data


This is an optimisation problem! 

![](Slides/assets/BO_1.png?raw=true)

Note:
* We have some measure of goodness of fit, we have a parameter, where is the trough?


## Solutions:
* Grid search?
* Gradient descent?
* MCMC?

Note: 
* Grid search has numerous issues e.g. what is the appropriate resolution? it goes exponential with dimensions, which in turn requires lots of call to model
* Gradient descent not applicable,  assumes optimisation function is convex. We also dont have gradient information
* MCMC is another nice paramter search technique but in this case it requires far too many calls to model


## Bayesian Optimisation
*a sequential design strategy for global optimization of black-box functions that doesn't require derivatives* 
* incorporates __prior__ belief about optimisation function
* updates the prior with samples drawn from function to get a posterior that better approximates optimisation function

Note:
Bayesian optimisation is ideal for this. It incorporates everything we covered, 
* A Bayesian approach that allows us to provide a guide as to how function behaves


* __Surrogate model__: approximates the optimisation function.
* __acquisition function__ decides where best to sample function

Note:
* There are two key functions required
* Surrogate model, GAussian Processes are the most favoured approach for this part
* Acquisition, numerous choices whihc give different balances to exploration and minimisation


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

Note:
The figure shows in 3d, how parameter space ins constrained before running simulations (left) and after (right). The movement is a proxy for uncertianty. The colours an indication of best fit.
We applied this approach to searching parameter space in order to calibrate the flood models
* We use Bayesian optimisation to effiecently work out the best parameters
* IT does this by choosing which parameters to run, run the simulation, update the Gaussian process model of the optimisation function, then picks the next paramters to use to either explore an unknow part of parameter space, or fine tune where the optimal point is.


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
Other obvious uses for this approach include:
* Emulator - Simulator - Physical system
* A/B testing: Optimize the web design to maximize sign-ups, downloads, purchases, etc
* Deep learning , reinforcment learning, 
* use a Gaussian process model to emulate the behavior of the cell, 


## Toolkits
* [Emukit](https://amzn.github.io/emukit/): Developed by Amazon research team
* [Ax and BOTorch](https://ax.dev/): Developed by Facebook research team
* [scikit optimize](https://scikit-optimize.github.io/notebooks/bayesian-optimization.html)
and more...