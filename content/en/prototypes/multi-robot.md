+++
description = "Collaborative operation of multiple ROS robots using the Photon library and VR environment"
bref = "Collaborative operation of multiple ROS robots using the Photon library and VR environment"
title = "Simulation of collaborative operation of multiple robots"
draft = false
weight = 300
toc = false
script = 'animation'
images = ["img/prototypes/modelBoverview.en.png"]
github = "https://github.com/toppers/hakoniwa-ros-multiplay"
+++

This prototype model simulates multiple robots and control programs in the same environment.
This prototype uses Unity's Photon library to synchronize multiple Unity environments and even time synchronization among assets and uses VR technology to dive into the simulation environment for verification.

{{< image src="img/prototypes/modelBoverview.en.png" width="700" >}}

### Design intent from a technical study perspective

- Study of methods of collaboration in multiple environments (e.g., simulation time synchronization)
- Study on how visualize communication among Hakoniwa assets (including ROS/ROS2 collaboration)/ROS2連携含む）
- Study of mechanisms to augment Hakoniwa assets

### Other design intent

- Promote Hakoniwa to the ROS user base (PR activities)

### Installation & Usage

Various demos are available at the following Github repository. Try them out.

‐ [toppers/hakoniwa-ros-multiplay](https://github.com/toppers/hakoniwa-ros-multiplay)

### Demonstration of examples
- Multiple robot collaboration with photon
{{< video src="/img/prototypes/modelBdemo1.mp4">}}
- Scene of connection with Oculus Quest
{{< video src="/img/prototypes/modelBdemo2.mp4">}}
- Scene diving into Hakoniwa using VR
{{< video src="/img/prototypes/modelBdemo3.mp4">}}

