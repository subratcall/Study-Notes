The arXiv link is https://arxiv.org/pdf/1808.03578v1.pdf.  

The github repository is https://github.com/noahfl/densenet-sdr/

Notes:

- SDR (stochastic delta rule) therefore implements a local gradient-dependent simulated annealing per weight converging to a bayes optimal network. 

- Dropout is a method that was created to mitigate the over- parameterization and therefore overfitting of deep-learning applications and incidentally to avoid poor local minima.

- Specifically, Dropout implements a Bernoulli random variable with probability p (“biased coin-toss”) on each update to randomly remove hidden units and its connections from the network on each update producing a sparse network architecture in which the remaining weights are updated and retained for the next Dropout step. 

- SDR implements a random variable per weight and provide update rules for each parameter in the random variable, in this case a gaussian with adaptive parameters (μwij , σwij . Although any SDR would work with any random variable (gamma, beta, binomial, etc..). 

- The difference at this point with Dropout is that SDR adjusts the weights and the effect of the hidden unit attached to each weight to change adapatively with the error gradient on that update. The effect here again is similar to Dropout, except each hidden unit’s response is factored across its weights (proportional to their effect on the credit assignment from the classification error). 

- The consequence of the local noise injection has a global effect on the network convergence and provide the DL with greater search efficiency which we examine later on. 

- The weight sharing in SDR is more local per hidden unit than that of Dropout 
