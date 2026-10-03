---
layout: page
title: DQN and PPO implementation on Breakout Atari Game.
description: Developed and compared the Deep Q-Network and Proximal Policy Optimization algorithm on Breakout Atari Game.
img: assets/img/8.gif
github: https://github.com/omgaikwad08/Final-Reinforcement-learning-Project-CS525
importance: 5
category: Deep Learning
giscus_comments: false
---

This project implements and compares two reinforcement learning algorithms — **Deep Q-Network (DQN)** and **Proximal Policy Optimization (PPO)** — on the **Breakout Atari game** environment using OpenAI Gym.

## Environment — Breakout (Atari)

Breakout is a classic Atari game where an agent controls a paddle to bounce a ball and break bricks. The agent:
- Receives raw pixel frames as input
- Must learn to maximize score through trial and error
- Faces sparse rewards and requires long-horizon planning

## Deep Q-Network (DQN)

DQN is a **value-based** off-policy algorithm that approximates the optimal action-value function Q(s, a) using a deep neural network.

### Key Components:
- **Experience Replay Buffer** — stores past transitions (s, a, r, s') to break temporal correlations during training.
- **Target Network** — a periodically updated copy of the Q-network to stabilize training.
- **ε-Greedy Exploration** — balances exploration vs. exploitation by randomly selecting actions with probability ε.

### Network Architecture:
- 3 convolutional layers for raw pixel processing
- Fully connected layers mapping to Q-values for each action

## Proximal Policy Optimization (PPO)

PPO is a **policy gradient** on-policy algorithm that directly optimizes the policy while constraining how much it changes per update — preventing destructively large policy updates.

### Key Components:
- **Clipped Surrogate Objective** — limits the policy ratio to a small range [1-ε, 1+ε], ensuring stable updates.
- **Actor-Critic Architecture** — separate heads for policy (actor) and value function (critic).
- **Generalized Advantage Estimation (GAE)** — reduces variance in policy gradient estimates.

## Comparison

| Feature | DQN | PPO |
|---|---|---|
| Type | Value-based | Policy gradient |
| On/Off policy | Off-policy | On-policy |
| Sample efficiency | Higher | Lower |
| Stability | Moderate | High |
| Continuous actions | ❌ | ✅ |

## Results
Both algorithms were trained and evaluated on Breakout. PPO demonstrated more stable training curves, while DQN achieved competitive scores with higher sample efficiency. Performance was measured using average episode reward over training iterations.
