+++
title = "Underlying technology"
draft = false
weight = 50
toc = false
script = 'animation'
description = "Introduction to the underlying technology comprising Hakoniwa"
bref = "Introduction to the underlying technology comprising Hakoniwa"
+++

### TOPPERS Kernel

Developed by the [TOPPERS Project](https://toppers.jp), it is an open-source real-time kernel that extends the standard profile of the µITRON4.0 specification.
It primarily targeted embedded systems that require high reliability, safety, and real-time performance.

[![TOPPERS](https://www.toppers.jp/imgs/logo.gif)](https://toppers.jp/)

### Athrill

The CPU instruction set simulator is the core of Hakoniwa.    
Members of Hokoniwa WG mainly develop it. It enables debugging and functional verification of the behavior of embedded microcontrollers and peripherals at the instruction level. Currently, V850/RH850 and ARMv7-A are mainly supported.


The software is being developed as open source under the TOPPERS license.
- https://github.com/toppers/athrill

{{< image src="/img/athrill.png" width="200" href="https://github.com/toppers/athrill" >}}


### mROS

ｍROS is a lightweight ROS (ROS1) execution environment for embedded systems.
It enables publication-subscription communication from an embedded microcontroller to a ROS master and ROS nodes on a host PC. 
[Computing System Laboratory, Graduate School of IST, The University of Tokyo](http://www.hal.ipc.i.u-tokyo.ac.jp/index-e.html) plays a leading role in the development.    
It targets systems such as [Simulation of collaborative operation of multiple robots](/hakoniwa/en/prototypes/multi-robot).

- https://github.com/mROS-base

{{< image src="img/mROS.png" width="300" href="https://github.com/mROS-base" >}}

### RDBOX

RDBOX (Robotics Developers BOX) is a framework for automatically building Kubernetes clusters and secure, scalable Wi-Fi networks optimized for ROS robots and IoT. 
It aims to bridge simulation and real-world work environments. 
Intec Inc. is developing [RDBOX Project](https://rdbox-intec.github.io/homepage_jp/).    
We are collaborating with Hakoniwa to construct prototype model for [Simulation of inter-robot cooperative operation](/hakoniwa/en/prototypes/harmony-robot).

- https://github.com/rdbox-intec/rdbox

{{< rawhtml >}}
<a href="https://github.com/rdbox-intec/rdbox">
<img src="https://rdbox-intec.github.io/homepage_en/icons/icon-512x512.png" width="250">
</a>
<br>
<br>
{{< /rawhtml >}}

### Unity

It is a real-time 3D development platform, famous as a game engine with a built-in IDE.    
Hakoniwa uses it for its physics engine and spatial visualization.

- https://unity.com/

{{< rawhtml >}}
<br>
<a href="https://unity.com/">
<img src="https://meetup-uploads.unity3d.jp/2ec5b714ac553e261a155a0dc1b649406f9264a2.png" width="250">
</a>
<br>
<br>
<br>
{{< /rawhtml >}}

---
The Hokoniwa WG is currently looking into other technological elements helpful in building virtual environments in the age of IoT/Cloud Robotics.
If you know of any technologies that can generate synergies or have sound knowledge, please let us know.


{{< rawhtml >}}
<span style="font-size: 70%">
Note: This web page is not sponsored by or affiliated with Unity Technologies or its affiliates.
All Unity trademarks included in <a href="https://unity3d.com/jp/legal/trademarks" target="_blank">the list of Unity trademarks</a> on this site are registered trademarks or trademarks of Unity Technologies or its affiliates in the United States and/or other countries.
</span>
{{< /rawhtml >}}


