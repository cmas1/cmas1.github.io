---
layout: page
title: CyberMotion Simulator
description: a motion simulator based on an industrial robot arm
img: assets/img/research/cybermotion/cover.jpg
importance: 4
category: past
related_publications: false
---

The [CyberMotion Simulator](https://www.cyberneum.de/CyberMotionSimulator) is a motion simulator based on an anthropomorphic robot that was developed in house at the [Max Planck Institute for Biological Cybernetics](https://www.kyb.tuebingen.mpg.de/en). In comparison to the more common and widely available platforms based on a parallel hexapod, the serial structure of the robotic arm allows to have a much larger motion envelop, particularly for what concerns the rotations of the end-effector (i.e. the passenger seat). The idea of the motion simulator is the person onbord the platform guides a simulated vehicle (e.g. a car or a helicopter). The robot then should move according to the trajectory of the virtual vehicle. The goal is for the visual and vestibular feedbacks combined to reproduce **same sensation the person would have if they were riding the vehicle**. Note that the platform does not have to reproduce exacty the motion of the vehicle. Indeed, this is generally not possible since the robot has a limited motion envelop.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/cybermotion/cybermotion.jpg" title="shared control paradigm" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 1:</b> Different control paradigms for various levels of autonomy. Shared control lies between direct control, where the human manualy steers the robot, and supervisory control, where the robot autonomously executes the task while only receiving high-level directives from the operator. Image from my PhD dissertation, titled <a href="https://elib.uni-stuttgart.de/handle/11682/4606">Planning and control for robotic tasks with a human-in-the-loop</a>.
</div>

I have participated to the development of the control and motion planning algorithm for this simulator during my M.sc. thesis and at the beginning of my Ph.D. Since the robot has a very limited translational workspace, it cannot reproduce the sustained translational movements typical of many vehicles (e.g. a car driving on a road). Thus, to reproduce the same sensation we resort to motion cueing algorithms, using in particular *washout filters* to reproduce high-frequency motions, and tilt-coordination algorithms to reproduce the low-frequency components.
The intuition is that the high-frequency component is reproduced by actually moving the motion platform, since this component will in general generate small (thus feasible) displacements. On the other hand, the low-frequency component, comprehensive of sustained linear accelerations, is not achieved by physically accelerating the platform, but by exploiting the local gravity vector as a source of ‘persistent’ acceleration.
The motion cuieing algorithm that we developed used a polar coordinate system to make it better fit the capability of the robot to achieve large rotations around its first joint.


<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/cybermotion/cybermotion_kin.jpg" title="the robot" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt- mt-md-0">
        {% include figure.liquid path="assets/img/research/cybermotion/F1_sim.jpg" title="me inside the cabin" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 2.</b> <b>Left</b>: a lateral view of the robot.
    <b>Right</b>: me inside the cabin, testing the control and motion cueing algorithm on a simulated F1 car.
</div>


<iframe width="560" height="315" src="https://www.youtube.com/embed/-Q8YDPnJqdM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



Another part of my work was modelling the novel 7-th joint that was integrated with the cabin. The joint has a complex behaviour, because it is composed by a rail with straight and curve components. This leads to a switching behaviour that, depending on the state of the joint, can produce translations, rotations or a combination of both.
<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/cybermotion/cabin.jpg" title="the novel actuated cabin" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt- mt-md-0">
        {% include figure.liquid path="assets/img/research/cybermotion/cabin_model.jpg" title="kinematics of the cabin" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 2.</b> Images from the novel actuated cabin that was designed and developed for the CyberMotion Simulator. Left: Details of the cabin. Right: a simplified view of the joint motion of the cabin.
</div>


---
<h2>Related Publications</h2>
<div class="publications">
  {% bibliography -f papers -q @*[keywords~=CyberMotion simulator]* %}
</div> 