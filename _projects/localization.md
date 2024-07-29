---
layout: page
title: Localization
description: Where am I? Where is everything else?
img: assets/img/research/localization/cover.jpg
importance: 1
category: spatial intelligence
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/localization/localization_cover.jpg" title="localization and spatial intelligence" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 1.</b> (Vision-based) localization is an important part of spatial intelligence. Photo credits to <a href="https://unsplash.com/photos/world-map-poster-9-xfYKAI6ZI">Tabea Schimpf</a>.
</div>

What is **spatial intelligence**? It may be defined as *"the ability to generate, retain, retrieve, and transform well-structured visual images"* (D. F. Lohman, Spatial ability and g, 1996) or, more broadly, *"human's computational capacity that provides the ability or mental skill to solve spatial problems of navigation, visualization of objects from different angles and space, faces or scenes recognition, or to notice fine details"* (H. Gardner).

**(Vision-based) Localization**, i.e., the ability to place a visual (or multimodal) observation in space, or rather a suitable representation of space, is an important ingredient of spatial intelligence. This kind of reasoning is well developed and studied in humans. For example, when looking at the picture of a famous landmark, we can easily recognize it and infer where that picture was taken. In our daily routine, when we go around we are collecting observations of the space around us and we organize them in a *cognitive map*, a unified representation of the spatial environment that we can access both to support memory (e.g., to relate past observations with respect to each other and with respect to new observations) and to guide our future actions (e.g., when we mentally plan a route to a destination).
Me and my team and colleagues in [VANDAL](http://vandal.polito.it/) are working on creating new and better algorithms that can provide this kind of reasoning, which is critical to develop applications that require advanced interactions with the world. For example, to enable autonomous navigation of robots and vehicles, to create more convincing and immersive augmented/extended reality applications, to make smarter personal assistive devices, etcetera.

Although it is only a part of spatial resoning, the research field of (vision-based) localization itself is very broad. The kind of reasoning that can be achieved may depend on how we represent the space (e.g., as an unordered collection of images, as a sparse point-cloud, as a dense 3D map, ...). We may even not have a prior representation of the world, in which case we may seek to deduce the location of an observation relative to another one, without placing it in a map. The goals may also vary depending on the task we need to solve: we may be interested in coarsely predicting the geographical location of an observation (**Visual Place Recognition** or **Visual Geo-localization**); we may want to estimate the precise pose of the sensor that captured that observation (**Visual Localization**); we may want to recognize a place/object, irrespectively of the point from where we observe it (**Landmark Recognition**); we may want to refine a pose estimate (**Pose refinement**); we may try to establish correspondences between two different observations (**Image Matching**); and many more.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/localization/geoloc_1.jpg" title="the task" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 2.</b> "Where is this place?" Example of Visual Place Recognition, where we try to predicting the coarse location where the image was taken with respect to a map.
</div>


### What are we working on?
We have been working largely on Visual Place Recognition problems, which is often taken as a first step in hierarchical localization pipelines.
You may check [A Survey on Deep Visual Place Recognition](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9336674) and 
[Deep Visual Geo-localization Benchmark](http://arxiv.org/abs/2204.03444) for an overview on this task.

We have been particularly interested in making these algorithms robust and scalable.
##### Robustness 
One of the biggest challenges in visual geolocalization is the fact that the same place viewed at different times, in different weather conditions,  and from slightly different angles may look substantially different. Making a visual geolocalization system robust to these variations and achieve good performance across different conditions and in presence of distractors or occlusions is a major topic of research. 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/localization/adageo_svox.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-3 mt- mt-md-0">
        {% include figure.liquid path="assets/img/research/localization/vg_viewpoint_shift.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 3.</b> <b>Left</b>: The appearance of a place naturally changes in different weather conditions, seasons and due to day/night cycles. Image from <a href="https://openaccess.thecvf.com/content/WACV2021/html/Berton_Adaptive-Attentive_Geolocalization_From_Few_Queries_A_Hybrid_Approach_WACV_2021_paper.html">Adaptive-Attentive Geolocalization from few queries: a hybrid approach</a>.
    <b>Right</b>: A place viewed from from slightly different observation points may appear difficult to recognize. Image from <a href="https://arxiv.org/abs/2109.09827">Viewpoint Invariant Dense Matching for Visual Geolocalization</a>.
</div>

##### Scalability
 Until recent, visual geolocalization research has focused on recognizing the location of images in moderately sized geographical areas, such as a neighborhood or a single route in a city. However, to empower the promised real-world applications of this technology, such as enabling the navigation of autonomous agents, it is ecessary to scale this task to much wider areas with databases of spatially-densely sampled images.
The question of scalability in visual geolocalization system not only demands for larger datasets, but it the problems of how to make the deployed system scalable at test time on a limited budget of memory and computational time.


<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/localization/cosplace_expl.jpg" title="CosPlace" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
<b>Figure 4.</b> In CosPlace we use a classification task as a proxy to train the model that is used to extract the global descriptors for retrieving images from the same place as the query to geo-localize. For this purpose, naively dividing the environment in cells (<b>left image</b>) and using these cells as classes is not effective because i) images from adjaccent cells may see the same scene and thus be from the same place, and ii) the number of classes required to cover a large space will grow quickly. To solve these issues, CosPlace proposes a division of the space in sub-datasets (the slices with different colors in the <b>image on the right</b>), and the training iterates through the different sub-datasets, replacing the classification head.
Images from <a href="https://arxiv.org/abs/2204.02287">Rethinking Visual Geo-localization for Large Scale Applications</a>.
</div>

##### Using different 3D representations
One of the key questions in localization, when using a 3D representation of the known world (map), is what kind of representation to use? What are the advantages and disadvantages of different representations.
We are exploring different solutions, particularly trying to aim for scalable approaches.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/localization/berlin_animation.gif" title="Visual geo-loclization using a 3D mesh" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 5.</b> <a href="https://meshvpr.github.io/">MeshVPR</a> Citywide Visual Place Recognition Using 3D Meshes.
</div>

##### Robotics application
Classical Visual Place Recognition methods have been devised to localize a single query image at a time, but a robot navigating would collect a continuous stream of images from a camera. 
Thus, we seek new solutions that can also exploit the temporal information in this stream to reason about the location. An idea that we have explored is to to use sequential descriptors that summarize sequences as a whole, thus enabling to directly perform a sequence-to-sequence similarity search (see Figure 5). This idea is alluring, not only for its efficiency but also because a sequential descriptor naturally incorporates the temproal information from the sequence, which provides more robustness to high-confidence false matches than single image descriptors.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/localization/seqDesc.jpg" title="Sequential Descriptors" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
<b>Figure 6.</b> (Top) Sequence matching individually processes each frame in the sequences to extract single-image descriptors. The frame-to-frame similarity
scores build a matrix, and the best matching sequence is determined by aggregating the scores in the matrix. (Bottom) With sequential descriptors,
each sequence is mapped to a learned descriptor, and the best matching sequence is directly determined by measuring the sequence-to-sequence
similarity Images from <a href="https://arxiv.org/abs/2207.03868">Learning Sequential Descriptors for Sequence-Based Visual Place Recognition</a>.
</div>

##### Image matching
The ability to match and find correspondances between images is a cornerstone for vision based localization solutions. We have been working to understand how different image matching techniques work in different conditions, theyr advantages and shortcomings, but also to develop new keypoint detection/description strategies that are independent of scale by leveraging Morse theory and persistent homology, powerful tools rooted in algebraic topology.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/research/localization/persistent_keypoints.jpg" title="topological feature" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 7.</b> The evolution of the sub-level sets of a surface filtered by height, i.e. value on the z axis. As the height crosses z1, a new loop is born in correspondence with a saddle (green point), then the loop changes smoothly until z hits z2, the value of a corresponding maximum (blue point), and the loop disappears. z1 and z2 are, respectively, the topological feature’s birth time and death time. <a href="https://arxiv.org/abs/2406.01315">Scale-Free Image Keypoints Using Differentiable Persistent Homology</a>.
</div>

##### Lost in Space?
Yes, we have also worked on the problem of localizing observations taken from space. In fact, it is little known that astronauts on the International Space Station take thousands of photos each month, which are used for disaster management, climate change studies, and other earth science research. However, before a photo can be used, it must be localized: this was historically done manually, in a task that NASA defines as "monumentally important, but monumentally time-consuming job".
We provided tools to automatize this process.
<div class="row">
    <div class="col-sm-6 mt- mt-md-0">
        {% include figure.liquid path="assets/img/research/localization/earthloc_animation.gif" title="pipeline for localization of astronaut photography" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt- mt-md-0">
        {% include figure.liquid path="assets/img/research/localization/earthmatch_animation.gif" title="pipeline for localization of astronaut photography" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 8.</b> <a href="https://earthloc-and-earthmatch.github.io/">EarthLoc + EarthMatch</a> pipeline, to localize photos taken from the ISS.
</div>

##### And many more things
We are working on many other things related to the problem of localization and, more in general, mapping observations to a spatial representation. Please check teh related publications down below for a more complete overview.


---
<h2>Related Publications</h2>
<div class="publications">
  {% bibliography -f papers -q @*[keywords~=localization]* %}
</div>