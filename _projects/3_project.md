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

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/inputPointCloud.png" title="Input Point Cloud" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/outPutPointCloud.png" title="Output Point Cloud after Plane Removal" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: Raw input point cloud. Right: Point cloud after RANSAC plane removal, isolating the target object.
</div>

### 2. Symmetry-Based Point Cloud Completion
- Evaluates multiple candidate symmetry planes for the object.
- Selects the optimal plane using a **visibility scoring metric**, accounting for occlusions introduced by the camera perspective.
- Uses the identified symmetry to reconstruct the incomplete side of the object's point cloud.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/pointCloudCompletion.png" title="Point Cloud Completion using Symmetry" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Symmetry-based point cloud completion — reconstructing occluded regions of the object.
</div>

### 3. Surface Normal Analysis
- Computes surface normal vectors at each point using local neighborhood analysis.
- Leverages **KDTree spatial indexing** for efficient nearest-neighbor queries across the point cloud.

### 4. Grasp Point Identification
- Identifies the first contact point nearest to the point cloud's **centroid**.
- Selects a second contact point that **minimizes the angle** between the surface normals and the grasp vector, maximizing grasp stability.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/bestGrasp.png" title="Best Grasp Configuration" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Identified optimal grasp contact points based on symmetry and surface normal analysis.
</div>

## Results
The approach was demonstrated on:
- **Cylindrical objects** — beverage cans
- **Spherical objects** — cricket balls

Both object classes were grasped reliably, validating the method's versatility across different geometric forms.

## Key Takeaways
- Combines geometric symmetry detection with physics-based grasp stability principles.
- Computationally efficient — suitable for real-time robotic manipulation.
- No object-specific training or CAD models required.
