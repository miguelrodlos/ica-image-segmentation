# Independent Component Analysis for Image Segmentation (R)

## Overview
This project implements an **Independent Component Analysis (ICA)–inspired approach** for image segmentation using **linear projections that maximize class separability**.  
The task is based on whitening, subspace projections, and Fisher’s discriminant index, applied to a real dermatological image.

The work was completed as part of an academic assignment focused on:
- Linear algebra and change of basis
- Optimization over projection spaces
- Unsupervised image segmentation

## Problem Description
Given a color image (RGB), the goal is to:
1. Transform pixel data into a whitened space
2. Search for linear projections that maximize **non-Gaussian structure**
3. Segment the projected image into two classes using **k-means**
4. Evaluate each projection using the **Fisher index**
5. Identify multiple **orthogonal projections** revealing internal image structure

## Methodology
The implemented workflow follows these steps:

1. **Image loading and visualization**
   - A dermatological image is selected and displayed.

2. **Data matrix construction**
   - Each pixel is represented as a 3-dimensional vector (R, G, B).
   - Pixels are arranged column-wise into a data matrix.

3. **Whitening**
   - The data matrix is centered and whitened using eigen-decomposition.
   - The covariance of the whitened data is verified to be (approximately) the identity matrix.

4. **Projection optimization**
   - Linear projections are explored in spherical coordinates.
   - For each projection:
     - Pixels are projected onto a 1D subspace
     - k-means clustering (k=2) is applied
     - The Fisher index is computed
   - The projection maximizing the Fisher index is selected.
   - The optimization surface is visualized using **Plotly**.

5. **Orthogonal projections**
   - A second projection orthogonal to the first is found by restricting the search space.
   - A third projection orthogonal to the first two is then computed.
   - Each projection reveals different internal structures of the image.

6. **Segmentation and analysis**
   - Projected images, histograms, and segmentations are visualized and discussed.

## Technologies Used
- **Language:** R
- **Key concepts:** ICA, whitening, Fisher discriminant, k-means clustering
- **Libraries:** base R, Plotly (for optimization surface visualization)
- **Visualization:** image plots, histograms, interactive 3D surfaces

## Repository Structure

```text
.
├── ICA.Rmd      Main R Markdown file containing the full analysis
├── ICA.html     Rendered HTML output of the analysis
├── README.md    Project documentation  
