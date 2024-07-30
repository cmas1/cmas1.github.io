---
layout: page
title: HolorLib
description: A C++20 header-only library for generic multi-dimensional containers.
img: assets/img/software/holorlib/holorlib_cover.jpg
importance: 1
category: C++
related_publications: false
---


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/software/holorlib/holorlib_landing_page.jpg" title="HolorLib" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 1:</b> Landing page of the  <a href="https://cmas1.github.io/HolorLib/index.html">HolorLib</a> documentation website.
</div>


HolorLib is a C++ library (written using C++20 features) that implements generic multi-dimensional containers of homogeneus elements, i.e., all the elements must have the same type.
These **Holor containers** are objects with three fundamental components:
* they have access to a contiguous area of **memory** where the elements are stored. The container may own the memory (`Holor`) or not (`HolorRef`).
* a **layout** that contains the informaiton necessary to map from the multi-dimensional coordinate system of the container (indices) to the memory location that stores the value of the element.
* a set of **indexing and slicing operations** that allow to access individual elements of the container or slices.

<div class="row">
    <div class="col-sm">
        {% include figure.liquid path="assets/img/software/holorlib/holor.jpg" title="Holor container fundamentals" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Figure 2:</b> Fundamental components of Holor containers.
</div>



Using these containers is fairly easy, as the syntax is quit intuitive.

**Example 1: Holor**. Creating a container that owns the memory
{% highlight c++ linenos %}
#include <holor/holor_full.h>;
holor::Holor<int,2> A = { {1,2,3,4},{5,6,7,8},{9,10,11,12} }; // 3-by-4 matrix of integers
auto c = A(2,3); // indexing a single element. c has the value 8. 
auto B = A(holor::range(0,1), holor::range(2,3)); // Slicing a 2-by-2 matrix. B is a HolorRef that views the elements { {3,4}, {7,8} } of A
{% endhighlight %}


**Example 2: HolorRef**. Creating a container that does not own the memory
{% highlight c++ linenos %}
#include <holor/holor_full.h>
std::vector<int> my_sequence{1,2,3,4,5,6,7,8,9,10};
holor::HolorRef<int,2> matrix_view(my_sequence.data(), holor::Layout<2>{2,5}); //constructor passing a layout
{% endhighlight %}

For a full description of the functionalities of this library please refer to the official [documentation page](https://cmas1.github.io/HolorLib/index.html). 
