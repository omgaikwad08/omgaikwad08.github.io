---
layout: page
title: Grasping Assuming Symmetery
description: Used a depth camera to capture real-time 3D representations of the environment, focusing on object symmetries to optimize grasping points. 
img: assets/img/3.png
github: https://github.com/omgaikwad08/Grasping-Assuming-Symmetry
importance: 2
category: Motion Planning
giscus_comments: false
---

This project presents a robotic grasping system that leverages object symmetry properties detected through depth camera data to determine stable grasp points — without relying on object-specific models or training data.

## Methodology

### 1. Preprocessing
- Downsamples raw point cloud data using **voxel grids** to reduce computational overhead.
- Removes environmental planes (tables, floors) using **RANSAC**, isolating the target object cleanly.

### 2. Symmetry-Based Point Cloud Completion
- Evaluates multiple candidate symmetry planes for the object.
- Selects the optimal plane using a **visibility scoring metric**, accounting for occlusions introduced by the camera perspective.
- Uses the identified symmetry to reconstruct the incomplete side of the object's point cloud.

### 3. Surface Normal Analysis
- Computes surface normal vectors at each point using local neighborhood analysis.
- Leverages **KDTree spatial indexing** for efficient nearest-neighbor queries across the point cloud.

### 4. Grasp Point Identification
- Identifies the first contact point nearest to the point cloud's **centroid**.
- Selects a second contact point that **minimizes the angle** between the surface normals and the grasp vector, maximizing grasp stability.

## Results
The approach was demonstrated on:
- **Cylindrical objects** — beverage cans
- **Spherical objects** — cricket balls

Both object classes were grasped reliably, validating the method's versatility across different geometric forms.

## Key Takeaways
- Combines geometric symmetry detection with physics-based grasp stability principles.
- Computationally efficient — suitable for real-time robotic manipulation.
- No object-specific training or CAD models required.
