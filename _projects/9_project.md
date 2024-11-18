---
layout: page
title: Low-Cost LiDAR scanner for Indoor Mapping
description: a prototype of an inexpensive and more flexible design of a 3-Dimensional (3D) LiDAR scanner with the use of a singlepoint ranging LiDAR sensor is presented. The design consists of an electromechanical setup, an optical sensor and a microcontroller for data acquisition (TF-Luna Range Sensor and Arduino Module).
img: assets/img/lidar.jpeg
github: https://ijiset.com/vol8/v8s12/IJISET_V8_I12_06.pdf
importance: 5
category: Hands-on Projects
giscus_comments: true
---

Engineered a cost-effective LiDAR-based scanning system aimed at enhancing the affordability and accessibility of indoor mapping solutions. This project involved developing a custom hardware-software integration for 3D point cloud generation, focusing on precision, efficiency, and cost-effectiveness.

## Key Contributions:
### LiDAR Hardware Integration:

- Selected and integrated a 2D LiDAR sensor with custom-built mechanical assemblies to enable continuous 360° scanning.
- Designed a rotating platform driven by a stepper motor for controlled scanning, ensuring comprehensive coverage of indoor environments.
### Data Acquisition and Processing:

- Implemented a data acquisition pipeline using microcontrollers and interfaces to capture LiDAR distance measurements in real-time.
- Developed algorithms to convert 2D LiDAR data into a 3D point cloud, enabling accurate spatial representation of indoor environments.
### Cost Optimization:

- Prioritized affordability by utilizing readily available components and efficient design practices, reducing the overall system cost compared to commercial alternatives.
- Conducted a comparative analysis against existing solutions to validate the cost-performance trade-off.
### System Calibration and Testing:

- Calibrated the LiDAR scanner for optimal accuracy in distance measurement and angle estimation, achieving an error margin of less than 2% in controlled environments.
- Conducted extensive testing in diverse indoor settings to ensure reliability and adaptability.
### Software Development:

- Developed a user-friendly interface to visualize the generated 3D point cloud data in real-time, aiding in navigation and analysis.
- Integrated mapping outputs with open-source platforms for further processing and analysis.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/l1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/l2.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/l3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Impact:
Provided an accessible solution for applications in robotics, indoor navigation, and environment mapping.
Significantly lowered the barrier to entry for small-scale researchers and developers by reducing hardware costs.
Demonstrated the potential of low-cost solutions for democratizing advanced technologies in spatial computing.