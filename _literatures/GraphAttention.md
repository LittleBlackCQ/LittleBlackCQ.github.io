---
layout: page
title: Graph Attention Networks
description: Attention-like method to compute correlation between nodes.
# img: assets/img/data_structure.jpg
importance: 2
category: Graph
---

### About
- PDF Link:  <a href="https://arxiv.org/pdf/1710.10903.pdf">here</a>
- Authors: Petar Velickovic, Guillen Cucurull
- Institute: University of Cambridge

### Innovative Designs
- Simply caculate the coefficient between a node with its neighboring nodes, and assign the weighted linear combination of the neighboring nodes to obtain the feature of the node for next iteration.

- Use a **parametrized matrix** to convert a node feature to a high-level attentionable feature (much like the $$W_{query}$$, $$W_{value}$$ in Transformer). Use a **parametrized vector** to convert concatenated features of two nodes to the edge weight between them.

- Use **multi-head attention (multiple $$W$$)** and simply concatenated or averaged the features of the next layer.

### Diagram
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/literatures/graph_attention_network.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Diagram of Graph Attention Networks
</div>