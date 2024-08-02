---
layout: page
title: Anomaly segmentation in driving scenes.
description: A new benchmark and evaluation.
img: assets/img/theses/dataset_uncertainty_carla/cover.jpg
importance: 1
category: active
related_publications: false
---

#### Supervision
The thesis will be supervised by and performed with the Visual and Multimodal lab ([VANDAL](https://vandal.polito.it/)) @ Politecnico di Torino. The VANDAL lab is an excellence research lab for Machine Learning and Computer Vision, both for theoretical and application-driven problems (e.g., in Robotics, Industry 4.0+, Autonomous Driving, etc.). VANDAL is part of the European Laboratory for Learning and Intelligent Systems ([ELLIS](https://ellis.eu/)), a European Network of the top research institutions in AI.

#### Guidance and contacts
* **Carlo Masone**: carlo.masone@polito.it  
* **Tatiana Tommasi**: tatiana.tommasi@polito.it

#### Number of Positions
**Up to 3 students**.

#### Context
In recent years the automotive industry has been heavily investing in AI, causing a profound shift in the future of automobiles. Considering the complexity of driving environments, where there is a multitude of scenes and unpredictable dynamic elements, model-based approaches inevitably are not enough, and data-driven solution hold the promise of enabling a new breed of algorithms that can increase the safety and autonomy of vehicles.

Perception, and more specifically understanding the intricacies of the scene surrounding the vehicle only using its onboard sensors, is one of the most difficult tasks, one with many open problems and room for improvements. To develop more advanced assistive functionalities and even future autonomous vehicles, we must be able to finely detect, classify and localize all the elements in the vehicle’s surroundings. That is the reason why segmentation approaches are widely researched and developed for driving applications, and some of the most notorious open-source semantic segmentation datasets come from this application domain (e.g., Cityscapes [1], BDD100K [2], Indian Driving Dataset [3], ApolloScape [4], …).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/theses/dataset_uncertainty_carla/semseg_examples.jpg" title="examples of semantic segmentation in driving scenes" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 1.</b> Examples of semantic segmentation from Cityscapes, BDD100k, Indian Driving Simulator.
</div>

The ability to finely segment and comprehend the vehicle surroundings is critical to identify driveable spaces, static and dynamic agents, and ultimately it is a step that is essential to create a local map of the vehicle which can be used for maneuver and motion planning. Yet, considering the safety critical nature of the application, these segmentation algorithms must be judged not only by the accuracy of their predictions, but also by the degree of certainty of those predictions and their capability to identify anomalies.


**Anomaly segmentation** is the term that denotes the task of precisely (pixel-wise) segmenting anomalies, i.e., patterns and elements which deviate from the normality. This is an important focus in research and driving applications, as demonstrated by the numerous recent publications [5-8] and workshops/events organized at the major conferences with industrial sponsorships [9-10].


#### Goal
Currently, there are few benchmarks available specifically for anomaly segmentation in driving scenes: FishyScapes, SegmentMeIfYouCan (SMIYC) and RoadAnomaly.
These datasets contain real or synthetic images collected from a monocular camera and generally represent anomalies/obstacles as new (i.e., unseen during training) things on the road. Yet, there are a few problems with these benchmarks:
* They have a narrow concept of what an anomaly is. Namely, they consider as anomalies new objects unseen during training, mostly placed on the street. Yet, the notion of anomaly is more general, as something that is not in the normal way of operation. For example, an anomaly could also be an instance of an object category seen during training, but in a strange configuration (e.g., a fallen tree).
* Since anomalies in these benchmarks are new classes, most anomaly segmentation methods at the top of these leaderboards are fine-tuned with supervision obtained by artificially pasting new objects on the training data and using them as anomalies. Yet, we would like to go towards unsupervised solutions that simply rely on the notion of something that goes beyond the normality.
* They have a single modality (RGB camera) and do not really allow to explore different sensor modalities (e.g., point-cloud, depth, …).
* They do not consider temporal information, whereas cars they acquire continuous streams of data.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/theses/dataset_uncertainty_carla/anomaly_segmentation_example.jpg" title="examples of anomalies from SegmentMeIfYouCan" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 2.</b> Examples of anomalies from the <a href="https://segmentmeifyoucan.com/">SegmentMeIfYouCan</a> benchmark.
</div>

The goal of this thesis is to address these limitations, by creating a new dataset and benchmark that is more representative of general anomalies and that contains data from multiple sensor modalities. The datasets will be created using the open source CARLA simulator and it will be used to test existing methods, to gain new insights on their limitations and to go towards purely unsupervised solutions.

#### Methodology

The plan is to use the open-source simulator [CARLA](https://carla.org//). This is the most notorious open-source driving simulator available, and it constantly used as a test bench for challenges at the top conferences in computer vision, robotics and artificial intelligence (e.g., at [CVPR 2024](https://opendrivelab.com/challenge2024/#carla) ).
The simulator itself builds upon the Unreal engine (currently the version 4.0, but they are upgrading to the 5.0 version), which allows to have high quality graphics and realistic dynamics.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/theses/dataset_uncertainty_carla/screenshots_carla.jpg" title="screenshots from the CARLA simulator" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Screenshots from the <a href="https://carla.org//">CARLA</a> simulator.
</div>

The simulator provides several functionalities and assets already implemented, including maps, vehicles and pedestrian agents, sensors (cameras, lidars, radars, event cameras), the ability to change weather conditions and many other parameters in the simulation. A python API allows to easily interact with the simulation.

The first and major part of the thesis will be devoted to the creation of the dataset. This implies not only using the Python scripts already packaged with CARLA, but it will require modification of the underlying Unreal scenes, to insert anomalies.
The second part of the thesis will involve testing a variety of segmentation algorithms available in literature on the newly collected data. In particular, we aim to have at least algorithms working with RGB images and algorithm for point-clouds. If more students select this thesis at the same time, they are expected to work together on the dataset creation and perhaps differentiate their works by testing different algorithms or by focusing on different aspects (e.g., different sensor modalities or different weather/illumination conditions).

_**The dataset and benchmark have the potential to become a publication and impact this field of research, which is potentially of interest to companies as well.**_

#### References
[1] M. Cordts et al., “The Cityscapes Dataset for Semantic Urban Scene Understanding”, IEEE/CVF CVPR 2016 

[2] F. Yu et al., “BDD100K: A Diverse Driving Dataset for Heterogeneous Multitask Learning”, IEEE/CVF CVPR 2020 

[3] C. Parikh et al., “IDD-X: A Multi-View Dataset for Ego-relative Important Object Localization and Explanation in Dense and Unstructured Traffic”, IEEE ICRA 2024 

[4] X. Huang et al., “The ApolloScape Open Dataset for Autonomous Driving and its Application”, IEEE T-PAMI 2020 

[5] S. Nandan Rai et al., “Mask2Anomaly: Mask Transformer for Universal Open-set Segmentation”, IEEE T-PAMI 2024 

[6] N. Nayal et al., “RbA: Segmenting unknown regions rejected by all”, IEEE/CVF ICCV 2023 

[7] J. Ackermann et al., “Maskomaly: Zeroshot mask anomaly segmentation”, BMVC 2023 

[8] M. Grcic et al., “On advantages of mask-level recognition for outlier-aware segmentation”, IEEE/CVF ICCV-W 2023 

[9] [ROAM: Robust, Out-of-Distribution And Multi-Modal models for Autonomous Driving](https://sites.google.com/view/roameccv2024/), ECCV 2024 

[10] [ROAD++: The Third Workshop & Challenge: Event Detection for Situation Awareness in Autonomous Driving](https://sites.google.com/view/road-eccv2024/home ), ECCV 2024

[11] H. Blum et al., [The Fishyscapes Benchmark: Measuring Blind Spots in Semantic Segmentation](https://fishyscapes.com/ ), IJCV 2021 

[12] R. Chan et al., [SegmentMeIfYouCan: A Benchmark for Anomaly Segmentation](https://segmentmeifyoucan.com/ ), NeurIPS 2021

[13] K. Lis et al., “Detecting the Unexpected via Image Resynthesis”, IEEE/CVF ICCV 2019