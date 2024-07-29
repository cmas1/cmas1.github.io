---
layout: page
title: Fine grained visual understanding
description: from patch-level to pixel-level details
img: assets/img/research/fine_grained_visual/cover.jpg
importance: 2
category: spatial intelligence
related_publications: false
---


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/fine_grained_visual/semserg_research_example.jpg" title="the task" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 1.</b> Example of semantic segmentation from an RGB image in a driving scenario Image from the <a href="https://www.cityscapes-dataset.com/">Cityscapes dataset</a>.
</div>

What is **spatial intelligence**? It may be defined as *"the ability to generate, retain, retrieve, and transform well-structured visual images"* (D. F. Lohman, Spatial ability and g, 1996) or, more broadly, *"human's computational capacity that provides the ability or mental skill to solve spatial problems of navigation, visualization of objects from different angles and space, faces or scenes recognition, or to notice fine details"* (H. Gardner).

Understanding the fine grained details in images (or other forms of sensing) is a form of spatial reasoning that is useful for many applications. It is a **spatial** reasoning because the informative content of a fraction of the image (from a patch to a single pixel) depend on the context given by its surrounding.
Me and my team have been working on the development of fine grained visual understanding algorithms for various use-cases, e.g., 
for **driving scenes**, **aerial imagery** and **industrial applications**.


##### Driving scenes
Understanding the fine details in images collected from cameras onboard vehicles is extremely important for the development of the perception stack of a autonomous/assisted car. It is also a challenging task, due to variations in scenery and weather/illumination conditions, the cost of labeling, etcetera. 
At [Vandal](http://vandal.polito.it/) we have been working on this topics, developing tools that can help support research, like the [IDDA dataset](https://idda-dataset.github.io/home/welcome/), which contains 105 different scenarios that differentiate for the weather condition, environment and point of view of the camera.
We have also developed several algorithms, with a focus on robustness across domains ([Pixel-by-Pixel Cross-Domain Alignment for Few-Shot Semantic Segmentation](https://arxiv.org/abs/2110.11650)) and capable to handle anomalies ([Mask2Anomaly: Mask Transformer for Universal Open-set Segmentation](https://ieeexplore.ieee.org/abstract/document/10574844)).

<div class="row justify-content-sm-center">
    <div class="col-sm-8">
        {% include figure.liquid path="assets/img/research/fine_grained_visual/idda_scenarios.jpg" title="IDDA scenarios" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4">
        {% include figure.liquid path="assets/img/research/fine_grained_visual/idda_modalities.jpg" title="IDDA modalities" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 2.</b> <a href="https://idda-dataset.github.io/home/welcome/">IDDA</a> offers 105 scenarios of driving scenes, with weather conditions, environments and points of view of the camera (on a car, jeep, mini van, ...). Each RGB images is accompanied by a semantic mask and depth image.
</div>

##### Aerial scenes
In aerial imagery there is a lot of fine detailed information that can be extremely valuable, e.g., to monitor urban development or support environmental monitoring. Unlike in driving scenes, where the street is always at the bottom and the sky on top, in aerial imagery the model cannot rely on a fixed semantic structure of the scene. Moreover, the the relative scale of different visual elements may be extremely different. 
We have developed solutions that address the domain shift problem in aerial segmentation and are tailored to address the specificities of these scenes.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/fine_grained_visual/aerial_augm_invariance.jpg" title="Augmentation invariance and adaptive sampling for aerial segmentation" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/fine_grained_visual/HiMix.jpg" title="Hierachical mixing for aerial images" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 3.</b>  Some of the solutions that we have developed specifically for aerial segmentation. Left: <a href="https://arxiv.org/abs/2204.07969">Augmentation Invariance and Adaptive Sampling in Semantic Segmentation of Agricultural Aerial Images</a>. Right: <a href="https://arxiv.org/abs/2210.06216">Hierarchical Instance Mixing Across Domains in Aerial Segmentation</a>.
</div>


---
<h2>Related Publications</h2>
<div class="publications">
  {% bibliography -f papers -q @*[keywords~=fine grained understanding]* %}
</div>