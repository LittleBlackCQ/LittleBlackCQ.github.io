---
layout: page
title: DeepGate2
description: Improved with Functionality-aware
# img: assets/img/data_structure.jpg
importance: 1
category: Netlist
---

### About
- PDF Link:  <a href="https://arxiv.org/pdf/2305.16373.pdf">here</a>
- Authors: Zhengyuan Shi, Qiang Xu
- Lab: CURE Lab of CUHK

### Intriguing Arguments
- "For example, a NOT gate and its fan-in gate can both have a logic-1 probability of 0.5, but their truth tables are entirely opposite, thus highlighting the inadequacy of this supervision method."

- "The circuit representation learning model aims to map both circuit
structure and functionality into embedding space, where the structure represents the connecting relationship of logic gates and the functionality means the logic computational mapping from inputs to outputs."

### Innovative Designs
- Replace logic probability with **truth table** as the new supervision.
- Compose the vector embeddings of a PI of a **structural embedding** (orthogonal with each other) and a function embedding (the same as all PIs have the same logic probability).
- Divide the training stages into an easy one (logic probability prediction + reconvergence equivalence) and a hard one (+ functionality-aware learning aka distance of truth table).

### Diagram
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/literatures/deepgate2_training.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    DeepGate2 training process.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/literatures/deepgate2_propagation.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>

    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/literatures/deepgate2_loss.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: One-round propagation process; Right: Functionality-aware loss.
</div>

### Reference
```bib
@inproceedings{shi2023deepgate2,
  title={Deepgate2: Functionality-aware circuit representation learning},
  author={Shi, Zhengyuan and Pan, Hongyang and Khan, Sadaf and Li, Min and Liu, Yi and Huang, Junhua and Zhen, Hui-Ling and Yuan, Mingxuan and Chu, Zhufei and Xu, Qiang},
  booktitle={2023 IEEE/ACM International Conference on Computer Aided Design (ICCAD)},
  pages={1--9},
  year={2023},
  organization={IEEE}
}
```