# Q-Learning-Algorithm
# Q-Learning Agent

## Project Overview

This project demonstrates the implementation of a **Q-Learning agent** using Python.

Q-Learning is a model-free reinforcement learning algorithm that allows an agent to learn the best action to take in a given state by interacting with an environment and receiving rewards.

The agent gradually improves its behavior by updating a Q-table that stores the estimated value of taking each action in each state.

## Objective

The objective of this project is to understand how a reinforcement learning agent learns through trial and error.

The project demonstrates how an agent can:

- Observe the current state
- Select an action
- Receive a reward
- Move to a new state
- Update its Q-value
- Improve its policy over time

## Q-Learning Concept

Q-Learning estimates the value of performing an action in a particular state.

The Q-value is updated using the following equation:

\[
Q(s,a) =
Q(s,a) +
\alpha
\left[
r +
\gamma \max Q(s',a')
-
Q(s,a)
\right]
\]

Where:

- \(Q(s,a)\) = current Q-value
- \(\alpha\) = learning rate
- \(r\) = reward
- \(\gamma\) = discount factor
- \(s'\) = next state
- \(\max Q(s',a')\) = maximum expected future reward

## How the Agent Learns

The learning process follows these steps:

1. The environment starts in an initial state.
2. The agent observes the current state.
3. The agent selects an action.
4. The environment returns a reward and the next state.
5. The agent updates the corresponding Q-value.
6. The process continues until the episode ends.
7. Training is repeated across multiple episodes.

Over time, the agent learns which actions produce the highest long-term rewards.

## Q-Table

The Q-table stores the estimated value of each state-action pair.

Example:

| State | Action 1 | Action 2 | Action 3 |
|---|---:|---:|---:|
| State 0 | 0.10 | 0.45 | 0.20 |
| State 1 | 0.35 | 0.15 | 0.70 |
| State 2 | 0.80 | 0.40 | 0.25 |

The agent generally prefers the action with the highest Q-value after sufficient training.

## Exploration and Exploitation

The agent uses an **epsilon-greedy strategy** to balance exploration and exploitation.

### Exploration

The agent chooses a random action to discover new possibilities.

### Exploitation

The agent chooses the action with the highest known Q-value.

During training, epsilon can gradually decrease so that the agent explores more in the beginning and relies more on learned knowledge later.

## Main Hyperparameters

### Learning Rate

The learning rate determines how strongly new information changes the existing Q-value.

\[
0 < \alpha \leq 1
\]

### Discount Factor

The discount factor determines how much the agent values future rewards.

\[
0 \leq \gamma \leq 1
\]

### Epsilon

Epsilon controls the probability of selecting a random action.

A higher epsilon encourages more exploration.

## Training Process

The general Q-Learning training process is:

```text
Initialize Q-table

For each episode:

    Reset the environment

    Observe the current state

    While the episode is not finished:

        Select an action using epsilon-greedy policy

        Perform the action

        Observe reward and next state

        Find the maximum Q-value for the next state

        Update the current Q-value

        Move to the next state
```

## Example Q-Value Update

Suppose:

```text
Old Q-value = 0.50
Learning Rate = 0.10
Reward = 1
Discount Factor = 0.90
Best Future Q-value = 0.80
```

The update becomes:

```text
New Q =
0.50 + 0.10 × (1 + 0.90 × 0.80 - 0.50)
```

The updated Q-value becomes approximately:

```text
0.622
```

This process is repeated continuously during training.

## Technologies Used

- Python
- NumPy
- Reinforcement Learning
- Q-Learning
- Epsilon-Greedy Exploration
- Google Colab / Jupyter Notebook

## Project Structure

```text
Q-Learning-Agent/
│
├── README.md
├── q_learning_agent.ipynb
└── q_learning_agent.py
```

Additional files such as plots or evaluation results can also be included.

## Evaluation

The performance of the agent can be evaluated using metrics such as:

- Total reward per episode
- Average reward
- Number of steps per episode
- Success rate
- Convergence of Q-values
- Final learned policy

## Key Concepts Demonstrated

This project demonstrates:

- Reinforcement Learning
- Q-Learning
- Q-Tables
- State-action values
- Reward-based learning
- Exploration vs. exploitation
- Epsilon-greedy strategy
- Learning rate
- Discount factor
- Policy improvement

## Limitations

Tabular Q-Learning works well when the number of states and actions is relatively small.

For environments with very large or continuous state spaces, maintaining a Q-table becomes difficult.

In those situations, more advanced methods such as Deep Q-Networks can be used to approximate Q-values with neural networks.

## Conclusion

This project demonstrates how a reinforcement learning agent can learn an effective policy through interaction with an environment.

Instead of being given explicit rules, the Q-Learning agent improves its decisions by receiving rewards, updating Q-values, and balancing exploration with exploitation.

The project provides a foundation for understanding more advanced reinforcement learning algorithms such as Deep Q-Learning, DQN, PPO, and Actor-Critic methods.

## Author

**Chakradhar Patnam**

Applied Machine Intelligence and Reinforcement Learning
