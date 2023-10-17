# Workshop on epidemiology

## Abstract
In compartmental models individuals move across compartments, representing different disease states, to model the spread of an epidemic in a population [Keeling and Rohani, 2011]. Compartmental models can be viewed as Hidden Markov models [Chopin and Papaspiliopoulos, 2020] in which the hidden signal is represented by the number of individuals in each compartment over time, and noisily observed via customizable observation models, which might encompass clutter, mislabels, and miscounting. Their exceptional flexibility empowers modelers to incorporate diverse dynamics in the model, such as immigration-emigration effects, subpopulation, spatial interaction, and seasonal variations over time.

This workshop aims to provide participants with a comprehensive understanding of compartmental models for epidemiological modeling and associated techniques for likelihood computation and parameter inference. Most of the sections will be accompanied by practical implementation in Python, showing how to leverage Machine Learning libraries and GPU computing to implement efficient algorithms. 

The workshop will commence with an introduction to compartmental models and their relevance to epidemiology, accompanied by illustrative examples. Participants will explore the distinction between stochastic models and deterministic models, while also considering the advantages and disadvantages of choosing continuous-in-time models versus discrete-in-time models [Keeling and Rohani, 2011]. The participants will then delve into a dense section explaining why compartmental models are hidden Markov models and the main challenges in their likelihood computation. A significant space will be given to sequential Monte Carlo algorithms [Chopin and Papaspiliopoulos, 2020], where the main algorithm will be described along with strategies to choose the proposal distribution and resampling scheme. The compartmental models’ section will conclude with parameters’ inference, considering both basic likelihood optimization, MCMC [Robert et al., 1999, Andrieu et al., 2010] and ABC [Kypraios et al., 2017]. The workshop will further explore novel methodologies to approximate the likelihood of compartmental models through parametric distributions. The first part will deal with the well-known Kalman filter to then go beyond the Gaussian approximation and provide other families of distributions that can exploit conjugacy in hidden Markov models [Whiteley and Rimella, 2021, Whitehouse et al., 2023]. Once the connection with compartmental models is clear, the problem of overdispersion and overconfidence in statistical output will be mentioned, along with possible ways to overcome it. 

The final segment of the workshop will introduce the challenging individual-based models [Rimella et al.,2023a,b], offering the participants an alternative perspective to epidemiological modeling. Foundational concepts of individual-based models will be presented, accompanied by relevant inference techniques. By the end of the workshop, participants will have gained a general theoretical and computational understanding of compartmental models for epidemiological modeling, as well as the associated challenges and techniques for likelihood computation and parameter inference.

## Practical session (for the masterclass on Parallel computing)
The practical session focuses on leveraging TensorFlow within the context of epidemiological modeling. We begin with a concise introduction to fundamental TensorFlow commands, elucidating techniques for tensor management, broadcasting, and harnessing the power of the "einsum" notation. In addition to TensorFlow, we explore some commands of TensorFlow Probability, revealing how probabilistic programming facilitates tasks such as sampling and effortless computation of probability mass functions (p.m.f.) and log p.m.f.

Subsequently, we dive into the world of epidemiological modeling simulation, and specifically compartmental modelling, with the classic SIR model serving as our guiding example. Within this segment, we show how to implement a compartmental model efficiently, emphasizing the importance of implementation choices that enable parallel simulation of multiple models.

The final section of our tutorial is dedicated to inference. We commence by exploring vanilla Approximate Bayesian Computation (ABC) and illustrate how it yields an approximation of the posterior distribution over model parameters, progressively refining the prior domain. As we conclude, our focus shifts to the Poisson Approximation Likelihood (PAL), where we approximate the likelihood of the compartmental model using a Poisson distribution. We delve into the core steps of the recursion and elucidate how to design the PAL for efficient parallel execution across various parameter choices. Beyond merely plotting profile likelihoods for the parameters of interest, we also unveil the techniques for gradient computation and parameter optimization through a TensorFlow optimizer.

## References
C. Andrieu, A. Doucet, and R. Holenstein. Particle markov chain monte carlo methods. Journal of the Royal Statistical Society Series B: Statistical Methodology, 72(3):269–342, 2010.

N. Chopin and O. Papaspiliopoulos. Introduction to Sequential Monte Carlo. Springer International Publishing, 2020.

M. J. Keeling and P. Rohani. Modeling infectious diseases in humans and animals. In Modeling infectious diseases in humans and animals. Princeton university press, 2011.

T. Kypraios, P. Neal, and D. Prangle. A tutorial introduction to bayesian inference for stochastic epidemic models using approximate bayesian computation. Mathematical biosciences, 287:42–53, 2017.

L. Rimella, S. Alderton, M. Sammarro, B. Rowlingson, D. Cocker, N. Feasey, P. Fearnhead, and C. Jewell. Inference on extended-spectrum beta-lactamase Escherichia coli and Klebsiella pneumoniae data through SMC2. Journal of the Royal Statistical Society Series C: Applied Statistics, page qlad055, 07 2023a. ISSN 0035-9254. doi: 10.1093/jrsssc/qlad055. URL https://doi.org/10.1093/jrsssc/qlad055.

L. Rimella, C. Jewell, and P. Fearnhead. Approximating Optimal SMC Proposal Distributions in Individual-Based Epidemic Models. Statistica Sinica, pages SS–2022–0198, 05 2023b. ISSN 1017-0405. doi: 10.5705/ss.202022.0198.

C. P. Robert, G. Casella, and G. Casella. Monte Carlo statistical methods, volume 2. Springer, 1999.

M. Whitehouse, N. Whiteley, and L. Rimella. Consistent and fast inference in compartmental models of epidemics using Poisson Approximate Likelihoods. Journal of the Royal Statistical Society Series B: Statistical Methodology, page qkad065, 07 2023. ISSN 1369-7412. doi: 10.1093/jrsssb/qkad065. URL https://doi.org/10.1093/jrsssb/qkad065.

N. Whiteley and L. Rimella. Inference in stochastic epidemic models via multinomial approximations. In International Conference on Artificial Intelligence and Statistics, pages 1297–1305. PMLR, 2021.
