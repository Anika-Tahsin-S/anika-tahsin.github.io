---
layout: page
title: Brain MRI Segmentation with U-Net (MobileNetV2 Encoder)
description: Lightweight medical image segmentation pipeline (PyTorch + SMP)
img: assets/img/projects/mri/mri.jpg
importance: 1
category: work
related_publications: true
---

Developed a lightweight medical image segmentation pipeline on Kaggle’s MRI dataset.
Converted 3D NIfTI volumes to 2D slices, applied z-score normalization, and binarized masks (nearest-neighbor). 
Trained a U-Net with a MobileNetV2 encoder (PyTorch/SMP) using BCE+Dice, mixed precision (AMP), gradient clipping, cosine LR, and early stopping. 
Evaluated with Dice/IoU/Precision/Recall/F1 and performed a threshold sweep to optimize inference.

**Repo:** [GitHub](https://github.com/Anika-Tahsin-S/MRI_Segmentation_with_U-Net_MobileNetV2_encoder)

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/mri/1.png" title="Sample MRI slice" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/mri/2.png" title="Ground-truth mask" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/mri/3.png" title="Prediction overlay" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">
  Left: original slice. Middle: binary mask. Right: overlay with U-Net (MobileNetV2) prediction.
</div>

**Highlights**
- Frameworks: PyTorch, segmentation-models-pytorch (SMP)
- Losses: BCE + Dice
- Training: AMP, gradient clipping, cosine schedule, early stopping
- Metrics: Dice, IoU, Precision, Recall, F1

<!-- <div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/projects/mri/4.jpg" title="Training curves" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/projects/mri/5.jpg" title="Threshold sweep" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">
  Training dynamics (left) and threshold sweep for optimal Dice (right).
</div> -->
