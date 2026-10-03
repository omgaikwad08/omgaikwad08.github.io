---
layout: page
title: Control Design of Quadcopter for UAV catch and return.
description: The proposed project is an implementation of the Linear Quadrotor Regulator (LQR) theory for the control of a quadrotor that spans the given restricted airspace. Moroever, the idea focuses on the capture and retrieval of unknown aerial intruders such as a UAV. 
img: assets/img/6.jpg
github: https://github.com/omgaikwad08/Control-Design-of-Quadcopter-for-UAV-catch-and-return-
importance: 9
category: State Estimation
giscus_comments: false
---

This project implements a **Linear Quadratic Regulator (LQR)** controller for autonomous quadrotor flight, with a focus on capturing and retrieving unknown aerial intruders (UAVs) within a restricted airspace.

## Problem Statement

Unauthorized UAVs operating in restricted airspace pose a growing security and safety threat. This project proposes an autonomous quadrotor system capable of:
- Navigating the restricted airspace with stability
- Intercepting an unknown aerial intruder
- Executing a capture and retrieval maneuver

## System Modeling

### Nonlinear Dynamics
The quadrotor's full nonlinear equations of motion are derived, capturing:
- 6-DOF rigid body dynamics (3 translational + 3 rotational)
- Rotor thrust and torque interactions
- Gyroscopic effects from spinning rotors

### Linearization
The nonlinear model is linearized around a **hover equilibrium point** using a **first-order Taylor series expansion**, producing a linear state-space model suitable for LQR design.

## LQR Controller Design

The LQR minimizes a quadratic cost function:

$$J = \int_0^\infty \left( x^T Q x + u^T R u \right) dt$$

- **Q matrix** — penalizes state deviations (position, velocity, orientation errors)
- **R matrix** — penalizes control effort (rotor forces)
- Optimal gain matrix **K** computed by solving the **Algebraic Riccati Equation (ARE)**

## Mission Profile: Catch & Return

The controller was designed to handle:
1. **Launch** — stable takeoff and entry into restricted airspace
2. **Trajectory Control** — smooth pursuit of the intruder UAV
3. **Capture** — precise interception with minimal overshoot
4. **Return** — stable return flight with the captured UAV

Key performance factors evaluated: response time, trajectory smoothness, and capture accuracy.

## Simulation
The full simulation is implemented in **MATLAB** (`Quadrotor_LQR_Sim.m`) and validated the controller's ability to stabilize the quadrotor and execute the capture mission across multiple flight scenarios.
