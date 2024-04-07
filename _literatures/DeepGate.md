---
layout: page
title: DeepGate
description: Extract features from graph-based netlist.
# img: assets/img/data_structure.jpg
importance: 1
category: Netlist
---

### About
- PDF Link:  <a href="https://dl.acm.org/doi/pdf/10.1145/3489517.3530497">here</a>
- Authors: Min Li, Sadaf Khan, Qiang Xu
- Lab: CURE Lab of CUHK

### Innovative Designs
- Represent a netlist as an **and-inverter directed acyclic graph**.
- Use **logic-simulated probabilities** (the probability of being logic '1') as the supervision metrics.
- Propose a novel GNN including **attention mechanisms** and **reversed propagation layers**.
- Add direct edges between the fan-out node and the reconvergence node (skip connection) to solve the **reconvergence problem**.

### Diagram
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/literatures/deepgate_schematic.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Diagram of the whole training process of DeepGate
</div>