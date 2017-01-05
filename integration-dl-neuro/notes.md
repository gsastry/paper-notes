# Title: Towards an Integration of Deep Learning and Neuroscience #
# Authors: Adam H. Marblestone, Greg Wayne, Konrad P. Kording #

## Summary
- ML / DL has progressed with tools from theory of optimization; so maybe
the brain also optimizes a cost function
- These cost functions that the brain optimizes are different across
functional areas and development (?)

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

and holy crap! everyone says backprop "isn't biologically plausible" but
the authors cite like 8 different papers, all of which employ the same
basic idea of "feedback connections that carry error phasically."

#### Credit assignment

#### Spiking

The core "problem" is that modern artificial neurons are power hungry little
beasts, while biological neurons mainly communicate via spikes. 

I'm not sure if this is really a "problem" to build advanced ML systems or
necessarily to understand intelligence. The reason is that power hungry 
neurons may just be simulating the miserly biological neurons at more
advanced timesteps. This might help explain how DL models have "suprisingly"
achieved superhuman performance in many domains without requiring the same
scale of neurons as humans (but on the same order of data).
