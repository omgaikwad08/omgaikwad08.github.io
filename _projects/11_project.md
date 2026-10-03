---
layout: page
title: Agent Motion Prediction
description: Developed a CNN-RNN based model to predict motion of an agent using Lyft Dataset.
img: assets/img/7.jpg
github: https://github.com/omgaikwad08/Agent-Motion-Preditction/blob/main/cnn_rnn_agent_motion_prediction.ipynb
importance: 9
category: Deep Learning
giscus_comments: false
---

This project develops a **CNN-RNN hybrid deep learning model** to predict the future trajectory of agents (vehicles) using the **Lyft Level 5 Prediction Dataset** — a large-scale autonomous driving dataset containing rich map and agent history data.

## Problem Statement

Accurate motion prediction of surrounding agents is critical for safe autonomous driving. Given an agent's past trajectory and the map context, the goal is to predict where the agent will be at future timesteps.

## Dataset — Lyft Level 5

- Contains thousands of hours of driving data collected in Palo Alto, CA.
- Each sample includes:
  - **Agent history** — past positions and velocities over a fixed time window
  - **Semantic map raster** — top-down bird's-eye view with road lanes, crosswalks, and traffic information
  - **Ego vehicle context** — relative position and heading of the self-driving car

## Model Architecture

### CNN — Spatial Feature Extraction
- A **Convolutional Neural Network** processes the rasterized bird's-eye view map image.
- Extracts spatial features: lane geometry, road boundaries, nearby agents.
- Output is a compact feature vector representing the scene context.

### RNN — Temporal Sequence Modeling
- A **Recurrent Neural Network (LSTM)** processes the agent's historical trajectory as a time sequence.
- Captures temporal dependencies — speed trends, acceleration patterns, turning behavior.

### Combined Prediction Head
- CNN and RNN feature vectors are concatenated and passed through fully connected layers.
- Outputs predicted (x, y) coordinates for each future timestep.

## Training
- Loss function: **Mean Squared Error (MSE)** over predicted vs. ground truth future positions.
- Trained on GPU using the Lyft dataset's official API and evaluation metrics.

## Results
The CNN-RNN model successfully captured both spatial context and temporal motion patterns, producing smooth and realistic trajectory predictions across straight roads, lane changes, and intersection scenarios.
