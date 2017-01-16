# Title: TensorFlow: A System for Large-Scale Machine Learning #
# Authors: Google Brain #

# Intro

What happens when we intrepret training of large-scale ML models as a systems
problem? What are the design goals of such a system?

Before I read the article, here are some goals:
* Scalability
* Ease of use/experimentability for researchers
* Heterogenous: should compile to and work across different computational units,
CPUs, GPUs, ASICs, commodity machines, etc

# Summary

TensorFlow is Google's successor to DistBelief, their old system for training 
ANNs (2011). 

DistBelief was mainly split up into two pieces: stateless workers and stateful
parameter server (which held all the paramters for the network)



My questions:
* I believe the next generation of a system like this has to incorporate more
typed/FP concepts at the application level to be scalable. What will that look like?
* How can this system scale to support sparse models? In order to get incremental
gains, we can't really "depend" on algorithmic breakthroughs. Instead, can we support
1000x parameters with only 10x the compute?
