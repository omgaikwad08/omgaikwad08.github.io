---
layout: page
title: UKF-based-Quadcopter-Localization
description: A Uncenscted Kalman Filter (UKF) based approach for Quadcopter Localization.
img: assets/img/5.png
github: https://github.com/omgaikwad08/UKF-based-Quadcopter-Localization
importance: 5
category: State Estimation
giscus_comments: false
---

This project implements an **Unscented Kalman Filter (UKF)** for estimating the 6-DOF pose (position + orientation) of a quadcopter using noisy IMU sensor data — addressing the limitations of the Extended Kalman Filter in highly nonlinear systems.

📄 **[Full Project Report](https://github.com/user-attachments/files/17882609/Extended.Kalman.Filter.Report.pdf)**

## Why UKF over EKF?

The **Extended Kalman Filter** linearizes nonlinear functions via Jacobians — an approximation that degrades accuracy when the system is highly nonlinear (e.g., aggressive quadcopter maneuvers).

The **Unscented Kalman Filter** avoids this by using the **Unscented Transform**: instead of linearizing, it propagates a deterministic set of carefully chosen sample points (sigma points) through the exact nonlinear function.

## Methodology

### Sigma Point Generation
- Selects **2n + 1 sigma points** (where n is the state dimension) around the current mean and covariance.
- Sigma points are spread using a scaling parameter that controls how far they are from the mean.

### Prediction Step
- Propagates each sigma point through the nonlinear quadcopter dynamics model.
- Recomputes the predicted mean and covariance from the transformed sigma points.

### Update Step
- Maps sigma points through the measurement model.
- Computes the Kalman gain using the predicted measurement mean and cross-covariance.
- Updates state estimate with incoming sensor measurements.

## Quadcopter State Model
The state vector tracks:
- **Position**: x, y, z
- **Orientation**: roll (φ), pitch (θ), yaw (ψ)
- **Velocities**: linear and angular

Sensor inputs from the **IMU** (accelerometer + gyroscope) are fused to maintain real-time pose estimates.

## Results
The UKF demonstrated accurate localization across both hover and dynamic flight conditions, with significantly reduced estimation error compared to EKF during rapid orientation changes.
