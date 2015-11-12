# Why Sampling? Pros and Cons


### Why Sampling?


* It allows us to approximate the expectations in convenient ways. Which can allows as to calculate statistics like mean, variance and predictions.
* It allows us to do the posterior inference in general thus helping with the bayesian analysis. 
* One can have the visualization of the typical draws from the distribution of interest from a complicated distribution. 


Why expectations and not other other stats or other things?
because 

*  any probability is expectation of the indicator function of the set i.e formally the following is true


$$
\begin{matrix}
Assertion: & P(X \in A) = & \mathbb{E}[ \mathbb{I}(X \in A)]  \\  
Proof: & rhs = & \mathbb{E}[I(X \in A)]  \\ 
\quad & \quad = & \mathbb {I}(X \in A)*P(X \in  A) +  \mathbb{I}(X \notin A)*P(X \notin A) \\ 
\quad & \quad = & 1*P(X \in  A)+0*P(X \notin A) \\
\quad & \quad = & P(X \in A) \\
\quad & \quad = &  lhs
\end{matrix}
$$

* Approximation is needed for sum or integral which can represented as the expectation (in general in probabilities)


The implications of above is that if we can somehow calculate expectations of the distribution we can calculate it's distributions, various stats etc which every in need to have the complete distribution in the closed or analytic form. We will see how the sampling helps us with that.

### Pros

*  Easy to implement and understand compare to analytical or deterministic approximation.
*  General purpose and approximate calculations.
*  There are many sampling methods in open source libraries

### Cons


* Can be overused as it is easy i.e for hammer everything looks like nail.
* It can be slower compare to deterministic approximation.
* Getting good samples may be inefficient and difficult to assess if we are getting good approximations.


### Going forward...

Given that we have many sampling methods and we will explore them i.e basically monte carlo, importance, markow chain monte carlo, gibbs sampling.
