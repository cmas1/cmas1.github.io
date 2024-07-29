---
layout: page
title: Cooperative Aerial Transportation
description: a cable-suspended payload transported by a team of micro UAVs
img: assets/img/research/cooperative_transport/cover.jpg
importance: 3
category: past
related_publications: false
---

Aerial robots have been growing considerably in popularity and interest, both in terms of pure research, where it is a stable topic of discussion at all the major robotics conferences and journals, and in terms of real-world applications, where these platforms are now widely used in agriculture, monitoring of infrastructures, entertainment industry, etcetera.
This growth is reflected in the appearance of ever more complex tasks to be performed with aerial robots. One such task is the cooperative transportation and manipulation of objects using micro UAVs. My contribution to this field has been to introduce the concept that a cooperative transportation system composed by several UAVs connected to the payload by cables can be regarded as a **Cable-Driven Parallel Robot** (CDPR) and thus it can be studied with the well established methods that have been in use in that field for a long time.
Actually, this aerial transportation system is a generalization of a CDPR because the anchor points in the aerial system (the UAVS) can move whereas in traditional CDPR the anchors (winches) are fixed.

<div class="row">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/cooperative_transport/cover.jpg" title="idea of the aerial cable suspended transportation" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/cooperative_transport/cooperative_transport_math.jpg" title="sektch of the aerial cable suspended transportation kinematics system" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 1</b> The aerial transportation system of a cable-suspended payload can be regarded as a cable-driven parallel robot. Following this intuition, the UAVs can be considered as the anchors in a cable-driven parallel robot (CDPR). However, unlike traditional CDPRs, in this case the cable lengths are fixed and the anchors move. This increases the number of degrees of freedom from m (number of cables) to m x 6.
</div>


Considering this intuition, and with the visual help of Fig. 1, we can write the loop closure constraint for a single cable as

$$
{}^W \boldsymbol{l}_i = \rho_i \; {}^W\boldsymbol{n}_i = {}^W \boldsymbol{a}_i - {}^W\boldsymbol{p} - {}^W \boldsymbol{b}_i
$$

This is the classical loop closure equation for a CDPR. However, for CDPRs in general the anchor point $${}^W \boldsymbol{a}_i$$ and the cable length $$\rho_i$$ can change.  For the aerial transportation system it is the opposite, thus with $$m$$ cables there are $$m \times 6$$ degrees of freedom.
In the paper [Cooperative transportation of a payload using quadrotors: A reconfigurable cable-driven parallel robot](https://www.researchgate.net/publication/311754617_Cooperative_transportation_of_a_payload_using_quadrotors_A_reconfigurable_cable-driven_parallel_robot) we show that we can rewrite the loop-closure constraints for all cable in a compact form

$$
  N \boldsymbol{\rho} = \boldsymbol{\chi} - \boldsymbol{\xi}
$$
where $$\boldsymbol{\rho}$$ is the vector of cable lengths, $$N$$ is a block-diagonal matrix with the cable directions, $$\boldsymbol{\chi}$$ is the vector of the stacked anchor positions and $$\boldsymbol{\xi}$$ is the vector of stacked points where the cables are connected to the payload.
We further demonstrate that the trajectory of the anchors, denoted by $$\boldsymbol{\chi}$$ can be decomposed into two vector spaces:
* $$\mathcal{R}(N)$$, that is the $$m$$ dimensional range space of $$N$$. These are the motions of the anchors along the direction of their corresponding cables, and are the motions that instantaneously affect the payload.
* $$\mathcal{K}(N)$$, that is the $$2m$$ dimensional null space of $$N$$. These are the motions of the anchors that are orthogonal to the direction of their corresponding cables, and they do not affect instantaneously the payload. Namely, these are the internal motions of the system


This formalism exposes the possibility to exploit the internal motion of the system to adaptively achieve various objectives during operations depending on the current state of the system and of the environment, e.g. maximixing the stability of the payoad when there is an external disturbance or reducing the energy consumption of the UAVs to extend the flight duration. 


<div class="row">
    <div class="col-sm-7 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/cooperative_transport/coop_trans_sim.jpg" title="simulation" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/cooperative_transport/coop_trans_exp.jpg" title="experiment" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 2</b> Validation of the system in simulation (left) and with real quadrotors (right).
</div>

Building on this formalism we created a dual space control system based on solutions available in CDPR, and we demonstrated it both in simulation and with experiments as shown in Fig. 2. It was also further extended with the developmetn of a shared control framework tailored to allow a single human operator to manipulate the transported payload disregarding the individual behavior of the UAVs, while at the same time exploiting the extra degrees of freedom from the internal motions to perform obstacle avoidance and to reshape the formation.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/cooperative_transport/shared_control_arch.jpg" title="shared control architecture for the cooperative transportation system" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 3.</b> Shared control architecture for the cooperative transportation system. Image from the paper <a href="https://link.springer.com/content/pdf/10.1007/s10846-021-01457-4.pdf">Shared Control of an Aerial Cooperative Transportation System with a Cable-suspended Payload</a>.
</div>




---
<h2>Related Publications</h2>
<div class="publications">
  {% bibliography -f papers -q @*[keywords~=aerial cable robot]* %}
</div> 