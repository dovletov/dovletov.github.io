---
title: Radon-Transformation
layout: post
author: Ailurophile
date: '2018-10-07 13:07:46'
categories:
- CT
- MRI
comments: true
mathjax: true
---

This post is the mosts clear explanation of Radon-Transformations, which is used in computer tomography (CT) and magnetic resonance (MR) image generation and reconstruction.
<!--more-->

### Sinogram generation

The Radon transform data is often called a sinogram.

Example of sinogram generation.


### Reconstruction from sinogram

Homogeneous object, monochromatic radiation 

$$ I_d = I_0 \cdot \exp^{-\mu d} $$

$$ \ln{\frac{I_d}{I_0}} = -\mu d $$

$$ \ln{\frac{I_0}{I_d}} = \mu d $$

$$ \mu = \frac{1}{d}\ln{\frac{I_0}{I_d}} $$

Non-homogeneous object, mono-chromatic

$$ I_d = I_0 \cdot \exp^{-\mu_1 d_1-\mu_2 d_2-\mu_3 d_3 \dots} = I_0 \cdot \exp^{-\sum_i \mu_i d_i} = ( I_0 \cdot \int_0^d \mu ds ) $$

$$ \ln{\frac{I_0}{I_d}} = \sum_i \mu_i d_i $$

$$ \mu_i = ? $$

Inverse problem

Johann Radon (1887 – 1956): 2D signal can be determined from an infinite set of line integrals through this signal

Approximate signal by finite set of line integrals

03-Measurements.pdf
