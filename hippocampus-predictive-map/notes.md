# Title: The hippocampus as a predictive map #
# Authors: Kimberley Stachenfeld, Matthew Botvinick, Samuel Gershman #

# Summary

The hippocampus can be thought of as a "predictive map", as opposed to
a map (analogous to model-based in RL).

The key formalism is decomposing the standard RL value function (of a policy)
into two terms: R(s') (the reward at state s'), and M(s, s') the expected
states in the future of the agent (discounted).

The authors argue that this model better explains hippocampal data,
specifically place cells.

Place cells are active when the organism is at a certain location in its
environment; the discrepancy they address is firing of place cells due 
to environmental features like obstacles, direction of travel, and generally
the topology of the environment.

There are several advantages to this decomposition:
- When the reward changes in the environment, the agent can rapidly
recompute the value of the policy
- Similar future states can be compressed / stored together in the map,
allowing for more memory-efficient data structures in the agent
- Experimentally, can explain why hippocampal place representations depend
on reward (due to dependence on policy)

So the guess is that hippocampal place cells encode *future* locations,
not present locations. Crucially, this depends on the policy that the 
agent has.

How to test this? Well with a barrier in an environment, the predictive
map hypothesis says that the place cells will only be active on one side
of the barrier, since those states are successors.

The second hypothesis of paper is that the predictive map is compressed
by another type of cell (entorhinal grid cell). Formally, these support
the eigendecomposition of the predictive map.

These eigenvectors can provide info on "bottlneck" states, which are
essentially instrumental goals/states. The authors cite some results from 
graph theory (k-way mincut) to identify these states.

Cool stuff. This could provide more efficient on-policy RL agents?
