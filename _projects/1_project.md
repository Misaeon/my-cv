---
layout: page
title: project 1
description: with background image
img: assets/img/12.jpg
importance: 1
category: Past
related_publications: true
---

<ul class="nav nav-tabs" id="projectTabs" role="tablist">
  <li class="nav-item">
    <a class="nav-link active" id="desc-tab" data-toggle="tab" href="#description" role="tab">
      Description
    </a>
  </li>
</ul>

<div class="tab-content mt-3">
<div class="tab-pane fade show active" id="description" role="tabpanel">

<h3>Project Overview</h3>

<p>
IAQ4EDU platform for indoor air quality education and monitoring.
Below is a live project preview.
</p>

<!-- ========================= -->
<!-- Fake Browser Preview -->
<!-- ========================= -->

<a href="https://iaq4edu.upc.edu/en" target="_blank" style="text-decoration:none;">

<div style="
border:1px solid #ddd;
border-radius:10px;
overflow:hidden;
box-shadow:0 6px 18px rgba(0,0,0,0.08);
">

  <!-- fake browser bar -->
  <div style="
  background:#f5f5f5;
  padding:8px 12px;
  display:flex;
  align-items:center;
  font-size:14px;
  color:#666;
  ">

    <div style="display:flex; gap:6px; margin-right:10px;">
      <span style="width:10px;height:10px;background:#ff5f56;border-radius:50%;display:inline-block;"></span>
      <span style="width:10px;height:10px;background:#ffbd2e;border-radius:50%;display:inline-block;"></span>
      <span style="width:10px;height:10px;background:#27c93f;border-radius:50%;display:inline-block;"></span>
    </div>

    https://iaq4edu.upc.edu/en
  </div>

  <!-- preview image -->
  {% include figure.liquid
      path="assets/img/12.jpg"
      class="img-fluid"
      loading="eager"
  %}

</div>

</a>

<p style="margin-top:10px; font-size:14px; color:#666;">
Click to open the live website in a new tab.
</p>

</div>
</div>
