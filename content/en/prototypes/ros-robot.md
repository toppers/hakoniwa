
+++
description = "Example of simulation by collaboration between ROS and Hakoniwa"
bref = "Example of simulation by collaboration between ROS and Hakoniwa"
title = "ROS control robot simulation"
draft = false
weight = 200
toc = true
script = 'animation'
images = ["img/prototypes/modelROS.gif"]
github = "https://github.com/toppers/hakoniwa-ros2sim"
+++

This prototype model uses ROS/ROS2 to collaborate with multiple and single robots.
This prototype is lighter than Gazebo, often used with ROS, and allows for easy customization of robots and environments in Unity and the introduction of URDF format models.

### Design intent from a technical study perspective

- Running simulations using ROS, which is commonly used for robot control
- Study on how to coordinate with other robots 

### Other design intent

- Introduce robots controlled by ROS to create a simulation environment that mixes multiple control mechanisms

### Installation & Usage

A trial package with minimal configuration and procedures is available in the GitHub repository below.
We encourage you to try it out.

- [toppers/hakoniwa-ros2sim: 箱庭 ROS シミュレータ](https://github.com/toppers/hakoniwa-ros2sim)

### Demonstration of examples

![modelROSdemo](/hakoniwa/img/prototypes/modelROS.gif)

---

#### Acknowledgments & Notes

We want to thank Associate Professor Akio YOSHIOKA and undergraduate students Ryoji SUGISAKI and Akemi KIMURA of Takarazuka University school of media art in Tokyo for their cooperation in designing the Unity package for TurtleBot3.

TurtleBot3's Unity assets are based on data provided by Robotiz, Inc. 
We sincerely appreciate their cooperation.