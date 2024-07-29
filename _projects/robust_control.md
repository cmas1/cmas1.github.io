---
layout: page
title: Robust Control of Robotic Platforms
description: sliding mode controllers for robotic platforms
img: assets/img/research/robust_control/cover.jpg
importance: 4
category: past
related_publications: false
---

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/robust_control/ASTC_CDPR.jpg" title="ASTC applied to a CDPR" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/robust_control/ASTC_UAV.jpg" title="ASTC applied to a UAV" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 1.</b> We developed and applied the Adaptive Super Twisting Controller method both to cable-driven parallel robots (left) and to UAVs (right).
</div>



During my time at the Max Planck Institute for Biological Cybernetics I worked on the application of sliding mode controllers, and particularly of the Adaptive Super Twisting Controller from [Shtessel et al. (2012)](https://www.sciencedirect.com/science/article/pii/S0005109812000751), both to cable-driven parallel robots and UAVs. What is remarkable about this method is that:
* it considers all the uncertainties (parametric, model,disturbances) lumped together;
* it does not require the knowledge of the upper bound ofthe uncertainties;
* rather than adapting the parameters of the model, it adapts the gains;
* it uses a feedforward dynamic inversion (FF) to reduce the discontinuous control, thus improving performance and further reducing chattering.



<div class="row justify-content-sm-center">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/robust_control/ASTC_uav_plot1.jpg" title="ASTC_UAV" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/robust_control/ASTC_uav_plot2.jpg" title="ASTC_UAV" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/robust_control/ASTC_uav_plot3.jpg" title="ASTC_UAV" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 2.</b> Results from the application of an Adaptive Super Twisting controller to an UAV. The plots show that the controller is able to quickly react to unforeseen external disturbances.
</div>

<iframe width="560" height="315" src="https://www.youtube.com/embed/i1aUyPCtqiY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



---
<h2>Related Publications</h2>
<div class="publications">
  {% bibliography -f papers -q @*[keywords~=robust control]* %}
</div> 