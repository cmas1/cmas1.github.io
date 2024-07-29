---
layout: page
title: Distributed learning
description: (Learn) One for all, and all for one.
img: assets/img/research/distributed/cover.jpg
importance: 2
category: learning
related_publications: false
---


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/distributed/distributed_idea.jpg" title="learning together" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 1.</b> Learn one for all, and learn all for one. Image credits to Marvin Meyer <a href="https://unsplash.com/photos/people-sitting-down-near-table-with-assorted-laptop-computers-SYTO3xs06fU">Marvin Meyer</a>.
</div>

In many technological fields, from engineering to computer science, there is an effort to move from centralized solutions, where there is a single system that owns the data, reasons and acts to solve a problem, towards decentralized solutions, where the task is aplit across multiple systems.
This is also the case for machine learning. The term **Distributed Machine Learning** refers to the idea of distributing the process of learning from the data across multiple nodes (physical or virtual).
There are a lot of nuances to this idea, for example in the nature of the nodes, their location, if they are heterogenous or not, if the serve the same function or not, in the location of the data and whether it can be shared or not, in the goal of the learning procedure (learn a single model, learn personalized models), if the system aims to speed up the training, etcetera.

In [Vandal](http://vandal.polito.it/) there are a few researchers working on this topic, and I have been collaborating on a few projects.

##### Federated learning
**Federated learning** (also known as collaborative learning) is a sub-field the wider field of distributed machine learning focusing on settings in which multiple entities (often referred to as clients) collaboratively train a model while ensuring that their data remains decentralized (for example due to privacy constraints). The clients may also have limited computational power and availability to participate to the training.
One of the primary defining characteristics of federated learning is data heterogeneity. Due to the decentralized nature of the clients' data, there is no guarantee that data samples held by each client are independently and identically distributed.

We are working on solutions that try to address the problem of data heterogeneity, to improve the model convergence and final model quality while being efficient in terms of communication with the aggregation server.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/distributed/fedhbm_results.jpg" title="FedHBM" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 2.</b> Results obtained with our <a href="http://arxiv.org/abs/2404.13324">FedHBM and GHBM</a> methods.
</div>


We have also worked on new applications for federated learning. In fact, many solutions developed for federated learning are tested and validated for image classification tasks and on small datasets and models.
We have also proposed the first (to the best of our knowledge) application of **federated learning for image retrieval**, and more specifically to a visual geo-localization problem (where ther ecould be multiple robots/vehicles around the world collecting navigation data).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/distributed/fedvpr_training.jpg" title="Federated Visual Place Recognition" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 3.</b> Sketch of the training procedure for  <a href="http://arxiv.org/abs/2404.13324">Federated Visual Place Recognition</a>.
</div>

##### Training parallelization
Recent breakthroughs enabled by deep learning rely on increasingly complex architectures: the advent of Large Language Models (LLMs) has marked a new chapter for conversational agents like ChatGPT, but also introduced real challenges in training and serving such solutions for real-world applications. Therefore, scaling data and computing power are crucial for successful training, but speed-up scaling laws are not going to cope forever with the limits of current algorithms and architectures. 

We have been working on some projects related the parallelization and distribution of the training of these algorithm, in order to allow better scalability. One aspects that we have worked on, for the spcific application of visual place recognition, is on how to leverage a smarter data partition in order to improve and speed up the training (see Figure 4).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/distributed/dCosplace.jpg" title="Distributed CosPlace" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 4.</b> Sketch of the  <a href="http://arxiv.org/abs/2404.13324">Distributed CosPlace</a> algorithm for visual place recognition.
</div>


---
<h2>Related Publications</h2>
<div class="publications">
  {% bibliography -f papers -q @*[keywords~=distributed learning]* %}
</div>