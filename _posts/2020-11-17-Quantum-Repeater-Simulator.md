---
layout:     post
title:      Quantum Repeater Simulator
header-img: img/header-bg.png
catalog: 	 true
id:	Quantum_Repeater_Simulator
description: "<img class='bd-placeholder-img bd-placeholder-img-lg featurette-image img-fluid mx-auto' width='548' height='452' src='https://raw.githubusercontent.com/QuantumRepeaterSimulator/QuantumRepeaterSimulator.github.io/main/img/quantum_repeater/repeater_prototype.png'></img>"

---

# Theoretical Base of Quantum Repeater
## Entanglement Swapping
The quantum repeater is able to transfer the property of entanglement within two generated pairs, to two members of those pairs which were not previously entangled, an operation known as entanglement swapping.
![](https://raw.githubusercontent.com/QuantumRepeaterSimulator/QuantumRepeaterSimulator.github.io/main/img/quantum_repeater/entanglement_swapping.png)

## Quantum Memory
Two entangled pairs are generated and their members propagated to both the final destinations
and to an intermediate station, where a Bell-State Measurement (BSM) is performed after which the two remote members are then entangled. However, if the two sources are probabilistic then it is necessary to capture and store the pair members in quantum memories, which preserve their entangled state, until all four are ready to be read out.

Two important properties of quantum memories that would function in quantum repeaters are (i) they need to be readable, i.e., to have the photon emerge, on demand; and (ii) they need to be capable of heralding, meaning that one can perform a non-destructive measurement on each memory to confirm that a photon is stored there without measuring/projecting the photon’s value in the computational basis. With these two capabilities in hand, the repeater can adapt to entangled pairs being generated probabilistically by storing them until they can be heralded as all in place, and then synchronized.


# Quantum Repeater Prototype

![](https://raw.githubusercontent.com/QuantumRepeaterSimulator/QuantumRepeaterSimulator.github.io/main/img/quantum_repeater/repeater_prototype.png)
Three key components are added to the previous prototye: 1) master controller which has a global view of the entanglement distribution process, 2) clock which helps provide high-resolution time synchronized network, 3) and software-defined network (SDN) controller which allows us to control the traffic of quantum network.


# Network Simulation

## Mininet
Mininet creates a realistic virtual network, running real kernel, switch and application code, on a single machine.  Mininet is a great way to develop, share, and experiment with [OpenFlow](http://openflow.org/) and Software-Defined Networking systems.

## Open Network Operating System (ONOS)
The Open Network Operating System (ONOS) project is an [open source](https://en.wikipedia.org/wiki/Open_source "Open source") community hosted by [The Linux Foundation](https://en.wikipedia.org/wiki/The_Linux_Foundation "The Linux Foundation"). The goal of the project is to create a [software-defined networking](https://en.wikipedia.org/wiki/Software-defined_networking "Software-defined networking") (SDN) operating system for [communications service providers](https://en.wikipedia.org/wiki/Communications_service_provider "Communications service provider") that is designed for scalability, high performance and high availability.



## Network Topology
![](https://raw.githubusercontent.com/QuantumRepeaterSimulator/QuantumRepeaterSimulator.github.io/main/img/quantum_repeater/network_topology.png)

# Entanglement Distribution Simulation
## Entanglement Distribution Process
1. Master controller signals to entanglement sources asking for entanglement generation
2. Sources start to generating photons and send to quantum memory at Node A/ Node B, and two quantum memorys at BSM.
3. After receiving photons and saving photons at quantum memory, heralding messages are send to master controller.
4. Based on received heralding messages, whenever there are two pairs of photon, master controller would signal BSM to perform Bell State Measurement.
5. Bell Bell State Measurement results are sent back to master controller.  If Bell State Measurement succeed, then by now Node A and Node B have a pair of entanglements.

# Simulation Results
## Quantum Repeater performance
The following figure shows the Quantum Repeater performance.

A four-memory quantum repeater outperforms direct propagation at a distances of ∼ 53km when infrared conversion and transmission at 1324nm or 1367nm are considered.  The following target values were used in the model: R = 10,000 (entangled photons generated at source), α = 0.3dB/km (fiber transmission loss), η = 50% and F = 98.5% (storage efficiency and fidelity), det = 100% (detector efficiency), α = 50% (Bell state measurement visibility), conv = 100% (frequency conversion efficiency).
![](https://raw.githubusercontent.com/QuantumRepeaterSimulator/QuantumRepeaterSimulator.github.io/main/img/quantum_repeater/direct_transmission_vs_repeater.png)

## Memory assisted Quantum Repeater performance
The following figure shows the Memory assisted Quantum Repeater performance.
![](https://raw.githubusercontent.com/QuantumRepeaterSimulator/QuantumRepeaterSimulator.github.io/main/img/quantum_repeater/with_without_memory.png)
- When there are no momeries, whenever BSM receives two photons, it directly performs Bell State Measurement.  
- When distance is 0, and no photon is lost during transferring, all photons are able to perform bsm with or without quantum memory.
- When distance is small and photon loss rate is small during transferring, because quantum memory can only save one photon at a time, some photons that can be paired are excluded. Therefore, quantum memory negatively affect the entanglement distribution process.
- When distance is large and a lot of photons are lost during transferring, quantum memory can keep entanglement pairs at one side and wait another side for being paired, and vice versa. In such case, quantum memory brings more benefits to the entanglement distribution process.

## How do delay affect entanglement distribution?
The following figure shows the How do delay affect entanglement distribution?
![](https://raw.githubusercontent.com/QuantumRepeaterSimulator/QuantumRepeaterSimulator.github.io/main/img/quantum_repeater/delays_vs_entanglements.png)
- When there is no quantum memory, no matter how large delays the network has, the result is the same. Because the delays between sources and BSM are the same. So paired photons arrive BSM at the same time.
- It is the relative delays to generation period affects the entanglement distribution process.
- When distance is small and small amount of photons are lost during transferring, delays have larger impact on the number of entanglements. Because quantum memory can only save one photon at a time, some photons that can be paired are excluded.
- When distance is large and a lot of photons are lost during transferring, not many paired photons can be wasted. Hence, delays have smaller impact.

## How does quantum memory effectiveness affect entanglement distribution?
The following figure shows the How does quantum memory effectiveness affect entanglement distribution?
![](https://raw.githubusercontent.com/QuantumRepeaterSimulator/QuantumRepeaterSimulator.github.io/main/img/quantum_repeater/qm_hold_time_vs_entanglements.png)
- When distance is large and a lot of photons are lost during transferring, the longer quantum memory can saving a photons, the longer quantum memory can keep entanglement pairs at one side and wait another side for being paired, and vice versa. In such case, longer quantum memory holding photon time brings benefits to the entanglement distribution process.

# References
1. https://wiki.onosproject.org/display/ONOS/The+Network+Configuration+Service
2. http://mininet.org/