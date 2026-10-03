---
layout: page
title: Extended Kalman & Partical Filters.
description: Drone Trajectory Tracking using Extended Kalman & Partical Filter approach. 
img: assets/img/4.jpg
github: https://github.com/omgaikwad08/Kalman-Filter-based-Drone-Track
importance: 3
category: State Estimation
giscus_comments: false
---

This project implements and compares two state estimation approaches — **Extended Kalman Filter (EKF)** and **Particle Filter** — for tracking a drone's trajectory and estimating its 6-DOF pose in real time.

📄 **[Full Project Report](https://github.com/user-attachments/files/17882622/Kalman_Filter_Report-1.pdf)**

## Extended Kalman Filter (EKF)

The EKF extends the standard Kalman Filter to handle **nonlinear system dynamics** by linearizing around the current state estimate using a first-order Taylor series (Jacobian matrices).

### Key Steps:
- **Prediction**: Propagates the state estimate forward using the nonlinear motion model.
- **Update**: Incorporates sensor measurements by linearizing the observation model at each timestep.
- **Covariance Propagation**: Tracks uncertainty through the Jacobian of the motion and measurement models.

### Application to Drone Tracking:
- State vector includes position, velocity, and orientation (roll, pitch, yaw).
- IMU and GPS measurements fused to maintain consistent pose estimates across fast maneuvers.

## Particle Filter

The Particle Filter is a **Monte Carlo-based** approach that represents the probability distribution of the drone state using a set of weighted samples (particles) — capable of handling highly nonlinear and non-Gaussian systems.

### Key Steps:
- **Sampling**: Draws particles from the prior distribution at each timestep.
- **Weighting**: Assigns weights to particles based on how well they match incoming sensor data.
- **Resampling**: Eliminates low-weight particles and duplicates high-weight ones to concentrate samples in high-probability regions.

## Comparison

| Feature | EKF | Particle Filter |
|---|---|---|
| Handles nonlinearity | Approximate (linearization) | Exact (sampling) |
| Computational cost | Low | Higher (scales with # particles) |
| Non-Gaussian noise | Limited | Handles well |
| Real-time suitability | ✅ Yes | ⚠️ Depends on particle count |

## Results
Both filters were validated on simulated drone trajectory data, with the Particle Filter showing superior robustness during sharp turns and noisy conditions, while the EKF maintained lower computational overhead for smooth trajectories.
