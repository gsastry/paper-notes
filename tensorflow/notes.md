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

# Quick notes

- Core data structure is a dataflow graph. Nodes can 
be stateful
- Dataflow graph specifies operations on tensors (which are transformed as a result 
of the computation graph)
- `tf.Variable` is a handle to a stateful, mutable
tensor
- Client/server, with the client using the `Session` interface to communicate with
a `master` node, which coordinates `workers` (workers run on different computational
devices with different kernels, e.g. GPUs vs CPUs)

# Interesting implementation details

- A tensor is typed, and is stored on a specific device. This device manages the 
allocator for this. (deallocated when it detects no references remain to this tensor)
- How to handle execution on multiple devices?
  - Challenges: (1) which device to execute the computation on, and (2) managing
  communication latency if it depends on cross-device data
  - So how to do (1)? TODO - communication avoiding algorithms could be useful here



