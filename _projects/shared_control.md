---
layout: page
title: Shared Control and Planning of UAVs
description: control and planning algorithms for UAVs, whose execution is interfaced with a human operator.
img: assets/img/research/shared_control/cover.jpg
importance: 2
category: past
related_publications: false
---

An autonomous robot is a robot that is capable to act and perform its task without any supervision from humans or other agents. What are the capabilitis that the robot needs to be autonomous depends on the task it must perform and the context. In general, the most restricted and structured the environment, the easier it is to achieve autonomy. However, achieving autonomy at large, for complex tasks and in very dynamic and unpredictable environments is extremely challenging. For this reason, this endeavour come in incremental steps, commonly called levels of autonomy. 
The levels of autonomy were defined by [Sheridan and Verplanck (1978)](https://apps.dtic.mil/sti/pdfs/ADA057655.pdf) in the context of human-computer interactions. These levels mark a scale in which at one extreme the human executes the task and at the other extreme the computer does the job alone.
This concepts translates to robotics, where at the lowest level of autonomy a robot is directly maneuvered by a human who acts as a pilot (*direct control*), whereas at the highest level of autonomy the robot is fully autonomous and the human operator may only be present for supervision (*supervisory control*).
In between these two extremes, lies the **shared control** paradigm, in which the intelligence governing the execution of the task comes from a co-participation of a human and some automatic algorithm.
Shared control is a promising compromise to enable operation of robots in situations that are still far too complex for full autonomy. One such instance is the application to UAVs in unrestricted environments, where besides the complexity of the system there are may also be mandates from the regulator that impose the presence of a human teleoperator to either pilot the robot or supervise it being ready to take over control in critical situations.
At the [Max Planck Institute for Biological Cybernetics](https://www.kyb.tuebingen.mpg.de/en) I researched shared control solutions for several tasks with UAVs. In particular, I developed various **blending functions** to combine the different control inputs provided by the two systems --human operator and automatic control algorithm-- so that they do not interfere with each other.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/shared_control/shared_control.jpg" title="levels of autonomy in robotics control" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 1</b> Different control paradigms for various levels of autonomy. Shared control lies between direct control, where the human manualy steers the robot, and supervisory control, where the robot autonomously executes the task while only receiving high-level directives from the operator. Image from my PhD dissertation, titled <a href="http://dx.doi.org/10.18419/opus-4589">Planning and control for robotic tasks with a human-in-the-loop</a>.
</div>


### Shared control of a formation of UAVs
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/shared_control/shared_bearing_formation_concept.jpg" title="shared control paradigm" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 2.</b> Shared control framework for a formation of UAVs defined in terms of their relative bearings. Image from the PhD dissertation, titled <a href="http://dx.doi.org/10.18419/opus-4589">Planning and control for robotic tasks with a human-in-the-loop</a>.
</div>

In this research I investigated the problem f developing a shared control solution that would allow a single user to steer a formation of UAVs defined in terms of their relative bearing angles. The goal of this solution is to make the interface for the user easy, while guaranteeing asymptotic stability of the formation. The proposed solution was developed on the idea of splitting the task int two orthogonal components:
* Control the relative bearing angles among the UAVs to achieve and maintain the desired formation. 
* Control the motions of the UAVs that are in the orthogonal space to the formation, i.e. that do not alter the relaive bearing angles.

Based on this intuition, the proposed solutio npartitions the commands to the UAVs such that the automatic formation control algorithms regulates the relative bearing angles, whereas the human operator steers the free motions that do not alter the formation. The two orthogonal control inputs can thus be added together to provide the overal control input.
Figure 4-left shows what are the motions that are orthogonal to the bearing formation and that are controlled by the human operator. Figure 4-right shows the experimental setup with a 3-UAVs formation.


<div class="row justify-content-sm-center">
    <div class="col-sm-7 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/shared_control/bearing_invariant_motions.jpg" title="bearing invariant motions for a formation of UAVs" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/shared_control/shared_control_bearing_formation.jpg" title="shared control of a formation of UAVs defined by bearing" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 3.</b> Left: bearing invariant motions for a bearing formation with three agents. Right: Experiments with a formation with 3 UAVs.
    Images from the PhD dissertation titled <a href="http://dx.doi.org/10.18419/opus-4589">Planning and control for robotic tasks with a human-in-the-loop</a>.
</div>

<iframe width="560" height="315" src="https://www.youtube.com/embed/fWnz2Pc464E" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

I have also applied the paradigm of shared control to the case study of a formation of UAVs transporting a payload suspended by cables (see Fig. 4). In this case study the operator is in charge of steering the payload, without having to worry about controlling the individual UAVs. The shared control algorithm implements filtering techniques to generate a smooth reference trajectory for the system and to ensure that the formation does not reach a singular configuration. A geometric decomposition of the motions of the formation brings to light a series of internal motions (motions that do not change the formation) that are used for auxiliary tasks controlled either by the human (formation shrinking/expanding) or by an algorithm (formation control). The loop with the user is closed via a suitable force feedback.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/shared_control/shared_control_transport.jpg" title="shared control transportation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 4.</b> Shared control framework for the cooperative transportation of a cable suspended payload. Image from <a href="https://link.springer.com/content/pdf/10.1007/s10846-021-01457-4.pdf">Shared Control of an Aerial Cooperative Transportation System with a Cable-suspended Payload</a>.
</div>






### Shared planning for a single UAV
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/shared_control/shared_planning_concept.jpg" title="shared planning paradigm" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 5.</b> Shared planning framework for a single UAV. Image from the PhD dissertation, titled <a href="http://dx.doi.org/10.18419/opus-4589">Planning and control for robotic tasks with a human-in-the-loop</a>.
</div>

A shared control framework as the one described above effectively reduces the burden required to the human operator, who does not need to control that the formation is maintained but must only steer the collective group of robots. However, if the operator must still provide commands to the robots at all times, because without his/her input the robot won't move.
The idea of shared planning is to move the action of the person to a higher level in the navigation stack, placing him/her in charge of modifying a planned trajectory for the robot, rather than controlling the movement of the robot itself. This way, the robot will still move according the the current planned trajectory even when the operator provides no inputs.

In the spirit of sharing the planning effort, much like in the shared control, part of the trajectory modification is deputed to an automatic algorithm that is in charge of guaranteeing that the planned path has some properties, i.e. that it does not cross obstacles, that it has some geometric regularity and that it automatically passes through points of interest. This is achieved using artificial forces that are applied on the path, which is modeled as a B-spline. 
However, online modifications of the planend path may cause it to move away from the robot and result in a discontinuity in the tracking error. Thus, the proposed blending function is implemented via a null-space projection operator that imposes the invariance of the local geometric properties of the path at the current location of the robot regardless of the global changes brought by human and automatic inputs.


<div class="row justify-content-sm-center">
    <div class="col-sm-7 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/shared_control/null_space_blending.jpg" title="null space blending" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/shared_control/path_obstacle_avoidance.jpg" title="path obstacle avoidance" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 6.</b> Left: blending function based on the null-space projection, which preserves the local geometric properties of the path at the location of the robot. Right: example of the effect of the obstacle avoidance on the path.
    Images from the PhD dissertation titled <a href="http://dx.doi.org/10.18419/opus-4589">Planning and control for robotic tasks with a human-in-the-loop</a>.
</div>


The shared planning framework was demonstrated with physical experiments, as shown in Fig. 7.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/shared_control/shared_planning_exp.jpg" title="shared planning experiment" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 7.</b> Shared planning experiment. Image from the PhD dissertation, titled <a href="http://dx.doi.org/10.18419/opus-4589">Planning and control for robotic tasks with a human-in-the-loop</a>.
</div>

<iframe width="560" height="315" src="https://www.youtube.com/embed/ie5cvMFObbY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>




---
<h2>Related Publications</h2>
<div class="publications">
  {% bibliography -f papers -q @*[keywords~=shared control]* %}
</div>