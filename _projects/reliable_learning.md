---
layout: page
title: Reliable machine learning
description: Sorry, the AI is out of order. Please call the technician.
img: assets/img/research/reliable_learning/cover.jpg
importance: 1
category: learning
related_publications: false
---


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/reliable_learning/flying_donkey.jpg" title="reliable learning" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 1.</b> When your deployed model meets unexpected working conditions...
</div>


When discussing machine learning and AI solutions for various applications, we should not only care about performance metrics, but also about the **reliability** of these systems.
Indeed, we want to have solutions that do not stop working when they are deployed and experience a distribution of data that does not correspond to the one experienced during training. Moreover, we want to have ways and metrics to reliably determine if a model is certain in its prediction or not, instead of considering only performance metrics. 


##### Learning across domains
The [Vandal](http://vandal.polito.it/) laboratory has a long experience working on topics related to domain adaptation and domain generalization. We have been devising solutions to make algorithmos more robust to domain shifts, e.g., for a self-driving car navigating in different environments/weather conditions (Figure 2).
You can check the related publications down below to see a few works where we make use of these techniques.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/reliable_learning/idda_domains.jpg" title="IDDA dataset" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/reliable_learning/adageo_svox.jpg" title="Samples from the SVOX dataset" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 2.</b> Left: <a href="https://ieeexplore.ieee.org/abstract/document/9336674">IDDA</a> multi-domain dataset for autonomous driving. Right: samples from the <a href="https://arxiv.org/abs/2010.06897">SVOX</a> dataset.
</div>



##### Uncertainty quantification and anomaly detection
Accurately predicting the outcome of real-world events using machine learning models requires a clear understanding of the model's confidence in its predictions. This is particularly critical in high-stakes domains like healthcare, where decisions are made based on these predictions. While machine learning models often excel at making accurate predictions, quantifying the uncertainty surrounding these predictions remains a significant challenge. To be useful, uncertainty estimates must reliably indicate the range of possible outcomes and differentiate between predictions made with high and low confidence.

Related to this concept is the task of **anomaly segmentation**, which aims to segmenting the anomaly patterns which deviate from the normal patterns. A possible application of such a technology is to identify defects on production lines.
One of our solutions, tailored for driving scenes, is [Mask2Anomaly](https://ieeexplore.ieee.org/abstract/document/10574844) a universal anomaly segmentation architecture that reasons about anomalies not in terms of individual pixels, but rather per masks.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/reliable_learning/mask2anomaly_idea.jpg" title="mask2anomaly" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/reliable_learning/mask2anomaly.gif" title="mask2anomaly in action" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 4.</b> <a href="https://ieeexplore.ieee.org/abstract/document/10574844">Mask2Anomaly</a> algorithm for anomaly segmentation.
</div>


---
<h2>Related Publications</h2>
<div class="publications">
  {% bibliography -f papers -q @*[keywords~=uncertainty quantification]*%}
  {% bibliography -f papers -q @*[keywords~=robust learning]*%}
  <!-- {% bibliography -f papers -q @*[keywords~=uncertainty]  -q @*[keywords~=robust learning]*%} -->
</div>