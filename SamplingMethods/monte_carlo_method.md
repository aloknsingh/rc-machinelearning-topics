# Monte Carlo Approximation (method)

###Goals
1. The goals of Monte Carlo methods are 
to generate the sequence of the sample from the unknown probability distributions
2. As we saw every probability is the expectation of the indicator of the set. We can use this to estimates the probability using expectation which in-turn can be estimated by simple average technique with the assumption that averaging will be the unbiased estimator

###Intuition and Motivating Examples
Now we will ask, what is the intuition of the monte-carlo approximation. We will consider a few examples.

If a fair dice, the probability of getting a six is $$1/6$$. We can calculate it analytically because we know the distribution of rolling of dice. We could have found it even if we didn't know the pmf of fair dice. The obvious approach would be to roll the dice many times and count the number of times we found the number six. If we roll the dice say 6 times, it is quite possible that we won't get a number six but if we roll it for a reasonable times say 10000, we will get approximately, $$10k/6$$ number of six.
so as the number of rolling increases , the ratio of number of sixes to the total number of roll will approach to $$1/6$$. So what we did is a monte-carlo approximation for finding the distribution of number six.


In the previous example, we could have done it without sampling but now consider the example of finding the expectation where it is impossible to obtain analytically.Consider that, we are given a simple the task of finding the average concentration of a e-coli bacteria in a lake. We can't possible know the distribution of the micro organism in the lake so we can calculate the average. However we do have the ability to go to the any location on the surface of the lake via boat to draw a sample and measure the ecoli concentration i.e we can draw the samples from the unknown probability distribution of the concentration of ecoli in the lake.
i.e we can do the goal 1 of the monte-carlo approximation. How about calculation the expected value of it. But we can't take infinite samples so we approximate it using average of the random samples i.e we can randomly go to many points in the lake (even inside water) and do our measurement at points and average out the result to get the answer.But wait.. we can't possibly easily go inside the lake easily.but we can have a device which can measure the depth of the lake so that we can multiply the concentration at (x,y) by the depth to get the total concentration at (x,y) something like weighted samples . We can thus estimate that total average concentration of e-coli by simply.
Sum of weighted measurement / total weights.

###Formal explanation
Lets continuing with the lake analogy ...

Let's assume

$$ \vec x_{i} = (x_{i},y_{i})$$ be $$i$$'th randomly chosen point at the surface of lake

$$ P^{*}(\vec x_{i})$$ be the depth of the lake at  $$\vec x_{i} $$

$$ \phi(\vec x) $$ be the pdf of interest i.e the concentration of bacteria.

$$ \hat {\Phi}$$ be the estimated expected value.

Then going through the same reasoning as the previous explanation, we have 
$$ \hat {\Phi} = \sum_{i=1}^{N} \phi(\vec x_{i})P^{*}(\vec x_{i})/Z_{n}$$

Where $$Z_{n} = \sum_{i=1}^{N}P^{*}(\vec x_{i})$$

Where the normalized entry $$P(\vec x_{i}) = P^{*}(\vec x_{i})/Z_{n}$$ is the pdf of the height of lake. 

A lot of problem can be easily solved by simple simulation if we assume $$P(\vec x)$$ is uniform distribution. In that case, we have the simple average i.e the unbiased expectation as the approximation for $$\Phi $$ which is $$\hat \Phi$$.

One such example is the estimation of $$\pi$$ (@TODO: have example)

### Algorithm
1. Choose the distribution (say uniform) and draw random samples. 
2. Evaluate the value of unknown distribution at those random samples
3. Average them out to get the expected value.



###Software Example

