# Reinforcement-Learning

![img](https://datawhalechina.github.io/leedeeprl-notes/chapter1/img/1.1.png)

## Basic concept
How can an agent maximize the rewards in a complex and uncertain environment? 
The schematic diagram consists of two parts: agent and environment. During the reinforcement learning process, the agent and the environment are always interacting. 
The agent obtains the state in the environment, and the agent uses this state an action and a decision as output. Then this decision will be put into the environment, 
and the environment will use the decision that agent takes to output the next state and the reward for the current decision. 
The purpose of the agent is to get as many rewards from the environment as possible.

## Sequential Decision Making

### Reward
- A reward is a scalar feedback signal
- Indicate how well agent is doing at step t
- Reinforcement Learning is based on the maximization of rewards:
All goals of the agent can be described by the maximization of expected
cumulative reward.

### What is Sequential Decision Making?
- The history is the sequence of observations, actions, rewards.
- What happens next depends on the history
- State is the function used to determine what happens next
                      St = f(Ht)

- Environment state and agent state
- Full observability: agent directly observes the environment state,
formally as Markov decision process (MDP)
- Partial observability: agent indirectly observes the environment,
formally as partially observable Markov decision process
(POMDP) -> Black jack (only see public cards), Atari game with pixel observation.

## Major Components of an RL Agent

An RL agent may include one or more of these
components:
- Policy: agent’s behavior function
- Value function: how good is each state or action
- Model: agent’s state representation of the environment

### Policy
![img](https://datawhalechina.github.io/leedeeprl-notes/chapter1/img/1.26.png)

![img](https://datawhalechina.github.io/leedeeprl-notes/chapter1/img/1.31.png)


### Value Function
Value function: expected discounted sum of future rewards under a
particular policy
- Discount factor weights immediate vs future rewards
- Used to quantify goodness/badness of states and actions
- Q-function (could be used to select among actions)

![img](https://datawhalechina.github.io/leedeeprl-notes/chapter1/img/1.32.png)

### Model

![img](https://datawhalechina.github.io/leedeeprl-notes/chapter1/img/1.29.png)

### Types of RL Agents based on What the Agent Learns
- Value-based agent:
      - Explicit: Value function
      - Implicit: Policy (can derive a policy from value function)
- Policy-based agent:
      - Explicit: policy
      - No value function
- Actor-Critic agent:
      - Explicit: policy and value function


### Types of RL Agents on if there is model
- Model-based
      - Explicit: model
      - May or may not have policy and/or value function
- Model-free
      - Explicit: value function and/or policy function
      - No model.

![img](https://datawhalechina.github.io/leedeeprl-notes/chapter1/img/1.36.png)

### Exploration and Exploitation
- Agent only experiences what happens for the actions it tries!
- How should an RL agent balance its actions?
       - Exploration: trying new things that might enable the agent to make better
          decisions in the future
       - Exploitation: choosing actions that are expected to yield good reward given
          the past experience
- Often there may be an exploration-exploitation trade-off
       - May have to sacrifice reward in order to explore & learn about potentially
          better policy