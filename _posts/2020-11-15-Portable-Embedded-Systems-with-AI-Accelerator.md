---
layout:     post
title:      Portable Software Defined Network on Embedded Systems with AI Accelerator
header-img: img/header-bg.png
anchor:	Portable_Embedded_Systems
catalog: 	 true
description: "<img class='bd-placeholder-img bd-placeholder-img-lg featurette-image img-fluid mx-auto' width='548' height='452' src='https://raw.githubusercontent.com/QuantumRepeaterSimulator/QuantumRepeaterSimulator.github.io/main/img/portable_embedded_systems/jetson_nano.png'></img>"

---

The traditional software-defined network requires separated computer servers and hardware to implement the centralized SDN controller and distributed SDN infrastructure layer. It is difficult to implement and deploy in the existing network infrastructure because of the restriction in physical space, power consumption, portability, and operation costs.

Recent advancements in hardware standardize the co-processor architecture where the arm-based CPU handles the task scheduling and the GPU/FPGA co-processor for computation acceleration. The embedded system packs significant computation and storage power into a palm-sized computer. One popular embedded computer is NVIDIA Jetson TX2. It has sufficient computing and memory capacity to run deep learning inference tasks and output computer servers. The third generation of NVIDIA embedded system (NVIDIA Xavier) has 20 times more computing capability and three times larger memory capacity. We showed that the NVIDIA Xavier embedded system successfully trained a Deep Q-Learning network written in Python notebook for playing Atari games. Our laboratory benchmark tests confirmed that Xavier supports both training and inference of deep neural network and attains a superior performance to the server-grade NVIDIA K40 GPU card. It only consumes 30 Watts for these tasks. This type of embedded system offers a portable alternative for the SDN controller and infrastructure node.  Also, they are able to host one of the most popular SDN implements: open network operating system (ONOS), which makes them a goot candidate to implement quantum network. 

![](https://raw.githubusercontent.com/QuantumRepeaterSimulator/QuantumRepeaterSimulator.github.io/main/img/portable_embedded_systems/jetson_nano.png)


In sum, Jetson Xavier NX/TX2 Nano provides Intelligent control module to Quantum Networks

-   Phone-size supercomputer with small power budget 
    
-   Cost-effective
    
-   Full-fledged Operating Systems
    
-   Support Open Source SDN (ONOS) and Deep Neural Networks Software Stack
    
-   Easy Deployable at any environment
    
-   Commercial off-the-shelf Product