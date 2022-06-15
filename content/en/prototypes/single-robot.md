+++
description = "Example of collaboration between microcomputer simulator and Hakoniwa"
bref = "Example of collaboration between microcomputer simulator and Hakoniwa"
title = "Microcomputer-controlled robot simulation"
draft = false
weight = 100
toc = true
script = 'animation'
images = ["img/prototypes/modelAdemo1.gif"]
github =  "https://github.com/toppers/hakoniwa-single_robot"
+++

This is a Hakoniwa prototype model with one SBC, designed based on the challenges of [ET Robocon](https://www.etrobo.jp/).
This prototype can verify by linking the program's behavior on the embedded microcontroller with the robot's behavior.

### Design intent from a technical study perspective

- Study on how to integrate between physical simulators and microcomputer simulators
- Study of time synchronization between different simulators

### Other design intent

- Promote Hakoniwa to ET Robot contenst participants (PR activities)

{{< image src="/img/prototypes/modelA.en.png" width="700" >}}

###  Installation & Usage

A trial package with minimal configuration and procedures is available in the GitHub repository below.
We encourage you to try it out.

- [toppers/hakoniwa-single_robot](https://github.com/toppers/hakoniwa-single_robot)

### Demonstration of examples

![modelAdemo](/hakoniwa/img/prototypes/modelAdemo.gif)

![modelAdemo1](/hakoniwa/img/prototypes/modelAdemo1.gif)

![modelAdemo2](/hakoniwa/img/prototypes/modelAdemo2.gif)

---

#### Acknowledgments & Notes

We want to thank Associate Professor Akio YOSHIOKA and undergraduate students Ryoji SUGISAKI, Akemi KIMURA and Jumpei CHIBA of Takarazuka University school of media art in Tokyo for their cooperation in designing the Unity package.

Unity assets of HackEV are based on data provided by the ET Robocon Executive Committee. 
We want to express our deepest gratitude to the Executive Committee.  
However, please note that this asset is different from the production environment of the ET Robocon. 
Please use this asset only for personal or educational use.