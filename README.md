# Continuous_Control_using_Reinforcement_Learning

This repository presents a solution to the Unity "Reacher" environment based upon a Deep Deterministic Policy Gradient approach.

# Environment
The environment is a simulated set of 20 robot arms, where the objective is to ????

# Actor-Critic


# Deep Deterministic Policy Gradient
One of the earliest appearances of Deep Reinforcement Learning was the DQN model, which uses a neural network function approximator to estimate the action-value 
function for an environment with a discrete number of possible actions (see: https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf).  This worked extremely well, but would fail in the case of a continuous action space with a non-denumerable set of possible actions, as in the case of a robot determining how much torque to apply to keep its arm stable.
The solution proposed by a team at Google Deepmind (see: https://arxiv.org/pdf/1509.02971.pdf) is to use a second neural network which takes the state as the input and directly outputs the optimal action, which then gets fed into the larger Q network along with the state.  
