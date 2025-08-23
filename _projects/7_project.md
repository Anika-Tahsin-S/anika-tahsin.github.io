---
layout: page
title: GeoSemantic Flux (GSF): Unsupervised Semantic Segmentation for Wetland Fluctuation Forecasting
description: Vision–language-assisted unsupervised segmentation and time-series forecasting from satellite imagery (1983–2024)
img: assets/img/projects/geoflux/cover.jpg
importance: 1
category: journal
related_publications: true
---

- **GeoSemantic Flux (GSF)** is a modular framework for **unsupervised semantic segmentation** and **forecasting** of wetland area fluctuations from long-range satellite imagery (1983–2024).
- Combines **vision–language** prompting (RAM / Grounding-DINO) with **masking & refinement** (e.g., SAM with TS-SAM enhancements) to delineate dynamic wetland boundaries.
- Produces **forecast-ready time series** (per-class pixel counts/areas) for downstream trend analysis, anomaly detection, and **short-term prediction** of wetland changes.
- Includes reproducible **preprocessing** (CLAHE + NDWI), EDA/visualization notebooks, and evaluation scripts (IoU/Dice vs. manual samples; MAPE for forecasts).

**Repo:** [GitHub](https://github.com/Anika-Tahsin-S/GeoFlux)

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/geoflux/1.png" title="Satellite slice (1983–2024)" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/projects/geoflux/2.png" title="Unsupervised segmentation mask" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">
  GSF unsupervised mask & refinement
</div>

**Highlights**
- **Data:** Google Earth Timelapse (1983–2024); CLAHE + NDWI preprocessing; area & boundary extraction
- **Segmentation:** Vision–language proposals (RAM/Grounding-DINO) → SAM/TS-SAM refinement → post-processing & topology cleanup
- **Forecasting:** Per-class area series; trend/seasonality modeling; anomaly flags; uncertainty bands
- **Outputs:** Masks, boundaries, per-class area CSV/JSON, forecast charts; evaluation (IoU/Dice, MAPE)

---

### Models & Checkpoints
> Pretrained and fine-tuned weights (RAM, Grounding-DINO, SAM with TS-SAM enhancements) will be released **after the paper is officially published**.

### Data Access
> Processed datasets (CLAHE+NDWI satellite frames, segmentation masks, and forecast-ready series) will be made **publicly available post-publication**.
- Download links for segmented imagery
- Forecast-ready CSV/JSON time series
- MLRSNet subset annotations (subject to license)