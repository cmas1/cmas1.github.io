---
layout: page
title: CableRobot Simulator
description: world's first cable robot for passengers
img: assets/img/research/cablerobot/cover.jpg
importance: 2
category: past
related_publications: false
---

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/cablerobot/cablerobot_setup.jpg" title="the cable_robot configuration" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt- mt-md-0">
        {% include figure.liquid path="assets/img/research/cablerobot/cablerobot_lateral.jpg" title="lateral view" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 1.</b> The CableRobot Simulator. <b>Left</b>: a sketch of the setup.
    <b>Right</b>: lateral view of the simulator when operated.
</div>

The [CableRobot Simulator](https://www.cyberneum.de/CableRobotSimulator) is world's first motion simulator based on a cable-driven parallel robot developed in house at the [Max Planck Institute for Biological Cybernetics](https://www.kyb.tuebingen.mpg.de/en) in collaboration with [IPA Fraunhofer](https://www.ipa.fraunhofer.de/en.html). This robot uses a parallel platform, typical of the common hexapod simulators, but it uses cables and winches for actuation instead of rigid links. This approach allows to reduce significantly the moved mass and also to expand massively the workspace significantly (up to $$5\times 6 \times 4 m^3$$, with maximum roll, pitch and yaw angles of $$\pm40^\circ$$, $$\pm40^\circ$$, $$\pm5^\circ$$ respectively). In comparison to the CyberMotion Simulator, the parallel structure of the CableRobot Simulator allows to achieve higher accelerations ( up to $$14 m/s^2$$ at a payload of $$200 kg$$) and faster dynamics. Moreover, the use of cable grants greater flexibility, since the cables can be connected in different ways thus allowing to have different configurations in which the robot can be operated



<iframe width="560" height="315" src="https://www.youtube.com/embed/cJCsomGwdk0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


I contributed to the modelling of the system and to the development of control and tension distribution algorithms for it. One interesting study that we performed on this system was an investigation of the vibrations that occur at the cables for different values of pre-tension. This analysis is important because these vibrations injected in the system propagate to the moving platform and can disrupt the perception of the simulated motion. Using the setup shown in Fig. 2 and power spectral density analysis we measured the natural frequencies of the cable and compared these results to the frequencies predicted by two linear models: i) the linearization of partial differential equations of motion for a distributed cable, and ii) the discretization of the cable using a finite elements model. This comparison provides remarkable insights into the limits of approximated linear models as well as important properties of vibrating cables used in CDPR.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/cablerobot/vibration_setup.jpg" title="setup to study cable vibrations" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 2:</b> Setup used in <a href="https://www.researchgate.net/publication/313449830_Modeling_and_analysis_of_cable_vibrations_for_a_cable-driven_parallel_robot">"Modeling and analysis of cable vibrations for a cable-driven parallel robot"</a> to study cable vibrations.
</div>


---
<h2>Related Publications</h2>
<div class="publications">
  {% bibliography -f papers -q @*[keywords~=CableRobot simulator]* %}
</div> 