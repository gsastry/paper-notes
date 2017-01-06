# Title: Towards an Integration of Deep Learning and Neuroscience #
# Authors: Adam H. Marblestone, Greg Wayne, Konrad P. Kording #

## Summary
- ML / DL has progressed with tools from theory of optimization; so maybe
the brain also optimizes a cost function
- These cost functions that the brain optimizes are different across
functional areas and development (?)

## Why read this paper?

We have models in AI of [generally intelligent problem solvers](https://en.wikipedia.org/wiki/AIXI) 
that are interesting models yet widely impractical; even more practical 
reinforcement learning still needed a LOT of tweaks, use of DL for policy 
learning and Q-learning.

I'm interested in computational neuroscience to develop the right level
of abstraction to reason about practical, safe, intelligent systems.

For example, lots of current RL methods don't really explore in a smart
way. (epsilon-greedy Multi armed bandit is one example of this). Can
the brain tell us anything about how to direct our exploration?

### Does the brain optimize cost functions?

Well, "the purpose of our nervous system is to allow us to successfully
interact with our environment". The authors note that the brain learns
optimal strategies in certain domains like movement (minimizing energy
expenditure, impact and damage, maximize movement gains). 

There are several other studies in this line which show that animals
tend to the game theoretic optimal solution in situations which are analogous
to the fitness-testing situations that they evolved in: this suggests that
the human nervous system will tend to the bayes-optimal (or other idealized
notion of optimality) in situations that mirror our EEA.

The authors suggest that in order for the brain to be so good at certain
tasks (near-optimal), it *needs* to have evolved mechanisms for efficient
credit assignment in deep RNNs.

There are two key claims here:
(1) the brain has mechanisms for credit assignment that allow it to optimize
*global* cost functions
(2) the brain can tune which cost functions each of its subnetworks try
to optimize.

### Whence cost functions?

To explain different brain functional areas and findings from developmental
psychology, the authors propose that cost functions can be (1) locally
generated and (2) vary over time. 

Here's another way to stating the guess here: since the genome is only ~4GB,
the evolution can't specify much of the brain's machinery in its prior; 
instead it has to specify a small seed prior and a bootstrapping process
that allows for the brain to learn effective episodic cost over time.

### Specialization or generalization?

This paper slices up the tension between evolutionary psychology's
"evolved modularity hypothesis" and the "one learning algorithm"
(ferret rewiring experiments, Ng's paper on various unsupervised learning
algorithms corresponding to place cells in monkeys) in a different way. 
The authors note that specialization to makes a computational system more
efficient at solving certain problems, and cite architectural and functional
differences in the basal ganglia, hippocampus, and thalamus.

Specialization vs generalization is recast to: generally learning specific
and useful cost functions across different functional areas and over time.

### Biological plausiblity of ML algorithms

Backprop has fundamental advantages over local learning (requires 
coordination of all synapses...) and weight perturbation (high variance).
Differential error sensitivity (<-- what I just called backprop) is rapid
to calculate, and scales well (constant overhead in number of nodes, 
deepness, etc).

everyone says backprop "isn't biologically plausible" but
the authors cite like 8 different papers, all of which employ the same
basic idea of "feedback connections that carry error phasically."

#### Credit assignment, feasability of prevailing deep RL

Some of the "tweaks" used to make DQN plausible like freezing the target
function for a bit, seem to be biologically plausible. (authors call this
"temporally local learning")

Some information built into our prior can bootstrap supervised learning;
e.g. paying attention to hands as an in-built bias provides lots of training
data to downstream learning algorithms

#### Spiking

The core "problem" is that modern artificial neurons are power hungry little
beasts, while biological neurons mainly communicate via spikes. 

I'm not sure if this is really a "problem" to build advanced ML systems or
necessarily to understand intelligence. The reason is that power hungry 
neurons may just be simulating the miserly biological neurons at more
advanced timesteps. This might help explain how DL models have "suprisingly"
achieved superhuman performance in many domains without requiring the same
scale of neurons as humans (but on the same order of data).

### What an agent needs

#### Structured routing systems
- Attention, memory (short and long term)
- Switchboard (thalamus, basal ganglia in humans)
- Not sure if we know enough here for concrete new directions in DL / ML

#### representing cost functions etc

### ML intersect neuroscience

- Understanding backprop in brain can validate bunch of approaches or show
us what we don't know (inspiring new approaches)
- Specialized networks can work together (like brain has different cost
functions)





### Remainders / Future issues

## One shot learning
## Better unsupervised /semi-supervised learning

How does the brain learn with noisy or far off rewards?
