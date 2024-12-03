---
layout: page
title: RRT/RRT* and Informed RRT* Motion Planning
description: Implementation of RRT based planning algorithms.
img: assets/img/1.jpg
github: https://github.com/omgaikwad08/RRT-and-Informed-RRT-star-algorithm-Implementation
importance: 4
category: Motion Planning
giscus_comments: true
---

The Rapidly-Exploring Random Tree (RRT) and its enhanced versions, RRT* and Informed RRT*, are pivotal in robotic path planning, especially within complex, high-dimensional spaces. These algorithms facilitate the discovery of feasible and optimized paths for robots navigating through environments with obstacles.

## Key Features and Contributions:
### Rapidly-Exploring Random Tree (RRT):

- Purpose: Efficiently explores large, high-dimensional spaces to find feasible paths from a start to a goal position.
- Methodology: Incrementally builds a tree by randomly sampling points in the space and connecting them to the nearest existing tree node, ensuring rapid exploration.
- Application: Particularly useful in environments with complex constraints and obstacles, providing a probabilistically complete solution.

### RRT-Star

- Enhancement: Introduces an optimization process that rewires the tree during construction to find not just feasible but optimal paths.
- Advantages: Maintains the rapid exploration characteristic of RRT while ensuring asymptotic optimality, meaning the solution improves over time.

### Informed RRT-Star;

- mprovement: Focuses the sampling process within an ellipsoidal subset of the space that contains the optimal path, enhancing efficiency.
- Collision Detection: Efficient algorithms are necessary to verify that nodes and edges are within the free space.
- Benefits: Accelerates convergence to the optimal path by reducing unnecessary exploration, making it suitable for high-dimensional problems.

<style>
    .uniform-img-size {
        width: 450px; /* adjust width as necessary */
        height: 250px; /* adjust height as necessary */
        object-fit: cover; /* ensures images cover the area without distorting aspect ratio */
    }
</style>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/rr1.jpg" title="example image" class="img-fluid rounded z-depth-1 uniform-img-size" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/rr2.jpg" title="example image" class="img-fluid rounded z-depth-1 uniform-img-size" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/rr3.jpg" title="example image" class="img-fluid rounded z-depth-1 uniform-img-size" %}
</div>
<div class="caption">
   Outputs of RRT, RRT-Star, and Informed RRT-Star
</div>
