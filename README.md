# Green AI: Drone-Based Afforestation Monitoring

This repository provides a proof-of-concept (PoC) solution for monitoring afforestation patches using drone imagery and machine learning. The system detects sapling survival rates, identifies casualties, and generates reports for effective afforestation program evaluation.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Problem Statement](#problem-statement)
3. [Dataset and Ortho-Images](#dataset-and-ortho-images)
4. [Pipeline Overview](#pipeline-overview)
5. [Methodologies](#methodologies)
6. [Challenges and Limitations](#challenges-and-limitations)
7. [Final Outputs](#final-outputs)
8. [How to Run](#how-to-run)
9. [Contributing](#contributing)
10. [License](#license)

---

## Introduction

Green AI uses drone imagery and advanced ML/AI techniques to monitor afforestation patches. By analyzing high-resolution ortho-images, this system identifies sapling survival, evaluates patch health, and provides data-driven insights into the success of afforestation programs.

---

## Problem Statement

The Odisha Forest Department plants nearly 5 crore trees annually. Monitoring the survival of saplings across irregular patches poses significant challenges. This project focuses on:
- Using drone imagery to determine sapling survival percentages.
- Detecting locations where saplings have died.
- Automating the process for scalability.

---

## Dataset and Ortho-Images

Drone surveys were conducted during four key operational phases:
1. **Before OP1:** Initial state of the patch (no pits).
2. **After OP1:** Pits are visible.
3. **After OP2:** Saplings planted.
4. **After OP3:** Post-weeding phase.

Data includes:
- **Ortho-images** generated using Pix4D.
- Metadata with geo-coordinates of pixels (1m accuracy).
- Resolutions ranging from 2.46 cm to 2.81 cm per pixel.

---

## Pipeline Overview

1. **Stage 1: Data Preprocessing**
   - TIFF to PNG Conversion
   - Image Alignment & Denoising
   - Patch Extraction
   - Data Normalization

2. **Stage 2: Pit Detection**
   - Thresholding Analysis
   - Border Verification
   - Bounding Box Generation
   - Coordinate Extraction

3. **Stage 3: Deep Learning**
   - MobileVIT Model for Sapling Segmentation
   - Feature Extraction

4. **Stage 4: Coordinate Processing**
   - GPS Correction
   - KNN Analysis
   - Position Refinement

5. **Stage 5: Health Analysis**
   - Green Channel Analysis
   - NDVI Calculation
   - Vitality Classification

6. **Stage 6: GIS Integration**
   - GeoDataFrame Creation
   - Spatial Data Processing
   - Shapefile Generation

7. **Stage 7: Analytics**
   - Survival Metrics
   - Visual Reports
   - Performance Analysis

---

## Methodologies

1. **Image Processing:** 
   - Applied thresholding and denoising to extract key features like pits and saplings.
   - Used bounding boxes for spatial localization.

2. **Deep Learning:**
   - MobileVIT was fine-tuned for sapling segmentation tasks.
   - NDVI and green channel analysis were performed for vitality classification.

3. **Coordinate Processing:**
   - Coordinates from post-OP1 images were refined using KNN for accurate location matching.

4. **GIS Integration:**
   - Created shapefiles and spatial data for visualization and analysis.

---

## Challenges and Limitations

1. **Resolution Constraints:** 
   - Medium-resolution images limit the granularity of analysis.

2. **Greenery Overlap:**
   - Existing vegetation complicates sapling detection.

3. **Geospatial Accuracy:**
   - Limited GPS accuracy (1m) without RTK modules.

4. **Scalability:**
   - Optimizing for large-scale deployments is essential.

---

## Final Outputs

1. **Detection Results:** Identified locations of sapling casualties.
2. **Health Metrics:** NDVI-based health classifications.
3. **GIS Data:** Generated shapefiles for visualization.
4. **Visual Reports:** Survival metrics and performance analysis.

---
