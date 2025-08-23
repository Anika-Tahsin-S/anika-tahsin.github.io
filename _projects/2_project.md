---
layout: page
title: Ship Detection in Aerial Images Using YOLOv10
description: Real-time object detection pipeline for maritime monitoring
img: assets/img/projects/ships/cover.png
importance: 2
category: solo
related_publications: true
---

- Built a YOLOv10 pipeline to detect ships in aerial images under scale and background variability.
- Curated dataset, designed a custom DataLoader, and performed hyperparameter tuning for accuracy/latency trade-offs.
- Trained with standard augmentations and evaluated using mAP, precision–recall, and confusion analysis.
- Profiled inference for real-time feasibility with post-processing (NMS) configuration.

**Repo:** [GitHub](https://github.com/Anika-Tahsin-S/Ship-Object-Detection-YoloV10)
**Dataset:** [Kaggle](https://www.kaggle.com/datasets/siddharthkumarsah/ships-in-aerial-images)

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/ships/1.png" title="Aerial input" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/ships/2.png" title="YOLOv10 predictions" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/ships/3.png" title="Zoomed crops" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">
  Detected Ship Prediction Outputs
</div>

**Highlights**
- Frameworks: PyTorch, YOLOv10
- Data: Curated aerial imagery; augmentations; optional tiling for small objects
- Training: LR scheduling, mixed precision, validation hooks
- Metrics: mAP@0.5 / mAP@0.5:0.95, precision, recall; PR curves
