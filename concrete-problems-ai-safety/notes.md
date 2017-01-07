# Title: Concrete Problems in AI Safety #
# Authors: D. Amodei, C. Olah, J. Steinhardt, et al #

## Intro

As ML systems become more capable, deployed in increasingly general
environments, and more autonomous, the risk of accidents increases. The
authors specify a set of concrete technical problems that occur
in todays systems and hopefully scale to systems of the future, where
a mix of theoretical and empirical work can help reduce accident risk.

The authors identify some general trends that point to increasing risk:
(1) RL being a promising paradigm for AI: increased risk from agent-
environment interactions

(2) Complex, opaque agents and environments: harder for us to reason about

(3) Autonomous agents: less human control

## Problems

### Negative side effects

Some ideas:
- write an impact regularizer (hard)
- learn an impact regularizer (intuition here is that side-effects might
transfer better across environments than actions/performance)
- penalize influence (or empowerment)
- multiagent: IRL...
cool idea: reward autoencoder that encodes/decodes representations of
actions
- uncertainty about reward function


### Reward hacking

Another way of phrasing the point here is: dominating policies in RL exist
From the agent's point of view, hacking its reward function is just another 
malleable aspect of the environment. 
[TODO - analyze this from a security perspective]

In what situations can reward hacking arise?

- Partially observed goals
- Complexity in models/systems
- far/abstract rewards
- badly specified reward (goodhart's law)
- no cartesian boundary between agent/environment: its reward signal
is just another part of the environment

ideas:
- using adveraries to get good behavior (adversarial reward network)
- reward based on model lookahead, to avoid "wireheading" behavior
- crossvalidation for agents!
- formal verification applied to ML systems
- failsafe: reward capping
- multiple rewards: [TODO - vector valued reinforcement learning?]

TODO - potential experiment idea: delusion boxes in openAI gym environments


### Scalable oversight - Expensive to evaluate objective function

The authors model this in terms of semi-supervised RL, where the agent
can only see the reward on a small fraction of episodes. In the active RL
setting the agent can request to see the reward.

Hierarchical RL: analogous to principal agent problems that we face,
so could tell us something about safety that way also

### Safe exploration

- One idea is to optimize for criteria that are risk sensitive, e.g.
worst-case behavior. Could be testable with ANNs. Yarin Gal's thesis
on uncertainty in deep learning may be relevant here.
- IRL can reduce the need for exploration by learning from an expert policy
(which provides lots of clues for near-optimal behavior)
- Simulate exploration as much as possible
- Safe exploration: remain in ergodic part of the state space (might be
a short term measure since in general, environments we want these
agents to act in are non-ergodic)
- Trusted policy oversight: seems limited, not sure I fully understand

### Distributional shift

- We want our models to inductively detect ambiguity/uncertainty
- Here if we have well specified models there are well specified models
that might work well, like covariate shift, or building a generative
model of the distribution

- partially specified models: didn't really follow the methods here,
have to dive more deeply

- counterfactual reasoning is general form of distributional shift?





