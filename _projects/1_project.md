---
layout: page
title: PRM based Motion Planning
description: Implemented Probablisitc Roadmap Algorithm using Random, Uniform, Gaussian, and Bridge-sampling methods. 
img: assets/img/1.png
github: https://github.com/omgaikwad08/Probablisitic-Roadmap-PRM-Algorithm-Implementation
importance: 2
category: Motion Planning
giscus_comments: true
---

The Probabilistic Roadmap (PRM) algorithm is a fundamental method in robotic path planning, particularly effective in high-dimensional configuration spaces. It constructs a network of feasible paths by randomly sampling points in the environment and connecting them to form a roadmap, which a robot can then use to navigate from a start to a goal position.

## Key Features of PRM:
### Two-Phase Approach:

- Learning Phase: Randomly samples the configuration space to generate nodes and attempts to connect these nodes with collision-free edges, forming a roadmap.
- Query Phase: Utilizes the precomputed roadmap to find a path between the start and goal configurations using graph search algorithms like A*.

<style>
    .uniform-img-size {
        width: 450px; /* adjust width as necessary */
        height: 250px; /* adjust height as necessary */
        object-fit: cover; /* ensures images cover the area without distorting aspect ratio */
    }
</style>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/pp1.jpg" title="example image" class="img-fluid rounded z-depth-1 uniform-img-size" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/pp2.jpg" title="example image" class="img-fluid rounded z-depth-1 uniform-img-size" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/pp3.jpg" title="example image" class="img-fluid rounded z-depth-1 uniform-img-size" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/pp4.jpg" title="example image" class="img-fluid rounded z-depth-1 uniform-img-size" %}
    </div>
</div>
<div class="caption">
   PRM algorithm implemented on Uniform, Random, Gaussian, and Bridge sampling.
</div>

### Advantages:

- Probabilistic Completeness: Ensures that a path will be found if one exists, given sufficient sampling.
- Efficiency in Complex Spaces: Particularly useful in environments with numerous obstacles, as it doesn't require an explicit representation of the free space.

### Implementation Considerations:

- Sampling Strategy: The quality of the roadmap depends on the sampling density and distribution.
- Collision Detection: Efficient algorithms are necessary to verify that nodes and edges are within the free space.
- Graph Search: Algorithms like A* or Dijkstra's are employed to find the shortest path on the constructed roadmap.

